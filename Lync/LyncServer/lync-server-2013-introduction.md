---
title: Lync Server 2013 简介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 简介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

Lync Server 2013 及其客户端软件 (如 Lync 2013) 允许用户以新的方式连接和保持连接, 无论其物理位置如何。 Lync 和 Lync 服务器将人们在单个客户端界面中通信的不同方式结合在一起, 并将其部署为统一的平台, 并通过单个管理基础结构进行管理。

此表和以下部分介绍了 Lync Server 为你的用户提供的主要功能集或*工作负荷*。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>保证</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 和状态</p></td>
<td><p>即时消息 (IM) 和联机状态可帮助你的用户以高效和有效的方式与另一个用户查找和通信。</p>
<p>IM 提供了即时消息传递平台和对话历史记录, 并支持与公共 IM 网络用户 (如 MSN/Windows Live、Yahoo!、AOL 和 Google 通话) 的公共 IM 连接。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>


</div>
<p>状态: 通过使用公共状态 (如 "<strong>可用</strong>" 或 "<strong>忙碌</strong>"), 以及更详细的状态 (如 "<strong>立即返回</strong>" 和 "请勿打扰") 来确定用户的个人可用性和意愿<strong></strong>. 此丰富的状态信息使其他用户能够立即进行有效的通信选择。</p></td>
</tr>
<tr class="even">
<td><p>网络会议</p></td>
<td><p>Lync Server 包括对计划会议和即席会议的即时消息会议、音频会议、web 会议、视频会议和应用程序共享的支持。 所有这些会议类型均支持单个客户端。 Lync 服务器还支持电话拨入式会议, 以便公共交换电话网络 (PSTN) 手机的用户可以参与会议的音频部分。</p>
<p>会议可以实时无缝地进行更改和增长。 例如, 单个会议可以在几个用户之间启动即时消息, 并通过桌面共享和更大的受众即时、轻松且不中断对话流程提升到音频会议。</p></td>
</tr>
<tr class="odd">
<td><p>企业语音</p></td>
<td><p><em>企业语音</em>是 Lync Server 中的通过 Internet 协议 (VoIP) 提供的语音语音。 它提供了一个语音选项, 可增强或替换传统专用分支 exchange (PBX) 系统。 除了 IP PBX 的完整电话功能外, 企业语音还集成了丰富的状态、即时消息、协作和会议。 可直接支持呼叫应答、保持、恢复、转移、转发和转移等功能, 而个性化的快速拨号键将替换为 "联系人" 列表, 而自动 intercom 将被替换为即时消息。</p>
<p>企业语音支持通过呼叫许可控制 (CAC)、分支机构留存功能和扩展选项进行高可用性, 以便恢复数据。</p></td>
</tr>
<tr class="even">
<td><p>对远程用户的支持</p></td>
<td><p>通过部署名为<em>Edge 服务器</em>的服务器来为这些远程用户提供连接, 您可以为当前位于您的组织的防火墙之外的用户提供完整的 Lync Server 功能。 通过安装了安装了 Lync 2013 的个人计算机、电话或 web 界面, 这些远程用户可以连接到会议。</p>
<p>部署 Edge 服务器还使你能够与合作伙伴或供应商组织<em>联盟</em>。 联合关系使你的用户能够将联盟用户放在其联系人列表中、与这些用户交换状态信息和即时消息, 并邀请他们加入音频呼叫、视频通话和会议。</p></td>
</tr>
<tr class="odd">
<td><p>移动客户端支持</p></td>
<td><p>此外, 使用 Lync Server 移动服务, 用户可以在使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备时访问 Lync 功能, 并执行诸如发送和接收即时消息、查看联系人等活动。和查看状态。 此外, 移动设备支持某些企业语音功能, 例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。 对于不支持后台运行的应用程序的移动设备, 也支持推送通知。</p></td>
</tr>
<tr class="even">
<td><p>与其他产品集成</p></td>
<td><p>Lync Server 与多个其他产品集成, 为您的用户和管理员提供更多好处。</p>
<p>会议工具已集成到 Outlook 中, 使组织者可以通过单击一次来安排会议或开始即席会议, 并使与会者可以轻松加入会议。</p>
<p>联机状态信息集成到了 Outlook 和 SharePoint 中。</p>
<p>Exchange 统一消息 (UM) 提供多个集成功能。 用户可以在 Lync Server 中查看他们是否有新的语音邮件。 他们可以单击 Outlook 邮件中的 "播放" 按钮收听音频语音邮件, 或在通知消息中查看通话语音邮件。</p>
<p>此外, 通过 Exchange 2013 运行 Lync Server 2013 支持多项新功能, 例如统一联系人存储, 可供两种产品的客户端访问, 以及存储在 Exchange 2013 数据库中的联系人的高分辨率照片。</p></td>
</tr>
<tr class="odd">
<td><p>部署简单</p></td>
<td><p>为了帮助你规划和部署服务器和客户端, Lync Server 提供拓扑生成器。</p>
<p>拓扑生成器是 Lync Server 的安装组件。 你可以使用拓扑生成器创建、调整和发布你的计划拓扑。 它还会在您开始服务器安装之前验证您的拓扑。 在单个服务器上安装 Lync Server 时, 安装程序将按照拓扑中的指示部署服务器。</p></td>
</tr>
<tr class="even">
<td><p>简单的管理</p></td>
<td><p>部署 Lync Server 后, 它提供以下功能强大且优化的管理工具:</p>
<ul>
<li><p>中心配置管理, 使你能够集中管理更改, 并将其快速复制到整个部署。</p></li>
<li><p>Lync Server 控制面板, 面向管理员的基于 web 的图形用户界面。 通过这种基于 web 的 UI, Lync Server 管理员可以从公司网络上的任意位置管理其系统, 无需在其计算机上安装专用管理软件。</p></li>
<li><p>Lync Server Management Shell 命令行管理工具, 它基于 Windows PowerShell 命令行界面。 它提供了用于管理产品所有方面的丰富命令集, 并使 Lync 服务器管理员能够使用熟悉的工具自动执行重复任务。</p></li>
</ul></td>
</tr>
</tbody>
</table>


虽然即时消息和状态显示功能在每个 Lync Server 部署中自动安装, 但你可以选择是否部署会议、企业语音和远程用户访问, 以根据组织的需要调整部署。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的 IM 和状态](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 中的会议](lync-server-2013-conferencing.md)

  - [Lync Server 2013 中的企业语音](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013 可伸缩性](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

