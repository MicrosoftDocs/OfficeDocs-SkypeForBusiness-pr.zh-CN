---
title: Lync Server 2013：注册视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf0e0edd69685af866905fea08144de327c446c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536579"
---
# <a name="registration-view-in-lync-server-2013"></a>Lync Server 2013 中的 "注册" 视图

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

注册视图存储有关用户注册的信息。 此视图是在 Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>注册发生的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450) </p></td>
<td><p>注册用户的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>注册用户的 URI 的类型。 有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>注册用户的租户。 有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>用户注册使用的终结点的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>用于区分涉及相同用户和相同终结点的注册的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>取消注册发生的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>取消注册的原因。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>注册用户使用的客户端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>注册用户使用的客户端。 有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64) </p></td>
<td><p>注册用户使用的客户端的类别。</p></td>
</tr>
<tr class="even">
<td><p><strong>址</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>用户注册使用的 IP 地址。 这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775) </p></td>
<td><p>SIP 对话 ID。格式如下：</p>
<p>对话框; 从-标签; 到-标记</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>从 SIP 标头捕获的诊断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>注册</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>注册器的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>已捕获会话的数据的池的 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>注册用户使用的边缘服务器的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>位</p></td>
<td><p>指示用户是否是从内部网络登录的。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>位</p></td>
<td><p>指示 UserService 在注册时是否可用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>位</p></td>
<td><p>指示注册是否是使用主注册器的注册。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>已注册设备的 MAC 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>已注册设备的制造商。 有关详细信息，请参阅 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>已注册设备的硬件版本。 有关详细信息，请参阅 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

