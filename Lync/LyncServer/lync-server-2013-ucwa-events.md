---
title: Lync Server 2013： UCWA 事件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013 中的 UCWA 事件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 使用统一通信 Web API （UCWA）来实现许多用途，从访问 Microsoft Exchange 到联系人搜索以更新移动客户端的状态。

UCWA 将运行行为的记录编写成“信息”、“警告”和“错误”事件类型。下表介绍了可由 UCWA 组件编写的事件。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>事件 ID</th>
<th>事件类型</th>
<th>摘要</th>
<th>原因和解决方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>信息</p></td>
<td><p>UCWA 已初始化</p></td>
<td><p>不适用</p>
<p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>错误</p></td>
<td><p>UCWA 在初始化期间遇到意外异常</p></td>
<td><p>初始化期间出现意外错误</p>
<p>检查相关事件日志条目中的异常详细信息以确定可能的原因</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>错误</p></td>
<td><p>UCWA 遇到未经处理的异常</p></td>
<td><p>出现未经处理的异常</p>
<p>重新启动服务器。如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>错误</p></td>
<td><p>无法访问 Exchange 获取高清照片</p></td>
<td><p>与 Exchange 的连接不可用</p>
<p>确保与 Exchange 的连接可用</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>信息</p></td>
<td><p>从无法访问 Exchange 获取高清照片的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>错误</p></td>
<td><p>无法访问 Exchange 进行联系人搜索</p></td>
<td><p>与 Exchange 的连接不可用</p>
<p>确保与 Exchange 的连接可用</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>信息</p></td>
<td><p>从无法在 Exchange 中搜索联系人的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>尝试订阅超过每应用程序允许的状态订阅数量</p></td>
<td><p>尝试订阅超过每应用程序允许的状态订阅数量</p>
<p>检查客户端中不必要的订阅</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>尝试订阅超过每批允许的状态订阅数量</p></td>
<td><p>尝试订阅超过每批允许的状态订阅数量</p>
<p>检查客户端中不必要的订阅</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>错误</p></td>
<td><p>无法检索带内数据</p></td>
<td><p>无法检索带内数据</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>错误</p></td>
<td><p>无法订阅状态</p></td>
<td><p>无法订阅状态</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>错误</p></td>
<td><p>未能注册终结点</p></td>
<td><p>未能注册终结点</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>错误</p></td>
<td><p>IM MCU 不可用</p></td>
<td><p>IM MCU 不可用</p>
<p>查看 IM MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>信息</p></td>
<td><p>从无法连接 IM MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>错误</p></td>
<td><p>AV MCU 不可用</p></td>
<td><p>AV MCU 不可用</p>
<p>查看 AV MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>信息</p></td>
<td><p>从无法连接 AV MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>错误</p></td>
<td><p>AS MCU 不可用</p></td>
<td><p>AS MCU 不可用</p>
<p>查看 AS MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>信息</p></td>
<td><p>从无法连接 AS MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>错误</p></td>
<td><p>Data MCU 不可用</p></td>
<td><p>Data MCU 不可用</p>
<p>查看 Data MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>信息</p></td>
<td><p>从无法连接 Data MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>错误</p></td>
<td><p>无法加入 IM MCU</p></td>
<td><p>无法加入 IM MCU</p>
<p>查看 IM MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>错误</p></td>
<td><p>无法加入 AV MCU</p></td>
<td><p>无法加入 AV MCU</p>
<p>查看 AV MCU 是否在运行</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>错误</p></td>
<td><p>无法加入 AS MCU</p></td>
<td><p>无法加入 AS MCU</p>
<p>查看 AS MCU 是否在运行</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>错误</p></td>
<td><p>无法加入 Data MCU</p></td>
<td><p>无法加入 Data MCU</p>
<p>查看 Data MCU 是否在运行</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>错误</p></td>
<td><p>无法访问 Active Directory 获取照片</p></td>
<td><p>与 Active Directory 的连接不可用</p>
<p>确保与 Active Directory 的连接可用</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>信息</p></td>
<td><p>从无法访问 Active Directory 获取照片的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>无法反序列化</p></td>
<td><p>无法反序列化</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

