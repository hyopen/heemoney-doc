## 统一下单

接口说明：支持主扫、H5、微信公众号、小程序、服务窗、网银、快捷等

应用场景：系统调用该接口后，返回支付URL调起支付。

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
    <td>商户系统内部订单号,要求64个字符内、且在同一个商户号下唯一。</td>
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
    <td>channel_type</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道类型，扫码支付，WX_NATIVE、ALI_QRCODE、微信小程序：WX_APPLET，微信代扣：WX_WITHHOLD，等具体见接口规则-参数规定-通道类型</td>
    <td>WX_NATIVE</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>APP和网页支付提交用户端ip，Native支付填调用微信支付API的机器IP。</td>
    <td>192.*.*.*</td>
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
    <td>商户门店（部分通道必传，若返回消息为“门店不能为空”，则该参数必传）</td>
    <td>1002501974599</td>
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
    <td>支付参数信息，如果支付类型为微信代扣（WX_WITHHOLD）需要填入： hy_contract_no（汇元签约编号） JSON 格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，JSON 格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
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
<tr>
    <td>hy_extend_params</td>
    <td>String</td>
    <td>否</td>
    <td>512</td>
    <td>汇元返回支付扩展参数</td>
    <td>JSON格式，云闪付APP支付类型返回 {\"tn\":\"533142681549904444118\"}</td>
</tr>

</table>


## 直接下单

接口说明：付款码支付下单接口（商户扫用户）

应用场景：例如-收银员使用扫码设备读取用户付款码以后，二维码或条码信息会传送至商户收银台，由商户收银台或者商户后台调用该接口发起支付。

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
    <td>商户操作员或收银员编号</td>
    <td>1001</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>18</td>
    <td>商户门店（部分通道必传，若返回消息为“门店不能为空”，则该参数必传）</td>
    <td>1002501974599</td>
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
    <td>192.*.*.*</td>
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
    <td>否</td>
    <td>16</td>
    <td>通道类型刷卡类型：WX_MICROPAY、ALI_SWIPE、BANK_SWIPE具体见接口规则-参数规定-通道类型
    。不传从 auth_bar_code 参数自动识别</td>
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
    <td>支付参数信息，JSON 格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
    <td>{}</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息，格式：JSON {“key1”:”value1”,”key2”:”value2”,…}</td>
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
    <td>channel_bar_code</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>微信/支付宝支付成功账单交易单号条形码</td>
    <td>1121212019080811443774867818</td>
</tr>
<tr>
    <td>channel_return_msg</td>
    <td>stirng</td>
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
    <td>单据状态：Undeal=未支付，Success=支付成功，Failure=支付失败</td>
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
    <td>订单支付时间，格式为yyyy-MM-dd HHmmss</td>
    <td>2019-07-31 15：41：38</td>
</tr>
<tr>
    <td>company</td>
    <td>string</td>
    <td>是</td>
    <td></td>
    <td>公司名称</td>
    <td></td>
</tr>
</table>


## 订单查询

接口说明：查询支付订单接口

应用场景：该接口提供支付订单的查询，商户可以通过查询订单接口主动查询订单状态，完成下一步的业务逻辑。

需要调用查询接口的情况：

1. 当商户后台、网络、服务器等出现异常，商户系统最终未接收到支付通知；
2. 调用支付接口后，返回系统错误或未知交易状态情况；
3. 确保异步通知返回状态无误


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
    <td>channel_bar_code</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>微信/支付宝支付成功账单交易单号条形码</td>
    <td>1121212019080811443774867818</td>
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
    <td>单据状态：Undeal=未支付，Success=支付成功，Failure=支付失败</td>
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
    <td>订单支付时间，格式为yyyy-MM-dd HHmmss</td>
    <td>2019-07-31 15：41：38</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>附加数据</td>
    <td>100</td>
</tr>
<tr>
    <td>meta_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>商户定制信息</td>
    <td>JSON 格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
</tr>
<tr>
    <td>pay_option</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>支付参数信息</td>
    <td>JSON 格式：{“key1”:”value1”,”key2”:”value2”,…}</td>
</tr>
<tr>
    <td>channel_bar_code</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>微信/支付宝支付成功账单交易单号条形码</td>
    <td>1121212019080811443774867818</td>
</tr>
</table>

商户处理业务用real_fee，为实际支付金额,我方会按照此金额结算给商户。
total_fee=real_fee
用户支付金额=real_fee-coupon_amt



## 支付结果通知

接口说明：支付结果通知接口

应用场景：支付状态异步通知API，汇收银主动发请求给商户下单接口传递的异步通知地址

- 支付状态异步通知API

> 请求URL:`下单接口传递的异步通知地址`

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
    <td>应用ID</td>
    <td></td>
</tr>
<tr>
    <td>mch_uid</td>
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


## 申请退款

接口说明：退款申请接口

应用场景：当交易发生之后一段时间内，由于买家或者商户的原因需要退款时，商户可以通过退款接口将支付款退还给买家，汇收银将在收到退款请求并且验证成功之后，按照退款规则将支付款原路退回。

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
    <td>是</td>
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
    <td>是</td>
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
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际退款金额</td>
    <td>100</td>
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

接口说明：退款查询接口

应用场景：提交退款申请后，通过调用该接口查询退款状态。退款会有一定延时。

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
    <td>汇元退款单号</td>
    <td>TuiKuanlsjd2453</td>
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
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>实际退款金额</td>
    <td>100</td>
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
    <td>退款状态：Undeal=退款处理中，Success=退款成功，Failure=退款失败</td>
    <td>Undeal</td>
</tr>
</table>	


