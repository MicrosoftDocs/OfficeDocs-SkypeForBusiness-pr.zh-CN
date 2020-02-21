---
title: Lync Server 2013：常见会议概念
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2afd309f59a66a7117d43b930500a7807d493d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="c459a-102">Lync Server 2013 中的常见会议概念</span><span class="sxs-lookup"><span data-stu-id="c459a-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c459a-103">_**上次修改的主题：** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="c459a-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="c459a-p101">有几个概念对所有类型的会议是通用的。这些概念将在以下章节中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="c459a-p101">Several concepts are common to all types of conferencing. These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="c459a-106">策略和带宽管理</span><span class="sxs-lookup"><span data-stu-id="c459a-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="c459a-107">Lync Server 2013 使管理员能够为用户可组织的会议类型设置策略。</span><span class="sxs-lookup"><span data-stu-id="c459a-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="c459a-108">这有助于实施组织的策略和控制带宽使用情况。</span><span class="sxs-lookup"><span data-stu-id="c459a-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="c459a-109">您可以定义各种会议策略，并将其分配给各个用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="c459a-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="c459a-110">还可以设置用于管理对等对话的策略。</span><span class="sxs-lookup"><span data-stu-id="c459a-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="c459a-111">有关设置会议策略的详细信息，请参阅操作文档中的[Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="c459a-112">有关带宽管理的详细信息，请参阅[Lync server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)和[在 lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="c459a-113">存档与合规性功能</span><span class="sxs-lookup"><span data-stu-id="c459a-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="c459a-114">如果您的组织必须遵循合规性管理法规，Lync Server 2013 提供了您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c459a-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="c459a-115">您可以使用存档功能存档会议中呈现的内容，以及即时消息 (IM) 对话和 IM 会议内容。</span><span class="sxs-lookup"><span data-stu-id="c459a-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="c459a-116">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="c459a-117">您可以使用持久聊天服务器的合规性功能存档基于主题的多方持续对话。</span><span class="sxs-lookup"><span data-stu-id="c459a-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c459a-118">有关详细信息，请参阅规划文档中的在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="c459a-119">监控功能</span><span class="sxs-lookup"><span data-stu-id="c459a-119">Monitoring Feature</span></span>

<span data-ttu-id="c459a-120">监视服务器功能可以捕获呼叫详细信息记录（Cdr），您可以使用它来跟踪哪些用户与使用 Lync Server 2013 的其他用户通信。</span><span class="sxs-lookup"><span data-stu-id="c459a-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="c459a-121">有关部署和配置监控的详细信息，请参阅[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="c459a-122">允许外部参加会议</span><span class="sxs-lookup"><span data-stu-id="c459a-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="c459a-123">您可以通过让外部用户也在受邀时加入会议，从而大大提高您的投资在 Lync Server 2013 会议中的优势。</span><span class="sxs-lookup"><span data-stu-id="c459a-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="c459a-124">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="c459a-124">External users can include:</span></span>

  - <span data-ttu-id="c459a-125">\*\*\*\*   当您的组织的用户在防火墙外工作并使用其便携式计算机或其他 Lync Server 2013 设备时，远程用户自己的用户。</span><span class="sxs-lookup"><span data-stu-id="c459a-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="c459a-126">**联合用户**   来自公司的用户也可以使用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c459a-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="c459a-127">若要使您的用户能够轻松地与这些用户联系，您可以创建与这些公司的联盟关系。</span><span class="sxs-lookup"><span data-stu-id="c459a-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="c459a-128">**匿名用户**   由您的用户专门邀请以加入特定会议的任何其他外部用户。</span><span class="sxs-lookup"><span data-stu-id="c459a-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="c459a-129">公司中的会议组织者可以向外部用户发送会议的电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="c459a-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="c459a-130">该电子邮件包含外部用户可单击以加入会议的链接。</span><span class="sxs-lookup"><span data-stu-id="c459a-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="c459a-131">若要启用任何或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 2013 部署和外部用户之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="c459a-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="c459a-132">使用边缘服务器的 Lync Server 2013 解决方案可提供比其他解决方案（如虚拟专用网络（VPN））更高的媒体质量。</span><span class="sxs-lookup"><span data-stu-id="c459a-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="c459a-133">有关详细信息，请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c459a-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="c459a-134">此外，无论是否部署边缘服务器，用户（即，组织内部或外部）都可以通过标准 PSTN 电话拨入以加入内部音频会议。</span><span class="sxs-lookup"><span data-stu-id="c459a-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="c459a-135">这是通过部署 Lync Server 2013 电话拨入式会议来实现的。</span><span class="sxs-lookup"><span data-stu-id="c459a-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="c459a-136">会议类型和客户端版本之间的兼容性</span><span class="sxs-lookup"><span data-stu-id="c459a-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="c459a-137">如果您将 Lync Server 2013 与 Office 通信服务器及其客户端的早期版本进行互操作，则必须注意以下问题：</span><span class="sxs-lookup"><span data-stu-id="c459a-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="c459a-138">使用 Lync Server 2013 的用户无法安排 Live Meeting 会议，也无法修改此类型的任何已迁移的会议。</span><span class="sxs-lookup"><span data-stu-id="c459a-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="c459a-139">使用 Lync Server 2013 的用户需要参加运行 Office 通信服务器 2007 R2 的服务器上的 Live Meeting 会议的用户必须在其计算机上安装 Live Meeting 客户端（除了 Lync Server 2013），才能参加这些会议。</span><span class="sxs-lookup"><span data-stu-id="c459a-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="c459a-140">当 Live Meeting 会议迁移到 Lync Server 2013 时，会议内容不会迁移。</span><span class="sxs-lookup"><span data-stu-id="c459a-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="c459a-141">如果需要此内容，则必须重新上载。</span><span class="sxs-lookup"><span data-stu-id="c459a-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

