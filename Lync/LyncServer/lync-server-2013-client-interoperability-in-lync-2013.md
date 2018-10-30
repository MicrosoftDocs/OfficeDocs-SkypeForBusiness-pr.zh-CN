---
title: Lync Server 2013：Lync 2013 中的客户端互操作性
TOCTitle: Lync 2013 中的客户端互操作性
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204672(v=OCS.15)
ms:contentKeyID: 49312011
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 中的客户端互操作性

 

_**上一次修改主题：** 2016-03-04_

本主题讨论 Microsoft Lync Server 2013 客户端与早期版本的 Lync Server 和 Office Communications Server 客户端共存和交互的功能。

## 服务器和客户端兼容性

下表显示受支持的客户端版本和服务器版本组合。此表表明当客户端尝试连接到所指的服务器时是否支持登录。Lync Server 2013 支持以前的客户端版本。另外，与以前的版本不同，Lync Server 2010 支持新的 Lync 2013 客户端。这将允许从 Lync Server 2010 升级的组织独立于 Lync Server 升级推出新的客户端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>支持5</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本</p></td>
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
<td><p>Lync 2010 群聊</p></td>
<td><p>支持1</p></td>
<td><p>支持2</p></td>
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
<td><p>不支持3</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>可互操作4</p></td>
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


1有关详细信息，请参阅[从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

2在 Microsoft Lync Server 2010 中，群聊功能适用于群聊服务器，它是用于 Lync Server 2010 的第三方受信任应用程序。Lync 2013 客户端与 Lync Server 2010 群聊不兼容。

3Lync Web App 2013 现在提供一个完整的会议内体验，包括计算机音频和视频，可取代 Lync 2010 Attendee。只有当您使用不受支持的浏览器（Internet Explorer 6 或 Internet Explorer 7）和 Windows XP 时，Lync 2010 Attendee 才会连接到 Lync Server 2013。

4Office Communicator 2007 R2 中的状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。在从 Office Communications Server 2007 R2 迁移的过程中，Office Communicator 2007 R2 可提供状态和 IM 互操作性，但用户应使用 Lync Web App 2013 来加入 Lync Server 2013 会议。

5 有关限制，请参阅本主题后面部分中的“Lync Server 2010 会议中对 Lync 2013 客户端的会议功能支持”。

## 客户端之间的互操作性

使用 Lync Server 2013 版本，各种客户端版本都可以在对等和会议方案中无缝交互。本节讨论当用户与使用不同客户端和服务器版本的其他用户交互时的功能可用性。

## 对等功能支持

支持驻留在不同服务器版本上和使用不同客户端版本的用户利用对等功能。最终用户体验和可用功能与用户客户端的功能和用户登录到的服务器版本一致。换言之：

  - 如果用户通过旧客户端登录到 Lync Server 2013，用户获得的体验与以往一样。只有当用户客户端升级后，在 Lync Server 2013 中引入的新功能才可用。示例包括视频库视图、高清视频、PowerPoint 共享以及用于在进入会议时将所有与会者音频和视频静音的选项。[Lync Server 2013 中新的会议功能](lync-server-2013-new-conferencing-features.md)和 [Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)中概述了新功能。

  - 如果用户使用 Lync 2013 客户端登录到 Lync Server 2010，则只有当用户移至 Lync Server 2013 后，Lync Server 2010 所不支持的新功能才可用。

下表比较了在客户端登录到 Lync Server 2013 或 Lync Server 2010 的对等会话中功能的可用性。

> [!NOTE]  
> Lync Web App 和 Lync 2010 Attendee 只是会议类客户端，不包括在此表中。




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
<th>客户端</th>
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
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>是</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是1</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>公共 IM（AOL、Yahoo!）</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>公共 IM（MSN、Windows Live Messenger）</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 将不再用于购买新的或续订协议。具有活动许可证的客户将能继续与 Yahoo! Messenger 联盟，直到服务关闭日期。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的每用户、每月订阅许可证。Microsoft 是否能够提供此服务视 Yahoo! 的支持而定，将不续订 Yahoo! 的底层协议。</p></li>
> <li><p>与以往相比，Lync 是一个更强大的工具，可用于跨多个组织进行联系以及与世界各地的各个用户进行联系。与 Windows Live Messenger 联盟无需 Lync Standard CAL 之外的其他任何用户/设备许可证。Skype 联盟将添加到此列表，使 Lync 用户能够通过 IM 和语音与数亿人联系。</p></li>
> </ul>


1 在 Office Communicator 2007 R2 中，仅桌面共享（而非程序共享）可用。

## Lync Server 2010 会议中对 Lync 2013 客户端的会议功能支持

当用户使用 Lync 2013 客户端加入 Lync Server 2010 会议时，用户可以访问 Lync 2013 客户端功能，但存在以下例外：

  - 在“参与者”管理选项（通过在会议窗口中指向人员图标可以访问这些选项）中，“关闭会议即时消息”选项不起作用。

  - 在视频会议中，“库视图”不起作用。用户只能看到当前发言人，而不是看到所有发言人。在“选择布局”选项中，“库视图”不可用。

  - 在视频会议中，默认情况下显示参与者列表。

  - 在参与者列表中右键单击用户时，“锁定视频焦点”和“固定至库”参与者管理选项不可用。

## Lync Server 2013 会议中的会议功能支持

Lync Server 2013 提供了新的会议功能，当用户的帐户移动到 Lync Server 2013 并且使用 Lync 2013 客户端登录之后，能够使用这些功能。示例包括视频库视图、高清视频、PowerPoint 共享以及用于在进入会议时将所有与会者音频和视频静音的选项。[Lync Server 2013 中新的会议功能](lync-server-2013-new-conferencing-features.md)和[Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)中概述了新功能。

在 Lync Server 2013 会议中，支持驻留在不同服务器版本上和使用不同客户端和客户端版本的用户利用特定会议功能。当客户端加入 Lync Server 2013 会议时，用户可以访问下表所示的特性和功能：


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
<th>客户端</th>
<th>对等 IM</th>
<th>语音</th>
<th>视频</th>
<th>应用程序共享</th>
<th>PowerPoint</th>
<th>文件传输</th>
<th>白板</th>
<th>轮询</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持2</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>是3</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R24</p></td>
<td><p>是</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


1 在 Office Communicator 2007 R2 中，仅桌面共享（而非程序共享）可用。

2Lync Server 2013 使用一种更新机制来上传 PowerPoint 文件。加入 Lync Server 2010 上某个原定会议的 Lync Web App 用户可以查看和导航 PowerPoint 演示文稿，但不能上传 PowerPoint 文件。

3 如果在 Lync Server 2013 上安排了该会议，并且 PowerPoint 幻灯片是由某个 Lync 2013 客户端上载的，则 Lync 2010 用户只能查看这些幻灯片。相反，如果 PowerPoint 幻灯片是由某个 Lync 2010 用户上载的，Lync Server 2013 用户将能够查看这些幻灯片，如果已配置 Office Web Apps 服务器，那么他们能够访问较高分辨率显示、动画、幻灯片切换和嵌入视频等新功能。有关详细信息，请参阅[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

4Office Communicator 2007 R2 中的状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。在从 Office Communications Server 2007 R2 迁移的过程中， Office Communicator 2007 R2 可提供状态和 IM 互操作性，但用户应使用 Lync Web App 2013 来加入 Lync Server 2013 会议。

## 日程安排外接程序支持

对各种日程安排外接程序的服务器支持与服务器和客户端版本兼容性保持一致。通常，Lync Server 2013 支持以下日程安排外接程序。但是，早期版本的外接程序不提供新的 Lync 2013 外接程序功能，例如加入会议后使所有与会者的音频和视频静音的选项。

  - **Lync 2013 联机会议外接程序**   除了提供与 Lync 2010 在线会议外接程序相同的功能外，还提供与会者静音控件，以允许会议组织者安排将与会者音频和视频默认静音的会议。管理员还可以通过添加自定义徽标、支持 URL、法律免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。

  - **Lync 2010 联机会议外接程序**   为 Lync 会议提供日程安排功能，并删除了安排 Office Live Meeting 会议的功能。

  - **Office Communicator 2007 R2 会议外接程序**   同时为 Office Live Meeting 会议和 Office Communicator 2007 R2 会议提供日程安排功能。 

> [!NOTE]  
> 不能在 Lync Server 2013 上安排 Live Meeting 会议。




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
<td><p>Lync 2013 联机会议外接程序（可与 Office 2013、Outlook 2010 和 Outlook 2007 结合使用）</p></td>
<td><p>支持</p></td>
<td><p>支持（新的外接程序功能不可用）</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web 计划程序</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 联机会议外接程序</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 会议外接程序</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
</tbody>
</table>


## 支持加入会议

允许 Lync Server 2013 支持的所有客户端加入 Lync 2013 会议。因为 Lync Web App 是服务器的一个 Web 组件，所以当 Lync Web App 用于加入 Lync Server 2013 会议时，总是使用 Lync Web App 的较新版本。

Lync 2013 客户端可以利用缩减功能加入 Lync 2010 和 Office Communications Server 2007 R2 上承载的会议。会议内功能受到承载会议的服务器的版本限制。

## 另请参阅

#### 概念

[Lync Windows Store 应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 中新的会议功能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)

