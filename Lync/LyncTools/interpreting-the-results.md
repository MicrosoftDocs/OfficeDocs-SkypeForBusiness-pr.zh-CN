---
title: 解释结果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>解释结果

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

Lync Server 2013 应力和性能工具 (LyncPerfTool) 具有许多计数器, 你可以使用这些计数器来了解客户端正在执行的操作以及它是否会遇到问题。

<div>

## <a name="client-counters"></a>客户端计数器

正在运行的 LyncPerfTool 的每个实例都具有计数器的单独实例。 每个实例均按其进程 ID 命名。

如果客户端超载, 可能会出现问题。 若要防止这些问题, 请执行下列操作:

1.  监视客户端计算机上的 CPU 和内存使用情况。 如果 CPU 持续超过 90%, 请减少用户数。

2.  如果内存占用量较高, 则当页面文件不够大时, 可能会遇到问题。 验证确认费用未达到计算机的限制。 如果您运行的是内存限制, 请考虑增加页面文件大小或减少用户数

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
<td><p>分钟花费的时间</p></td>
<td><p>启动流程后所花费的时间。</p></td>
</tr>
<tr class="even">
<td><p>活动终结点</p></td>
<td><p>当前连接到服务器的终结点的数量。</p></td>
</tr>
<tr class="odd">
<td><p>失败的登录</p></td>
<td><p>终结点登录失败总数。</p></td>
</tr>
<tr class="even">
<td><p>登录尝试</p></td>
<td><p>终结点登录尝试的总数。</p></td>
</tr>
<tr class="odd">
<td><p>终结点断开连接</p></td>
<td><p>已断开连接的终结点的总数。</p></td>
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
<td><p>SetPresence 通话</p></td>
<td><p>联机状态更改尝试总数。 对于不同类型的状态更改, 请参阅 SetPresence (状态类型) 调用性能计数器。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence 的 NNN 响应</p></td>
<td><p>从服务器接收的 nnn 响应代码的总数。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 通话</p></td>
<td><p>获取状态请求尝试的总次数。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence 的 NNN 响应</p></td>
<td><p>从服务器接收的 nnn 响应代码的总数。</p></td>
</tr>
</tbody>
</table>


**通讯簿服务信息**

此类别包括用于监视通讯簿服务 (ABS) 文件下载和通讯簿 Web 查询服务请求的计数器。


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
<td><p>已尝试绝对值完整/增量文件下载</p></td>
<td><p>已尝试的完整或增量文件下载请求的总数。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完整/增量文件下载成功</p></td>
<td><p>已尝试的完整或增量文件下载请求的总数。</p></td>
</tr>
<tr class="odd">
<td><p>通讯簿 Web 查询服务相关计数器</p></td>
<td><p>通讯簿文件下载相关计数器。</p></td>
</tr>
<tr class="even">
<td><p>尝试进行 ABS WS 呼叫</p></td>
<td><p>尝试的通讯簿 Web 查询服务请求总数。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 呼叫成功</p></td>
<td><p>返回成功响应代码的通讯簿 Web 查询服务请求的总数。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 呼叫失败</p></td>
<td><p>返回错误响应代码的通讯簿 Web 查询服务请求的总数。</p></td>
</tr>
</tbody>
</table>


**通讯组列表 (DL) 信息**


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
<td><p>已尝试呼叫</p></td>
<td><p>尝试的通讯组列表展开 (DLX) web 服务请求的总数。</p></td>
</tr>
<tr class="even">
<td><p>通话成功</p></td>
<td><p>返回成功响应代码的 DLX web 服务请求的总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫失败</p></td>
<td><p>返回了错误响应代码的 DLX web 服务请求的总数。</p></td>
</tr>
</tbody>
</table>


**VoIP 基本信息**

以下列出的性能计数器将在启用这些方案时针对所有 IP 语音 (VoIP) 呼叫 (包括中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理) 的报告编号。


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
<td><p>通话处于活动状态</p></td>
<td><p>当前正在进行的传入/传出语音呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>通话终止</p></td>
<td><p>已终止的传入/传出语音通话总数。</p></td>
</tr>
<tr class="odd">
<td><p>通话被拒绝</p></td>
<td><p>已拒绝的传入语音呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>已尝试拨入/拨出电话</p></td>
<td><p>已尝试传入/传出语音通话的总数。</p></td>
</tr>
<tr class="odd">
<td><p>已建立传入/传出呼叫</p></td>
<td><p>已建立的传入/传出语音通话的总数。</p></td>
</tr>
<tr class="even">
<td><p>呼叫接收的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码的总数。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 传递率 (%)</p></td>
<td><p>已建立通话总次数/尝试的通话总次数。</p></td>
</tr>
</tbody>
</table>


**响应组服务呼叫信息**


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
<td><p>通话处于活动状态</p></td>
<td><p>对响应组应用程序的活动呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>已尝试呼叫</p></td>
<td><p>尝试的通话总次数。</p></td>
</tr>
</tbody>
</table>


**即时消息 (IM) 呼叫信息**


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
<td><p>通话处于活动状态</p></td>
<td><p>正在进行的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>通话终止</p></td>
<td><p>已终止的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫接收的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码的总数。</p></td>
</tr>
<tr class="even">
<td><p>接收/发送的 IM 消息</p></td>
<td><p>所有会话的已接收或已发送邮件的总数。</p></td>
</tr>
<tr class="odd">
<td><p>已尝试拨入/拨出电话</p></td>
<td><p>尝试的传入/传出即时消息呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>已建立传入/传出呼叫</p></td>
<td><p>已建立的传入/传出即时消息呼叫总数。</p></td>
</tr>
</tbody>
</table>


**应用共享呼叫信息**


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
<td><p>通话处于活动状态</p></td>
<td><p>正在进行的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>通话终止</p></td>
<td><p>已终止的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫接收的 NNN</p></td>
<td><p>从服务器接收的 nnn 响应代码的总数。</p></td>
</tr>
<tr class="even">
<td><p>已尝试拨入/拨出电话</p></td>
<td><p>尝试的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>已建立传入/传出呼叫</p></td>
<td><p>已建立的传入/传出应用程序共享呼叫总数。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA 通话信息**


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
<td><p>通话处于活动状态</p></td>
<td><p>当前正在进行的传入/传出公共交换电话网络 (PSTN) 呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>通话终止</p></td>
<td><p>已终止的传入/传出 PSTN 呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p>已尝试拨入/拨出电话</p></td>
<td><p>尝试的传入/传出 PSTN 呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p>已建立传入/传出呼叫</p></td>
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
<td><p>活动音频/视频会议</p></td>
<td><p>正在进行的音频/视频 (A/V) 会议总数。</p></td>
</tr>
<tr class="odd">
<td><p>活动应用程序共享会议</p></td>
<td><p>正在进行的应用程序共享会议总数。</p></td>
</tr>
<tr class="even">
<td><p>参与者的人数</p></td>
<td><p>当前连接到会议的参与者总数。</p></td>
</tr>
<tr class="odd">
<td><p>会议计划失败</p></td>
<td><p>尝试安排会议时失败的总次数。</p></td>
</tr>
<tr class="even">
<td><p>加入会议失败</p></td>
<td><p>尝试连接到会议时失败的总次数。</p></td>
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
<td><p>已成功联接的 IMMCU 总数</p></td>
<td><p>已加入的即时消息会议的总数。</p></td>
</tr>
<tr class="even">
<td><p>已成功联接的 DMCU 总数</p></td>
<td><p>已加入/V 会议的总数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

