---
title: 解释结果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c226e3b677965db03ba4d5fcc3c3dadb37192548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>解释结果

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

Lync Server 2013 压力和性能工具（LyncPerfTool）具有许多计数器，您可以使用这些计数器来了解客户端正在执行的操作以及它是否遇到问题。

<div>

## <a name="client-counters"></a>客户端计数器

运行的 LyncPerfTool 的每个实例都有一个单独的计数器实例。 每个实例都按其进程 ID 命名。

如果客户端过载，则可能会出现问题。 若要避免这些问题，请执行以下操作：

1.  监视客户端计算机上的 CPU 和内存使用率。 如果 CPU 的使用率持续高于90%，则减少用户数。

2.  如果内存占用量较高，则在页面文件不够大的情况下可能会遇到问题。 确认确认费用未超出计算机上的限制。 如果您正在运行内存限制，请考虑增加页面文件大小或减少用户数

下表列出了关键 LyncPerfTool 性能计数器。

**常规信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>花费的时间（分钟）</p></td>
<td><p>启动进程后所用的时间。</p></td>
</tr>
<tr class="even">
<td><p>活动终结点</p></td>
<td><p>当前连接到服务器的终结点的数目。</p></td>
</tr>
<tr class="odd">
<td><p>失败登录</p></td>
<td><p>总的终结点登录失败次数。</p></td>
</tr>
<tr class="even">
<td><p>登录尝试</p></td>
<td><p>尝试登录尝试的总次数。</p></td>
</tr>
<tr class="odd">
<td><p>终结点断开</p></td>
<td><p>已断开连接的终结点总数。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**状态信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 调用</p></td>
<td><p>状态更改尝试的总数。 有关不同类型的状态更改，请参阅 SetPresence （状态类型）调用性能计数器。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence 的 NNN 响应</p></td>
<td><p>从服务器接收的 nnn 响应代码总数。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 调用</p></td>
<td><p>Get 状态请求尝试总数。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence 的 NNN 响应</p></td>
<td><p>从服务器接收的 nnn 响应代码总数。</p></td>
</tr>
</tbody>
</table>


**通讯簿服务信息**

此类别包括用于监视通讯簿服务（ABS）文件下载和通讯簿 Web 查询服务请求的计数器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>试图进行的 ABS 完全/增量文件下载</p></td>
<td><p>尝试的完整或增量文件下载请求的总数。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完全/增量文件下载成功</p></td>
<td><p>尝试的完整或增量文件下载请求的总数。</p></td>
</tr>
<tr class="odd">
<td><p>通讯簿 Web 查询服务相关计数器</p></td>
<td><p>通讯簿文件下载相关计数器。</p></td>
</tr>
<tr class="even">
<td><p>尝试的 ABS WS 调用</p></td>
<td><p>尝试的通讯簿 Web 查询服务请求总数。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 调用成功</p></td>
<td><p>返回成功响应代码的通讯簿 Web 查询服务请求总数。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 调用失败</p></td>
<td><p>返回错误响应代码的通讯簿 Web 查询服务请求总数。</p></td>
</tr>
</tbody>
</table>


**通讯组列表（DL）信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>尝试的呼叫</p></td>
<td><p>尝试的通讯组列表展开（DLX） web 服务请求总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫成功</p></td>
<td><p>返回成功响应代码的 DLX web 服务请求总数。</p></td>
</tr>
<tr class="odd">
<td><p>调用失败</p></td>
<td><p>返回错误响应代码的 DLX web 服务请求总数。</p></td>
</tr>
</tbody>
</table>


**VoIP 基本信息**

在启用这些方案时，下面列出了所有 IP 语音（VoIP）呼叫的报告编号，包括对中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理的呼叫。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动呼叫</p></td>
<td><p>当前正在进行的传入/传出语音呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已终止</p></td>
<td><p>已终止的传入/传出语音呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫被拒绝</p></td>
<td><p>已拒绝的传入语音呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>尝试传入/传出呼叫</p></td>
<td><p>尝试的传入/传出语音呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>建立的传入/传出呼叫</p></td>
<td><p>建立的传入/传出语音呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫收到的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码总数。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 传递率（%）</p></td>
<td><p>已建立的呼叫总数/尝试的总呼叫数。</p></td>
</tr>
</tbody>
</table>


**响应组服务调用信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动呼叫</p></td>
<td><p>对响应组应用程序的活动呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>尝试的呼叫</p></td>
<td><p>尝试的呼叫总数。</p></td>
</tr>
</tbody>
</table>


**即时消息（IM）呼叫信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动呼叫</p></td>
<td><p>正在进行的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已终止</p></td>
<td><p>已终止的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫收到的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码总数。</p></td>
</tr>
<tr class="even">
<td><p>接收/发送的 IM 消息</p></td>
<td><p>所有会话接收或发送的邮件总数。</p></td>
</tr>
<tr class="odd">
<td><p>尝试传入/传出呼叫</p></td>
<td><p>尝试的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>建立的传入/传出呼叫</p></td>
<td><p>已建立的传入/传出即时消息呼叫总数。</p></td>
</tr>
</tbody>
</table>


**应用程序共享呼叫信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动呼叫</p></td>
<td><p>正在进行的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已终止</p></td>
<td><p>已终止的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫收到的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码总数。</p></td>
</tr>
<tr class="even">
<td><p>尝试传入/传出呼叫</p></td>
<td><p>尝试的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>建立的传入/传出呼叫</p></td>
<td><p>已建立的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA 呼叫信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动呼叫</p></td>
<td><p>当前正在进行的传入/传出公用电话交换网（PSTN）呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已终止</p></td>
<td><p>已终止的传入/传出 PSTN 呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>尝试传入/传出呼叫</p></td>
<td><p>尝试的传入/传出 PSTN 呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>建立的传入/传出呼叫</p></td>
<td><p>已建立的传入/传出 PSTN 呼叫总数。</p></td>
</tr>
</tbody>
</table>


**会议信息**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>活动即时消息会议</p></td>
<td><p>正在进行的即时消息会议总数。</p></td>
</tr>
<tr class="even">
<td><p>活动的音频/视频会议</p></td>
<td><p>正在进行的音频/视频（A/V）会议总数。</p></td>
</tr>
<tr class="odd">
<td><p>活动应用程序共享会议</p></td>
<td><p>正在进行的应用程序共享会议总数。</p></td>
</tr>
<tr class="even">
<td><p>参与者数量</p></td>
<td><p>当前连接到会议的参与者总数。</p></td>
</tr>
<tr class="odd">
<td><p>会议日程安排失败</p></td>
<td><p>尝试安排会议时出现的失败总次数。</p></td>
</tr>
<tr class="even">
<td><p>加入会议失败</p></td>
<td><p>尝试连接到会议时出现的失败总次数。</p></td>
</tr>
</tbody>
</table>


**UCWA 客户端计数器**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>性能计数器</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>成功的 IMMCU 联接总数</p></td>
<td><p>加入的即时消息会议总数。</p></td>
</tr>
<tr class="even">
<td><p>成功的 DMCU 联接总数</p></td>
<td><p>加入的 A/V 会议总数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

