## 公共信息
- 接口请求
  - 联调地址 URL：`https://demo.heemoney.com/api`
  - 正式地址 URL：`https://api.heemoney.com`
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
        <td>heemoney.coupon.couponlist</td>
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
        <td>MD5</td>
    </tr>
    <tr>
        <td>timestamp</td>
        <td>String</td>
        <td>是</td>
        <td>14</td>
        <td>请求时间(yyyyMMddHHmmss)</td>
        <td>20200701010101</td>
    </tr>
    <tr>
        <td>isv_app_id</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>服务商应用ID</td>
        <td>A2sdfjkl</td>
    </tr>
    <tr>
        <td>isv_mch_uid</td>
        <td>String</td>
        <td>是</td>
        <td>32</td>
        <td>服务商商户编号</td>
        <td>22255522</td>
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
- 注：当业务状态码result_code为SUCCESS时才返回业务响应参数


## 发放优惠券列表
- 请求地址：`https://api.heemoney.com/v1/CouponList`
- 请求方式：`Post` 
- 是否需要证书：`否`
- method：heemoney.coupon.couponlist
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
        <td>coupon_type</td>
        <td>int</td>
        <td>是</td>
        <td>3</td>
        <td>优惠券类别</td>
        <td>0(0=全部,1=食品,2=手机,3=服饰,4=家电,5=生鲜,...)</td>
    </tr>
</table>

- 业务响应参数
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
        <td>coupon_data</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>用户优惠券信息（json数组）具体见下方优惠券信息参数说明</td>
        <td>{"coupon_data":[{"merch_id":"4706******500","coupon_name":"电子产品消费券",...},{...}]}</td>
    </tr>
</table>

- 优惠券信息参数说明
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>merch_name</td>
        <td>string</td>
        <td>是</td>
        <td>30</td>
        <td>商户名称</td>
        <td>北京***生活超市</td>
    </tr>
    <tr>
        <td>activity_uid</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>活动编号</td>
        <td>1**11</td>
    </tr>
    <tr>
        <td>coupon_id</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>优惠券编号</td>
        <td>1**01</td>
    </tr>
    <tr>
        <td>coupon_kind</td>
        <td>int</td>
        <td>是</td>
        <td>2</td>
        <td>优惠券券种</td>
        <td>1=代金券,2=打折券,3=兑换券,4=时长券</td>
    </tr>
    <tr>
        <td>coupon_type</td>
        <td>int</td>
        <td>是</td>
        <td>3</td>
        <td>优惠券类别</td>
        <td>0(0=全部,1=食品,2=手机,3=服饰,4=家电,5=生鲜,...)</td>
    </tr>
    <tr>
        <td>coupon_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>优惠券名称</td>
        <td>电子产品消费券</td>
    </tr>  
    <tr>
        <td>coupon_amt</td>
        <td>String</td>
        <td>是</td>
        <td>10000</td>
        <td>优惠券面值</td>
        <td>66（单位：元）</td>
    </tr>
    <tr>
        <td>coupon_num</td>
        <td>int</td>
        <td>是</td>
        <td>1000</td>
        <td>优惠券发行总数</td>
        <td>100</td>
    </tr>
    <tr>
        <td>can_use_num</td>
        <td>int</td>
        <td>否</td>
        <td>1000</td>
        <td>优惠券剩余数量</td>
        <td>100</td>
    </tr>
    <tr>
        <td>pay_upper_limit_amt</td>
        <td>String</td>
        <td>是</td>
        <td>10000</td>
        <td>订单门槛金额(达到门槛消费金额才可使用该券)</td>
        <td>66（单位：元）</td>
    </tr>
    <tr>
        <td>limit_gain_num</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>限制领取次数</td>
        <td>0（0=不限制，1=限制领取1次）</td>
    </tr>
    <tr>
        <td>begin_time</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>开始有效期</td>
        <td>2020-07-01</td>
    </tr>
    <tr>
        <td>end_time</td>
        <td>String</td>
        <td>是</td>
        <td>10</td>
        <td>结束有效期</td>
        <td>2020-07-01</td>
    </tr>
    <tr>
        <td>coupon_statust</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>优惠券状态/td>
        <td>1（0=不可用，1=可用）</td>
    </tr>
</table>

## 领取优惠券
- 请求地址：`https://api.heemoney.com/v1/GetCoupon`
- 请求方式：`Post` 
- 是否需要证书：`否`
- method：heemoney.coupon.getcoupon
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>activity_uid</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>活动编号</td>
        <td>1**11</td>
    </tr>
    <tr>
        <td>coupon_id</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>优惠券编号</td>
        <td>1**01</td>
    </tr>
    <tr>
        <td>third_app_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>应用编号</td>
        <td>wx4********51beac</td>
    </tr>
    <tr>
        <td>third_open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
        <tr>
        <td>third_union_id</td>
        <td>string</td>
        <td>否</td>
        <td>50</td>
        <td>群组用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
</table>

- 业务响应参数
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
        <td>third_app_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>应用编号</td>
        <td>wx4********51beac</td>
    </tr>
    <tr>
        <td>third_open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
    <tr>
        <td>coupon_no</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>优惠券券号</td>
        <td>12545*******01</td>
    </tr>
    <tr>
        <td>coupon_status</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>领取优惠券状态</td>
        <td>1（0=失败，1=成功）</td>
    </tr>
</table>

## 用户优惠券列表
- 请求地址：`https://api.heemoney.com/v1/UserCouponList`
- 请求方式：`Post` 
- 是否需要证书：`否`
- method：heemoney.coupon.usercouponlist
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
        <td>third_app_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>应用编号</td>
        <td>wx4********51beac</td>
    </tr>
    <tr>
        <td>third_open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
    <tr>
        <td>coupon_status</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>优惠券状态</td>
        <td>0（0=全部，1=可使用，2=已使用，3=已过期）</td>
    </tr>
</table>

- 业务响应参数
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
        <td>app_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>应用编号</td>
        <td>wx4********51beac</td>
    </tr>
    <tr>
        <td>open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
    <tr>
        <td>coupon_data</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>用户优惠券信息（json数组）具体见下方优惠券信息参数说明</td>
        <td>{...，"coupon_data":[{"coupon_no":"1***5333","coupon_name":"电子产品消费券",...},{...}]}</td>
    </tr>
</table>

- 优惠券信息参数说明
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>activity_uid</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>活动编号</td>
        <td>1**11</td>
    </tr>
    <tr>
        <td>coupon_no</td>
        <td>int</td>
        <td>是</td>
        <td>20</td>
        <td>优惠券券号</td>
        <td>1***5333</td>
    </tr>
    <tr>
        <td>coupon_name</td>
        <td>String</td>
        <td>是</td>
        <td>20</td>
        <td>优惠券名称</td>
        <td>电子产品消费券</td>
    </tr>  
    <tr>
        <td>coupon_amt</td>
        <td>String</td>
        <td>是</td>
        <td>10000</td>
        <td>优惠券面值</td>
        <td>66（单位：元）</td>
    </tr>
    <tr>
        <td>coupon_status</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>优惠券状态</td>
        <td>1（1=可使用，2=已使用，3=已过期）</td>
    </tr>
</table>

## 核销优惠券
- 请求地址：`https://api.heemoney.com/v1/CancelCoupon`
- 请求方式：`Post` 
- 是否需要证书：`否`
- method：heemoney.coupon.cancelcoupon
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>coupon_no</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>优惠券券号</td>
        <td>12545*******01</td>
    </tr>
    <tr>
        <td>third_open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
        <tr>
        <td>bill_no</td>
        <td>string</td>
        <td>否</td>
        <td>50</td>
        <td>支付单号</td>
        <td>134**************4234</td>
    </tr>
</table>

- 业务响应参数
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>third_open_id</td>
        <td>string</td>
        <td>是</td>
        <td>50</td>
        <td>用户唯一标识</td>
        <td>oiz2w**********MJI</td>
    </tr>
    <tr>
        <td>coupon_no</td>
        <td>int</td>
        <td>是</td>
        <td>6</td>
        <td>优惠券券号</td>
        <td>12545*******01</td>
    </tr>
    <tr>
        <td>coupon_status</td>
        <td>int</td>
        <td>是</td>
        <td>1</td>
        <td>优惠券核销状态</td>
        <td>1（0=失败,1=成功）</td>
    </tr>
</table>

## 服务商（代理商）直属商户列表
- 请求地址：`https://api.heemoney.com/v1/MerchList`
- 请求方式：`Post` 
- 是否需要证书：`否`
- method：heemoney.coupon.merchlist
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
</table>

- 业务响应参数
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
        <td>merch_uid</td>
        <td>long</td>
        <td>是</td>
        <td>15</td>
        <td>商户编号</td>
        <td>4706******500</td>
    </tr>
    <tr>
        <td>merch_name</td>
        <td>string</td>
        <td>是</td>
        <td>30</td>
        <td>商户名称</td>
        <td>北京***生活超市</td>
    </tr>
    <tr>
        <td>merch_account</td>
        <td>string</td>
        <td>否</td>
        <td>30</td>
        <td>商户账号</td>
        <td>ce*****i23</td>
    </tr>
    <tr>
        <td>merch_status</td>
        <td>int</td>
        <td>否</td>
        <td>1</td>
        <td>商户状态</td>
        <td>1（-1=无效，0=不可用，1=可用）</td>
    </tr>
</table>