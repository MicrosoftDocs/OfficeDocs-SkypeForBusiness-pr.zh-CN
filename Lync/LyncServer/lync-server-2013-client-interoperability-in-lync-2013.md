---
title: Lync Server 2013： Lync 2013 中的客户端互操作性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Lync 2013 中的客户端互操作性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-03-04_

本主题讨论 Microsoft Lync Server 2013 客户端与早期版本的 Lync Server 和 Office 通信服务器之间共存并与客户端进行交互的能力。

<div>

## <a name="server-and-client-compatibility"></a>服务器和客户端兼容性

下表显示受支持的客户端版本和服务器版本的组合。 此表指示客户端尝试连接到指示的服务器时是否支持登录。 Lync Server 2013 支持以前的客户端版本。 此外，与以前的版本不同的是，Lync Server 2010 支持新的 Lync 2013 客户端。 这使得从 Lync Server 2010 升级的组织可以独立于 Lync Server 升级来部署新的客户端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>Supported5</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 组聊天</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>不 Supported3</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows 应用商店应用</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
</tbody>
</table>


1For 详细信息，请参阅[从 Lync server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync server 2013、持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

2In Microsoft Lync Server 2010，组聊天功能可用于 Lync Server 2010 的第三方受信任应用程序的组聊天服务器。 Lync 2013 客户端与 Lync Server 2010、组聊天不兼容。

3Lync Web App 2013 现在提供了完整的会议体验，包括计算机音频和视频，并被视为 Lync 2010 与会者的替代项。 仅当您使用不受支持的浏览器（Internet Explorer 6 或 Internet Explorer 7）和 Windows XP 时，lync 2010 与会者才会连接到 Lync Server 2013。

Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。 从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。

5有关限制，请参阅本主题后面的 "在 Lync Server 2010 会议中为 Lync 2013 客户端提供会议功能支持"。

</div>

<div>

## <a name="interoperability-among-clients"></a>客户端之间的互操作性

在 Lync Server 2013 版本中，各种客户端版本可以在对等和会议方案中无缝交互。 本部分讨论当用户与使用不同版本的客户端和服务器的其他用户进行交互时的功能可用性。

<div>

## <a name="peer-to-peer-feature-support"></a>对等功能支持

对于驻留在不同版本的服务器上的用户以及使用不同客户端版本的用户，支持对等功能。 最终用户体验和可用功能与用户客户端的功能和用户登录到的服务器版本一致。 换言之：

  - 如果用户使用旧版客户端登录到 Lync Server 2013，则用户将拥有自己使用的相同体验。 在升级用户的客户端之前，Lync Server 2013 中引入的所有新功能均不可用。 示例包括视频库视图、HD 视频、更新的 PowerPoint 共享以及在会议进入时将所有与会者音频和视频设为静音的选项。 [Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

  - 如果用户使用 Lync 2013 客户端登录到 Lync Server 2010，则在用户移动到 Lync Server 2013 之前，Lync Server 2010 不支持的任何新功能将不可用。

下表比较了客户端登录到 Lync Server 2013 或 Lync Server 2010 的对等会话中的功能可用性。

<div>


> [!NOTE]  
> Lync Web App 和 Lync 2010 与会者是仅会议客户端，不包括在此表中。



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>即时消息</th>
<th>状态</th>
<th>语音</th>
<th>视频</th>
<th>应用程序共享</th>
<th>文件传输</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>Yes1</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>公共 IM （AOL、Yahoo！）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公共 IM （MSN、Windows Live Messenger）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从9月1日起，2012，Microsoft Lync 公共 IM 连接用户订阅许可证（PIC USL）不再可用于购买新的或续订的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时消息连接</A>。。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</P></LI></UL>



</div>

1在 Office Communicator 2007 R2 中，仅有桌面共享（而非程序共享）可用。

<div>


> [!NOTE]  
> 如果强制实施 Skype for Business 2015 客户端用户界面，则无法从较新的客户端启动 Office Communicator 2007 R2 和 Skype for Business 2015 之间的桌面共享。



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 会议中 Lync 2013 客户端的会议功能支持

当用户使用 Lync 2013 客户端加入 Lync Server 2010 会议时，他们可以访问 Lync 2013 客户端功能，但有以下例外：

  - 在**参与者**管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，"**无会议即时消息**" 选项不起作用。

  - 库视图在视频会议中不起作用。 用户仅看到活动的扬声器，而不是所有扬声器。 在 "**选取布局**" 选项列表中，"**库视图**" 不可用

  - 默认情况下，参与者列表在视频会议中显示。

  - 右键单击 "参与者" 列表中的用户时，"**锁定视频焦点**并**固定到库**参与者管理" 选项不可用。

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 会议中的会议功能支持

Lync Server 2013 提供新的会议功能，这些功能在其帐户移动到 Lync Server 2013 并使用 Lync 2013 客户端登录后可供用户使用。 示例包括视频库视图、HD 视频、PowerPoint 共享，以及在会议进入时将所有与会者音频和视频设为静音的选项。 [Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

在 Lync Server 2013 会议中，某些会议功能对于驻留在不同版本的服务器上的用户以及使用不同客户端和客户端版本的用户都受支持。 当客户端加入 Lync Server 2013 会议时，用户可以访问此表中所示的特性和功能。


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>对等 IM</th>
<th>语音</th>
<th>视频</th>
<th>应用程序共享</th>
<th>PowerPoint</th>
<th>文件传输</th>
<th>Whiteboard</th>
<th>轮询</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是2</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>Yes3</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1在 Office Communicator 2007 R2 中，仅有桌面共享（而非程序共享）可用。

2 Lync Server 2013 使用更新的机制来上载 PowerPoint 文件。 加入最初在 Lync Server 2010 上安排的会议的 Lync Web App 用户可以查看和导航 PowerPoint 演示文稿，但不能上载 PowerPoint 文件。

3如果会议是在 Lync Server 2013 上安排的，并且 PowerPoint 幻灯片已由 Lync 2013 客户端上载，Lync 2010 用户可以仅查看对幻灯片的访问权限。 相反，如果 Lync 2010 用户上传了 PowerPoint 幻灯片，Lync Server 2013 用户将能够查看和幻灯片，如果配置了 Office Web Apps Server，则可以访问新的功能，例如更高分辨率的显示、动画、幻灯片切换和嵌入的视频。 有关详细信息，请参阅[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。 从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>计划加载项支持

对各种计划外接程序的服务器支持与服务器和客户端版本的兼容性一致。 通常情况下，以下计划外接程序在 Lync Server 2013 上受支持。 但是，早期版本的外接程序不提供新的 Lync 2013 外接程序功能，例如，在会议进入时将所有与会者音频和视频设为静音的选项。

  - **Lync 2013**   的联机会议外接程序提供了与 lync 2010 的联机会议外接程序相同的功能，并添加了 "与会者静音" 控件，使会议组织者可以计划默认情况下为与会者音频和视频静音的会议。 管理员还可以通过添加自定义徽标、支持 URL、合法免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。

  - **Lync 2010**   的联机会议外接程序为 lync 会议提供了计划，并删除了安排 Office Live 会议会议的功能。

  - **Office communicator 2007 r2 会议外接程序**   为 Office Live Meeting 会议和 office Communicator 2007 R2 会议提供计划。 

<div>


> [!NOTE]  
> 无法在 Lync Server 2013 上计划 Live Meeting 会议。



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>计划客户端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>适用于 Lync 2013 的联机会议外接程序（可与 Office 2013、Outlook 2010 和 Outlook 2007 一起使用）</p></td>
<td><p>支持</p></td>
<td><p>支持（新加载项功能不可用）</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web 计划程序</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Online Meeting Add-in for Lync 2010 － Lync 2010 联机会议外接程序</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 会议加载项</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>支持加入会议

允许 Lync Server 2013 支持的所有客户端加入 Lync 2013 会议。 由于 Lync web App 是服务器的 Web 组件，因此，如果使用 Lync Web App 加入 Lync Server 2013 会议，则始终使用最新版本的 Lync Web App。

Lync 2013 客户端可以加入在 Lync 2010 上托管的会议和 Office 通信服务器 2007 R2 （向下扩展功能）。 会议中的功能受托管会议的服务器版本的限制。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 的 lync Windows 应用商店应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 中的新会议功能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 中客户端的新增功能](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

