## 公共信息
- 接口请求
  - 联调地址 URL：`https://demo.heemoney.com/YunBiz/Enterprise/V1`
  - 正式地址 URL：`https://yunbiz.heepay.com/Enterprise/V1`
  - 请求方式：`Post` 

- 公共请求参数
<table data-hy-role="doctbl">
  <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
    </tr>
    <tr>
        <td>method</td>
        <td>String</td>
        <td>否</td>
        <td>100</td>
        <td>请求方法</td>
        <td>V1/Login</td>
    </tr>
    <tr>
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>
    <tr>
        <td>app_id</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>应用ID</td>
        <td>hyp190918494589000018558B0707C82</td>
    </tr>
    <tr>
        <td>charset</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>编码格式</td>
        <td>utf-8</td>
    </tr>
    <tr>
        <td>sign_type</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>签名类型</td>
        <td>MD5、RSA</td>
    </tr>
    <tr>
        <td>timestamp</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>请求时间(yyyyMMddHHmmss)</td>
        <td>MD5、RSA</td>
    </tr>   
    <tr>
        <td>biz_content</td>
        <td>String</td>
        <td>是</td>
        <td>不限</td>
        <td>业务参数集合,Json格式,长度不限,具体参数见如下业务参数</td>
        <td>JSON String</td>
    </tr>
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
<table>

- 业务请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>  
     <tr>
        <td>parames</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>其他参数</td>
        <td>parames</td>
    </tr>
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>异步通知地址</td>
        <td>http://www.baidu.com</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>256</td>
        <td>支付完成返回商户URL地址</td>
        <td>http://www.baidu.com</td>
    </tr>
</table>

- 公共响应参数
<table data-hy-role="doctbl">
  <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
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
        <td>SUCCESS</td>
        <td>返回状态码描述</td>
        <td>提交成功</td>
    </tr>
    <tr>
        <td>result_code</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>业务状态码（return_code为SUCCESS返回）</td>
        <td>SUCCESS</td>
    </tr>   
    <tr>
        <td>result_msg</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>返回状态码描述（return_code为SUCCESS返回）</td>
        <td>成功</td>
    </tr>  
    <tr>
        <td>error_code</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>错误代码（return_code为FAIL返回）</td>
        <td></td>
    </tr>
    <tr>
        <td>error_msg</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>错误返回的信息描述（return_code为FAIL返回）</td>
        <td></td>
    </tr>
</table>

- 业务响应参数，以下字段在return_code为SUCCESS时返回，result_code为SUCCESS时返回
<table data-hy-role="doctbl">
  <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>   
    <tr>
        <td>result_code</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>交易状态</td>
        <td>SUCCESS</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>
     <tr>
        <td>app_id</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>应用ID</td>
        <td>hyp190918494589000018558B0707C82</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid(对接商户所属用户唯一标识)</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>http://www.demo.heemoney.com/Transfer/Index?token=454564654566</td>
     </tr>
</table>

## 企业开户（实名，绑卡）
- 请求方式：`Post` 
- 请求地址：`{URL}/Register`
- 是否需要证书：`否`
- 请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
   <tr>
        <td>login_account</td>
        <td>String</td>
        <td>是</td>
        <td>30</td>
        <td>登录账号</td>
        <td>709609096@163.com</td>
    </tr> 
    <tr>
        <td>company</td>
        <td>String</td>
        <td>是</td>
        <td>50</td>
        <td>公司名称</td>
        <td>北京长虹制品有限公司</td>
    </tr>
    <tr>
        <td>bank_type</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>银行类型</td>
        <td>0=对私，1=对公</td>
    </tr>
    <tr>
        <td>province_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户省份名称</td>
        <td>北京直辖市</td>
    </tr>
    <tr>
        <td>city_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户城市名称</td>
        <td>丰台区</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>string</td>
        <td>是</td>
        <td>不限</td>
        <td>3DES加密信息(具体加密参数信息 请查看下方“encrypt_data参数表”)</td>
        <td>F765BBA56235......6E0FF8B3105</td>
    </tr>
    <tr>
        <td>cert_type</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>证件类型 默认1=工商营业执照</td>
        <td>1</td>
    </tr>
    <tr>
        <td>cert_number</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>证件号</td>
        <td>91110108678221210D</td>
    </tr>
    <tr>
        <td>cert_pic</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>证件照</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>legal_person</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>法定代表人</td>
        <td>艾笑笑</td>
    </tr>
    <tr>
        <td>legal_idnumber</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>法人身份证号</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>legal_idnum_pic</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>法人身份证正面照片</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>legal_idnum_pic_2</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>法人身份证反面照片</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>contact_name</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>业务联系人姓名</td>
        <td>程笑笑</td>
    </tr>
    <tr>
        <td>contact_idnumber</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>业务联系人身份证号</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>contact_mobile</td>
        <td>string</td>
        <td>是</td>
        <td>11</td>
        <td>业务联系人手机号</td>
        <td>18000001111</td>
    </tr>
</table>
- 加密信息示例：user_bank_card_no={user_bank_card_no}&bank_name={bank_name}&bank_code={bank_code}&user_id_card={user_id_card}&user_mobile={user_mobile}&bank_branch_name={bank_branch_name}
拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输

- encrypt_data参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_bank_card_no</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行账号</td>
        <td>6227002845010113928</td>
    </tr> 
    <tr>
        <td>bank_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行名称</td>
        <td>建设银行</td>
    </tr>
    <tr>
        <td>bank_code</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行编码 </td>
        <td>CCB</td>
    </tr>
     <tr>
        <td>user_id_card</td>
        <td>string</td>
        <td>否</td>
        <td>20</td>
        <td>开户银行身份证号（对私银行类型时填写）</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>string</td>
        <td>否</td>
        <td>11</td>
        <td>银行预留手机号（对私银行类型时填写）</td>
        <td>18000001111</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>开户人名称</td>
        <td>黄笑笑</td>
    </tr>
    <tr>
        <td>bank_branch_name</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>开户支行名称</td>
        <td>北京市丰台区首经贸建设支行</td>
    </tr>
</table>
- [开户银行编码对照表](/wallet/bank.info.md)

- 响应参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>  
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>银行卡UID</td>
        <td>100001</td>
    </tr>
</table>


## 简单注册
- 请求方式：`Post` 
- 请求地址：`{URL}/SimpleReg`
- 是否需要证书：`否`
- 请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
   <tr>
        <td>login_account</td>
        <td>String</td>
        <td>是</td>
        <td>30</td>
        <td>登录账号</td>
        <td>709609096@163.com</td>
    </tr> 
    <tr>
        <td>company</td>
        <td>String</td>
        <td>是</td>
        <td>50</td>
        <td>公司名称</td>
        <td>北京长虹制品有限公司</td>
    </tr>
</table>
- 响应参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>
</table>

## 实名认证
- 请求方式：`Post` 
- 请求地址：`{URL}/Reality`
- 是否需要证书：`否`
- 请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>login_account</td>
        <td>String</td>
        <td>否</td>
        <td>30</td>
        <td>登录账号(二选一)</td>
        <td>709609096@163.com</td>
    </tr> 
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>否</td>
        <td>50</td>
        <td>用户UID(二选一)</td>
        <td>100210300798111</td>
    </tr>
    <tr>
        <td>cert_type</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>证件类型 默认1=工商营业执照</td>
        <td>1</td>
    </tr>
    <tr>
        <td>cert_number</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>证件号</td>
        <td>91110108678221210D</td>
    </tr>
    <tr>
        <td>cert_pic</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>证件照</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>legal_person</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>法定代表人</td>
        <td>艾笑笑</td>
    </tr>
    <tr>
        <td>legal_idnumber</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>法人身份证号</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>legal_idnum_pic</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>法人身份证正面照片</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>legal_idnum_pic_2</td>
        <td>string</td>
        <td>是</td>
        <td>1M以下图片</td>
        <td>法人身份证反面照片</td>
        <td>图片格式base64编码</td>
    </tr>
    <tr>
        <td>contact_name</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>业务联系人姓名</td>
        <td>程笑笑</td>
    </tr>
    <tr>
        <td>contact_idnumber</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>业务联系人身份证号</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>contact_mobile</td>
        <td>string</td>
        <td>是</td>
        <td>11</td>
        <td>业务联系人手机号</td>
        <td>18000001111</td>
    </tr>
</table>

- 响应参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>
</table>

## 绑定银行卡
- 请求方式：`Post` 
- 请求地址：`{URL}/BindCard`
- 是否需要证书：`否`
- 请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>login_account</td>
        <td>String</td>
        <td>否</td>
        <td>30</td>
        <td>登录账号(二选一)</td>
        <td>709609096@163.com</td>
    </tr> 
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>否</td>
        <td>50</td>
        <td>用户UID(二选一)</td>
        <td>100210300798111</td>
    </tr>
    <tr>
        <td>bank_type</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>银行类型</td>
        <td>0=对私，1=对公</td>
    </tr>
    <tr>
        <td>province_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户省份名称</td>
        <td>北京直辖市</td>
    </tr>
    <tr>
        <td>city_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户城市名称</td>
        <td>丰台区</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>string</td>
        <td>是</td>
        <td>不限</td>
        <td>3DES加密信息(具体加密参数信息 请查看下方“encrypt_data参数表”)</td>
        <td>F765BBA56235......6E0FF8B3105</td>
    </tr>
</table>
- 加密信息示例：user_bank_card_no={user_bank_card_no}&bank_name={bank_name}&bank_code={bank_code}&user_id_card={user_id_card}&user_mobile={user_mobile}&bank_branch_name={bank_branch_name}
拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输

- encrypt_data参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_bank_card_no</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行账号</td>
        <td>6227002845010113928</td>
    </tr> 
    <tr>
        <td>bank_name</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行名称</td>
        <td>建设银行</td>
    </tr>
    <tr>
        <td>bank_code</td>
        <td>string</td>
        <td>是</td>
        <td>20</td>
        <td>开户银行编码</td>
        <td>CCB</td>
    </tr>
     <tr>
        <td>user_id_card</td>
        <td>string</td>
        <td>否</td>
        <td>20</td>
        <td>开户银行身份证号（对私银行类型时填写）</td>
        <td>422700198012121011</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>string</td>
        <td>否</td>
        <td>11</td>
        <td>银行预留手机号（对私银行类型时填写）</td>
        <td>18000001111</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>string</td>
        <td>是</td>
        <td>16</td>
        <td>开户人名称</td>
        <td>黄笑笑</td>
    </tr>
    <tr>
        <td>bank_branch_name</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>开户支行名称</td>
        <td>北京市丰台区首经贸建设支行</td>
    </tr>
</table>
- [开户银行编码对照表](/wallet/bank.info.md)

- 响应参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>  
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>银行卡UID</td>
        <td>100001</td>
    </tr>
</table>

## 企业登录
- 请求地址：`{URL}/Login`
- 请求方式：`Post` 
- 是否需要证书：`否`
- 请求参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>login_account</td>
        <td>String</td>
        <td>是</td>
        <td>30</td>
        <td>登录账号</td>
        <td>709609096@163.com</td>
    </tr>   
</table>

- 响应参数
<table data-hy-role="doctbl">
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>http://************</td>
     </tr>
</table>