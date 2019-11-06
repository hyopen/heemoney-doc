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
    <td>mch_uid</td>
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
    <td>鉴权数据详细集合,Json格式,长度不限，需要进行3DES加密（ECB）</td>
    <td>[{"bank_card_type":"","auth_bank_card":"","auth_name":""}]</td>
</tr>
</table>

auth_data_info	鉴权数据详细json格式示例


```javascript
bank_card_type：银行卡类型，1=储蓄卡，2=信用卡
auth_bank_card：银行卡号
auth_name：姓名
cvv2：信用卡安全码，银行卡背面3位数字
expire_date：信用卡过期时间
auth_id_card：身份证号码
auth_mobile：银行预留手机号
//银行卡二要素 
//储蓄卡： 
[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_name":"张三"}] 
//信用卡： 
[{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_name":"张三","cvv2":"233","expire_date":"1225"}]

//银行卡三要素 
//储蓄卡：
[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三"}] 
//信用卡： 
[{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","cvv2":"233","expire_date":"1225"}]

//银行卡四要素 
//储蓄卡：
[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111"}] 
//信用卡：
[{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111","cvv2":"233","expire_date":"1225"}]

//身份证二要素： 
[{"auth_id_card":"320926195511175276","auth_name":"张三"}] 
//身份证三要素： 
[{"auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111"}]

```



## 鉴权查询接口

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
    <td>mch_uid</td>
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



## 信用卡还款-银行卡绑定

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/CardRepaymentBind`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.card.repayment.bind`

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
    <td>heemoney.card.repayment.bind</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>记录号</td>
    <td>CA1908A32E0</td>
</tr>
<tr>
    <td>province</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>开户省份(名称)</td>
    <td>河北</td>
</tr>
<tr>
    <td>city</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>开户城市(名称)</td>
    <td>石家庄</td>
</tr>
<tr>
    <td>open_bank</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>开户行名称</td>
    <td>中国银行</td>
</tr>
<tr>
    <td>open_branch_bank</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>开户支行名称</td>
    <td>黄河大道支行</td>
</tr>
<tr>
    <td>fee_rate</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>手续费，0.5表示0.5%</td>
    <td>0.5</td>
</tr>
<tr>
    <td>auth_data_info</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>银行卡信息Json格式，需要进行3DES加密（ECB）</td>
    <td>[{"bank_card_type":"","auth_bank_card":"","auth_id_card":"","auth_name":"","auth_mobile":""}]</td>
</tr>
</table>


```javascript
bank_card_type：银行卡类型，1=储蓄卡，2=信用卡
auth_bank_card：银行卡号
auth_name：姓名
cvv2：信用卡安全码，银行卡背面3位数字
expire_date：信用卡过期时间
auth_id_card：身份证号码
auth_mobile：银行预留手机号
储蓄卡：[{"bank_card_type":"1","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111"}]
信用卡： [{"bank_card_type":"2","auth_bank_card":"6217000130000751966","auth_id_card":"320926195511175276","auth_name":"张三","auth_mobile":"13811111111","cvv2":"233","expire_date":"1225"}]

```

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
    <td>成功</td>
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
    <td></td>
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
    <td>ref_record_code</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>绑卡记录号</td>
    <td>47CE87071D18</td>
</tr>
<tr>
    <td>agreement_key</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>协议编号</td>
    <td>F1908071045</td>
</tr>
<tr>
    <td>return_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>信息描述</td>
    <td>进件信息提交成功</td>
</tr>
</table>	



## 信用卡还款-支付申请

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/CardRepaymentPay`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.card.repayment.Pay`

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
    <td>heemoney.card.repayment.Pay</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>商户系统内部订单号，且在同一个商户号下唯一</td>
    <td>CA1908A32E0</td>
</tr>
<tr>
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>订单标题</td>
    <td>购买礼品</td>
</tr>
<tr>
    <td>city</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>城市(名称)</td>
    <td>石家庄</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>Int</td>
    <td>是</td>
    <td>-</td>
    <td>订单总金额,单位为分</td>
    <td>100</td>
</tr>
<tr>
    <td>fee_rate</td>
    <td>String</td>
    <td>否</td>
    <td>10</td>
    <td>费率，0.38表示0.38%</td>
    <td>0.38</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>客户端IP</td>
    <td>127.0.0.1</td>
</tr>
<tr>
    <td>agreement_key</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>协议编号</td>
    <td></td>
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
    <td>成功</td>
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
    <td></td>
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
    <td>channel_id</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道代码</td>
    <td>138</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>5613218541</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇收银订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>hy_pay_id</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单号，TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>thpinfo</td>
    <td>String</td>
    <td>否</td>
    <td>-</td>
    <td>通道代码</td>
    <td>交易信息</td>
</tr>
</table>	




## 信用卡还款-余额查询

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/CardRepaymentBalance`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.card.repayment.balance`

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
    <td>heemoney.card.repayment.balance</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>channel_id</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>通道ID</td>
    <td>138</td>
</tr>
<tr>
    <td>agreement_key</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>绑定协议号</td>
    <td>64614321</td>
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
    <td>成功</td>
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
    <td></td>
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
    <td>balance</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>余额，元</td>
    <td>9.94</td>
</tr>
</table>	




## 信用卡还款-付款申请

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/CardRepaymentTransfer`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.card.repayment.repay`

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
    <td>heemoney.card.repayment.repay</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>否</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>2B89FE832B46476</td>
</tr>
<tr>
    <td>subject</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>订单标题</td>
    <td>购买礼品</td>
</tr>
<tr>
    <td>total_fee</td>
    <td>int</td>
    <td>是</td>
    <td>-</td>
    <td>订单金额，单位：分</td>
    <td>100</td>
</tr>
<tr>
    <td>fee_rate</td>
    <td>int</td>
    <td>否</td>
    <td>-</td>
    <td>手续费金额，单位：分</td>
    <td>10</td>
</tr>
<tr>
    <td>client_ip</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>客户端IP</td>
    <td>127.0.0.1</td>
</tr>
<tr>
    <td>agreement_key</td>
    <td>String</td>
    <td>是</td>
    <td>255</td>
    <td>协议编号</td>
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
    <td>成功</td>
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
    <td></td>
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
    <td>channel_id</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道代码</td>
    <td>138</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>6546544</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇收银订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>hy_pay_id</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单号，TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>Status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>交易状态，1成功-1失败</td>
    <td>1</td>
</tr>
</table>	






## 信用卡还款-交易单查询

支付交易、提现和付款交易订单的查询接口

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/CardRepaymentQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.card.repayment.query`

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
    <td>heemoney.card.repayment.query</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>否</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>2B89FE832B46476</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇收银订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>bill_type</td>
    <td>String</td>
    <td>是</td>
    <td>-</td>
    <td>订单类型，1=支付单，3=付款单</td>
    <td>1</td>
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
    <td>成功</td>
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
    <td></td>
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
    <td>channel_id</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>通道代码</td>
    <td>138</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户订单号</td>
    <td>6546544</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇收银订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>hy_pay_id</td>
    <td>String</td>
    <td>是</td>
    <td>256</td>
    <td>订单号，TokenID</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>交易状态，1成功-1失败</td>
    <td>1</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>时间yyyyMMddHHmmss</td>
    <td>-</td>
</tr>
</table>



## 信用卡还款-对账文件下载

通过接口下载指定日期的对账文件，返回下载文件路径

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/MerchBillReport`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.bill.download`

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
    <td>heemoney.card.repayment.query</td>
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
    <td>商户UID</td>
    <td>1002502108093</td>
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
    <td>date</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>交易日期，yyyyMMdd</td>
    <td>-</td>
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
    <td>成功</td>
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
    <td></td>
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
    <td>商户UID</td>
    <td>10025021</td>
</tr>
<tr>
    <td>url</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>获取对账文件的url</td>
    <td>http://....</td>
</tr>
</table>


