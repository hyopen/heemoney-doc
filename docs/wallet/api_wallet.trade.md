## 公共信息
- 接口请求
  - 地址 URL：`https://demo.heemoney.com/YunBiz/Wallet/V1`
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
        <td>method</td>
        <td>String</td>
        <td>是</td>
        <td>100</td>
        <td>具体业务接口名称</td>
        <td>yunbiz.wallet.***</td>
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
        <td>api_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>API请求类型 0=API接口,1=嵌套H5</td>
        <td>0</td>
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
        <td>redirect_url</td>
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
        <td>成功</td>
        <td>返回状态码描述SUCCESS=成功,FAIL=失败,UNDEAL=处理中</td>
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
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>跳转URL,api_type 为1（嵌套H5）时,每个接口都返回。其它根据具体接口</td>
        <td>ok</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回,result_code为SUCCESS时返回
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
        <td>版本号,1.0</td>
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
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>http://www.demo.heemoney.com/Transfer/Index?token=454564654566</td>
     </tr>
</table>
    <tr>
        <th width="120">参数</th>
        <th width="70">类型</th>
        <th width="60">是否必填</th>
        <th width="80">最大长度</th>
        <th width="220">描述</th>
        <th width="153">示例值</th>
    </tr>
   <tr>
        <td>cust_id</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>渠道用户唯一标识</td>
        <td>1.0</td>
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

## 统一支付申请
- 接口请求
  - 地址：`{URL}/ApplyPay`
  - 请求方式：`Post`
  - 是否需要证书：`否`
  - 说明：`担保支付需要再次请求ConfirmPay支付确认接口,分润支付需要再次请求ApplyPayShare分润申请接口`

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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>pay_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,单位分</td>
        <td>1500</td> 
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>pay_type</td>
        <td>int</td>
        <td>否</td>
        <td></td>
        <td>请求支付类型｜0=即时支付,1=担保支付,2=担保分润支付</td>
        <td>1</td>
    </tr>
    <tr>
        <td>without_password</td>
        <td>int</td>
        <td>否</td>
        <td></td>
        <td>是否免密｜0=不免密,1=免密（免密只针对1000元以下的支付）</td>
        <td>0</td>
    </tr>
    <tr>
        <td>pay_method</td>
        <td>int</td>
        <td>否</td>
        <td></td>
        <td>支付方式｜0=账户余额,固定值可以不传</td>
        <td>0</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>
    <tr>
        <td>user_ip</td>
        <td>String</td>
        <td>否</td>
        <td>15</td>
        <td>用户ip</td>
        <td>202.181.38.148</td>
    </tr>
    <tr>
        <td>subject</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品标题</td>
        <td></td>
    </tr>
    <tr>
        <td>goods_tag</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品描述</td>
        <td></td>
    </tr> 
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>异步通知的地址</td>
        <td>http</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>同步返回的URL地址</td>
        <td>http</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>否</td>
        <td></td>
        <td>支付密码确认,返回跳转地址,（带token）</td>
        <td></td>
    </tr>
</table> 

## 分润支付申请（确认）
- 接口请求
  - 地址：`{URL}/ApplyPayShare`
  - 请求方式：`Post`
  - 是否需要证书：`否`
  - 说明：`分润支付,请求分润`

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
        <td>hy_bill_no</td>
        <td>int</td>
        <td>是</td>
        <td></td>
        <td>汇元单号</td>
        <td></td> 
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
     <tr>
        <td>out_share_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户分润订单号,同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>pay_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,请求分润总金额,单位：分</td>
        <td>1</td>
    </tr>  
    <tr>
        <td>share_info</td>
        <td>String</td>
        <td>是</td>
        <td>不限</td>
        <td>分润明细,接收分润的用户和金额,不分润则该项为指定收款人</td>
        <td>[{user_uid:1211,share_amt_fen:1000},{user_uid:1213,share_amt_fen:500}]</td>
    </tr>  
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>异步通知的地址</td>
        <td>http</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>同步返回的URL地址</td>
        <td>http</td>
    </tr>
</table>

-返回参数 <br>
`见公共返回参数`

## 担保支付确认
- 接口请求
  - 地址：`{URL}/ConfirmPay`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>否</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr> 
</table>

-返回参数 <br>
`见公共返回参数`


## 支付退款
- 接口请求
  - 地址：`{URL}/refund`
  - 请求方式：`Post`
  - 是否需要证书：`否`
  - 说明：`已经产生了结算单则不能退款`

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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
     <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>out_refund_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户退款请求订单号,同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>refund_reason</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>退款说明</td>
        <td></td>
    </tr>
    <tr>
        <td>refund_amt_fen</td>
        <td>int</td>
        <td>否</td>
        <td></td>
        <td>退款金额,单位分,默认为0全额退</td>
        <td></td>
    </tr>
     <tr>
        <td>notify_url</td>
        <td>int</td>
        <td>否</td>
        <td></td>
        <td>通知地址</td>
        <td></td>
    </tr>
</table>

- 业务响应参数 （以下字段在异步通知时返回）
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
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>out_refund_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>商户请求单号</td>
        <td></td>
    </tr>    
    <tr>
        <td>hy_refund_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的退款单号</td>
        <td></td>
    </tr>
</table> 

## 用户充值
- 接口请求
  - 请求地址：`{URL}/ApplyCharge`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>charge_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>充值金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>   
    </tr>
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>已绑定银行卡UID（银行卡支付需要传入）</td>
        <td>1231231231</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>异步通知地址</td>
        <td>www.baidu.com</td>
    </tr>  
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>完成返回商户URL地址</td>
        <td>www.baidu.com</td>
    </tr>  
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>charge_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td></td>
        <td>消费金额,单位：分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>www.demo.heemoney.com/Charge/Confirm?token=454564654566</td>
     </tr>
</table>

## 用户提现
- 接口请求
  - 地址：`{URL}/ApplyFetch`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>fetch_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>提现金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>  
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>已绑定银行卡UID（银行卡支付需要传入）</td>
        <td>132132132132</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>异步通知地址</td>
        <td>www.baidu.com</td>
    </tr>    
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>是</td>
        <td>256</td>
        <td>支付完成返回商户URL地址</td>
        <td>www.baidu.com</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td>F开头的单号</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>fetch_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td></td>
        <td>消费金额,单位：分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>www.demo.heemoney.com/Charge/Confirm?token=454564654566</td>
     </tr>
</table>

## 用户转账
- 接口请求
  - 地址：`{URL}/Transfer`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>transfer_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>转账类型 0=到余额</td>
        <td>0</td>
    </tr> 
    <tr>
        <td>from_user_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>出款用户UID|默认当前账户</td>
        <td>100001</td>
    </tr>    
    <tr>
        <td>to_user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>收款用户UID</td>
        <td>100002</td>
    </tr>
    <tr>
        <td>transfer_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>to_bank_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>不传到默认卡,传则到指定卡</td>
        <td>1231213212</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>    
    <tr>
        <td>transfer_note</td>
        <td>int</td>
        <td>是</td>
        <td>255</td>
        <td>转账备注</td>
        <td>255</td>
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

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td>F开头的单号</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>from_user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>to_user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>transfer_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td></td>
        <td>消费金额,单位：分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>redirect_url</td>
        <td>String</td>
        <td>是</td>
        <td>500</td>
        <td>返回跳转地址（携带token）</td>
        <td>http://www.demo.heemoney.com/Transfer/Confirm?token=454564654566</td>
     </tr>
</table>


## 交易查询
- 接口请求
  - 地址：`{URL}/TradeQuery`
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
        <td>100001</td>
    </tr>
    <tr>
        <td>trade_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易类型|1=转账,2=充值,4=提现,5=支付,7=退款,8=分润</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>page_num</td>
        <td>String</td>
        <td>否</td>
        <td>1</td>
        <td>起始页</td>
        <td>默认第一页</td>
    </tr>
    <tr>
        <td>page_size</td>
        <td>String</td>
        <td>否</td>
        <td>1</td>
        <td>页大小</td>
        <td>默认每页十条数据</td>
    </tr>
    <tr>
        <td>begin_time</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>开始时间</td>
        <td>20191025101010</td>
    </tr>
    <tr>
        <td>end_time</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>截止时间</td>
        <td>20191025101010</td>
    </tr>
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>否</td>
        <td>1</td>
        <td>交易状态|0=处理中,1=成功,-1=失败,默认查询全部</td>
        <td>1</td>
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
        <td>100001</td>
    </tr>
    <tr>
        <td>total_size</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>总记录数</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>trade_list</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td></td>
        <td>【列表对象开始】</td>
    </tr>
    <tr>
        <td>trade_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易类型</td>
        <td>交易类型|1=转账,2=充值,4=提现,5=支付,7=退款,8=分润</td>
    </tr>
    <tr>
        <td>trade_date</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>交易时间</td>
        <td>20191120100000</td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,单位分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|0=处理中,1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>bank_card_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>银行卡记录标识</td>
        <td>******</td>
    </tr>
    <tr>
        <td>trade_list</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td></td>
        <td>【列表对象结束】</td>
    </tr>
</table>

## 订单详情
- 接口请求
  - 地址：`{URL}/BillInfo`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>否</td>
        <td>64</td>
        <td>汇元单号|查询速度更快、更准确,建议优先使用</td>
        <td></td>
    </tr>    
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>    
    <tr>
        <tr>
        <td>trade_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易类型|1=转账,2=充值,4=提现,5=支付,7=退款,8=分润</td>
        <td>100001</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>bill_info</td>
        <td>String</td>
        <td>是</td>
        <td></td>
        <td>订单详情</td>
        <td></td>
    </tr>
</table> 

返回示例：`{`
    `"return_code":"SUCCESS",`
    `"return_msg":"提交成功",`
    `"result_code":"SUCCESS",`
    `"bill_info":"{"bill_status":"Success","bill_status_name":"成功","share_info":"{\"user_uid\":\"100000000011128\",\"share_amt_fen\":\"10\",\"status\":\"Undeal\",\"status_name\":\"处理中\"}"}",`
    `"sign":"F573C5C5E711159BF974D081F0B7B58B"`
`}`

<!-- 

## 骏卡购卡
- 接口请求
  - 地址：`{URL}/BuyJunKa`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
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
        <td>user_name</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>姓名</td>
        <td>张三</td>
    </tr>
    <tr>
        <td>user_mobile</td>
        <td>String</td>
        <td>否</td>
        <td>11</td>
        <td>手机号</td>
        <td>13066668888</td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>购买卡金额,单位：分</td>
        <td>1</td>
    </tr>
    <tr>
        <td>user_pay_type</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>用户支付类型|1=银行卡,2=微信,3=支付宝</td>
        <td>2</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>    
    <tr>
        <td>user_ip</td>
        <td>String</td>
        <td>否</td>
        <td>15</td>
        <td>用户ip</td>
        <td>202.181.38.148</td>
    </tr>
    <tr>
        <td>subject</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品标题</td>
        <td></td>
    </tr>
    <tr>
        <td>goods_tag</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品描述</td>
        <td></td>
    </tr> 
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>异步通知的地址</td>
        <td>http://www.baidu.com</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>同步返回的URL地址</td>
        <td>http://www.baidu.com</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>购买卡金额,单位：分</td>
        <td>1</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,卡号密码数据,如骏卡一卡通最多支持3张,3DES解密后格式为：卡号1,密码1,面值1,有效期1|卡号2,密码2,面值2,有效期2|卡号3,密码3,面值3,有效期3） </td>
        <td></td>
    </tr>
     <tr>
        <td>card_num</td>
        <td>String</td>
        <td>是</td>
        <td>1000</td>
        <td>卡张数</td>
        <td>1</td>
    </tr>
</table> 

## 骏卡消费
- 接口请求
  - 地址：`{URL}/UseJunKa`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
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
        <td>trade_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>消费卡金额,单位：分</td>
        <td>100</td>
    </tr>
    <tr>
        <td>from_type</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>来源类型|0=PC,1=H5,2=SDK</td>
        <td>1</td>
    </tr>    
    <tr>
        <td>user_ip</td>
        <td>String</td>
        <td>否</td>
        <td>15</td>
        <td>用户ip</td>
        <td>202.181.38.148</td>
    </tr>
    <tr>
        <td>subject</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品标题</td>
        <td>subject</td>
    </tr>
    <tr>
        <td>goods_tag</td>
        <td>String</td>
        <td>否</td>
        <td>125</td>
        <td>商品描述</td>
        <td>test</td>
    </tr> 
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>否</td>
        <td>200</td>
        <td>不传默认从账户找,卡号数据,3DES解密后格式为：卡号1,密码1,金额1|卡号2,密码2,金额2|卡号3,密码3,金额3）</td>
        <td></td>
    </tr>
    <tr>
        <td>notify_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>异步通知的地址</td>
        <td>http://www.baidu.com</td>
    </tr>
    <tr>
        <td>return_url</td>
        <td>String</td>
        <td>否</td>
        <td>255</td>
        <td>同步返回的URL地址</td>
        <td>http://www.baidu.com</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
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
        <td>trade_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>消费卡金额,单位：分</td>
        <td>1</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据</td>
        <td>3DES解密后格式为：cardno1,cardpws1,par1|cardno2,cardpws2,par2</td>
    </tr>
    <tr>
        <td>card_use_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡使用明细信息</td>
        <td>格式为：卡号1=金额1,卡号2=金额2,卡号3=金额3</td>
    </tr>    
</table> 

## 骏卡购买查询
- 接口请求
  - 地址：`{URL}/QueryBuyJunKa`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>汇元单号|查询速度更快、更准确,建议优先使用</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
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
        <td>trade_date</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>交易时间</td>
        <td>20191120100000</td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,单位分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|0=处理中,1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,3DES解密后格式为：卡号1,密码1,金额1|卡号2,密码2,金额2|卡号3,密码3,金额3） </td>
        <td></td>
    </tr>
     <tr>
        <td>card_num</td>
        <td>String</td>
        <td>是</td>
        <td>1000</td>
        <td>卡张数</td>
        <td>1</td>
    </tr>
</table>

## 骏卡消费查询
- 接口请求
  - 地址：`{URL}/QueryUseJunKa`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号|查询速度更快、更准确,建议优先使用</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,同一个商户号下唯一</td>
        <td>12345678</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>汇元单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号</td>
        <td>12345678</td>
    </tr>
    <tr>
        <td>user_uid</td>
        <td>String</td>
        <td>是</td>
        <td>16</td>
        <td>用户uid</td>
        <td>100001</td>
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
        <td>trade_date</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>交易时间</td>
        <td>20191120100000</td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>交易金额,单位分</td>
        <td>500</td>
    </tr>    
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|0=处理中,1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,3DES解密后格式为：卡号1,密码1,金额1|卡号2,密码2,金额2|卡号3,密码3,金额3）</td>
        <td></td>
    </tr>
    <tr>
        <td>card_use_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡使用明细信息</td>
        <td>格式为：卡号1=金额1,卡号2=金额2,卡号3=金额3</td>
    </tr>
</table>

## 用户卡查询
- 接口请求
  - 地址：`{URL}/QueryUserJunKa`
  - 请求方式：`Post`
  - 是否需要证书：`否`

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
        <td>user_uid</td>
        <td>String</td>
        <td>否</td>
        <td>16</td>
        <td>用户uid|与 user_code 二选一</td>
        <td>100001</td>
    </tr>
    <tr>
        <td>user_code</td>
        <td>String</td>
        <td>否</td>
        <td>20</td>
        <td>渠道用户唯一标识|与 user_uid 二选一 </td>
        <td>10001</td>
    </tr>
</table>

- 业务响应参数,以下字段在return_code为SUCCESS时返回
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
        <td>100001</td>
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
        <td>ucard_amt_fen</td>
        <td>String</td>
        <td>是</td>
        <td>5000000</td>
        <td>骏卡金额,单位分</td>
        <td>100</td>
    </tr>
    <tr>
        <td>card_num</td>
        <td>String</td>
        <td>是</td>
        <td>1000</td>
        <td>可用卡张数</td>
        <td>1</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,卡号密码数据,如骏卡一卡通最多支持3张,3DES解密后格式为：卡号1,密码1,金额1|卡号2,密码2,金额2|卡号3,密码3,金额3） </td>
        <td></td>
    </tr>
    <tr>
        <td>card_use_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡使用明细信息</td>
        <td>已经使用完的卡数据:卡号1|卡号2|卡号3</td>
    </tr>
</table>
-->