---
title: Lync Server 2013 简介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 892985a42e11a7f0b3466ad66e35ad5cf6c29ec4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 简介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

Lync Server 2013 及其客户端软件（如 Lync 2013）使用户能够以新的方式连接并保持连接状态，而不考虑其物理位置。 Lync 和 Lync Server 将人们在单个客户端界面中进行通信的不同方法组合在一起，作为一个统一的平台进行部署，并通过单个管理基础结构进行管理。

此表和以下各节说明了 Lync Server 为您的用户提供的主要功能集或*工作负荷*。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Workload</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 和状态</p></td>
<td><p>即时消息 (IM) 和状态可帮助用户有效且高效地找到对方并进行通信。</p>
<p>IM 提供了带有对话历史记录的即时消息平台，并支持与公共 IM 网络（如 MSN/Windows Live、Yahoo!、AOL 和 Google Talk）的用户进行公共 IM 连接。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>


</div>
<p>状态通过使用常用状态（如“空闲”<strong></strong>或“忙碌”<strong></strong>和更详细的状态（如“马上回来”<strong></strong>和“请勿打扰”<strong></strong>）建立并显示用户的个人空闲状况以及通信意愿。丰富的状态信息使其他用户可以立即做出有效的通信选择。</p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>Lync Server 包括对计划会议和即席会议的 IM 会议、音频会议、web 会议、视频会议和应用程序共享的支持。 单一客户端支持所有这些会议类型。 Lync Server 还支持电话拨入式会议，以便公共交换电话网络（PSTN）电话的用户可以参与会议的音频部分。</p>
<p>会议可以实时进行无缝地更改和发展。例如，单个会议可从一些用户之间的即时消息开始，并在无需中断对话流的情况下，即时轻松地升级到具有桌面共享和更多受众的音频会议。</p></td>
</tr>
<tr class="odd">
<td><p>企业语音</p></td>
<td><p><em>企业语音</em>是 Lync Server 中的 "语音 Over Internet 协议（VoIP）" 产品。 它提供了可增强或取代传统专用交换机 (PBX) 系统的语音选项。 除了 IP PBX 的完整电话功能，企业语音还集成了丰富的状态、IM、协作和会议功能。 直接支持诸如呼叫应答、呼叫保持、继续呼叫、呼叫转移、呼叫转接等功能，同时使用联系人列表取代个性化的快速拨号键，并使用 IM 取代自动对讲机。</p>
<p>企业语音通过呼叫允许控制 (CAC)、分支机构生存能力和数据恢复能力的扩展选项支持高可用性。</p></td>
</tr>
<tr class="even">
<td><p>支持远程用户</p></td>
<td><p>您可以通过部署称为 "<em>边缘服务器</em>" 的服务器来为这些远程用户提供连接，从而为当前位于您组织的防火墙外部的用户提供完整的 Lync Server 功能。 这些远程用户可以通过安装了安装了 Lync 2013 的个人计算机、电话或 web 界面来连接到会议。</p>
<p>通过部署边缘服务器，还可以与伙伴或供应商组织进行“联盟”<em></em>。联盟关系使您的用户可以将联盟用户加入联系人列表中，与联盟用户交换状态信息和即时消息，以及邀请他们加入音频呼叫、视频呼叫和会议。</p></td>
</tr>
<tr class="odd">
<td><p>移动客户端支持</p></td>
<td><p>此外，使用 Lync Server 移动服务，用户可以在使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备时访问 Lync 功能，并执行类似发送和接收即时消息、查看联系人等活动。和查看状态。 此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。 不支持在后台运行的应用程序的移动设备支持推送通知。</p></td>
</tr>
<tr class="even">
<td><p>与其他产品集成</p></td>
<td><p>Lync Server 与其他几个产品集成，以向用户和管理员提供更多好处。</p>
<p>会议工具已集成到 Outlook 中，使组织者能够通过一次单击安排会议或启动即席会议，并使与会者易于加入。</p>
<p>状态信息集成到了 Outlook 和 SharePoint 中。</p>
<p>Exchange 统一消息 (UM) 提供了多个集成功能。 用户可以查看他们是否在 Lync Server 中具有新的语音邮件。 他们可以在 Outlook 邮件中单击播放按钮收听音频语音邮件，或在通知邮件中查看语音邮件的转录。</p>
<p>此外，通过 Exchange 2013 运行 Lync Server 2013，还支持多个新功能，例如，两个产品的客户端可以访问的统一联系人存储库，以及存储在 Exchange 2013 数据库中的联系人的高分辨率照片。</p></td>
</tr>
<tr class="odd">
<td><p>简单部署</p></td>
<td><p>为了帮助您规划和部署服务器和客户端，Lync Server 提供拓扑生成器。</p>
<p>拓扑生成器是 Lync Server 的安装组件。 您可以使用拓扑生成器来创建、调整和发布规划的拓扑。 该工具还可以在开始安装服务器之前验证您的拓扑。 在单独的服务器上安装 Lync Server 时，安装程序将按照拓扑中的指导来部署服务器。</p></td>
</tr>
<tr class="even">
<td><p>简单管理</p></td>
<td><p>在部署 Lync Server 后，它提供了以下功能强大且简化的管理工具：</p>
<ul>
<li><p>中央配置管理，使您能够集中管理更改并使其迅速复制到整个部署中。</p></li>
<li><p>Lync Server 控制面板，面向管理员的基于 web 的图形用户界面。 通过这种基于 web 的 UI，Lync Server 管理员可以从公司网络的任何位置管理其系统，而无需在其计算机上安装专用管理软件。</p></li>
<li><p>Lync Server Management Shell 命令行管理工具，它基于 Windows PowerShell 命令行接口。 它提供了用于管理产品的所有方面的丰富命令集，并使 Lync Server 管理员能够使用熟悉的工具自动执行重复任务。</p></li>
</ul></td>
</tr>
</tbody>
</table>


尽管 IM 和状态功能会自动安装在每个 Lync Server 部署中，但你可以选择是否部署会议、企业语音和远程用户访问，以根据组织的需求进行部署。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的 IM 和状态](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 中的会议](lync-server-2013-conferencing.md)

  - [Lync Server 2013 中的企业语音](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013 的可伸缩性](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

