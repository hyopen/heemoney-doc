## 公共信息
- 接口请求
  - 联调地址 URL：`https://demo.heemoney.com/YunBiz/Wallet/V1`
  - 正式地址 URL：`https://yunbiz.heepay.com/Wallet/V1`
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
        <td>0</td>
    </tr>
    <tr>
        <td>error_msg</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>错误返回的信息描述（return_code为FAIL返回）</td>
        <td>ok</td>
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
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>http://www.demo.heemoney.com/Transfer/Index?token=454564654566</td>
     </tr>
</table>


## 简单注册
- 请求方式：`Post` 
- 请求地址：`{URL}/SimpleRegister`
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
        <td>user_code</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>渠道用户唯一标识</td>
        <td>10001</td>
    </tr> 
    <tr>
        <td>user_nick_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户昵称</td>
        <td>张三</td>
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
        <td>100001300210091</td>
    </tr>  
</table>

## 实名注册
- 请求方式：`Post` 
- 请求地址：`{URL}/RealityRegister`
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
        <td>user_code</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>渠道用户唯一标识</td>
        <td>10001</td>
    </tr> 
    <tr>
        <td>user_nick_name</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>用户昵称</td>
        <td>张三</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数开始】</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>姓名</td>
        <td>张三</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>是</td>
        <td>11</td>
        <td>手机号</td>
        <td>13066668888</td>
    </tr>
    <tr>
        <td>user_id_card</td>
        <td>String</td>
        <td>是</td>
        <td>18</td>
        <td>身份证号码</td>
        <td>104547198012121234</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数结束】</td>
    </tr>
</table>
- 加密信息例子：user_name={user_name}&user_mobile={user_mobile}&user_id_card={user_id_card} 拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输
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
        <td>100001300210091</td>
    </tr>  
</table>

## 用户实名
- 请求地址：`{URL}/RealityVerify`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数开始】</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户姓名</td>
        <td>张三</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>是</td>
        <td>11</td>
        <td>用户手机号</td>
        <td>13066668888</td>
    </tr>
    <tr>
        <td>user_id_card</td>
        <td>String</td>
        <td>是</td>
        <td>18</td>
        <td>身份证号码</td>
        <td>104547198012121234</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数结束】</td>
    </tr>
</table>
- 加密信息例子：user_name={user_name}&user_mobile={user_mobile}&user_id_card={user_id_card} 拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输
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
        <td>100001300210091</td>
    </tr>  
</table>

## 用户绑卡
- 请求地址：`{URL}/ApplyBindCard`
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
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数开始】</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>String</td>
        <td>否</td>
        <td>50</td>
        <td>用户未实名认证时必填</td>
        <td>张三</td>
    </tr> 
    <tr>
        <td>user_id_card</td>
        <td>String</td>
        <td>否</td>
        <td>30</td>
        <td>用户未实名认证时必填</td>
        <td>张三</td>
    </tr>  
    <tr>
        <td>user_bank_card_no</td>
        <td>String</td>
        <td>是</td>
        <td>50</td>
        <td>银行卡号</td>
        <td>6227002845010113927</td>
    </tr> 
     <tr>
        <td>user_bank_mobile</td>
        <td>String</td>
        <td>是</td>
        <td>11</td>
        <td>银行预留手机号</td>
        <td>13300001111</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数结束】</td>
    </tr>
</table>
- 加密信息例子：user_name={user_name}&user_id_card={user_id_card}&user_bank_card_no={user_bank_card_no}&user_bank_mobile={user_bank_mobile} 拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输
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
        <td>token</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>绑卡申请token</td>
        <td>http://***</td>
    </tr>
</table>

## 绑卡确认
- 请求地址：`{URL}/BindCardConfirm`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>verify_code</td>
        <td>String</td>
        <td>是</td>
        <td>6</td>
        <td>短信验证码</td>
        <td>123456</td>
    </tr>
    <tr>
        <td>token</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>绑卡申请返回的token</td>
        <td>http://***</td>
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
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户绑卡记录标识</td>
        <td>100080800202027</td>
    </tr>
</table>

## 用户信息
- 请求地址：`{URL}/GetUserAccountInfo`
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
        <td>user_code</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>渠道用户唯一标识,两个必须填写一个</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>用户uid,两个必须填写一个</td>
        <td>100001300210091</td>
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
        <td>100002</td>
    </tr>
    <tr>
        <td>user_total_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>账户余额，单位分</td>
        <td>100</td>
    </tr>
    <tr>
        <td>reality_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>实名状态|0未认证，1已认证</td>
        <td>0</td>
    </tr>
    <tr>
        <td>bind_card_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>是否绑定银行卡|0未绑定，1已绑定</td>
        <td>0</td>
    </tr>
    <tr>
        <td>user_real_name</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>用户姓名</td>
        <td>张三</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>用户手机号</td>
        <td>13011112222</td>
    </tr>
    <tr>
        <td>user_id_card</td>
        <td>String</td>
        <td>否</td>
        <td>18</td>
        <td>用户身份证号</td>
        <td>104547198012121234</td>
    </tr>
</table>

## 设置支付密码
- 请求方式：`Post` 
- 请求地址：`{URL}/SetTradePwd`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>商户返回地址</td>
        <td>https://***</td>
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
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>设置密码跳转地址</td>
        <td>https://****?token=123456</td>
    </tr>
</table>

## 修改支付密码
- 请求方式：`Post` 
- 请求地址：`{URL}/UpdateTradePwd`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>用户唯一标识</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>商户返回地址</td>
        <td>https://***</td>
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
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>设置密码跳转地址</td>
        <td>https://****?token=123456</td>
    </tr>
</table>

## 重置支付密码
- 请求方式：`Post` 
- 请求地址：`{URL}/ResetTradePwd`
- 是否需要证书：`否`
- 请求参数
- 备注：短信验证码发往用户实名手机号，请先实名后调用
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
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>商户返回地址</td>
        <td>https://***</td>
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
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>重置密码跳转地址</td>
        <td>https://****?token=123456</td>
    </tr>
</table>

<!-- ## 发送短信
- 请求方式：`Post` 
- 请求地址：`{URL}/SendSms`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>为空时将短信验证码发送至注册手机号</td>
        <td>13011112222</td>
    </tr>    
    <tr>
        <td>type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>0充值，1提现</td>
        <td>0</td>
    </tr>
</table>
- 响应参数
  - 见公共响应参数 -->

## 用户绑卡列表
- 请求方式：`Post` 
- 请求地址：`{URL}/GetUserBindCardList`
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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001300210091</td>
    </tr>
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>用户绑卡记录标识，不传获取全部</td>
        <td>********</td>
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
        <td>total_size</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>绑定卡总记录数</td>
        <td>1</td>
    </tr>
    <tr>
        <td>bank_card_list</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【绑卡集合开始】</td>
    </tr>
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>绑卡记录UID</td>
        <td>1</td>
    </tr>
    <tr>
        <td>bank_card_no</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>银行卡号</td>
        <td>6227002845010113927</td>
    </tr>
    <tr>
        <td>bank_card_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>银行名称</td>
        <td>建设银行</td>
    </tr>
    <tr>
        <td>bank_card_code</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>银行编号</td>
        <td>15</td>
    </tr>
    <tr>
        <td>bank_card_type</td>
        <td>String</td>
        <td>是</td>
        <td>2</td>
        <td>卡类型|00=银行卡,01=存折,02=信用卡</td>
        <td>15</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>否</td>
        <td>11</td>
        <td>用户手机号</td>
        <td>15</td>
    </tr>    
    <tr>
        <td>bank_card_list</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【绑卡集合结束】</td>
    </tr>
</table>
 - 返回json例子：{bank_card_list:[{bank_card_uid:绑卡记录UID,bank_card_no:卡号,bank_card_name:银行名称,bank_card_code:银行编号,bank_card_type:卡类型,user_mobile:手机号}]}

## 银行列表
- 请求方式：`Post` 
- 请求地址：`{URL}/GetBankList`
- 是否需要证书：`否`
- 请求参数
  - 公共请求参数

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
        <td>bank_list</td>
        <td>String</td>
        <td>是</td>
        <td>100</td>
        <td></td>
        <td>【银行集合开始】</td>
    </tr>
    <tr>
        <td>bank_no</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>银行编码</td>
        <td>001</td>
    </tr>
    <tr>
        <td>bank_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>银行名称</td>
        <td>建设银行</td>
    </tr>
    <tr>
        <td>bank_list</td>
        <td>String</td>
        <td>是</td>
        <td>100</td>
        <td></td>
        <td>【银行集合结束】</td>
    </tr>
</table>
 - 返回json例子：{bank_list:[{"bank_no":"001","bank_name":"中国人民银行"},{"bank_no":"003","bank_name":"003"},{"bank_no":"100","bank_name":"we"},{"bank_no":"102","bank_name":"中国工商银行"}]}

 ## 用户激活申请
- 请求地址：`{URL}/ApplyActive`
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
        <td>user_code</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>渠道用户唯一标识</td>
        <td>10001</td>
    </tr> 
    <tr>
        <td>user_nick_name</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>用户昵称</td>
        <td>张三</td>
    </tr> 
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数开始】</td>
    </tr>
    <tr>
        <td>user_name</td>
        <td>String</td>
        <td>否</td>
        <td>50</td>
        <td>用户姓名</td>
        <td>张三</td>
    </tr>    
     <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>是</td>
        <td>11</td>
        <td>银行预留手机号</td>
        <td>13300001111</td>
    </tr>
    <tr>
        <td>encrypt_data</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td></td>
        <td>【加密信息参数结束】</td>
    </tr>
</table>
- 加密信息例子：user_name={user_name}&user_mobile={user_mobile} 拼接字符串进行3DES加密后放入业务参数 encrypt_data 中进行传输
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
        <td>token</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>激活申请token</td>
        <td>http://***</td>
    </tr>
</table>