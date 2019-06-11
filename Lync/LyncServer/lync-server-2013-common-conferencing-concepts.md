---
title: 'Lync Server 2013: 常见的会议概念'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 240415ccdf8c0ab9be2eaf10304973b62c302c79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="886b7-102">Lync Server 2013 中的常见会议概念</span><span class="sxs-lookup"><span data-stu-id="886b7-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="886b7-103">_**主题上次修改时间:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="886b7-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="886b7-104">许多概念是所有类型的会议所共有的。</span><span class="sxs-lookup"><span data-stu-id="886b7-104">Several concepts are common to all types of conferencing.</span></span> <span data-ttu-id="886b7-105">以下部分将介绍这些内容。</span><span class="sxs-lookup"><span data-stu-id="886b7-105">These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="886b7-106">策略和带宽管理</span><span class="sxs-lookup"><span data-stu-id="886b7-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="886b7-107">Lync Server 2013 允许管理员为用户可组织的会议类型设置策略。</span><span class="sxs-lookup"><span data-stu-id="886b7-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="886b7-108">这可帮助你强制实施你的组织的策略和控制带宽使用。</span><span class="sxs-lookup"><span data-stu-id="886b7-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="886b7-109">你可以定义各种会议策略, 并将其分配给单个用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="886b7-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="886b7-110">还可以设置管理对等对话的策略。</span><span class="sxs-lookup"><span data-stu-id="886b7-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="886b7-111">有关设置会议策略的详细信息, 请参阅操作文档中[Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="886b7-112">有关带宽管理的详细信息, 请参阅[Lync server 2013 中的 "呼叫许可控制" 概述](lync-server-2013-overview-of-call-admission-control.md)和[在 lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="886b7-113">存档和合规性功能</span><span class="sxs-lookup"><span data-stu-id="886b7-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="886b7-114">如果您的组织必须遵守合规性法规, 则 Lync Server 2013 提供了可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="886b7-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="886b7-115">你可以使用存档功能来存档会议中显示的内容, 还可以使用即时消息 (IM) 对话和 IM 会议的内容。</span><span class="sxs-lookup"><span data-stu-id="886b7-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="886b7-116">有关详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="886b7-117">你可以使用持久聊天服务器的合规性功能来存档随时间变化的基于主题的多个对话。</span><span class="sxs-lookup"><span data-stu-id="886b7-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="886b7-118">有关详细信息, 请参阅规划文档中的在[Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="886b7-119">监视功能</span><span class="sxs-lookup"><span data-stu-id="886b7-119">Monitoring Feature</span></span>

<span data-ttu-id="886b7-120">监视服务器功能可以捕获呼叫详细记录 (CDRs), 您可以使用该记录跟踪与使用 Lync Server 2013 的其他用户交谈的用户。</span><span class="sxs-lookup"><span data-stu-id="886b7-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="886b7-121">有关部署和配置监视的详细信息, 请参阅[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="886b7-122">在会议中启用外部参与</span><span class="sxs-lookup"><span data-stu-id="886b7-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="886b7-123">通过使外部用户也可以在受邀的会议中参与会议, 您可以在 Lync Server 2013 会议中大大增加投资的优势。</span><span class="sxs-lookup"><span data-stu-id="886b7-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="886b7-124">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="886b7-124">External users can include:</span></span>

  - <span data-ttu-id="886b7-125">\*\*\*\*   当您的组织的用户在您的防火墙外工作且正在使用其笔记本或其他 Lync Server 2013 设备时, 您的组织自己的用户的远程用户。</span><span class="sxs-lookup"><span data-stu-id="886b7-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="886b7-126">**联合用户**   来自您与其他人同时运行 Lync Server 2013 的公司用户。</span><span class="sxs-lookup"><span data-stu-id="886b7-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="886b7-127">要使用户轻松与这些用户联系，应与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="886b7-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="886b7-128">**匿名用户**   由您的用户专门邀请的、用于加入特定会议的任何其他外部用户。</span><span class="sxs-lookup"><span data-stu-id="886b7-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="886b7-129">公司的会议组织者可以向外部用户发送电子邮件以邀请他们参加会议。</span><span class="sxs-lookup"><span data-stu-id="886b7-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="886b7-130">该电子邮件包含一个链接，外部用户通过单击该链接即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="886b7-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="886b7-131">若要启用任何或所有这些方案, 你需要部署边缘服务器以帮助在 Lync Server 2013 部署和外部用户之间实现安全通信。</span><span class="sxs-lookup"><span data-stu-id="886b7-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="886b7-132">使用 Edge 服务器的 Lync Server 2013 解决方案比其他解决方案 (如虚拟专用网络 (VPN)) 提供更高质量的媒体。</span><span class="sxs-lookup"><span data-stu-id="886b7-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="886b7-133">有关详细信息, 请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="886b7-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="886b7-134">此外, 无论是否部署 Edge 服务器, 您都可以启用从标准 PSTN 电话拨入的用户 (即组织内部或外部的用户) 以加入本地音频会议。</span><span class="sxs-lookup"><span data-stu-id="886b7-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="886b7-135">这可通过部署 Lync Server 2013 拨入式会议来完成。</span><span class="sxs-lookup"><span data-stu-id="886b7-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="886b7-136">会议类型和客户端版本之间的兼容性</span><span class="sxs-lookup"><span data-stu-id="886b7-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="886b7-137">如果您要让 Lync Server 2013 与以前版本的 Office 通信服务器及其客户端互操作, 则必须注意以下问题:</span><span class="sxs-lookup"><span data-stu-id="886b7-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="886b7-138">使用 Lync Server 2013 的用户无法安排 Live Meeting 会议或修改此类型的任何已迁移的会议。</span><span class="sxs-lookup"><span data-stu-id="886b7-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="886b7-139">使用 Lync Server 2013 的用户需要参与运行 Office 通信服务器 2007 R2 的服务器上托管的 Live Meeting 会议时, 其计算机上安装了 Live Meeting 客户端 (除了 Lync Server 2013), 以便参与这些会议。</span><span class="sxs-lookup"><span data-stu-id="886b7-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="886b7-140">当 Live Meeting 会议迁移到 Lync Server 2013 时, 会议内容不会迁移。</span><span class="sxs-lookup"><span data-stu-id="886b7-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="886b7-141">如果需要此内容, 必须重新上传。</span><span class="sxs-lookup"><span data-stu-id="886b7-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

