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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <td>wx_js_code</td>
    <td>String</td>
    <td>否</td>
    <td>50</td>
    <td>微信小程序jsCode，获取OpenID用，微信小程序支付必传</td>
    <td>ofOjKwQhQDI7pQU1DoQ2lU4ycPd0</td>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <td><a href="files/所在地地区代码.xlsx">省市编码</a></td>
</tr>
<tr>
    <td>city_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>城市ID</td>
    <td><a href="files/所在地地区代码.xlsx">省市编码</a></td>
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
    <td><a href="files/所在地地区代码.xlsx">所在地地区编码</a></td>
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
    <td><a href="files/所在地地区代码.xlsx">省市编码</a></td>
</tr>
<tr>
    <td>bank_city_id</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>银行城市ID</td>
    <td><a href="files/所在地地区代码.xlsx">省市编码</a></td>
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

## 聚合分账

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


- 分账异步通知API（汇收银主动发请求给商户）

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




- 分账查询接口

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


## 扫码开票

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/QrCodeInvoice`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.invoice.qrcode`

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
    <td>heemoney.invoice.qrcode</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>否</td>
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
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户系统内部订单号,要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>merch_name</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>商户名称</td>
    <td>张三的店</td>
</tr>
<tr>
    <td>merch_identification_num</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>商户纳税人识别号</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>total_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>价税合计,保留两位小数</td>
    <td>5.00</td>
</tr>
<tr>
    <td>note</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>发票备注</td>
    <td></td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>异步通知的地址(暂时还不支持回调)</td>
    <td>http://www.***.com/***</td>
</tr>
<tr>
    <td>invoice_items</td>
    <td>String</td>
    <td>是</td>
    <td>不限</td>
    <td>发票明细</td>
    <td>json格式</td>
</tr>
</table>

- 发票明细参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>invoice_line_type</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>发票行类型，0=正常行,1=折扣行,2=被折扣行</td>
    <td>0</td>
</tr>
<tr>
    <td>invoice_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>行号，有折扣时需要必输</td>
    <td></td>
</tr>
<tr>
    <td>discount_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>折扣行行号，如果本行为被折扣行即invoice_line_type值为2时此字段为必输，值为本行对应的折扣行行号，折扣行的invoice_line_type值为1</td>
    <td></td>
</tr>
<tr>
    <td>invoice_subject_name</td>
    <td>string</td>
    <td>是</td>
    <td>255</td>
    <td>发票项目名称</td>
    <td>餐费</td>
</tr>
<tr>
    <td>invoice_specifications</td>
    <td>string</td>
    <td>否</td>
    <td>16</td>
    <td>规格型号</td>
    <td>牙膏</td>
</tr>
<tr>
    <td>invoice_unit</td>
    <td>string</td>
    <td>否</td>
    <td>16</td>
    <td>个</td>
    <td></td>
</tr>
<tr>
    <td>invoice_num</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>数量</td>
    <td>1</td>
</tr>
<tr>
    <td>invoice_price</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目单价，项目单价为空时，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>invoice_amt</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目金额,保留两位小数，项目金额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>subject_total_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>项目价税合计</td>
    <td></td>
</tr>
<tr>
    <td>invoice_fee</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票费率,如果费率是6%，则传0.06</td>
    <td>0.06</td>
</tr>
<tr>
    <td>invoice_fee_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票税额,保留两位小数，税额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>0.28</td>
</tr>
<tr>
    <td>revenue_code</td>
    <td>string</td>
    <td>是</td>
    <td>50</td>
    <td>商品税收编码</td>
    <td>餐费 3070401000000000000</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>QRCODE_INVOICE</td>
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
    <td>code_url</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>发票二维码链接</td>
    <td>https://..或http://</td>
</tr>
</table>



- 开票状态查询接口

> 请求URL:`https://api.heemoney.com/v1/QueryInvoice`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.invoice.query`

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
    <td>heemoney.pay.applypay</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>否</td>
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

返回响应：


- 公共响应参数

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
    <th width="220">描述</th>
    <th width="163">示例值</th>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
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
    <td>merch_name</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户名称</td>
    <td>张三的店</td>
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
    <td>merch_identification_num</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>商户纳税人识别号</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>invoice_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票金额</td>
    <td>4.72</td>
</tr>
<tr>
    <td>invoice_fee_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票税额</td>
    <td>0.28</td>
</tr>
<tr>
    <td>total_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>价税合计</td>
    <td>5.00</td>
</tr>
<tr>
    <td>invoice_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>状态</td>
    <td>UnKnow=待开票，Starting=开票中，Success=开票成功，Failure=开票失败</td>
</tr>
<tr>
    <td>invoice_drawer</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>开票人</td>
    <td>张三</td>
</tr>
<tr>
    <td>invoice_review</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>复核人</td>
    <td>李四</td>
</tr>
<tr>
    <td>invoice_code</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>发票代码</td>
    <td>762370394413</td>
</tr>
<tr>
    <td>invoice_no</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>发票号码</td>
    <td>73558796</td>
</tr>
<tr>
    <td>invoice_check_code</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>发票校验码</td>
    <td>57644233870940613901</td>
</tr>
<tr>
    <td>invocie_password</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>发票密文</td> <td>\u003c-\u003c\u003e48938\u003c4+\u003c14\u003e735+\u003c25548-1-\u003c+15\u003c026+848686/2/3//0\u003e+\u003e\u003e\u003e356\u003c757/47\u003e90+\u003c25\u003c\u003c3575*934\u003c+15\u003c026+848686--57</td>
</tr>
<tr>
    <td>invocie_device_num</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>机器编号</td>
    <td>66666</td>
</tr>
<tr>
    <td>invocie_time</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>开票时间</td>
    <td>20190617114346</td>
</tr>
<tr>
    <td>invoice_extract_url</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>发票提取地址</td>
    <td>https://yesfp.yonyoucloud.com/output-ta</td>
</tr>
<tr>
    <td>items</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>发票明细</td>
    <td>json格式</td>
</tr>
</table>


- 发票明细参数 


<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>invoice_line_type</td>
    <td>Int</td>
    <td>否</td>
    <td>16</td>
    <td>发票行类型，0=正常行,1=折扣行,2=被折扣行</td>
    <td>0</td>
</tr>
<tr>
    <td>invoice_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>行号，有折扣时需要必输</td>
    <td></td>
</tr>
<tr>
    <td>discount_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>折扣行行号，如果本行为被折扣行即invoice_line_type值为2时此字段为必输，值为本行对应的折扣行行号，折扣行的invoice_line_type值为1</td>
    <td></td>
</tr>
<tr>
    <td>invoice_subject_name</td>
    <td>string</td>
    <td>是</td>
    <td>255</td>
    <td>发票项目名称</td>
    <td>餐费</td>
</tr>
<tr>
    <td>invoice_specifications</td>
    <td>string</td>
    <td>否</td>
    <td>16</td>
    <td>规格型号</td>
    <td>牙膏</td>
</tr>
<tr>
    <td>invoice_unit</td>
    <td>string</td>
    <td>否</td>
    <td>16</td>
    <td>单位</td>
    <td>1</td>
</tr>
<tr>
    <td>invoice_num</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>数量</td>
    <td>1</td>
</tr>
<tr>
    <td>invoice_price</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目单价，项目单价为空时，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>invoice_amt</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目金额,保留两位小数，项目金额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>subject_total_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>项目价税合计</td>
    <td></td>
</tr>
<tr>
    <td>invoice_fee</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票费率,如果费率是6%，则传0.06</td>
    <td>0.06</td>
</tr>
<tr>
    <td>invoice_fee_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票税额,保留两位小数，税额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>0.28</td>
</tr>
<tr>
    <td>revenue_code</td>
    <td>string</td>
    <td>是</td>
    <td>50</td>
    <td>商品税收编码</td>
    <td>餐费 3070401000000000000</td>
</tr>
</table>



- 直接开票接口

> 请求URL:`https://api.heemoney.com/v1/DirectInvoice`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.invoice.direct`

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
    <td>heemoney.invoice.qrcode</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>否</td>
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
    <td>charset</td>
    <td>String</td>
    <td>否</td>
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
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户系统内部订单号，要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>invoice_type</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>  <td>发票类型,1=增值税电子普通发票,3=增值税普通发票,4=增值税专用发票,8=增值税电子普通发票（成品油）,9=成品油普通发票(卷式),10=成品油普通发票，11=成品油专用发票，12=增值税普通发票(卷式)</td>
    <td>默认1</td>
</tr>
<tr>
    <td>merch_name</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>商户</td>
    <td>张三的店</td>
</tr>
<tr>
    <td>merch_identification_num</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>商户纳税人识别号</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>merch_phone</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>销售方电话地址</td>
    <td>1560700800000 中关村</td>
</tr>
<tr>
    <td>merch_bank_card_no</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>销售方开户行及账号</td>
    <td>建行1 62202201212121212</td>
</tr>
<tr>
    <td>buyer_name</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>购买方名称</td>
    <td>汇元网</td>
</tr>
<tr>
    <td>buyer_identification_num</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>购买方纳税人识别号</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>buyer_phone</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>购买方电话地址</td>
    <td>1560700800000 中关村</td>
</tr>
<tr>
    <td>buyer_bank_card_no</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>购买方开户行及账号</td>
    <td>建行1 62202201212121212</td>
</tr>
<tr>
    <td>note</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>发票备注(暂时还不支持回调)</td>
    <td></td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>异步通知的地址(暂时还不支持回调)</td>
    <td>http://www.***.com/***</td>
</tr>
<tr>
    <td>invoice_items</td>
    <td>String</td>
    <td>是</td>
    <td>不限</td>
    <td>发票明细</td>
    <td>json格式</td>
</tr>
</table>

- 发票明细参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>invoice_subject_name</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>发票项目名称</td>
    <td>餐费</td>
</tr>
<tr>
    <td>invoice_specifications</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>规格型号</td>
    <td>牙膏</td>
</tr>
<tr>
    <td>invoice_unit</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>单位</td>
    <td>个</td>
</tr>
<tr>
    <td>invoice_num</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>数量</td>
    <td>1</td>
</tr>
<tr>
    <td>invoice_price</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目单价，项目单价为空时，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>invoice_amt</td>
    <td>decimal</td>
    <td>否</td>
    <td>16</td>
    <td>项目金额,保留两位小数，项目金额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>4.72</td>
</tr>
<tr>
    <td>subject_total_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>项目价税合计</td>
    <td></td>
</tr>
<tr>
    <td>invoice_fee</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票费率,如果费率是6%，则传0.06</td>
    <td>0.06</td>
</tr>
<tr>
    <td>invoice_fee_amt</td>
    <td>decimal</td>
    <td>是</td>
    <td>16</td>
    <td>发票税额,保留两位小数，税额为空，根据价税合计反算。不为空时不进行计算</td>
    <td>0.28</td>
</tr>
<tr>
    <td>revenue_code</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>商品税收编码</td>
    <td>餐费 3070401000000000000</td>
</tr>
<tr>
    <td>invoice_line_type</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>发票行类型，0=正常行,1=折扣行,2=被折扣行</td>
    <td>0</td>
</tr>
<tr>
    <td>invoice_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>行号，有折扣时需要必输</td>
    <td>个</td>
</tr>
<tr>
    <td>discount_line_num</td>
    <td>int</td>
    <td>否</td>
    <td>16</td>
    <td>折扣行行号，如果本行为被折扣行即invoice_line_type值为2时此字段为必输，值为本行对应的折扣行行号，折扣行的invoice_line_type值为1</td>
    <td>个</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>QRCODE_INVOICE</td>
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
    <td>invoice_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>状态</td>
    <td>UnKnow=待开票，Starting=开票中，Success=开票成功，Failure=开票失败</td>
</tr>
</table>	



- 发票红冲接口

> 请求URL:`https://api.heemoney.com/v1/InvoiceRed`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.invoice.red`

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
    <td>heemoney.invoice.qrcode</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>否</td>
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
    <td>charset</td>
    <td>String</td>
    <td>否</td>
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
    <td></td>
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
    <td>64</td>
    <td>商户开票记录订单号，要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>out_invoice_red_no</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>  
	<td>商户发票红冲订单号，要求64个字符内、且在同一个商户号下唯一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>invoice_Code</td>
    <td>String</td>
    <td>是</td>
    <td>12</td>
    <td>原发票代码</td>
    <td>201609140000001</td>
</tr>
<tr>
    <td>invoice_no</td>
    <td>String</td>
    <td>是</td>
    <td>8</td>
    <td>发票号码</td>
    <td>45949403</td>
</tr>
<tr>
    <td>invoice_payee</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>收款人</td>
    <td>李四</td>
</tr>
<tr>
    <td>invoice_drawer</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>开票人</td>
    <td>李四</td>
</tr>
<tr>
    <td>invoice_review</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>复核人</td>
    <td>李四</td>
</tr>
</table>



- 公共响应参数：

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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>支付类型</td>
    <td>QRCODE_INVOICE</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户发票红冲订单号</td>
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
    <td>invoice_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>红冲状态</td>
    <td>UnKnow=未红冲，Starting=红冲中，Success=红冲成功，Failure=红冲失败</td>
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
    <td>机构号</td>
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
    <td>http://............</td>
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



- 转账查询接口

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
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>org_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>机构号</td>
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

- 支付请求接口

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
    <th>描述</th>
    <th>示例值</th>
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
    <td>否</td>
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
    <td>是</td>
    <td>255</td>
    <td>收款码UIDs(多个英文逗号分隔)</td>
    <td></td>
</tr>
<tr>
    <td>device_uids</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>设备UIDs(多个英文逗号分隔)</td>
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

## 商户登录

- 订单查询接口

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
    <th>描述</th>
    <th>示例值</th>
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
    <td>否</td>
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
    <td>否</td>
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
    <th>描述</th>
    <th>示例值</th>
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
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>所有业务参数组织成json格式再3eds加密后放到login_info参数里面传递</td>
    <td>{"mch_account":"zhifubaoceshi","mch_emp_account":"15110186488","login_pwd":"123456","device_uid":"100250000000938","dpass_pwd":"123456"}</td>
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




## 商户设备激活

- 直接开票接口

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
    <th>描述</th>
    <th>示例值</th>
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
    <td>否</td>
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
    <td>否</td>
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
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
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
    <th>描述</th>
    <th>示例值</th>
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
    <td>QRCODE_INVOICE</td>
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