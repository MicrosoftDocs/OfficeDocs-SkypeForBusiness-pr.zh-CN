---
title: Lync Server 2013 简介
TOCTitle: Lync Server 简介
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398795(v=OCS.15)
ms:contentKeyID: 49313711
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 简介

 

_**上一次修改主题：** 2015-03-09_

Lync Server 2013 及其客户端软件（例如 Lync 2013）使您的用户无论身在何处都可以使用新的方式进行连接并保持连接状态。 Lync 和 Lync Server 将用户在单一客户端接口上进行通信的不同方式整合在一起，部署为统一的平台，并通过单个管理基础结构进行管理。

此表和以下几节介绍了 Lync Server 为用户提供的主要功能集或“工作负荷”。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工作负荷</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 和状态</p></td>
<td><p>即时消息 (IM) 和状态可帮助用户有效且高效地找到对方并进行通信。</p>
<p>IM 提供了带有对话历史记录的即时消息平台，并支持与公共 IM 网络（如 MSN/Windows Live、Yahoo!、AOL 和 Google Talk）的用户进行公共 IM 连接。</p>

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>

</td>
<p>状态通过使用常用状态（如“空闲”或“忙碌”和更详细的状态（如“马上回来”和“请勿打扰”）建立并显示用户的个人空闲状况以及通信意愿。丰富的状态信息使其他用户可以立即做出有效的通信选择。</p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>Lync Server 支持 IM 会议、音频会议、Web 会议、视频会议和应用程序共享，预定会议和临时会议均适用。单一客户端支持所有这些会议类型。 Lync Server 还支持电话拨入式会议，以便公用电话交换网 (PSTN) 电话的用户可以参加会议的音频部分。</p>
<p>会议可以实时进行无缝地更改和发展。例如，单个会议可从一些用户之间的即时消息开始，并在无需中断对话流的情况下，即时轻松地升级到具有桌面共享和更多受众的音频会议。</p></td>
</tr>
<tr class="odd">
<td><p>企业语音</p></td>
<td><p>“企业语音”是 Lync Server 中的 IP 语音 (VoIP) 服务。它提供了可增强或取代传统专用交换机 (PBX) 系统的语音选项。除了 IP PBX 的完整电话功能，企业语音还集成了丰富的状态、IM、协作和会议功能。直接支持诸如呼叫应答、呼叫保持、继续呼叫、呼叫转移、呼叫转接等功能，同时使用联系人列表取代个性化的快速拨号键，并使用 IM 取代自动对讲机。</p>
<p>企业语音通过呼叫允许控制 (CAC)、分支机构生存能力和数据恢复能力的扩展选项支持高可用性。</p></td>
</tr>
<tr class="even">
<td><p>支持远程用户</p></td>
<td><p>通过部署称为“边缘服务器”的服务器为当前在组织防火墙之外的用户提供连接，可以为这些远程用户提供 Lync Server 的完整功能。这些远程用户可以通过使用安装有 Lync 2013 的个人计算机、电话或 Web 接口连接到会议。</p>
<p>通过部署边缘服务器，还可以与伙伴或供应商组织进行“<em>联盟</em>”。联盟关系使您的用户可以将联盟用户加入联系人列表中，与联盟用户交换状态信息和即时消息，以及邀请他们加入音频呼叫、视频呼叫和会议。</p></td>
</tr>
<tr class="odd">
<td><p>移动客户端支持</p></td>
<td><p>此外，利用 Lync Server 移动功能，您的用户可在使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备时访问 Lync 功能并执行发送和接收即时消息、查看联系人和查看状态等活动。此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。不支持在后台运行的应用程序的移动设备支持推送通知。</p></td>
</tr>
<tr class="even">
<td><p>与其他产品集成</p></td>
<td><p>Lync Server 与多个其他产品集成以向您的用户和管理员提供其他权益。</p>
<p>会议工具集成到 Outlook 中，使组织者可以通过一次单击安排会议或启动临时会议，并方便与会者加入会议。</p>
<p>状态信息将集成到 Outlook 和 SharePoint 中。</p>
<p>Exchange 统一消息 (UM) 提供了多个集成功能。用户可以查看 Lync Server 中是否有新的语音邮件。他们可以在 Outlook 邮件中单击播放按钮收听音频语音邮件，或在通知邮件中查看语音邮件的转录。</p>
<p>此外，运行带 Exchange 2013 的 Lync Server 2013 可启用多项新功能，例如，可通过这两种产品的客户端访问的统一的联系人存储库，以及存储在 Exchange 2013 数据库中的联系人的高分辨率照片。</p></td>
</tr>
<tr class="odd">
<td><p>简单部署</p></td>
<td><p>为了帮助您规划和部署服务器和客户端， Lync Server 提供了 拓扑生成器。</p>
<p></p>
<p>拓扑生成器是 Lync Server 的一个安装组件。使用 拓扑生成器可以创建、调整和发布您所规划的拓扑。该工具还可以在开始安装服务器之前验证您的拓扑。在各台服务器上安装 Lync Server 时，安装程序会按照拓扑中的指示来部署服务器。</p></td>
</tr>
<tr class="even">
<td><p>简单管理</p></td>
<td><p>部署 Lync Server 后，它会提供以下功能强大且简化的管理工具：</p>
<ul>
<li><p>中央配置管理，使您能够集中管理更改并使其迅速复制到整个部署中。</p></li>
<li><p>Lync Server 控制面板，面向管理员的基于 Web 的图形用户界面。通过此基于 Web 的 UI， Lync Server 管理员可以在企业网络的任何位置管理系统，而无需在计算机上安装专门的管理软件。</p></li>
<li><p>Lync Server 命令行管理程序命令行管理工具，基于 Windows PowerShell 命令行接口。该工具提供了一组丰富的命令以管理产品的所有方面，并使 Lync Server 管理员能够使用熟悉的工具自动处理重复任务。</p></li>
</ul></td>
</tr>
</tbody>
</table>


尽管 IM 和状态功能自动安装在所有的 Lync Server 部署中，但您可以选择是否部署会议、企业语音和远程用户访问，以根据组织的需求定制部署。

## 本部分内容

  - [Lync Server 2013 中的 IM 和状态](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 中的会议](lync-server-2013-conferencing.md)

  - [Lync Server 2013 中的企业语音](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013 可伸缩性](lync-server-2013-scalability.md)

