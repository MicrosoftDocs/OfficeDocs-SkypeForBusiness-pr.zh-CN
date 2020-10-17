---
title: Lync Server 2013：移动性能计数器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513599"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013 中的移动性能计数器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

下表列出了可用于监视运行统一通信 Web API (UCWA) 和 Lync Server 2013 Mcx 移动服务的服务器的性能计数器的名称和说明。

UCWA 表中的计数器的类别名称为 **LS： WEB – UCWA**。

Mcx 移动服务表中的计数器的类别名称为 **LS： WEB-移动通信服务**。

<div>

## <a name="performance-counters-for-ucwa"></a>UCWA 的性能计数器


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>计数器</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动应用程序计数</p></td>
<td><p>当前的应用程序数</p></td>
</tr>
<tr class="even">
<td><p>活动应用程序共享模态计数</p></td>
<td><p>当前的应用程序共享模态数量</p></td>
</tr>
<tr class="odd">
<td><p>主动音频模态计数</p></td>
<td><p>音频模态的当前数量</p></td>
</tr>
<tr class="even">
<td><p>主动数据协作的模态计数</p></td>
<td><p>当前的数据协作模态数量</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 照片获取延迟 (毫秒) </p></td>
<td><p>此计数器显示从 active directory 检索照片的平均时间（以毫秒为单位） () </p></td>
</tr>
<tr class="even">
<td><p>活动邮件模态计数</p></td>
<td><p>当前邮件模态的数量</p></td>
</tr>
<tr class="odd">
<td><p>活动全景视频模态计数</p></td>
<td><p>当前的全景视频模态数</p></td>
</tr>
<tr class="even">
<td><p>活动挂起获取计数</p></td>
<td><p>当前处于活动状态的挂起获取的数目;与服务器的长时间保持连接</p></td>
</tr>
<tr class="odd">
<td><p>活动会话计数</p></td>
<td><p>每个应用程序的 UCWA 中注册的当前终结点数和总数</p></td>
</tr>
<tr class="even">
<td><p>活动用户实例计数</p></td>
<td><p>当前用户实例数</p></td>
</tr>
<tr class="odd">
<td><p>没有应用程序的活动用户实例</p></td>
<td><p>当前不包含应用程序的用户实例数</p></td>
</tr>
<tr class="even">
<td><p>活动视频模态计数</p></td>
<td><p>视频模态的当前数量</p></td>
</tr>
<tr class="odd">
<td><p>收到的应用程序创建请求数/秒</p></td>
<td><p>每秒收到应用程序创建请求的速率</p></td>
</tr>
<tr class="even">
<td><p>作为 MCU 联接失败</p></td>
<td><p>作为 MCU 联接失败的次数</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 联接失败</p></td>
<td><p>AV MCU 联接失败的次数</p></td>
</tr>
<tr class="even">
<td><p> (毫秒的平均应用程序启动时间) </p></td>
<td><p>应用程序的平均启动时间（以毫秒为单位）</p></td>
</tr>
<tr class="odd">
<td><p>会话 (ms 的平均生存期) </p></td>
<td><p>会话的平均生存时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>数据 MCU 联接失败</p></td>
<td><p>数据 MCU 联接失败次数</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 联系人搜索延迟 (毫秒) </p></td>
<td><p>此计数器显示在 Exchange 中搜索联系人的平均时间 (（以毫秒为单位）) </p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 照片获取延迟 (毫秒) </p></td>
<td><p>此计数器显示从 Exchange 检索照片的平均时间（以毫秒为单位） () </p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 响应数/秒</p></td>
<td><p>HTTP 4xx 代码的每秒响应速率</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 响应数/秒</p></td>
<td><p>HTTP 5xx 代码的每秒响应速率</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU 联接失败</p></td>
<td><p>IM MCU 联接失败的次数</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 照片获取失败的次数</p></td>
<td><p>从 Active Directory 检索照片的失败总次数</p></td>
</tr>
<tr class="odd">
<td><p>联系人搜索失败的次数</p></td>
<td><p>在 Exchange 中搜索联系人的失败总次数</p></td>
</tr>
<tr class="even">
<td><p>反序列化失败次数</p></td>
<td><p>反序列化失败总次数</p></td>
</tr>
<tr class="odd">
<td><p>HD 照片获取失败的次数</p></td>
<td><p>从 Exchange 检索 HD 照片的失败总次数</p></td>
</tr>
<tr class="even">
<td><p>在每个应用程序的最大订阅数</p></td>
<td><p>每个应用程序允许的最大订阅请求数</p></td>
</tr>
<tr class="odd">
<td><p>在每批的最大订阅数</p></td>
<td><p>每个批处理允许的最大订阅请求数</p></td>
</tr>
<tr class="even">
<td><p>状态订阅失败</p></td>
<td><p>订阅状态失败的次数</p></td>
</tr>
<tr class="odd">
<td><p>注册终结点故障</p></td>
<td><p>注册终结点的失败次数</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>每秒收到的请求数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second</p></td>
<td><p>每秒成功请求 (HTTP 2xx/3xx 响应代码的速率) </p></td>
</tr>
<tr class="even">
<td><p>已成功创建应用程序请求/秒</p></td>
<td><p>每秒成功的应用程序创建请求的速率</p></td>
</tr>
<tr class="odd">
<td><p>挂起 Get Count 超时</p></td>
<td><p>超时的挂起获取数</p></td>
</tr>
<tr class="even">
<td><p>收到的应用程序创建请求总数</p></td>
<td><p>自启动服务以来收到的应用程序创建请求总数</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 响应总数</p></td>
<td><p>HTTP 4xx 响应总数</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 响应总数</p></td>
<td><p>HTTP 5xx 响应总次数</p></td>
</tr>
<tr class="odd">
<td><p>在命令通道上收到的请求总数</p></td>
<td><p>命令通道上收到的请求总数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded</p></td>
<td><p>成功的请求总数</p></td>
</tr>
<tr class="odd">
<td><p>启动的会话总数</p></td>
<td><p>启动服务后启动的会话总数</p></td>
</tr>
<tr class="even">
<td><p>由于空闲超时而终止的会话总数</p></td>
<td><p>因用户空闲超时终止的会话总数</p></td>
</tr>
<tr class="odd">
<td><p>限制的应用程序总数</p></td>
<td><p>限制的应用程序数</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx 移动服务的性能计数器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>计数器</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Average Lifetime for a Session in Milliseconds</p></td>
<td><p>会话的平均生存时间（以毫秒为单位）</p></td>
</tr>
<tr class="even">
<td><p>Current Push Notification Subscriptions</p></td>
<td><p>当前推送通知订阅数。 此数字与当前活动会话计数联合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

