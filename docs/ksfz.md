## 付款结算账户

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/TransferThirdBindAdd`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.transfer.account.add`

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
    <td>heemoney.transfer.account.add</td>
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
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户号</td>
    <td>1002502109403</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>门店uid</td>
    <td>1002502109403</td>
</tr>
<tr>
    <td>account_type</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>账户类型：1=个人,2=企业</td>
    <td>1</td>
</tr>
<tr>
    <td>account_class</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>账户性质：0=实户（固定值）</td>
    <td>0</td>
</tr>
<tr>
    <td>bank_code</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>银行编号</td>
    <td><a href="files/银行编号.xlsx">银行编号</td>
</tr>
<tr>
    <td>bank_province_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>开户支行所在省编号</td>
    <td><a href="files/省市区编码.xlsx">省市编码</td>
</tr>
<tr>
    <td>bank_city_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>开户支行所在市编号</td>
    <td><a href="files/省市区编码.xlsx">省市编码</td>
</tr>
<tr>
    <td>open_branch_bank</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>开户支行名称，账户类型为企业时必填</td>
    <td></td>
</tr>
<tr>
    <td>business_no</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>营业执照编号，账户类型为企业时必填</td>
    <td></td>
</tr>
<tr>
    <td>bank_mobile</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>银行预留手机号，账户类型为个人时必填</td>
    <td></td>
</tr>
<tr>
    <td>corp_idcard_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>证件类型，1=身份证，2=护照</td>
    <td>1</td>
</tr>
<tr>
    <td>legal_user</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>法人姓名，企业账户必填</td>
    <td>张三</td>
</tr>
<tr>
    <td>legal_idcard</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>证件号码/法人证件号码</td>
    <td></td>
</tr>
<tr>
    <td>bank_card_no</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>银行卡号</td>
    <td></td>
</tr>
<tr>
    <td>bank_account</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>开户人/企业名称</td>
    <td></td>
</tr>
<tr>
    <td>provider_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>付款通道，客商</td>
    <td>客商</td>
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
    <td>提交操作申请成功</td>
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
    <td>应用ID，商户的应用id</td>
    <td>hyp1908091002</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
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
</table>	




## 付款

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/TransferSubmit`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.transfer.submit`

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
    <td>heemoney.transfer.submit</td>
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
    <td>mch_uid	</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
    <td>4945892</td>
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
    <td>store_uid</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户门店号</td>
    <td>123123123123</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>付款批次单号</td>
    <td>1111111111</td>
</tr>
<tr>
    <td>remark</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>付款说明</td>
    <td>测试</td>
</tr>
<tr>
    <td>attach</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>附加数据</td>
    <td></td>
</tr>
<tr>
    <td>bill_num</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>笔数</td>
    <td>1</td>
</tr>
<tr>
    <td>bill_fee</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>总金额(单位分)</td>
    <td>100</td>
</tr>
<tr>
    <td>transfer_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>付款类型，6=银行余额</td>
    <td>6</td>
</tr>
<tr>
    <td>account_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>账户类型，1=对私，2=对公</td>
    <td>1</td>
</tr>
<tr>
    <td>provider_type</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>通道提供方，固定值=133</td>
    <td>133</td>
</tr>
<tr>
    <td>business_no</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>营业执照编号，账户类型为企业时必填</td>
    <td></td>
</tr>
<tr>
    <td>recipients</td>
    <td>String</td>
    <td>否</td>
    <td>-</td>
    <td>付款明细，merch_detail_id=商户明细流水，to_bind_id=账户绑定ID（在平台付款管理 第三方绑定中可以查询到），transfer_fee=金额（单位：分）</td>
    <td>[{"merch_detail_id":"111cca11","to_bind_id":"1002","transfer_fee":"101"},{"merch_detail_id":"1100ca11","to_bind id":"1001","transfer_fee":"101"}]</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>异步通知</td>
    <td>https://...</td>
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
    <td>付款申请成功</td>
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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>版本号，1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>hyp1908091002</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户付款批次单号</td>
    <td>1222232323</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇付宝付款批次单号</td>
    <td>F190821155000283821002500137</td>
</tr>
<tr>
    <td>bill_num</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>总笔数</td>
    <td>1</td>
</tr>
<tr>
    <td>bill_fee</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>总金额，单位分</td>
    <td>1</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>付款状态，0=处理中</td>
    <td>0</td>
</tr>
<tr>
    <td>begin_time</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>下单时间</td>
    <td>20190725152322</td>
</tr>
</table>	


## 付款查询

- 请求接口

> 请求URL:`https://api.heemoney.com/v1/TransferQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.transfer.query`

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
    <td>heemoney.transfer.query</td>
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
    <td>商户付款批次单号</td>
    <td>123</td>
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
    <td>version</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>版本号，1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>应用ID，商户的应用id</td>
    <td>hyp1908091002</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户号</td>
    <td>Ap22512545</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>商户付款单号</td>
    <td>47CE87071D1846849CF010CA00CABF8B</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>汇元付款单号</td>
    <td>F190807104500261601002500133</td>
</tr>
<tr>
    <td>bill_num</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>总笔数</td>
    <td>1</td>
</tr>
<tr>
    <td>bill_fee</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>付款总金额，单位分</td>
    <td>1</td>
</tr>
<tr>
    <td>success_bill_num</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>成功笔数</td>
    <td>1</td>
</tr>
<tr>
    <td>success_bill_fee</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>付款成功金额，单位分</td>
    <td>1</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>交易单状态，1=成功，0=处理中，-1失败</td>
    <td>1</td>
</tr>
<tr>
    <td>begin_time</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>下单时间</td>
    <td>20190807104508</td>
</tr>
</table>	


