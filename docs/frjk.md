## 公共接口参数
> 请求URL:`https://pay.heemoney.com/v1/GuaranteeAllot`

> 请求方式:`POST`   

> 是否需要证书：`否`

>说明：接口请求和响应的公共参数，method 参数的值详情见具体接口标记

>例如：请求分润 method：heemoney.guaranteeallot.submit

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
    <td>heemoney.guaranteeallot.submit</td>
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
    <td>hyp180417100250000003720CF8776AA</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>商户统一编号</td>
    <td>1002501974599</td>
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
    <td>是</td>
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

> 公共响应参数

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

> 以下字段在return_code为SUCCESS时返回

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

>以下字段在return_code为SUCCESS时，result_code为FAIL时返回

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

## 聚合分润

应用场景：微信支付订单通过此接口把商户结算资金分润给指定商户

- 分润请求接口

> method：`heemoney.guaranteeallot.submit`

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
    <td>2016051718082840300</td>
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
    <td>[{\"login_account\":\"B\",\"allot_amt_fen\":\"100\"}，{\"login_account\":\"C\",\"allot_amt_fen\":\"200\"}]</td>
</tr>
</table>

**allot_data 说明**:
```Text
"allot_data":"[{\"login_account\":\"B\",\"allot_amt_fen\":\"100\"}，{\"login_account\":\"C\",\"allot_amt_fen\":\"200\"}]"

整体是一个Json 素组，对应的多条分润明细
login_account：被分润的登录账号
allot_amt_fen：被分润的金额|单位分

支付商户A收单了 100块。调用分润接口  分给B商户 1 块 和C商户  2块。
剩下的97结算给A商户

分润明细最多只支持4条。
```

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
    <td>2016051718082840300</td>
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

应用场景：通过调用该接口查询分润状态。分润会有一定的处理周期。

> method：`heemoney.guaranteeallot.submit.query`

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
    <td>2016051718082840300</td>
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
    <td>2016051718082840300</td>
</tr>
<tr>
    <td>allot_data</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td>分润详情</td>
    <td></td>
</tr>
</table>

allot_data 例子：
```JSON
{
    "remain_amt_fen": 0,
    "allot_amt_fen": 2,
    "allot_list": [
        {
            "to_login_account": "test1",
            "to_amt_fen": 1,
            "settle_status": "Settling",
            "settle_time": "2016-01-06 12:00:00:123",
            "create_time": "2016-01-05 12:00:00:123"
        },
        {
            "to_login_account": "test2",
            "to_amt_fen": 1,
            "settle_status": "Settling",
            "settle_time": "2016-01-07 12:00:00:123",
            "create_time": "2016-01-06 12:00:00:123"
        }
    ]
}
```

**allot_data 说明**:
```Text
remain_amt_fen:该支付单未分润金额
allot_amt_fen:该支付单提交的分润总金额
allot_list：分润明细数据，属性含义如下：
    to_login_account:收款人登录账号
    to_amt_fen:收款金额。支持小数点后4位
    settle_status:结算状态。Settling-未开始结算,SettleFinish-结算完成，收款人已收到款
    settle_time:分润处理时间，如果没处理就等于创建时间。格式：yyyy-MM-dd HH:mm:ss
    create_time:分润创建时间。格式：yyyy-MM-dd HH:mm:ss
```

## 可分润余额查询

应用场景：通过调用该接口查询分润状态。分润会有一定的处理周期。

> method：`heemoney.guaranteeallot.query.remain`

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
    <td>2016051718082840300</td>
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
    <td>2016051718082840300</td>
</tr>
<tr>
    <td>remain_amt_fen</td>
    <td>String</td>
    <td>是</td>
    <td>5000000</td>
    <td>该笔支付单可分润余额</td>
    <td>100</td>
</tr>
</table>

## 分润未完成查询

应用场景：通过调用该接口查询 支付单据包括**未开始分润单据**及**分润提交未完成单据**。

> method：`heemoney.guaranteeallot.query.not.allot`

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
    <td>begin_time</td>
    <td>String</td>
    <td>是</td>
    <td>8</td>
    <td>开始时间</td>
    <td>20200308</td>
    </tr>
<tr>
    <td>end_time</td>
    <td>String</td>
    <td>是</td>
    <td>8</td>
    <td>截止时间</td>
    <td>20200310</td>
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
    <td>汇元单号</td>
    <td>2016051718082840300</td>
</tr>
<tr>
    <td>allot_data</td>
    <td>String</td>
    <td>是</td>
    <td>500</td>
    <td>待分润信息</td>
    <td></td>
</tr>
</table>

请求参数：
```JSON
allot_data 例子：
{
    "start_date": "2016-05-18",
    "end_date": "2016-05-18",
    "allot_list": [
        {
            "hy_bill_no": "2016051718082840300",
            "channel_trade_no": "H1605181247957A0",            
            "real_amt_fen": "5",
            "settle_amt_fen": "2",
            "had_allot_amt_fen": "1",
            "remain_amt_fen": "3",
            "success_time": "2016-05-18 10:39:39"
        },
        {
            "hy_bill_no": "2016051814061960200",
            "channel_trade_no": "H1605181250450A0",            
            "real_amt_fen": "5",
            "settle_amt_fen": "2",
            "had_allot_amt_fen": "1",
            "remain_amt_fen": "3",
            "success_time": "2016-05-18 14:09:46"
        }
    ]
}
```

**例子说明：**
```Text
merch_uid:商户UID
start_date:查询支付成功起始时间,格式yyyy-MM-dd
end_date:查询支付成功起始时间,格式yyyy-MM-dd
allot_list:支付单据列表,[]表示没单据。
   hy_bill_no:商户单据号
   channel_trade_no:汇付宝单据号,H开头。
   real_amt_fen:实际支付金额,保留小数点后4位。
​   settle_amt_fen:结算金额（即该支付单据能分润总金额）,real_amt- settle_amt=汇付宝手续费。
​   had_allot_amt_fen:该支付单据已分润金额,保留小数点后4位。
​   remain_amt_fen:该支付单据剩余分润金额,保留小数点后4位。
​   success_time:单据支付成功时间。格式yyyy-MM-dd HH:mm:ss
```