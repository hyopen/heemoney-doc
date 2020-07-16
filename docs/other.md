## 公共接口参数
>说明：接口请求和响应的公共参数，method 参数的值详情见具体接口标记

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
    <td>{****}</td>
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
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>13</td>
    <td>商户统一编号</td>
    <td>4945892121387</td>
</tr>
<tr>
    <td>isv_app_id</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商/代理商应用ID</td>
    <td>A2sdfjkl</td>
</tr>
<tr>
    <td>isv_mch_uid</td>
    <td>String</td>
    <td>否</td>
    <td>32</td>
    <td>服务商/代理商应用ID</td>
    <td>22255522</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>是</td>
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

## 创建商户收款码

接口说明：创建商户收款码

应用场景：该接口可以使服务商通过API接口创建商户收款码

- 注册接口

> 正式请求URL:`https://api.heemoney.com/v1/MerchQRCode`

> 联调URL:`https://demo.heemoney.com/Api/v1/MerchQRCode`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.merch.qrcode.create`

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
    <td>qr_url_name</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>收款码名称</td>
    <td>测试收款码</td>
</tr>
<tr>
    <td>qr_url_type</td>
    <td>String</td>
    <td>是</td>
    <td>1</td>
    <td>链接类型|2=普通收款码</td>
    <td>2</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>否</td>
    <td>13</td>
    <td>收款码所在门店</td>
    <td>100250000015511</td>
</tr>
<tr>
    <td>pay_amt</td>
    <td>String</td>
    <td>否</td>
    <td>50000</td>
    <td>收款金额（元）</td>
    <td>100</td>
</tr>
<tr>
    <td>desk_no</td>
    <td>String</td>
    <td>否</td>
    <td>50</td>
    <td>桌号</td>
    <td>1</td>
</tr>
<tr>
    <td>qr_url_style</td>
    <td>String</td>
    <td>否</td>
    <td>1</td>
    <td>收款码样式|0=默认,1=绿色样式,2=蓝色样式,3=红色样式</td>
    <td>0</td>
</tr>
<tr>
    <td>note</td>
    <td>String</td>
    <td>否</td>
    <td>50</td>
    <td>收款码备注</td>
    <td>测试创建一个</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
    <td>否</td>
    <td>255</td>
    <td>收款码异步通知地址(可以带参数)</td>
    <td>https://www.baidu.com?test=111</td>
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
    <td>mch_uid</td>
    <td>String</td>
    <td>是</td>
    <td>13</td>
    <td>商户统一编号</td>
    <td>4945892121387</td>
</tr>
<tr>
    <td>qrurl_uid</td>
    <td>String</td>
    <td>是</td>
    <td>18</td>
    <td>收款码唯一标识</td>
    <td>494589000304272953</td>
</tr>
<tr>
    <td>store_uid</td>
    <td>String</td>
    <td>是</td>
    <td>18</td>
    <td>门店UID</td>
    <td>494589000297900282</td>
</tr>
<tr>
    <td>pay_amt</td>
    <td>String</td>
    <td>否</td>
    <td>50000</td>
    <td>收款金额（元）</td>
    <td>100</td>
</tr>
<tr>
    <td>qr_url</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>收款码支付URL</td>
    <td>https://qr.heemoney.com/S/494589000304272953</td>
</tr>
</table>


## 商户出金记录

接口说明：使用汇付宝通道，可以通过该接口查看商户结算资金信息

应用场景：查看代理商下商户结算信息

- 注册接口

> 正式请求URL:`https://api.heemoney.com/v1/MerchOutAmtQuery`

> 联调URL:`https://demo.heemoney.com/Api/v1/MerchOutAmtQuery`

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heemoney.outamt.query`

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
    <td>begin_time</td>
    <td>String</td>
    <td>是</td>
    <td>14</td>
    <td>开始时间</td>
    <td>20200716101203</td>
</tr>
<tr>
    <td>end_time</td>
    <td>String</td>
    <td>是</td>
    <td>14</td>
    <td>截止时间</td>
    <td>20200716101203</td>
</tr>
<tr>
    <td>page_num</td>
    <td>String</td>
    <td>是</td>
    <td>10</td>
    <td>起始页</td>
    <td>1</td>
</tr>
<tr>
    <td>page_size</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>页大小（最大500）</td>
    <td>10</td>
</tr>
<tr>
    <td>search_word</td>
    <td>String</td>
    <td>是</td>
    <td>100</td>
    <td>查询字段信息（商户UID/商户账号）</td>
    <td>loginAccount</td>
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
    <td>list</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td></td>
    <td>【记录集合开始】</td>
</tr>
<tr>
    <td>RecordID</td>
    <td>String</td>
    <td>是</td>
    <td>90000</td>
    <td>记录内码</td>
    <td>339657</td>
</tr>
<tr>
    <td>MerchUID</td>
    <td>String</td>
    <td>是</td>
    <td>18</td>
    <td>商户UID</td>
    <td>4945892106464</td>
</tr>
<tr>
    <td>LoginAccount</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>登录账号</td>
    <td>wjtest1</td>
</tr>
<tr>
    <td>Company</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>公司名称</td>
    <td>食品科技公司</td>
</tr>
<tr>
    <td>ShortName</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>门店名称</td>
    <td>王测试</td>
</tr>
<tr>
    <td>BankName</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>银行名称</td>
    <td>河北省石家庄市建设银行</td>
</tr>
<tr>
    <td>CashAmt</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>提现金额</td>
    <td>100</td>
</tr>
<tr>
    <td>RealAmt</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>到账金额</td>
    <td>100</td>
</tr>
<tr>
    <td>FeeAmt</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>到账金额</td>
    <td>100</td>
</tr>
<tr>
    <td>BillStatus</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>提现状态|1=成功，0=处理中，-1=失败</td>
    <td>1</td>
</tr>
<tr>
    <td>CreateTime</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>创建时间</td>
    <td>2020-07-14 14：45：34</td>
</tr>
<tr>
    <td>list</td>
    <td>String</td>
    <td>是</td>
    <td></td>
    <td></td>
    <td>【记录集合结束】</td>
</tr>
<tr>
    <td>currentpage</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>当前页数</td>
    <td>1</td>
</tr>
<tr>
    <td>totalpage</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>总页数</td>
    <td>10</td>
</tr>
<tr>
    <td>totalrows</td>
    <td>String</td>
    <td>是</td>
    <td>50</td>
    <td>总记录数</td>
    <td>100</td>
</tr>
</table>