## 接口调用说明

- 请求地址：`https://demo.heemoney.com/YunBiz/Wallet/V1` 
- 请求方式：`Post` 

## 公共请求参数
<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>否</td>
    <td>100</td>
    <td>公共类接口必传</td>
    <td>heemoney.pay.applypay</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号,默认1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>owner_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>所有者uid(对接商户唯一标识)</td>
    <td>1002502217680</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
    <td>是</td>
    <td>19</td>
    <td>发送请求的时间</td>
    <td>yyyyMMddHHmmss</td>
</tr>
<tr>
    <td>biz_content</td>
    <td>String</td>
    <td>是</td>
    <td>不限</td>
    <td>请求参数集合,Json格式,长度不限,具体参数见如下业务参数</td>
    <td>Json格式</td>
</tr>
<tr>
    <td>sign_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>商户生成签名字符串所使用的签名算法类型</td>
    <td>MD5</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>商户请求参数的签名串</td>
    <td>详见示例</td>
</tr>
</table>

## 公共响应参数
<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>return_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>返回状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>return_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>返回状态码描述</td>
    <td>ok</td>
</tr>
</table>

## 错误码
<table data-hy-role="doctbl">
    <th>错误码</th>
    <th>错误码描述</th>    
</tr>
<tr>
    <td>E0000</td>
    <td>业务处理成功</td>
</tr>
<tr>
    <td>E0001</td>
    <td>缺少必要参数</td>
</tr>
<tr>
    <td>E0002</td>
    <td>无效的参数</td>
</tr>
<tr>
    <td>E0003</td>
    <td>应用ID不存在</td>
</tr>
<tr>
    <td>E0004</td>
    <td>应用审核未成功</td>
</tr>
<tr>
    <td>E0005</td>
    <td>应用未开启</td>
</tr>
<tr>
    <td>E0006</td>
    <td>签名错误</td>
</tr>
<tr>
    <td>E0007</td>
    <td>系统错误</td>
</tr>
<tr>
    <td>E0008</td>
    <td>数据处理错误</td>
</tr>
</table>

返回代码及说明：
trade_status
-4=关闭
-3=支付方单不存在
-2=验证失败
-1=失败
0=未知
1=支付成功
2=支付中

接口字段中的三个url区分：
notify_url:系统处理业务后通知商户的URL
return_url:系统处理业务后返回到商户的URL
redirect_url:钱包业务返回的URL，需要商户跳转到此URL进行后续操作

