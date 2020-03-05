
<table data-hy-role="doctbl">
    <th>错误码</th>
    <th>错误码描述</th>
    
</tr>
<tr>
    <td>E0000</td>
    <td>业务处理成功</td>
</tr>
<tr>
    <td>E0001</td>
    <td>缺少必要参数</td>
</tr>
<tr>
    <td>E0002</td>
    <td>无效的参数</td>
</tr>
<tr>
    <td>E0003</td>
    <td>应用ID不存在</td>
</tr>
<tr>
    <td>E0004</td>
    <td>应用审核未成功</td>
</tr>
<tr>
    <td>E0005</td>
    <td>应用未开启</td>
</tr>
<tr>
    <td>E0006</td>
    <td>签名错误</td>
</tr>
<tr>
    <td>E0007</td>
    <td>系统错误</td>
</tr>
<tr>
    <td>E0008</td>
    <td>数据处理错误</td>
</tr>
</table>

返回代码及说明：
trade_status
-4=关闭
-3=支付方单不存在
-2=验证失败
-1=失败
0=未知
1=支付成功
2=支付中

接口字段中的三个url区分：
notify_url:系统处理业务后通知商户的URL
return_url:系统处理业务后返回到商户的URL
redirect_url:钱包业务返回的URL，需要商户跳转到此URL进行后续操作