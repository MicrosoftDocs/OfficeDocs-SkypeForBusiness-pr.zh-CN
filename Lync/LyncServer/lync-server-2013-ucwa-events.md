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
ms.openlocfilehash: 717f4e9686574a04434889f2c44a029a02e75768
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013 中的 UCWA 事件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 使用统一通信 Web API （UCWA）来实现多种用途，从访问 Microsoft Exchange 以进行联系人搜索，以更新移动客户端的状态。

UCWA 会将操作行为的记录编写为事件类型信息、警告和错误。 下表介绍了 UCWA 组件可以编写的事件。


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
<th>总结</th>
<th>原因和解决方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>之</p></td>
<td><p>UCWA 已初始化</p></td>
<td><p>不适用</p>
<p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA 在初始化期间遇到意外异常</p></td>
<td><p>初始化过程中出现意外错误</p>
<p>在关联的事件日志条目中检查异常详细信息，以确定可能的原因</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA 遇到未经处理的异常</p></td>
<td><p>发生未处理的异常</p>
<p>重新启动服务器。 如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>无法访问 HD 照片的 Exchange</p></td>
<td><p>与 Exchange 的连接不可用</p>
<p>请确保与 Exchange 的连接可用</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>之</p></td>
<td><p>从无法访问 Exchange for HD 照片的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>无法访问联系人搜索的 Exchange</p></td>
<td><p>与 Exchange 的连接不可用</p>
<p>请确保与 Exchange 的连接可用</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>之</p></td>
<td><p>从 Exchange 中的搜索联系人故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>尝试为每个应用程序订阅多于允许的状态订阅</p></td>
<td><p>尝试为每个应用程序订阅多于允许的状态订阅</p>
<p>检查客户端是否有不必要的订阅</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>每批次尝试订阅的订阅数超过允许的状态订阅数</p></td>
<td><p>每批次尝试订阅的订阅数超过允许的状态订阅数</p>
<p>检查客户端是否有不必要的订阅</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>无法检索带内数据</p></td>
<td><p>无法检索带内数据</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>无法订阅状态</p></td>
<td><p>无法订阅状态</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>无法注册终结点</p></td>
<td><p>无法注册终结点</p>
<p>如果问题仍然存在，请联系产品支持人员</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>IM MCU 不可用</p></td>
<td><p>IM MCU 不可用</p>
<p>查看 IM MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>之</p></td>
<td><p>从无法连接到 IM MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>AV MCU 不可用</p></td>
<td><p>AV MCU 不可用</p>
<p>查看 AV MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>之</p></td>
<td><p>从无法连接到 AV MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>AS MCU 不可用</p></td>
<td><p>AS MCU 不可用</p>
<p>查看 AS MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>之</p></td>
<td><p>从无法连接到 MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>数据 MCU 不可用</p></td>
<td><p>数据 MCU 不可用</p>
<p>查看数据 MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>之</p></td>
<td><p>从无法连接到数据 MCU 的故障中恢复</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>无法加入 IM MCU</p></td>
<td><p>无法加入 IM MCU</p>
<p>查看 IM MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>无法加入 AV MCU</p></td>
<td><p>无法加入 AV MCU</p>
<p>查看 AV MCU 是否正在运行</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>无法作为 MCU 加入</p></td>
<td><p>无法作为 MCU 加入</p>
<p>查看 AS MCU 是否正在运行</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>无法加入数据 MCU</p></td>
<td><p>无法加入数据 MCU</p>
<p>查看数据 MCU 是否正在运行</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>无法访问 active directory 中的照片</p></td>
<td><p>Active directory 的连接不可用</p>
<p>请确保与 active directory 的连接可用</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>之</p></td>
<td><p>从无法访问 active directory for photo 的故障中恢复</p></td>
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

