## 聚合分账

接口说明：分账请求接口

应用场景：微信支付订单通过此接口分账给微信个人账号（目前只支持微信）

- 分账请求接口

> 请求URL:`https://pay.heemoney.com/v1/PShard`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pshard.one/heemoney.pshard.multi`

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
    <td>单次分账heemoney.pshard.one/多次分账heemoney.pshard.multi</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td>A2sdfjkl</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>22255522</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>12342342342</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>out_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户分账单号</td>
    <td>UTF-8,GBK,GB2312</td>
</tr>
<tr>
    <td>hy_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元分账单号</td>
    <td>UTF-8,GBK,GB2312</td>
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
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用</td>
    <td>当当图书</td>
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

hy_bill_no、out_trade_no 两者二选其一
（商户分账单号）

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
    <td>64</td>
    <td>商户系统内部订单号,要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元支付订单</td>
    <td>21235845103</td>
</tr>
<tr>
    <td>out_pshard_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户系统内部分账订单号，要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsj</td>
</tr>
<tr>
    <td>pshared_notify_url</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>分账异步通知的地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>pshard_desc</td>
    <td>String</td>
    <td>是</td>
    <td>125</td>
    <td>分账描述</td>
    <td></td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td></td>
</tr>
<tr>
    <td>pshard_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>分账参数信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td></td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td></td>
</tr>
<tr>
    <td>pshard_receivers</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>分账接收方</td>
    <td></td>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td>-</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>-</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>WX_NATIVE</td>
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
    <td>out_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>订单号 TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>hy_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元分账单号</td>
    <td>12313156</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用</td>
    <td>当当图书</td>
</tr>
</table>


## 分账异步通知API

接口说明：分账异步通知请求接口

应用场景：分账成功后汇收银主动发分账接口给商户

> 请求URL:`异步通知地址`

> 请求方式:`POST`   

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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号,默认1.0</td>
    <td></td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td></td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td></td>
</tr>
<tr>
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td></td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td></td>
</tr>
<tr>
    <td>out_trabe_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>商户订单号</td>
    <td>123456</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>支付订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>out_pshard_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>商户分账单号</td>
    <td>123456</td>
</tr>
<tr>
    <td>hy_pshard_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>汇元分账单号</td>
    <td>123456</td>
</tr>
<tr>
    <td>pshard_status</td>
    <td>String</td>
    <td>是</td>
    <td>-</td>
    <td>分账状态，-1=分账失败，0=未分账，1=分账申请中，2=分账处理中，3=分账成功，4=分账完成</td>
    <td>4</td>
</tr>
<tr>
    <td>pshard_fee</td>
    <td>String</td>
    <td>是</td>
    <td>-</td>
    <td>完结分账金额</td>
    <td></td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>商户附加信息</td>
    <td></td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>商户媒体扩展信息</td>
    <td></td>
</tr>
<tr>
    <td>pshard_option</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>商户支付扩展信息</td>
    <td></td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>数据签名</td>
    <td></td>
</tr>
</table>




## 分账查询接口

接口说明：分账查询请求接口

应用场景：通过调用该接口查询分账状态。分账会有一定的处理周期。

> 请求URL:`https://pay.heemoney.com/v1/PShard`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pshard.query`

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
    <td>32</td>
    <td>方法</td>
    <td>heemoney.pshard.query</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td>A2sdfjkl</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>22255522</td>
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


hy_bill_no、out_trade_no 两者二选其一
（商户分账单号）

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>out_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户分账单号</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>hy_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元分账单号</td>
    <td>21235845103</td>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td>-</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>-</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>WX_NATIVE</td>
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
    <td>out_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户分账单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>hy_pshared_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元分账单号</td>
    <td>12311231</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用</td>
    <td>当当图书</td>
</tr>
<tr>
    <td>pshared_status</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>分账状态</td>
    <td></td>
</tr>
<tr>
    <td>pshare_amt</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>完结分账金额,在查询完结分账的时候才有</td>
    <td></td>
</tr>
</table>
