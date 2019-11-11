## 商户基础信息简要注册

接口说明：账号注册接口

应用场景：该接口可以使服务商通过API接口创建商户账号，并返回创建结果

- 注册接口

> 请求URL:`http://api.heemoney.com/v1/MerchRegister`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.account.register`

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
    <td>heemoney.merch.account.register</td>
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
    <td>parent_mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>上级UID</td>
    <td>1002501975866</td>
</tr>
<tr>
    <td>mch_account</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户账号(只能有数字，字母及下划线组成，6 - 30位)</td>
    <td>18618225555</td>
</tr>
<tr>
    <td>company</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>公司名称</td>
    <td>北京市蔬果公司</td>
</tr>
<tr>
    <td>contact_name</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>联系人</td>
    <td>张三</td>
</tr>
<tr>
    <td>contact_mobile</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>手机号</td>
    <td>18688888888</td>
</tr>
<tr>
    <td>remark</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>备注</td>
    <td>测试</td>
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
    <td>提交成功</td>
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
    <td>result_msg</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>返回状态码描述</td>
    <td>进件成功</td>
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
    <td>merch_sub_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>子商户UID</td>
    <td>1002502109599</td>
</tr>
<tr>
    <td>mch_account</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>账号</td>
    <td>13612341234</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>版本号，1.0</td>
    <td>1.0</td>
</tr>
<tr>
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商的应用id</td>
    <td>hyp180514100250</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商商户号</td>
    <td>1002501975866</td>
</tr>
</table>


```javascript
1不输入渠道提交信息--{"return_code":"FAIL","return_msg":"parent_mch_uid参数为空"}
2不输入商户账号提交--{"return_code":"FAIL","return_msg":"mch_account参数为空"}
3不输入名称提交信息--{"return_code":"FAIL","return_msg":"company参数为空"}
4不输入联系人提交--{"return_code":"FAIL","return_msg":"contact_name参数为空"}
5不输入手机号提交--{"return_code":"FAIL","return_msg":"联系人手机号格式不正确"}
```


## 统一进件

接口说明：商户进件通道接口

应用场景：该接口通过服务商上传下属商户的资料为下属商户进件通道

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
    <td>销售ID，固定值（实例）</td>
    <td>32d21a32-8f49-4ae2-a557-a24a7b4f5d9f</td>
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
    <td>trasifer_flag</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>是否开通批量付款功能，0=否，1=是</td>
    <td>1</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>进件审核通过通知地址</td>
    <td>https://...</td>
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
<tr>
    <td>protocol_upload_file</td>
    <td>String</td>
    <td>否</td>
    <td>256</td>
    <td>协议照,开通付款功能必填，图片的全路径</td>
    <td>http://192.168.2.1/pay/bc6a1.jpg</td>
</tr>
<tr>
    <td>agreement_upload_file</td>
    <td>String</td>
    <td>否</td>
    <td>256</td>
    <td>申明协议函,开通付款功能必填，图片的全路径</td>
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
    <td>sub_mch_uid</td>
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

## 进件查询

接口说明：进件结果查询接口

应用场景：该接口提供给服务商和商户通过API返回业务开通的结果

- 进件查询接口

> 请求URL:`http://api.heemoney.com/v1/MerchProviderQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.provider.query`

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
    <td>heemoney.merch.provider.query</td>
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
    <td>查询成功</td>
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
    <td>sub_mch_id_130</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>通道130子商户号||审核状态，审核状态1=成功、-1=失败、0=审核中</td>
    <td>LMFPAY100001742||1</td>
</tr>
<tr>
    <td>sub_mch_id_133</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>通道133子商户号||审核状态，审核状态1=成功、-1=失败、0=审核中</td>
    <td>LMFPAY100001742||1</td>
</tr>
</table>


## 微信支付配置

接口说明：通道进件后绑定微信公众号支付接口

应用场景：该接口用于在商户业务开通后通过API绑定商户的微信公众号支付业务

- 配置接口

> 请求URL:`http://api.heemoney.com/v1/MerchSetWxPayConfig`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.set.wxpay.config`

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
    <td>heemoney.set.wxpay.config</td>
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
    <td>sub_mch_id_133</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>通道133子商户号（客商）</td>
    <td>LMFPAY100001742</td>
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
    <td>操作成功</td>
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


```javascript
如何绑定微信公众号配置成功
Ø	客商通道已进件成功未绑定过微信公众号配置
Ø	响应数据：
{"return_code":"SUCCESS","return_msg":"操作成功","result_code":"SUCCESS","result_msg":"操作成功","status":"ok","sign":"23BE2F3D9BC827EC03167A646AE40588"}
3.3已绑定过再次绑定
Ø	该客商进件记录绑定过微信配置，再次绑定提示"已绑定成功，不能重复绑定" 
Ø	响应数据：
{"return_code":"SUCCESS","return_msg":"OK","result_code":"FAIL","error_msg":"已绑定成功，不能重复绑定","sign":"0FD65F8B1290072B0896B890E5989997"}
```
