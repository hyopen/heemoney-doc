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



## 开票状态查询接口

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



## 直接开票接口

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



## 发票红冲接口

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


