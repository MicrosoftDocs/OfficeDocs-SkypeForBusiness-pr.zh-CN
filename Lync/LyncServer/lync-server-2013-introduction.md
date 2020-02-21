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
ms.openlocfilehash: 2b25a989913db4e76b306eaaf7efba38612a2315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="cc01c-102">Lync Server 2013 简介</span><span class="sxs-lookup"><span data-stu-id="cc01c-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc01c-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="cc01c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="cc01c-104">Lync Server 2013 及其客户端软件（如 Lync 2013）使用户能够以新的方式连接并保持连接状态，而不考虑其物理位置。</span><span class="sxs-lookup"><span data-stu-id="cc01c-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="cc01c-105">Lync 和 Lync Server 将人们在单个客户端界面中进行通信的不同方法组合在一起，作为一个统一的平台进行部署，并通过单个管理基础结构进行管理。</span><span class="sxs-lookup"><span data-stu-id="cc01c-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="cc01c-106">此表和以下各节说明了 Lync Server 为您的用户提供的主要功能集或*工作负荷*。</span><span class="sxs-lookup"><span data-stu-id="cc01c-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc01c-107">Workload</span><span class="sxs-lookup"><span data-stu-id="cc01c-107">Workload</span></span></th>
<th><span data-ttu-id="cc01c-108">Description</span><span class="sxs-lookup"><span data-stu-id="cc01c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc01c-109">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="cc01c-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="cc01c-110">即时消息 (IM) 和状态可帮助用户有效且高效地找到对方并进行通信。</span><span class="sxs-lookup"><span data-stu-id="cc01c-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="cc01c-111">IM 提供了带有对话历史记录的即时消息平台，并支持与公共 IM 网络（如 MSN/Windows Live、Yahoo!、AOL 和 Google Talk）的用户进行公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="cc01c-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cc01c-112">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="cc01c-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cc01c-113">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="cc01c-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cc01c-114">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="cc01c-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="cc01c-115">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="cc01c-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cc01c-116">已宣布。</span><span class="sxs-lookup"><span data-stu-id="cc01c-116">has been announced.</span></span> <span data-ttu-id="cc01c-117">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="cc01c-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc01c-118">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="cc01c-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cc01c-119">Messenger.</span><span class="sxs-lookup"><span data-stu-id="cc01c-119">Messenger.</span></span> <span data-ttu-id="cc01c-120">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="cc01c-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc01c-121">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="cc01c-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cc01c-122">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="cc01c-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cc01c-123">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="cc01c-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="cc01c-p105">状态通过使用常用状态（如“空闲”<strong></strong>或“忙碌”<strong></strong>和更详细的状态（如“马上回来”<strong></strong>和“请勿打扰”<strong></strong>）建立并显示用户的个人空闲状况以及通信意愿。丰富的状态信息使其他用户可以立即做出有效的通信选择。</span><span class="sxs-lookup"><span data-stu-id="cc01c-p105">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>. This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc01c-126">会议</span><span class="sxs-lookup"><span data-stu-id="cc01c-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="cc01c-127">Lync Server 包括对计划会议和即席会议的 IM 会议、音频会议、web 会议、视频会议和应用程序共享的支持。</span><span class="sxs-lookup"><span data-stu-id="cc01c-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="cc01c-128">单一客户端支持所有这些会议类型。</span><span class="sxs-lookup"><span data-stu-id="cc01c-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="cc01c-129">Lync Server 还支持电话拨入式会议，以便公共交换电话网络（PSTN）电话的用户可以参与会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="cc01c-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="cc01c-p107">会议可以实时进行无缝地更改和发展。例如，单个会议可从一些用户之间的即时消息开始，并在无需中断对话流的情况下，即时轻松地升级到具有桌面共享和更多受众的音频会议。</span><span class="sxs-lookup"><span data-stu-id="cc01c-p107">Conferences can seamlessly change and grow in real time. For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc01c-132">企业语音</span><span class="sxs-lookup"><span data-stu-id="cc01c-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="cc01c-133"><em>企业语音</em>是 Lync Server 中的 "语音 Over Internet 协议（VoIP）" 产品。</span><span class="sxs-lookup"><span data-stu-id="cc01c-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="cc01c-134">它提供了可增强或取代传统专用交换机 (PBX) 系统的语音选项。</span><span class="sxs-lookup"><span data-stu-id="cc01c-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="cc01c-135">除了 IP PBX 的完整电话功能，企业语音还集成了丰富的状态、IM、协作和会议功能。</span><span class="sxs-lookup"><span data-stu-id="cc01c-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="cc01c-136">直接支持诸如呼叫应答、呼叫保持、继续呼叫、呼叫转移、呼叫转接等功能，同时使用联系人列表取代个性化的快速拨号键，并使用 IM 取代自动对讲机。</span><span class="sxs-lookup"><span data-stu-id="cc01c-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="cc01c-137">企业语音通过呼叫允许控制 (CAC)、分支机构生存能力和数据恢复能力的扩展选项支持高可用性。</span><span class="sxs-lookup"><span data-stu-id="cc01c-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc01c-138">支持远程用户</span><span class="sxs-lookup"><span data-stu-id="cc01c-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="cc01c-139">您可以通过部署称为 "<em>边缘服务器</em>" 的服务器来为这些远程用户提供连接，从而为当前位于您组织的防火墙外部的用户提供完整的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="cc01c-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="cc01c-140">这些远程用户可以通过安装了安装了 Lync 2013 的个人计算机、电话或 web 界面来连接到会议。</span><span class="sxs-lookup"><span data-stu-id="cc01c-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="cc01c-p110">通过部署边缘服务器，还可以与伙伴或供应商组织进行“联盟”<em></em>。联盟关系使您的用户可以将联盟用户加入联系人列表中，与联盟用户交换状态信息和即时消息，以及邀请他们加入音频呼叫、视频呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="cc01c-p110">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations. A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc01c-143">移动客户端支持</span><span class="sxs-lookup"><span data-stu-id="cc01c-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="cc01c-144">此外，使用 Lync Server 移动服务，用户可以在使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备时访问 Lync 功能，并执行类似发送和接收即时消息、查看联系人等活动。和查看状态。</span><span class="sxs-lookup"><span data-stu-id="cc01c-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="cc01c-145">此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。</span><span class="sxs-lookup"><span data-stu-id="cc01c-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="cc01c-146">不支持在后台运行的应用程序的移动设备支持推送通知。</span><span class="sxs-lookup"><span data-stu-id="cc01c-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc01c-147">与其他产品集成</span><span class="sxs-lookup"><span data-stu-id="cc01c-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="cc01c-148">Lync Server 与其他几个产品集成，以向用户和管理员提供更多好处。</span><span class="sxs-lookup"><span data-stu-id="cc01c-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="cc01c-149">会议工具已集成到 Outlook 中，使组织者能够通过一次单击安排会议或启动即席会议，并使与会者易于加入。</span><span class="sxs-lookup"><span data-stu-id="cc01c-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="cc01c-150">状态信息集成到了 Outlook 和 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="cc01c-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="cc01c-151">Exchange 统一消息 (UM) 提供了多个集成功能。</span><span class="sxs-lookup"><span data-stu-id="cc01c-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="cc01c-152">用户可以查看他们是否在 Lync Server 中具有新的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="cc01c-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="cc01c-153">他们可以在 Outlook 邮件中单击播放按钮收听音频语音邮件，或在通知邮件中查看语音邮件的转录。</span><span class="sxs-lookup"><span data-stu-id="cc01c-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="cc01c-154">此外，通过 Exchange 2013 运行 Lync Server 2013，还支持多个新功能，例如，两个产品的客户端可以访问的统一联系人存储库，以及存储在 Exchange 2013 数据库中的联系人的高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="cc01c-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc01c-155">简单部署</span><span class="sxs-lookup"><span data-stu-id="cc01c-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="cc01c-156">为了帮助您规划和部署服务器和客户端，Lync Server 提供拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="cc01c-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="cc01c-157">拓扑生成器是 Lync Server 的安装组件。</span><span class="sxs-lookup"><span data-stu-id="cc01c-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="cc01c-158">您可以使用拓扑生成器来创建、调整和发布规划的拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc01c-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="cc01c-159">该工具还可以在开始安装服务器之前验证您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc01c-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="cc01c-160">在单独的服务器上安装 Lync Server 时，安装程序将按照拓扑中的指导来部署服务器。</span><span class="sxs-lookup"><span data-stu-id="cc01c-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc01c-161">简单管理</span><span class="sxs-lookup"><span data-stu-id="cc01c-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="cc01c-162">在部署 Lync Server 后，它提供了以下功能强大且简化的管理工具：</span><span class="sxs-lookup"><span data-stu-id="cc01c-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc01c-163">中央配置管理，使您能够集中管理更改并使其迅速复制到整个部署中。</span><span class="sxs-lookup"><span data-stu-id="cc01c-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="cc01c-164">Lync Server 控制面板，面向管理员的基于 web 的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="cc01c-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="cc01c-165">通过这种基于 web 的 UI，Lync Server 管理员可以从公司网络的任何位置管理其系统，而无需在其计算机上安装专用管理软件。</span><span class="sxs-lookup"><span data-stu-id="cc01c-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="cc01c-166">Lync Server Management Shell 命令行管理工具，它基于 Windows PowerShell 命令行接口。</span><span class="sxs-lookup"><span data-stu-id="cc01c-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="cc01c-167">它提供了用于管理产品的所有方面的丰富命令集，并使 Lync Server 管理员能够使用熟悉的工具自动执行重复任务。</span><span class="sxs-lookup"><span data-stu-id="cc01c-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cc01c-168">尽管 IM 和状态功能会自动安装在每个 Lync Server 部署中，但你可以选择是否部署会议、企业语音和远程用户访问，以根据组织的需求进行部署。</span><span class="sxs-lookup"><span data-stu-id="cc01c-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc01c-169">本部分内容</span><span class="sxs-lookup"><span data-stu-id="cc01c-169">In This Section</span></span>

  - [<span data-ttu-id="cc01c-170">Lync Server 2013 中的 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="cc01c-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="cc01c-171">Lync Server 2013 中的会议</span><span class="sxs-lookup"><span data-stu-id="cc01c-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="cc01c-172">Lync Server 2013 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="cc01c-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="cc01c-173">Lync Server 2013 的可伸缩性</span><span class="sxs-lookup"><span data-stu-id="cc01c-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

