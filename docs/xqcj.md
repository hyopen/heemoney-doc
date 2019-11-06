## 商户设备激活

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/MerchDevice`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.device`

- 公共参数

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
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.merch.device</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td>276952</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>编码格式默认为utf-8</td>
    <td>utf-8</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
    <td>是</td>
    <td>19</td>
    <td>发送请求的时间</td>
    <td>yyyyMMddHHmmss,20181030152539</td>
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
    <td>md5</td>
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

- 业务参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>device_code</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>设备编码</td>
    <td>90-2B-34-63-2C-46</td>
</tr>
</table>



 -公共响应参数：

return_code为FAIL时只返回return_code和return_msg

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
    <td>否</td>
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
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>1234567890</td>
</tr>
</table>

以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>错误码</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>错误信息</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>店铺ID</td>
    <td>1222232323</td>
</tr>
<tr>
    <td>device_uid</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>设备id</td>
    <td>22512545</td>
</tr>
<tr>
    <td>company</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>公司名称</td>
    <td>测试超市</td>
</tr>
<tr>
    <td>store_name</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>店铺名称</td>
    <td>测试小点</td>
</tr>
<tr>
    <td>device_name</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>设备名称</td>
    <td>收银台1号</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>1234567890</td>
</tr>
</table>	



## 商户登录

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/MerchLogin`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.account.login`

- 公共参数

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
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
    <td>heemoney.merch.account.login</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>服务商的应用id</td>
    <td>hy1213131511</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>276952</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>编码格式默认为utf-8</td>
    <td>utf-8</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
    <td>是</td>
    <td>19</td>
    <td>发送请求的时间</td>
    <td>yyyyMMddHHmmss,20181030152539</td>
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
    <td>否</td>
    <td>10</td>
    <td>商户生成签名字符串所使用的签名算法类型</td>
    <td>md5</td>
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

- 业务参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>mch_account</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户账号(只能有数字，字母及下划线组成，6 - 30位)</td>
    <td>zhifubaoceshi</td>
</tr>
<tr>
    <td>mch_emp_account</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>员工账号</td>
    <td>15110186488</td>
</tr>
<tr>
    <td>login_pwd</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>密码</td>
    <td>123456</td>
</tr>
<tr>
    <td>device_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>设备UID</td>
    <td>100250000000938</td>
</tr>
<tr>
    <td>dpass_pwd</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>动态口令</td>
    <td>15113211350</td>
</tr>
<tr>
    <td>login_info</td>
    <td>json</td>
    <td>是</td>
    <td>255</td>
    <td>业务参数组织成json格式，再使用服务商3eds加密后放到login_info参数里面传递</td>
    <td>{" login_info ":"ABCDEFGHIJKLMN"}</td>
</tr>
</table>

login_info字段解密值说明

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>device_uid</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>设备唯一标识id</td>
    <td>100250000000938</td>
</tr>
<tr>
    <td>mch_account</td>
    <td>String</td>
    <td>是</td>
    <td>-</td>
    <td>商户账号(只能有数字，字母及下划线组成，6 - 30位)</td>
    <td>zhifubaoceshi</td>
</tr>
<tr>
    <td>mch_emp_account</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>员工账号</td>
    <td>15110186488</td>
</tr>
<tr>
    <td>login_pwd</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>密码</td>
    <td>123456</td>
</tr>
<tr>
    <td>dpass_pwd</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>动态口令</td>
    <td>123456</td>
</tr>
</table>


返回响应：


- 公共响应参数

return_code为FAIL时只返回return_code和return_msg

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>3213</td>
</tr>
</table>


*以下字段在return_code=SUCCESS&result_code=FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>Int</td>
    <td>是</td>
    <td>16</td>
    <td>错误码</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>错误信息</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
</tr>
</table>


- 响应参数

*以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID,商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td>276952</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>店铺id</td>
    <td>213213211</td>
</tr>
<tr>
    <td>clerk_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>职员id</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>1234567890</td>
</tr>
</table>




## 商户转账

- 转账请求接口

> 请求URL:`https://api.heemoney.com/v1/MerchTransitSubmit`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.transit.submit`

- 公共参数

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
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.transit.submit</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>代理号</td>
    <td>100250</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
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

- 业务参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>单号</td>
    <td>6EFE9B94</td>
</tr>
<tr>
    <td>from_accout</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>转出账号</td>
    <td>zhifubaoCeshi</td>
</tr>
<tr>
    <td>to_accout</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>转入账号</td>
    <td>ceshi123</td>
</tr>
<tr>
    <td>bill_fee</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>金额(单位分)</td>
    <td>2</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
</tr>
<tr>
    <td>note</td>
    <td>String</td>
    <td>是</td>
    <td>19</td>
    <td>转账说明</td>
    <td>测试</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>异步通知</td>
    <td>http://...</td>
</tr>
</table>


- 公共响应参数

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



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>签名结果</td>
    <td>565656565</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
    <td>ok</td>
</tr>
</table>

转账过程中报错说明：

```javascript
Ø	账号错误
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"转出账号不存在或不可用","sign":"E738ACD548C71C47428652A452C5B9C8"}

Ø	提交信息正确
{"return_code":"SUCCESS","hy_bill_no":"T190708101400013141002500064","return_msg":"转账信息提交成功","sign":"715E17FE5844755E11E828E89F372D6A"}

Ø	资金不足
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"账户可用资金不足","sign":"0A4574FC491B6E79075ACBDB32AA9582"}

Ø	金额有误：这里的金额单位为分
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"bill_fee有误
","sign":"BD07DA5FF5192C76919A427BB9E87A2C"}

Ø	跨系统测试报错
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"转出账号不在此机构体系,不能转账","sign":"249749C4ADD52FCC58F82472826AC8A5"}

Ø	其他字段异常校验
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"转出账号不存在或不可用","sign":"E738ACD548C71C47428652A452C5B9C8"}

{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"from_accout不能为空","sign":"D35666CD25136F157C0A564F0BAFEC33"}

Ø	应用id不匹配
应用缓存获取为空,OrgUID=100250,AppID=hyp1907021002500000053484D819E01


Ø	操作频率是1分钟内提交一次
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"转账操作太快","sign":"BC659338B068BF5383994EB3917D12ED"}

Ø	单笔限额100w
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"bill_fee不能超过100000000","sign":"88F2416F2D242230C7623F3A28563E9A"}

```

## 转账查询接口

> 请求URL:`https://api.heemoney.com/v1/MerchTransitQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.transit.query`

- 公共参数

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
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.transit.query</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>代理号</td>
    <td>100250</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
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

- 业务参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>单号</td>
    <td>6EFE9B94</td>
</tr>
</table>


- 公共响应参数

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


以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>签名结果</td>
    <td>565656565</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户订单号</td>
    <td>hlsjdklj2453</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>bill_fee</td>
    <td>int</td>
    <td>是</td>
    <td>16</td>
    <td>转账总金额单位分</td>
    <td>2</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>状态：Undeal=处理中，SUCCESS=成功，Failure=失败</td>
    <td>SUCCESS</td>
</tr>
</table>



## 商户上下班签退

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/MerchOnOffLine`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.onoffline`

- 公共参数

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
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.merch.onoffline</td>
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
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td>276952</td>
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
    <td>md5</td>
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

- 业务参数


<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>clerk_uid</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>职员UID</td>
    <td>100250000004951</td>
</tr>
<tr>
    <td>clerk_on_off_line</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>操作标识</td>
    <td>signout签退，on上班，off下班</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>店铺UID</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>url_uids</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>收款码UIDs(多个英文逗号分隔)，当clerk_on_off_line=on，不可与device_uids同时为空</td>
    <td></td>
</tr>
<tr>
    <td>device_uids</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>设备UIDs(多个英文逗号分隔)，当clerk_on_off_line=on，不可与url_uids同时为空</td>
    <td></td>
</tr>
</table>


-公共响应参数：

return_code为FAIL时只返回return_code和return_msg

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>return_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>业务状态码</td>
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
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>1234567890</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>错误返回的信息描述</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>sign_out_last_time</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>上次签退时间</td>
    <td>2019/7/10 16:44:10</td>
</tr>
<tr>
    <td>sign_out_time</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>本次签退时间</td>
    <td>2019/7/11 10:24:20</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>1234567890</td>
</tr>
</table>



