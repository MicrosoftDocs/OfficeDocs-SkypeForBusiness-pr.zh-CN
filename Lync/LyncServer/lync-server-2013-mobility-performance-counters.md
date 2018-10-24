---
title: 移动性能计数器
TOCTitle: 移动性能计数器
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690046(v=OCS.15)
ms:contentKeyID: 49314322
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移动性能计数器

 

_**上一次修改主题：** 2015-03-09_

下表列出了可用于监视运行统一通信 Web API (UCWA) 和 Lync Server 2013 Mcx Mobility Service 的服务器的性能计数器的名称和说明。

UCWA 表中计数器的类别名称为 **LS:WEB – UCWA**。

Mcx Mobility Service 表中计数器的类别名称为 **LS:WEB - Mobile Communication Service**。

## UCWA 性能计数器


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>计数器</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Active Application Count</p></td>
<td><p>当前应用程序数目</p></td>
</tr>
<tr class="even">
<td><p>Active Application Sharing Modality Count</p></td>
<td><p>当前应用程序共享形式数目</p></td>
</tr>
<tr class="odd">
<td><p>Active Audio Modality Count</p></td>
<td><p>当前音频形式数目</p></td>
</tr>
<tr class="even">
<td><p>Active Data Collaboration Modality Count</p></td>
<td><p>当前数据协作形式数目</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory Photo Get Latency (ms)</p></td>
<td><p>此计数器显示从 Active Directory 检索照片所花的平均时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>Active Messaging Modality Count</p></td>
<td><p>当前消息传递形式数目</p></td>
</tr>
<tr class="odd">
<td><p>Active Panoramic Video Modality Count</p></td>
<td><p>当前全景视频形式数目</p></td>
</tr>
<tr class="even">
<td><p>Active Pending Get Count</p></td>
<td><p>当前活动待处理项数；与服务器长期保持连接</p></td>
</tr>
<tr class="odd">
<td><p>Active Session Count</p></td>
<td><p>当前在 UCWA 中按应用程序注册的终结点数和总数</p></td>
</tr>
<tr class="even">
<td><p>Active User Instance Count</p></td>
<td><p>当前用户实例数</p></td>
</tr>
<tr class="odd">
<td><p>Active User Instances without Application</p></td>
<td><p>当前用户实例数（无应用程序）</p></td>
</tr>
<tr class="even">
<td><p>Active Video Modality Count</p></td>
<td><p>当前视频形式数目</p></td>
</tr>
<tr class="odd">
<td><p>Application Creation Requests Received/Second</p></td>
<td><p>应用程序创建请求的每秒接收速率</p></td>
</tr>
<tr class="even">
<td><p>AS MCU Join Failures</p></td>
<td><p>AS MCU 联接失败数</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU Join Failures</p></td>
<td><p>AV MCU 联接失败数</p></td>
</tr>
<tr class="even">
<td><p>Average Application Startup Time (ms)</p></td>
<td><p>应用程序平均启动时间（以毫秒为单位）</p></td>
</tr>
<tr class="odd">
<td><p>Average Lifetime for Session (ms)</p></td>
<td><p>会话的平均生存时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>Data MCU Join Failures</p></td>
<td><p>Data MCU 联接失败数</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Contact Search Latency (ms)</p></td>
<td><p>此计数器显示在 Exchange 中搜索联系人所花的平均时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get Latency (ms)</p></td>
<td><p>此计数器显示从 Exchange 中检索照片所花的平均时间（以毫秒为单位）</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx Responses/Second</p></td>
<td><p>HTTP 4xx 代码的每秒响应速率</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx Responses/Second</p></td>
<td><p>HTTP 5xx 代码的每秒响应速率</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU Join Failures</p></td>
<td><p>IM MCU 联接失败数</p></td>
</tr>
<tr class="even">
<td><p>Number of Active Directory Photo Get Failures</p></td>
<td><p>从 Active Directory 中检索照片的总失败次数</p></td>
</tr>
<tr class="odd">
<td><p>Number of Contact Search failures</p></td>
<td><p>在 Exchange 中搜索联系人的总失败次数</p></td>
</tr>
<tr class="even">
<td><p>Number of Deserialization Failures</p></td>
<td><p>反序列化的总失败次数</p></td>
</tr>
<tr class="odd">
<td><p>Number of HD Photo Get Failures</p></td>
<td><p>从 Exchange 中检索 HD 照片的总失败次数</p></td>
</tr>
<tr class="even">
<td><p>Over The Maximum Subscriptions Per Application</p></td>
<td><p>允许的每应用程序最大订阅请求数</p></td>
</tr>
<tr class="odd">
<td><p>Over The Maximum Subscriptions Per Batch</p></td>
<td><p>允许的每批次最大订阅请求数</p></td>
</tr>
<tr class="even">
<td><p>Presence Subscription Failures</p></td>
<td><p>订阅状态失败次数</p></td>
</tr>
<tr class="odd">
<td><p>Registering Endpoint Failures</p></td>
<td><p>注册终结点的失败次数</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>每秒收到的请求数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second</p></td>
<td><p>每秒的成功请求数（HTTP 2xx/3xx 响应代码）</p></td>
</tr>
<tr class="even">
<td><p>Succeeded Create Application Requests/Second</p></td>
<td><p>成功应用程序创建请求的每秒接收速率</p></td>
</tr>
<tr class="odd">
<td><p>Timed Out Pending Get Count</p></td>
<td><p>超时的待处理项数</p></td>
</tr>
<tr class="even">
<td><p>Total Application Creation Requests Received</p></td>
<td><p>自启动服务以来收到的应用程序创建请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total HTTP 4xx Responses</p></td>
<td><p>HTTP 4xx 响应总数</p></td>
</tr>
<tr class="even">
<td><p>Total HTTP 5xx Responses</p></td>
<td><p>HTTP 5xx 响应总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Received on the Command Channel</p></td>
<td><p>命令通道上收到的请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded</p></td>
<td><p>成功的请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Initiated</p></td>
<td><p>自启动服务以来启动的会话总数</p></td>
</tr>
<tr class="even">
<td><p>Total Sessions Terminated Because of Idle Timeout</p></td>
<td><p>因用户空闲超时终止的会话总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Throttled Applications</p></td>
<td><p>阻止的应用程序数</p></td>
</tr>
</tbody>
</table>


### Mcx Mobility Service 性能计数器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>计数器</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Average Lifetime for a Session in Milliseconds</p></td>
<td><p>会话的平均生存时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>Current Push Notification Subscriptions</p></td>
<td><p>当前推送通知订阅数。此数目与 Currently Active Session Count 结合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Network Timeout Poll Count</p></td>
<td><p>超时的网络投票数</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Poll Count</p></td>
<td><p>当前活动投票数（与服务器的长期连接）</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Session Count</p></td>
<td><p>当前注册到 Mobility Service 中的终结点的数目</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Session Count with Active Presence Subscriptions</p></td>
<td><p>包含活动状态订阅的当前活动会话的数目</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Failed/Second</p></td>
<td><p>每秒失败的推送通知数</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests Succeeded/Second</p></td>
<td><p>每秒成功的推送通知数</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Throttled/Second</p></td>
<td><p>每秒阻止的推送通知数</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests/Second</p></td>
<td><p>每秒发送的推送通知数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Failed/Second</p></td>
<td><p>每秒失败的请求数</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>每秒收到的请求数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Rejected/Second</p></td>
<td><p>每秒拒绝的请求数</p></td>
</tr>
<tr class="even">
<td><p>Requests Succeeded/Second</p></td>
<td><p>每秒成功的请求数</p></td>
</tr>
<tr class="odd">
<td><p>Succeeded Initiate Session Requests/Second</p></td>
<td><p>每秒成功的 Get Location 请求数。启动会话的请求占用了服务器上大部分 CPU。支持的峰值负载为 12/秒。可持续性依赖于服务器上的其他负载。启动会话通常意味着用户登录已注销很长一段时间。</p></td>
</tr>
<tr class="even">
<td><p>Total Declined Inbound Voice Calls</p></td>
<td><p>拒绝的入站语音呼叫总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Failed Inbound Voice Calls</p></td>
<td><p>失败的入站语音呼叫总数</p></td>
</tr>
<tr class="even">
<td><p>Total Failed Outbound Voice Calls</p></td>
<td><p>失败的出站语音呼叫总数</p></td>
</tr>
<tr class="odd">
<td><p>Total number of sessions terminated by user</p></td>
<td><p>用户终止的会话总数</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests</p></td>
<td><p>推送通知请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Failed</p></td>
<td><p>失败的推送通知请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests Succeeded</p></td>
<td><p>成功的推送通知请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Throttled</p></td>
<td><p>阻止的推送通知请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Failed</p></td>
<td><p>失败的请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests received on the Command Channel</p></td>
<td><p>命令通道上收到的请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Rejected</p></td>
<td><p>拒绝的请求总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Succeeded</p></td>
<td><p>成功发送给 Mobility Service 的请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Session Initiated Count</p></td>
<td><p>自启动 Mobility Service 后启动的会话总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Terminated Because of User Idle Timeout</p></td>
<td><p>因用户空闲超时终止的会话总数</p></td>
</tr>
<tr class="even">
<td><p>Total Successful Inbound Voice Calls</p></td>
<td><p>成功的入站语音呼叫总数</p></td>
</tr>
<tr class="odd">
<td><p>Total Successful Outbound Voice Calls</p></td>
<td><p>成功的出站语音呼叫总数</p></td>
</tr>
</tbody>
</table>

