## 聚合分润

接口说明：分润请求接口

应用场景：微信支付订单通过此接口把商户结算资金分润给指定商户

- 分润请求接口

> 请求URL:`https://pay.heemoney.com/v1/GuaranteeAllot`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.pshard.one/heemoney.guarantee.allot`

- 业务参数

hy_bill_no、out_trade_no 两者二选其一
（商户分润单号）

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
    <td>24</td>
    <td>汇元单号|与 out_trade_no 二选一</td>
    <td>21235845103</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>商户订单号|与 hy_bill_no 二选一</td>
    <td>Hylsjdklj245</td>
</tr>
<tr>
    <td>allot_data</td>
    <td>String</td>
    <td>是</td>
    <td>200</td>
    <td>分润明细参数</td>
    <td>[{merch_uid:1211,allot_amt_fen:1000},{merch_uid:1213,allot_amt_fen:500}]</td>
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
    <td>channel_trade_no</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>通道订单号</td>
    <td>hy123456</td>
</tr>
<tr>
    <td>allot_amt_fen</td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>分润的总金额</td>
    <td>100</td>
</tr>
</table>

## 分润查询接口

接口说明：分润查询请求接口

应用场景：通过调用该接口查询分润状态。分润会有一定的处理周期。

> 请求URL:`https://pay.heemoney.com/v1/GuaranteeAllot`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.guarantee.allot.query`

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
    <td>24</td>
    <td>汇元单号|与 out_trade_no 二选一</td>
    <td>21235845103</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
    <td>否</td>
    <td>64</td>
    <td>商户订单号|与 hy_bill_no 二选一</td>
    <td>Hylsjdklj245</td>
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
    <td></td>
    <td>String</td>
    <td>是</td>
    <td>64</td>
    <td>分润状态</td>
    <td></td>
</tr>
</table>