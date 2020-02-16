## 接口规则

<table data-hy-role="doctbl">
    <tr>
        <th>规则</th>
        <th>描述</th>   
    </tr>
    <tr>
        <td>传输方式</td>
        <td>为保证交易安全性，采用HTTPS传输</td>
    </tr>
    <tr>
        <td>提交方式</td>
        <td>采用POST方法提交</td>
    </tr>
    <tr>
        <td>字符编码</td>
        <td>统一采用UTF-8字符编码</td>
    </tr>
    <tr>
        <td>签名算法</td>
        <td>MD5，后续会兼容SHA1、SHA256、HMAC等。</td>
    </tr>
    <tr>
        <td>签名要求</td>
        <td>请求和接收数据均需要校验签名，详细方法请参考：MD5签名规则。</td>
    </tr>
    <tr>
        <td>证书要求</td>
        <td>调用申请退款、撤销订单接口需要商户证书</td>
    </tr>
    <tr>
        <td>判断逻辑</td>
        <td>先判断协议字段返回，再判断业务返回，最后判断交易状态</td>
    </tr>
</table>

## 签名规则

1. 把字典按Key的字母顺序排序；
- 把所有参数名和参数值串在一起；
- 在第二步生成的参数串后加入KEY;
- 讲第三步得到的参数串进行MD5加密；
- 将MD5串转大写。


例如：
```
APP_KEY：EA9DA4530C454D009D0E1291
```

请求参数（除sign外）：
```javascript
{
    "api_from_type": "Out_Api",
    "method": "heemoney.pay.applypay",
    "version": "1.0",
    "app_id": "hyp170420470720000001025BCB0C31E",
    "mch_uid": "4707201974600",
    "charset": "utf-8",
    "sign_type": "MD5",
    "timestamp": "20170511000017",
    "biz_content": "{\"out_trade_no\":\"20170511000017\",\"subject\":\"测试1分\",\"total_fee\":\"1\",\"client_ip\":\"127.0.0.1\",\"notify_url\":\"http://localhost/TestMergepay/Api/RecNotifyUrl.aspx\",\"return_url\":\"http://localhost/TestMergepay/Api/RecReturnUrl.aspx\",\"channel_type\":\"100\"}"
}
```

根据规则应生成MD5签名串：
```text
api_from_type=Out_Api&app_id=hyp170420470720000001025BCB0C31E&biz_content={"out_trade_no":"20170511000017","subject":"测试1分","total_fee":"1","client_ip":"127.0.0.1","notify_url":"http://localhost/TestMergepay/Api/RecNotifyUrl.aspx","return_url":"http://localhost/TestMergepay/Api/RecReturnUrl.aspx","channel_type":"100"}&charset=utf-8&mch_uid=4707201974600&method=heemoney.pay.applypay&sign_type=MD5&timestamp=20170511000017&version=1.0&key=EA9DA4530C454D009D0E1291
```

MD5签名转大写后：

```javascript
{
    "sign":"5799E16B62E6607704345E02C80D5ACF"
}
```



## 参数规定

- 交易金额
```text
交易金额默认为人民币交易，API中参数支付金额单位为【分】，参数值不能带小数。对账单中的交易金额单位为【元】。暂不支持外币。
```

- 货币类型
```text
货币类型的取值列表：
CNY：人民币
```

- 通道类型

<table data-hy-role="doctbl">
    <tr>
        <th>通道类别</th>
        <th>通道类型</th>
        <th>含义</th>
    </tr>
    <tr>
        <td rowspan="5">微信</td>
        <td>WX_NATIVE</td>
        <td>微信扫码</td>
    </tr>
    <tr>
        <td>WX_JSAPI</td>
        <td>微信公众号</td>
    </tr>
    <tr>
        <td>WX_H5</td>
        <td>微信H5</td>
    </tr>
    <tr>
        <td>WX_MICROPAY</td>
        <td>微信刷卡</td>
    </tr>
    <tr>
        <td>WX_APPLET</td>
        <td>微信小程序</td>
    </tr>
    <tr>
        <td rowspan="4">支付宝</td>
        <td>ALI_QRCODE</td>
        <td>支付宝扫码</td>
    </tr>
    <tr>
        <td>ALI_WAP</td>
        <td>支付宝WAP</td>
    </tr>
    <tr>
        <td>ALI_SWIPE</td>
        <td>支付宝刷卡</td>
    </tr>
    <tr>
        <td>ALi_JSAPI</td>
        <td>支付宝服务窗/生活号</td>
    </tr>
    <tr>
        <td>QQ钱包</td>
        <td>QQ_QRCODE</td>
        <td>QQ扫码</td>
    </tr>
    <tr>
        <td rowspan="2">快捷支付</td>
        <td>BANK_QUICK_PAY_FD</td>
        <td>快捷支付封顶</td>
    </tr>
    <tr>
        <td>BANK_QUICK_PAY_BFD</td>
        <td>快捷支付不封顶</td>
    </tr>
    <tr>
        <td>网银支付</td>
        <td>BANK_CYBER</td>
        <td>网银支付</td>
    </tr>
    <tr>
        <td rowspan="3">银联</td>
        <td>BANK_QRCODE</td>
        <td>银联扫码</td>
    </tr>
    <tr>
        <td>BANK_SWIPE</td>
        <td>银联刷卡</td>
    </tr>
    <tr>
        <td>BANK_WAP</td>
        <td>银联WAP</td>
    </tr>
    <tr>
        <td>京东H5</td>
        <td>JD_WAP</td>
        <td>京东H5</td>
    </tr>
</table>


```javascript
注： 快捷支付不封顶接口 pay_option 格式为{“Bank_Info”:”value”}，
该value值由（付款银行卡号|收款银行名称|收款银行卡号|身份证号|姓名）3DES(ECB)加密组成。
示例：
”pay_option”:{“Bank_Info”:”0w/7dSjd9DHk7qJssYNeN2dqTuIZCEtskBZ3ioRLKLzcKLQfYyTYwnshoEXqKaLsDhkOyFjD9/zdb3wbffxDybUEM5DgR7zxRSKT0+Utiqc=”}
```


- 签名算法
 ```text
技术同学把1.APPID，2.KEY 配置在代码中，对请求内容进行签名，并对汇收银返回的内容进行验签。
 ```

## 开发步骤

1. 申请注册汇收银商户账号
- 开通所需要的支付通道
- 查询商户UID、APPID、KEY,如果您是服务商模式，另外，如果您服务商模式的对接，需要查找服务商的商户UID、APPID、KEY,
- 根据API规范，开始程序对接
