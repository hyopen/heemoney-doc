## 统一下单

- 支付请求接口

> 请求URL:`https://pay.heemoney.com/v1/ApplyPay`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.applypay`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
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
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单标题</td>
    <td>购买礼品</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>Int</td>
    <td>是</td>
    <td></td>
    <td>订单总金额,单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>currency_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道类型，扫码支付，WX_NATIVE、ALI_QRCODE、微信小程序：WX_APPLET，微信代扣：WX_WITHHOLD，等具体见附录通道类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>APP和网页支付提交用户端ip，Native支付填调用微信支付API的机器IP。</td>
    <td>127.0.0.1</td>
</tr>
<tr>
    <td>device_code</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户机具终端编号，或盒子编号</td>
    <td>0001</td>
</tr>
<tr>
    <td>desk_no</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>桌号&餐饮等桌号</td>
    <td>01</td>
</tr>
<tr>
    <td>clerk_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户操作员或收银员编号</td>
    <td>1001</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户门店</td>
    <td>1号店</td>
</tr>
<tr>
    <td>terminal_info</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>终端信息</td>
    <td>-</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>pay_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>支付参数信息，如果支付类型为微信代扣（WX_WITHHOLD）需要填入： hy_contract_no（汇元签约编号）格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>异步通知的地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>return_url</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>同步通知地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>open_id</td>
    <td>String</td>
    <td>否</td>
    <td>50</td>
    <td>用户唯一标识（例如微信小程序openid）微信小程序支付必传</td>
    <td>ofOjKwQhQDI7pQU1DoQ2lU4ycPd0</td>
</tr>
</table>

- 公共响应参数

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
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
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
    <td>hy_pay_id</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单号 TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>标题</td>
    <td>购买</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>company</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>商户公司</td>
    <td></td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用 url</td>
    <td>当当图书</td>
</tr>
<tr>
    <td>code_url</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>二维码链接地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>hy_pay_url</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>支付链接地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>hy_js_auth_pay_url</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>公众号支付链接地址</td>
    <td>http://…</td>
</tr>
<tr>
    <td>hy_mini_pay_params</td>
    <td>String</td>
    <td>否</td>
    <td>512</td>
    <td>小程序支付串</td>
    <td></td>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>否</td>
    <td>28</td>
    <td>汇元签约编号，只有通道类型是微信代扣（WX_WITHHOLD）时才会返回改参数</td>
    <td></td>
</tr>
</table>

## 订单查询

- 订单查询接口

> 请求URL:`https://pay.heemoney.com/v1/payquery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.query`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>否</td>
    <td>28</td>
    <td>汇元单号 (汇元单号和商户订单号不可同时为空，同时都有以此参数为准)</td>
    <td>Hy2017022812</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>商户系统内部单号,要求同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
</table>

- 公共响应参数

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
</table>


以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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

以下字段在return_code=SUCCESS&result_code=FAIL时返回

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
    <td>int</td>
    <td>是</td>
    <td></td>
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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号，默认1.0</td>
    <td>1.0</td>
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
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>标题</td>
    <td>购买</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>商户订单号</td>
    <td>5456144</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>channel_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>通道交易单号</td>
    <td>123456</td>
</tr>
<tr>
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>channel_return_msg</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>通道返回信息</td>
    <td></td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>单据状态：Undeal=未支付，SUCCESS=支付成功，Failure=支付失败</td>
    <td>Undeal</td>
</tr>
<tr>
    <td>bank_type</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>支付银行</td>
    <td></td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>real_fee</td>
    <td>int</td>
    <td>是</td>
    <td>32</td>
    <td>实际支付金额</td>
    <td>100</td>
</tr>
<tr>
    <td>coupon_amt</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>通道优惠金额</td>
    <td>100</td>
</tr>
<tr>
    <td>time_end</td>
    <td>String</td>
    <td>是</td>
    <td>14</td>
    <td>订单支付时间，格式为yyyyMMddHHmmss</td>
    <td>20170101220011</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>是</td>
    <td>否</td>
    <td>附加数据</td>
    <td>100</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>Int</td>
    <td>否</td>
    <td>32</td>
    <td>商户定制信息</td>
    <td>Undeal</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>Int</td>
    <td>否</td>
    <td>32</td>
    <td>支付参数信息</td>
    <td>Undeal</td>
</tr>
</table>

商户处理业务用real_fee，为实际支付金额,我方会按照此金额结算给商户。
total_fee=real_fee
用户支付金额=real_fee-coupon_amt


## 申请退款

- 退款请求接口

> 请求URL:`https://pay.heemoney.com/v1/refund`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.refund`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户系统内部订单号，要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>out_refund_no</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>商户退款单号</td>
    <td>Shlsjdklj2453</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>总金额 正整数，单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>refund_fee</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>退款总金额，单位为分</td>
    <td>100</td>
</tr>
</table>

- 公共响应参数

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
</table>

以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号，默认1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
    <td>1222232323</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
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
    <td>汇元订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>out_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户退款单号</td>
    <td>Shlsjdklj2453</td>
</tr>
<tr>
    <td>hy_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>汇元退款单号</td>
    <td>TuiKuanlsjd2453</td>
</tr>
<tr>
    <td>channel_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>通道退款单号</td>
    <td>TuiKuanlsjd2453</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>订单总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>real_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际支付金额</td>
    <td>100</td>
</tr>
<tr>
    <td>refund_fee</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>退款总金额,单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>real_refund_fee</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>实际退款金额</td>
    <td>20170101220011</td>
</tr>
<tr>
    <td>channel_return_msg</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>通道返回信息</td>
    <td></td>
</tr>
</table>


## 查询退款

- 退款查询接口

> 请求URL:`https://pay.heemoney.com/v1/refundquery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.refund.query`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>out_refund_no</td>
    <td>String</td>
    <td>与hy_refund_no其中一个必填</td>
    <td>32</td>
    <td>商户退款单号</td>
    <td>Sklsjdklj245</td>
</tr>
<tr>
    <td>hy_refund_no</td>
    <td>String</td>
    <td>与out_refund_no其中一个必填</td>
    <td>32</td>
    <td>通道退款单号</td>
    <td>汇元退款单号</td>
</tr>
</table>

- 公共响应参数

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
</table>

以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>错误码</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>错误信息</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号，默认1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
    <td>1222232323</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
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
    <td>out_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户退款单号</td>
    <td>Shlsjdklj2453</td>
</tr>
<tr>
    <td>hy_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>汇元退款单号</td>
    <td>TuiKuanlsjd2453</td>
</tr>
<tr>
    <td>channel_refund_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>通道退款单号</td>
    <td>TuiKuanlsjd2453</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>订单总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>real_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际支付金额</td>
    <td>100</td>
</tr>
<tr>
    <td>refund_fee</td>
    <td>int</td>
    <td>否</td>
    <td></td>
    <td>退款总金额,单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>real_refund_fee</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>实际退款金额</td>
    <td>20170101220011</td>
</tr>
<tr>
    <td>channel_return_msg</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>通道返回信息</td>
    <td></td>
</tr>
<tr>
    <td>refund_status</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>退款状态：Undeal=退款处理中，SUCCESS=退款成功，Failure=退款失败</td>
    <td>100</td>
</tr>
</table>	


## 支付结果通知

- 支付状态异步通知API（汇收银主动发请求给商户）

> 请求URL:`https://***.***.com/recive/pay/***`

> 请求方式:`POST/GET`   


- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>应用ID</td>
    <td></td>
</tr>
<tr>
    <td>mch_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
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
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商应用ID</td>
    <td></td>
</tr>
<tr>
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>标题</td>
    <td>购买</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>123456</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>real_vol</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际支付金额</td>
    <td>100</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>单据状态：Undeal=未支付，Success=支付成功，Failure=支付失败</td>
    <td>Undeal</td>
</tr>
<tr>
    <td>time_end</td>
    <td>String</td>
    <td>是</td>
    <td>14</td>
    <td>订单支付时间，格式为yyyyMMddHHmmss</td>
    <td>20170101220011</td>
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
    <td>商户附加信息</td>
    <td></td>
</tr>
<tr>
    <td>pay_option</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>支付参数信息</td>
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

```
验签成功商户响应参数：ok 或者 success

```

## 直接下单

- 直接下单请求接口

> 请求URL:`https://pay.heemoney.com/v1/DirectPay`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.dirctpay`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
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
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单标题</td>
    <td>购买礼品</td>
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
    <td>total_fee</td>
    <td>Int</td>
    <td>是</td>
    <td></td>
    <td>订单总金额,单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>clerk_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>通道类型，扫码支付，WX_NATIVE、ALI_QRCODE、微信小程序：WX_APPLET，微信代扣：WX_WITHHOLD，等具体见附录通道类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户操作员或收银员编号</td>
    <td>1001</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户门店</td>
    <td>1号店</td>
</tr>
<tr>
    <td>device_code</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户机具终端编号，或盒子编号</td>
    <td>0001</td>
</tr>
<tr>
    <td>desk_no</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>桌号&餐饮等桌号</td>
    <td>01</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>APP和网页支付提交用户端ip，Native支付填调用微信支付API的机器IP</td>
    <td>127.0.0.1</td>
</tr>
<tr>
    <td>terminal_info</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>终端信息</td>
    <td></td>
</tr>
<tr>
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道类型，详情见通道类型刷卡类型：WX_MICROPAY、ALI_SWIPE、BANK_SWIPE</td>
    <td>BANK_SWIPE</td>
</tr>
<tr>
    <td>auth_bar_code</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>刷卡预授权条码</td>
    <td>56565656565656</td>
</tr>
<tr>
    <td>pay_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>支付参数信息，如果支付类型为微信代扣（WX_WITHHOLD）需要填入： hy_contract_no（汇元签约编号）格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
</table>

被扫不需要同步和异步地址，按照下方响应参数处理。


- 公共响应参数

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
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>hy123456</td>
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
    <td>channel_trade_no</td>
    <td>String</td>
    <td>否</td>
    <td>256</td>
    <td>渠道订单号 TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>channel_return_msg</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>渠道返回信息</td>
    <td>ok</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>单据状态：Undeal=未支付，SUCCESS=支付成功，Failure=支付失败</td>
    <td>Undeal</td>
</tr>
<tr>
    <td>bank_type</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>付款银行</td>
    <td>CCB_CREDIT</td>
</tr>
<tr>
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>标题</td>
    <td>购买</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>总金额</td>
    <td>100</td>
</tr>
<tr>
    <td>real_fee</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际支付金额</td>
    <td>100</td>
</tr>
<tr>
    <td>time_end</td>
    <td>String</td>
    <td>是</td>
    <td>14</td>
    <td>订单支付时间，格式为yyyyMMddHHmmss</td>
    <td>20170101220011</td>
</tr>
<tr>
    <td>company</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>公司名称</td>
    <td></td>
</tr>
</table>



## 申请签约

- 签约请求接口

> 请求URL:`https://pay.heemoney.com/v1/ApplyContract`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pay.applycontract`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>100	</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>商户签约编号</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>contract_display_account</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>用户账户名称</td>
    <td></td>
</tr>
<tr>
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>签约类型，WX_JSAPI_CONTRACT公众号签约</td>
    <td>WX_JSAPI_CONTRACT</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>APP和网页支付提交用户端ip，Native支付填调用微信支付API的机器IP</td>
    <td>127.0.0.1</td>
</tr>
<tr>
    <td>device_code</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户机具终端编号，或盒子编号</td>
    <td>0001</td>
</tr>
<tr>
    <td>desk_no</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>桌号&餐饮等桌号</td>
    <td>01</td>
</tr>
<tr>
    <td>clerk_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户操作员或收银员编号</td>
    <td>1001</td>
</tr>
<tr>
    <td>device_code</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户机具终端编号，或盒子编号</td>
    <td>0001</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户门店</td>
    <td>1号店</td>
</tr>
<tr>
    <td>terminal_info</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>终端信息</td>
    <td></td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>127</td>
    <td>附加数据，在查询API和支付通知中原样返回，可作为自定义参数使用格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>contract_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>签约扩展信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>异步通知的地址</td>
    <td>http://…</td>
</tr>
</table>


- 公共响应参数

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
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>签约类型</td>
    <td>WX_JSAPI_CONTRACT</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户签约编号</td>
    <td></td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>订单号</td>
    <td>汇元签约编号</td>
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
    <td>contract_url</td>
    <td>iStringnt</td>
    <td>是</td>
    <td>128</td>
    <td>签约url</td>
    <td>http://…</td>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>汇元签约编号</td>
    <td></td>
</tr>
</table>


## 查询签约

- 签约查询请求接口

> 请求URL:`https://pay.heemoney.com/v1/contractquery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.contract.query`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <td>否</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>否</td>
    <td>28	</td>
    <td>汇元签约编号</td>
    <td></td>
</tr>
<tr>
    <td>out_contract_no</td>
    <td>String</td>
    <td>否</td>
    <td>28</td>
    <td>商户签约编号</td>
    <td></td>
</tr>
</table>

```
hy_contract_no和out_contract_no二选其一，不能同时为空，优先hy_contract_no

```
- 公共响应参数

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
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本号，默认1.0</td>
    <td>1.0</td>
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
    <td>out_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>商户签约编号</td>
    <td></td>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>汇元签约编号</td>
    <td></td>
</tr>
<tr>
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>签约类型</td>
    <td>WX_JAPI_CONTRACT</td>
</tr>
<tr>
    <td>contract_status</td>
    <td>int</td>
    <td>是</td>
    <td>32</td>
    <td>签约状态:Unknown=未知，Success=签约成功，DeleteSuccess=解约成功，Failure=签约失败</td>
    <td></td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>附加数据</td>
    <td>100</td>
</tr>
<tr>
    <td>contract_option</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>签约扩展信息,格式：{“key1”：“value1”}</td>
    <td></td>
</tr>
<tr>
    <td>contract_signed_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议签署时间</td>
    <td></td>
</tr>
<tr>
    <td>contract_expired_time</td>
    <td>string</td>
    <td>否</td>
    <td></td>
    <td>协议解约时间 商户解除过签约后 该字段有值</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_mode</td>
    <td>string</td>
    <td>否</td>
    <td></td>
    <td>解约模式:Unknown=未签约，OverExpired=过有效期，SelfDelete=自主解约，ApiDelete=商户API解约，MchPlatform=商户平台解约</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_remark</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>解约备注</td>
    <td></td>
</tr>
</table>


## 解除签约

- 解约查询请求接口

> 请求URL:`https://pay.heemoney.com/v1/cancelcontract`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.contract.cancel`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>具体业务接口名称</td>
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
    <td>mch_id</td>
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
    <td>否</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>否</td>
    <td>28</td>
    <td>汇元签约编号</td>
    <td></td>
</tr>
<tr>
    <td>out_contract_no</td>
    <td>String</td>
    <td>否</td>
    <td>28</td>
    <td>商户签约编号</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_remark</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>解约备注</td>
    <td></td>
</tr>
</table>

```
hy_contract_no和out_contract_no二选其一，不能同时为空，优先hy_contract_no

```

- 公共响应参数

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
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>565656565</td>
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
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
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
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>version	</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>版本编号1.0</td>
    <td>1.0</td>
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
    <td>out_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>商户签约编号</td>
    <td></td>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>汇元签约编号</td>
    <td>hy123456</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>签约类型</td>
    <td>WX_JAPI_CONTRACT</td>
</tr>
<tr>
    <td>attach</td>
    <td>string</td>
    <td>否</td>
    <td></td>
    <td>附加数据</td>
    <td>100</td>
</tr>
<tr>
    <td>contract_signed_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议签署时间</td>
    <td></td>
</tr>
<tr>
    <td>contract_expired_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议到期时间</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议解约时间 商户解除过签约后 该字段有值</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_mode</td>
    <td>string</td>
    <td>否</td>
    <td></td>
    <td>签约状态:Unknown=未签约，OverExpired=过有效期，SelfDelete=自主解约，ApiDelete=商户API解约，MchPlatform=商户平台解约</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_remark</td>
    <td>string</td>
    <td>否</td>
    <td></td>
    <td>解约备注</td>
    <td></td>
</tr>
</table>

## 签/解约结果通知

- 签/解约异步通知API（汇收银主动发请求给商户）

> 请求URL:`异步通知地址`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.contract.cancel`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
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
    <td>mch_id</td>
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
    <td>change_type</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>商户签约编号</td>
    <td>123456</td>
</tr>
<tr>
    <td>hy_contract_no</td>
    <td>String</td>
    <td>是</td>
    <td>28</td>
    <td>汇元签约编号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>签约类型，WX_JSAPI_CONTRACT</td>
    <td>WX_JSAPI_CONTRACT</td>
</tr>
<tr>
    <td>contract_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签约状态:Unknown=未知，Success=签约成功，DeleteSuccess=解约成功，Failure=签约失败</td>
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
    <td>商户定制信息</td>
    <td></td>
</tr>
<tr>
    <td>contract_option</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>签约扩展信息</td>
    <td></td>
</tr>
<tr>
    <td>contract_signed_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议签署时间</td>
    <td></td>
</tr>
<tr>
    <td>contract_expired_time</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>协议到期时间，当change_type为ADD时有返回</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_time</td>
    <td>String</td>
    <td>否</td>
    <td></td>
    <td>协议解约时间 ， 商户解除过签约后 该字段有值</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_mode</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>解约模式，当change_type为DELETE时有返回， 0-未解约 ，1-有效期过自动解约，2-用户主动解约，3-商户API解约</td>
    <td></td>
</tr>
<tr>
    <td>contract_cancel_remark</td>
    <td>String</td>
    <td>否</td>
    <td>100</td>
    <td>解约备注</td>
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




## 鉴权

- 鉴权请求接口

> 请求URL:`http://api.heemoney.com/v1/UserAuthSubmit`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.user.auth.submit`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.user.auth.submit</td>
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
    <td>mch_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td></td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
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
    <td>鉴权参数集合,Json格式,长度不限,具体参数见如下业务参数</td>
    <td>Json格式</td>
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
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>单号,要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>auth_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>鉴权类型,0=未知,1=身份证鉴权,2=银行卡鉴权</td>
    <td>2</td>
</tr>
<tr>
    <td>auth_detail_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>鉴权详细类型,0=未知,1=二要素,2=三要素,3=四要素</td>
    <td>2</td>
</tr>
<tr>
    <td>auth_data_info</td>
    <td>String</td>
    <td>是</td>
    <td>-</td>
    <td>鉴权数据详细集合,Json格式,长度不限</td>
    <td>[{"bank_card_type":"","auth_bank_card":"","auth_name":""}]</td>
</tr>
</table>

```text
	auth_data_info	鉴权数据详细json格式
     示例
银行卡二要素 
储蓄卡： [{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_name":"张三"}] 
信用卡： [{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_name":"张三","cvv2":"233","expire_date":"1225"}]
银行卡三要素 
储蓄卡：[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三"}] 
信用卡： [{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","cvv2":"233","expire_date":"1225"}]
银行卡四要素 
储蓄卡：[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111"}] 
信用卡： [{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111","cvv2":"233","expire_date":"1225"}]

```



- 鉴权查询接口

> 请求URL:`http://api.heemoney.com/v1/UserAuthQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.user.auth.query`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.user.auth.query</td>
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
    <td>mch_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td></td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
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
    <td>鉴权参数集合,Json格式,长度不限,具体参数见如下业务参数</td>
    <td>Json格式</td>
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
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>单号,要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>auth_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>鉴权类型,0=未知,1=身份证鉴权,2=银行卡鉴权</td>
    <td>2</td>
</tr>
<tr>
    <td>auth_detail_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>鉴权详细类型,0=未知,1=二要素,2=三要素,3=四要素</td>
    <td>2</td>
</tr>
</table>




## 统一进件

- 进件接口

> 请求URL:`http://api.heemoney.com/v1/MerchProviderSubmit`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.provider.submit`

- 公共参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th>描述</th>
    <th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>具体业务接口名称</td>
    <td>heemoney.merch.provider.submit</td>
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
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>1002501975866</td>
</tr>
<tr>
    <td>isv_app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>服务商的应用id</td>
    <td>hyp180514100</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
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
    <td>鉴权参数集合,Json格式,长度不限,具体参数见如下业务参数</td>
    <td>Json格式</td>
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
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户号</td>
    <td>1002502108179</td>
</tr>
<tr>
    <td>merch_full_name</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>商户全名称</td>
    <td></td>
</tr>
<tr>
    <td>merch_short_name</td>
    <td>String</td>
    <td>是</td>
    <td>20</td>
    <td>商户简称</td>
    <td></td>
</tr>
<tr>
    <td>merch_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>商户类型编码，0线下商户，1线上商户，-1未知</td>
    <td>0</td>
</tr>
<tr>
    <td>province_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>省份ID</td>
    <td><a href="files/省区县数据.txt">省市县编码下载</a></td>
</tr>
<tr>
    <td>city_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>城市ID</td>
    <td><a href="files/省区县数据.txt">省市县编码</a></td>
</tr>
<tr>
    <td>county_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>县ID</td>
    <td><a href="files/省区县数据.txt">省市县编码</a></td>
</tr>
<tr>
    <td>offical_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>商户行政类型，5 个体工商户，4 企业，6 个人</td>
    <td>6</td>
</tr>
<tr>
    <td>contact_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>联系人类型，LEGAL_PERSON 法人，CONTROLLER 实际控制人，AGENT代理人，OTHER 其他</td>
    <td>LEGAL_PERSON</td>
</tr>
<tr>
    <td>contact_name</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>联系人姓名</td>
    <td>张三</td>
</tr>
<tr>
    <td>contact_mobile</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>联系人手机号</td>
    <td>13811111111</td>
</tr>
<tr>
    <td>contact_idcard</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>联系人身份证号</td>
    <td></td>
</tr>
<tr>
    <td>contact_idcard_valid</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>联系人身份证有效期</td>
    <td>2015-6-8_2025-6-8_10或者2015-6-8__长期</td>
</tr>
<tr>
    <td>area_type</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>营业执照类型,营业执照:NATIONAL_LEGAL,营业执照()多证合一):NATIONAL_LEGAL_MERGE,事业单位法人证书:INST_RGST_CTF</td>
    <td>NATIONAL_LEGAL_MERGE</td>
</tr>
<tr>
    <td>business_no</td>
    <td>String</td>
    <td>是</td>
    <td>30</td>
    <td>营业执照号</td>
    <td>2334dghhs2</td>
</tr>
<tr>
    <td>business_name</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>营业执照注册名称</td>
    <td>公司名称</td>
</tr>
<tr>
    <td>business_valid</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>营业执照有效期</td>
    <td>2015-6-8_2025-6-8_10或者2015-6-8__长期</td>
</tr>
<tr>
    <td>licence_address</td>
    <td>String</td>
    <td>是</td>
    <td>125</td>
    <td>营业执照上的地址</td>
    <td></td>
</tr>
<tr>
    <td>address</td>
    <td>String</td>
    <td>是</td>
    <td>125</td>
    <td>商户经营地址</td>
    <td></td>
</tr>
<tr>
    <td>legal_user</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>法人姓名</td>
    <td></td>
</tr>
<tr>
    <td>legal_mobile</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>法人手机号</td>
    <td></td>
</tr>
<tr>
    <td>legal_idcard</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>法人身份证号</td>
    <td></td>
</tr>
<tr>
    <td>legal_idcard_valid</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>法人身份证有效期限</td>
    <td>2015-6-8_2025-6-8_10或者2015-6-8__长期</td>
</tr>
<tr>
    <td>business_scope</td>
    <td>String</td>
    <td>是</td>
    <td>500</td>
    <td>经营范围</td>
    <td>报刊亭，小商店等</td>
</tr>
<tr>
    <td>industry_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>所属行业编码,详情看下方示例编码</td>
    <td>15</td>
</tr>
<tr>
    <td>serv_phone</td>
    <td>String</td>
    <td>是</td>
    <td>30</td>
    <td>客服电话</td>
    <td>1235885</td>
</tr>
<tr>
    <td>serv_email</td>
    <td>String</td>
    <td>是</td>
    <td>30</td>
    <td>邮箱</td>
    <td>1235885@qq.com</td>
</tr>
<tr>
    <td>shop_id_card</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>店主身份证号</td>
    <td>421224199212141641</td>
</tr>
<tr>
    <td>sale_id</td>
    <td>String</td>
    <td>是</td>
    <td>36</td>
    <td>销售ID</td>
    <td>4f2eba6c-0f12-40fc-900d-d5c1365b5058</td>
</tr>
<tr>
    <td>local_code</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>门店所在地地区代码</td>
    <td><a href="files/门店所在地地区代码.xlsx">门店所在地地区编码</a></td>
</tr>
<tr>
    <td>settle_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>结算类型,T：T+1结算,D：D+1结算</td>
    <td>T</td>
</tr>
<tr>
    <td>acct_type</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>银行开户类型,1对公,2对私</td>
    <td>1</td>
</tr>
<tr>
    <td>bank_card_no</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>银行卡号</td>
    <td>4654894</td>
</tr>
<tr>
    <td>bank_account</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>银行账户名称</td>
    <td></td>
</tr>
<tr>
    <td>open_bank</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>开户行名称</td>
    <td>建设银行</td>
</tr>
<tr>
    <td>bank_code</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>银行总行联行号</td>
    <td><a href="files/银行总行号.xlsx">银行总行号编码</a></td>
</tr>
<tr>
    <td>open_branch_bank</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>开户支行名称</td>
    <td></td>
</tr>
<tr>
    <td>bank_branch_code</td>
    <td>String</td>
    <td>否</td>
    <td>10</td>
    <td>银行支行联行号</td>
    <td></td>
</tr>
<tr>
    <td>bank_province_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>银行省份ID</td>
    <td><a href="files/省区县数据.txt">省市编码</a></td>
</tr>
<tr>
    <td>bank_city_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>银行城市ID</td>
    <td><a href="files/省区县数据.txt">省市编码</a></td>
</tr>
<tr>
    <td>bank_mobile</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>银行预留手机号</td>
    <td>15212341234</td>
</tr>
<tr>
    <td>wei_xin_fee_rate</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>微信费率,优质商户固定为0.38,非优质商户0.25~0.6,百分比</td>
    <td>0.38</td>
</tr>
<tr>
    <td>alipay_fee_rate</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>支付宝费率,优质商户固定为0.38,非优质商户0.25~0.6,百分比</td>
    <td>0.38</td>
</tr>
<tr>
    <td>material_upload_7file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>收银台照片,图片的全路径</td>
    <td>http://192.168.1.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>registry_upload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>门头照,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>rupload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>对公账户许可,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>legal_upload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>法人身份证国徽(反面照),图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>bupload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>营业执照,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>photo_upload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>内部经营照片,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_2file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>结算银行卡正面照,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_3file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>店主身份证国徽面(反面),图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_4file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>店主身份证人像面(正面),图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_5file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>入账人手持身份证正面,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>法人身份证人像面(正面),图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>material_upload_1file</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>入账授权书,图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
</table>

- 响应参数

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
    <td>返回的信息描述</td>
    <td>进件信息提交成功</td>
</tr>
<tr>
    <td>status</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>返回的信息状态</td>
    <td>ok</td>
</tr>
<tr>
    <td>sub_mch_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户编号</td>
    <td>LMFPAY000001068</td>
</tr>
</table>


```text
industry_id参数行业及编码:

8	小型超市/便利店/零售商店
9	小吃/快餐/美食城
10	水果零售/蔬菜零售
11	水吧/饮料/冷饮
12	药品/医疗/保健
13	美发/美容/足疗保健
14	网吧/KTV/酒吧休闲娱乐类
15	大中型餐饮
16	大中型连锁超市
17	校园内食堂/餐饮
18	校园内超市/便利店/零售
19	快递
20	彩票
21	交通运输/票务旅游
22	教育
23	烟酒零食
24	其他
```





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