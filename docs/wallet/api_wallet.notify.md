## 支付通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>    
    <tr>
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>pay_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>支付金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>trade_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>

## 充值通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
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
        <td>fee_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>手续费,单位：分</td>
        <td>50</td>
    </tr>
    <tr>
        <td>real_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>实际充值金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>

## 提现通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
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
        <td>fee_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>手续费,单位：分</td>
        <td>50</td>
    </tr>
    <tr>
        <td>real_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>实际提现金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>

## 转账通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
    </tr>
    <tr>
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
    </tr>
    <tr>
        <td>trade_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>转账金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>fee_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>手续费,单位：分</td>
        <td>50</td>
    </tr>
    <tr>
        <td>real_amt_fen</td>
        <td>int</td>
        <td>是</td>
        <td>5000000</td>
        <td>实际转账金额,单位：分</td>
        <td>500</td>
    </tr>
    <tr>
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>

<!--  
## 骏卡购买通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
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
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,卡号密码数据,如骏卡一卡通最多支持3张,格式为：卡号1,密码1,面值1,有效期1|卡号2,密码2,面值2,有效期2|卡号3,密码3,面值3,有效期3） </td>
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
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>

## 骏卡消耗通知
- 接口请求
  - 地址：`提交请求时的异步通知地址`
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
        <td>version</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>接口请求版本</td>
        <td>1.0</td>
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
        <td>owner_uid</td>
        <td>String</td>
        <td>是</td>
        <td>13</td>
        <td>所有者uid(对接商户唯一标识)</td>
        <td>1002501966169</td>
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
        <td>hy_bill_no</td>
        <td>String</td>
        <td>是</td>
        <td>24</td>
        <td>生成的消费单号</td>
        <td></td>
    </tr>
    <tr>
        <td>out_trade_no</td>
        <td>String</td>
        <td>是</td>
        <td>64</td>
        <td>商户订单号,要求64个字符内、且在同一个商户号下唯一</td>
        <td></td>
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
        <td>bill_status</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>交易状态|1=成功,-1=失败</td>
        <td>1</td>
    </tr>
    <tr>
        <td>time_end</td>
        <td>String</td>
        <td>是</td>
        <td>1</td>
        <td>订单处理时间</td>
        <td>20200214161720</td>
    </tr>
    <tr>
        <td>card_data</td>
        <td>String</td>
        <td>是</td>
        <td>200</td>
        <td>卡号密码数据,卡号密码数据,如骏卡一卡通最多支持3张,格式为：卡号1,密码1,面值1,有效期1|卡号2,密码2,面值2,有效期2|卡号3,密码3,面值3,有效期3） </td>
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
    <tr>
        <td>sign</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>数据签名</td>
        <td>CA63B4F88B5634015FDDBDD7F42B4E8B</td>
    </tr>
</table>
-->