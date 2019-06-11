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

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="09902-102">Lync Server 2013 简介</span><span class="sxs-lookup"><span data-stu-id="09902-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09902-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="09902-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="09902-104">Lync Server 2013 及其客户端软件 (如 Lync 2013) 允许用户以新的方式连接和保持连接, 无论其物理位置如何。</span><span class="sxs-lookup"><span data-stu-id="09902-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="09902-105">Lync 和 Lync 服务器将人们在单个客户端界面中通信的不同方式结合在一起, 并将其部署为统一的平台, 并通过单个管理基础结构进行管理。</span><span class="sxs-lookup"><span data-stu-id="09902-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="09902-106">此表和以下部分介绍了 Lync Server 为你的用户提供的主要功能集或*工作负荷*。</span><span class="sxs-lookup"><span data-stu-id="09902-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09902-107">保证</span><span class="sxs-lookup"><span data-stu-id="09902-107">Workload</span></span></th>
<th><span data-ttu-id="09902-108">说明</span><span class="sxs-lookup"><span data-stu-id="09902-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09902-109">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="09902-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="09902-110">即时消息 (IM) 和联机状态可帮助你的用户以高效和有效的方式与另一个用户查找和通信。</span><span class="sxs-lookup"><span data-stu-id="09902-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="09902-111">IM 提供了即时消息传递平台和对话历史记录, 并支持与公共 IM 网络用户 (如 MSN/Windows Live、Yahoo!、AOL 和 Google 通话) 的公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="09902-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="09902-112">从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="09902-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="09902-113">具有活动许可证的客户将能够继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="09902-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="09902-114">Messenger, 直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="09902-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="09902-115">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="09902-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="09902-116">已宣布。</span><span class="sxs-lookup"><span data-stu-id="09902-116">has been announced.</span></span> <span data-ttu-id="09902-117">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="09902-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="09902-118">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="09902-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="09902-119">Messenger.</span><span class="sxs-lookup"><span data-stu-id="09902-119">Messenger.</span></span> <span data-ttu-id="09902-120">Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="09902-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="09902-121">Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="09902-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="09902-122">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="09902-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="09902-123">Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="09902-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="09902-124">状态: 通过使用公共状态 (如 "<strong>可用</strong>" 或 "<strong>忙碌</strong>"), 以及更详细的状态 (如 "<strong>立即返回</strong>" 和 "请勿打扰") 来确定用户的个人可用性和意愿<strong></strong>.</span><span class="sxs-lookup"><span data-stu-id="09902-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="09902-125">此丰富的状态信息使其他用户能够立即进行有效的通信选择。</span><span class="sxs-lookup"><span data-stu-id="09902-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09902-126">网络会议</span><span class="sxs-lookup"><span data-stu-id="09902-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="09902-127">Lync Server 包括对计划会议和即席会议的即时消息会议、音频会议、web 会议、视频会议和应用程序共享的支持。</span><span class="sxs-lookup"><span data-stu-id="09902-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="09902-128">所有这些会议类型均支持单个客户端。</span><span class="sxs-lookup"><span data-stu-id="09902-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="09902-129">Lync 服务器还支持电话拨入式会议, 以便公共交换电话网络 (PSTN) 手机的用户可以参与会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="09902-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="09902-130">会议可以实时无缝地进行更改和增长。</span><span class="sxs-lookup"><span data-stu-id="09902-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="09902-131">例如, 单个会议可以在几个用户之间启动即时消息, 并通过桌面共享和更大的受众即时、轻松且不中断对话流程提升到音频会议。</span><span class="sxs-lookup"><span data-stu-id="09902-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09902-132">企业语音</span><span class="sxs-lookup"><span data-stu-id="09902-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="09902-133"><em>企业语音</em>是 Lync Server 中的通过 Internet 协议 (VoIP) 提供的语音语音。</span><span class="sxs-lookup"><span data-stu-id="09902-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="09902-134">它提供了一个语音选项, 可增强或替换传统专用分支 exchange (PBX) 系统。</span><span class="sxs-lookup"><span data-stu-id="09902-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="09902-135">除了 IP PBX 的完整电话功能外, 企业语音还集成了丰富的状态、即时消息、协作和会议。</span><span class="sxs-lookup"><span data-stu-id="09902-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="09902-136">可直接支持呼叫应答、保持、恢复、转移、转发和转移等功能, 而个性化的快速拨号键将替换为 "联系人" 列表, 而自动 intercom 将被替换为即时消息。</span><span class="sxs-lookup"><span data-stu-id="09902-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="09902-137">企业语音支持通过呼叫许可控制 (CAC)、分支机构留存功能和扩展选项进行高可用性, 以便恢复数据。</span><span class="sxs-lookup"><span data-stu-id="09902-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09902-138">对远程用户的支持</span><span class="sxs-lookup"><span data-stu-id="09902-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="09902-139">通过部署名为<em>Edge 服务器</em>的服务器来为这些远程用户提供连接, 您可以为当前位于您的组织的防火墙之外的用户提供完整的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="09902-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="09902-140">通过安装了安装了 Lync 2013 的个人计算机、电话或 web 界面, 这些远程用户可以连接到会议。</span><span class="sxs-lookup"><span data-stu-id="09902-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="09902-141">部署 Edge 服务器还使你能够与合作伙伴或供应商组织<em>联盟</em>。</span><span class="sxs-lookup"><span data-stu-id="09902-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="09902-142">联合关系使你的用户能够将联盟用户放在其联系人列表中、与这些用户交换状态信息和即时消息, 并邀请他们加入音频呼叫、视频通话和会议。</span><span class="sxs-lookup"><span data-stu-id="09902-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09902-143">移动客户端支持</span><span class="sxs-lookup"><span data-stu-id="09902-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="09902-144">此外, 使用 Lync Server 移动服务, 用户可以在使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备时访问 Lync 功能, 并执行诸如发送和接收即时消息、查看联系人等活动。和查看状态。</span><span class="sxs-lookup"><span data-stu-id="09902-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="09902-145">此外, 移动设备支持某些企业语音功能, 例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="09902-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="09902-146">对于不支持后台运行的应用程序的移动设备, 也支持推送通知。</span><span class="sxs-lookup"><span data-stu-id="09902-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09902-147">与其他产品集成</span><span class="sxs-lookup"><span data-stu-id="09902-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="09902-148">Lync Server 与多个其他产品集成, 为您的用户和管理员提供更多好处。</span><span class="sxs-lookup"><span data-stu-id="09902-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="09902-149">会议工具已集成到 Outlook 中, 使组织者可以通过单击一次来安排会议或开始即席会议, 并使与会者可以轻松加入会议。</span><span class="sxs-lookup"><span data-stu-id="09902-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="09902-150">联机状态信息集成到了 Outlook 和 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="09902-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="09902-151">Exchange 统一消息 (UM) 提供多个集成功能。</span><span class="sxs-lookup"><span data-stu-id="09902-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="09902-152">用户可以在 Lync Server 中查看他们是否有新的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="09902-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="09902-153">他们可以单击 Outlook 邮件中的 "播放" 按钮收听音频语音邮件, 或在通知消息中查看通话语音邮件。</span><span class="sxs-lookup"><span data-stu-id="09902-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="09902-154">此外, 通过 Exchange 2013 运行 Lync Server 2013 支持多项新功能, 例如统一联系人存储, 可供两种产品的客户端访问, 以及存储在 Exchange 2013 数据库中的联系人的高分辨率照片。</span><span class="sxs-lookup"><span data-stu-id="09902-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09902-155">部署简单</span><span class="sxs-lookup"><span data-stu-id="09902-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="09902-156">为了帮助你规划和部署服务器和客户端, Lync Server 提供拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="09902-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="09902-157">拓扑生成器是 Lync Server 的安装组件。</span><span class="sxs-lookup"><span data-stu-id="09902-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="09902-158">你可以使用拓扑生成器创建、调整和发布你的计划拓扑。</span><span class="sxs-lookup"><span data-stu-id="09902-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="09902-159">它还会在您开始服务器安装之前验证您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="09902-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="09902-160">在单个服务器上安装 Lync Server 时, 安装程序将按照拓扑中的指示部署服务器。</span><span class="sxs-lookup"><span data-stu-id="09902-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09902-161">简单的管理</span><span class="sxs-lookup"><span data-stu-id="09902-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="09902-162">部署 Lync Server 后, 它提供以下功能强大且优化的管理工具:</span><span class="sxs-lookup"><span data-stu-id="09902-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="09902-163">中心配置管理, 使你能够集中管理更改, 并将其快速复制到整个部署。</span><span class="sxs-lookup"><span data-stu-id="09902-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="09902-164">Lync Server 控制面板, 面向管理员的基于 web 的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="09902-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="09902-165">通过这种基于 web 的 UI, Lync Server 管理员可以从公司网络上的任意位置管理其系统, 无需在其计算机上安装专用管理软件。</span><span class="sxs-lookup"><span data-stu-id="09902-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="09902-166">Lync Server Management Shell 命令行管理工具, 它基于 Windows PowerShell 命令行界面。</span><span class="sxs-lookup"><span data-stu-id="09902-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="09902-167">它提供了用于管理产品所有方面的丰富命令集, 并使 Lync 服务器管理员能够使用熟悉的工具自动执行重复任务。</span><span class="sxs-lookup"><span data-stu-id="09902-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="09902-168">虽然即时消息和状态显示功能在每个 Lync Server 部署中自动安装, 但你可以选择是否部署会议、企业语音和远程用户访问, 以根据组织的需要调整部署。</span><span class="sxs-lookup"><span data-stu-id="09902-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09902-169">本节内容</span><span class="sxs-lookup"><span data-stu-id="09902-169">In This Section</span></span>

  - [<span data-ttu-id="09902-170">Lync Server 2013 中的 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="09902-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="09902-171">Lync Server 2013 中的会议</span><span class="sxs-lookup"><span data-stu-id="09902-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="09902-172">Lync Server 2013 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="09902-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="09902-173">Lync Server 2013 可伸缩性</span><span class="sxs-lookup"><span data-stu-id="09902-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

