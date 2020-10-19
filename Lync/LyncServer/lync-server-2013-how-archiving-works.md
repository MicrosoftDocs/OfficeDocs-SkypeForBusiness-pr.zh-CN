---
title: Lync Server 2013：存档的工作方式
description: Lync Server 2013：存档的工作方式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543378"
---
# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="8129a-103">Lync Server 2013 中的存档工作原理</span><span class="sxs-lookup"><span data-stu-id="8129a-103">How Archiving works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8129a-104">_**上次修改的主题：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="8129a-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="8129a-105">Lync Server 2013 存档提供了可帮助您满足合规性需求的选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-105">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="8129a-106">若要以最有效地满足组织要求的方式实施和维护它，应了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="8129a-106">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="8129a-107">可以存档的信息。</span><span class="sxs-lookup"><span data-stu-id="8129a-107">What information can be archived.</span></span>

  - <span data-ttu-id="8129a-108">如何在您的部署中启用和禁用存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-108">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="8129a-109">可以配置以控制如何实现存档的存档选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-109">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="8129a-110">可以存档哪些信息？</span><span class="sxs-lookup"><span data-stu-id="8129a-110">What Information Can Be Archived?</span></span>

<span data-ttu-id="8129a-111">可以存档以下类型的内容：</span><span class="sxs-lookup"><span data-stu-id="8129a-111">The following types of content can be archived:</span></span>

  - <span data-ttu-id="8129a-112">对等即时消息</span><span class="sxs-lookup"><span data-stu-id="8129a-112">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="8129a-113">多方即时消息的会议</span><span class="sxs-lookup"><span data-stu-id="8129a-113">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="8129a-114">会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）</span><span class="sxs-lookup"><span data-stu-id="8129a-114">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="8129a-115">会议期间共享的白板和投票</span><span class="sxs-lookup"><span data-stu-id="8129a-115">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="8129a-116">不存档以下类型的内容：</span><span class="sxs-lookup"><span data-stu-id="8129a-116">The following types of content are not archived:</span></span>

  - <span data-ttu-id="8129a-117">对等文件传输</span><span class="sxs-lookup"><span data-stu-id="8129a-117">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="8129a-118">对等即时消息和会议的音频/视频</span><span class="sxs-lookup"><span data-stu-id="8129a-118">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="8129a-119">对等即时消息和会议的桌面和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="8129a-119">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="8129a-120">Lync Server 也不会存档持久聊天对话。</span><span class="sxs-lookup"><span data-stu-id="8129a-120">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="8129a-121">若要存档持久聊天对话，您必须启用和配置合规性服务，该服务是可以使用 Microsoft Lync Server 2013、持久聊天服务器部署的组件。</span><span class="sxs-lookup"><span data-stu-id="8129a-121">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8129a-122">有关详细信息，请参阅规划文档中的在 [Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-122">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="8129a-123">如何开始使用存档？</span><span class="sxs-lookup"><span data-stu-id="8129a-123">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="8129a-p103">部署每台前端服务器时将自动在该服务器上安装存档，但存档在您配置之前不会启用。配置存档的方式由存档的部署方式决定：</span><span class="sxs-lookup"><span data-stu-id="8129a-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="8129a-126">**使用 Microsoft Exchange 集成进行存档。**</span><span class="sxs-lookup"><span data-stu-id="8129a-126">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="8129a-127">如果您有托管在 Exchange 2013 上的用户，并且已将其邮箱置于 In-Place 保留状态，则可以选择将 Lync Server 2013 存储与 Exchange 存储集成的选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-127">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="8129a-128">如果选择 "Microsoft Exchange 集成" 选项，请使用 Exchange 2013 策略和配置来控制这些用户的 Lync Server 2013 数据的存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-128">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="8129a-129">**使用 Lync Server 存档数据库的存档。**</span><span class="sxs-lookup"><span data-stu-id="8129a-129">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="8129a-130">如果您有未驻留在 Exchange 2013 上的用户或未将其邮箱置于 In-Place 保留状态的用户，或者如果您不希望对部署中的任何用户或所有用户使用 Microsoft Exchange 集成，则可以使用 SQL Server 部署 Lync Server 存档数据库，以存储这些用户的存档数据。</span><span class="sxs-lookup"><span data-stu-id="8129a-130">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="8129a-131">在这种情况下，Lync Server 2013 存档策略和配置将确定是否启用存档以及如何实现存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-131">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="8129a-132">若要使用 Lync Server 2013，您必须将相应的 SQL Server 数据库添加到拓扑中并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="8129a-132">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="8129a-133">使用 Microsoft Exchange 集成时的存档设置</span><span class="sxs-lookup"><span data-stu-id="8129a-133">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="8129a-134">如果您的用户托管在 Exchange 2013 上，并且已将其邮箱置于 In-Place 保留状态，则可以选择 " **Microsoft Exchange 集成** " 选项 (如本节后面所述) 为这些用户存档 Lync Server 2013，然后通过指定 Exchange In-Place 保留策略和设置来控制这些用户的存档，以及控制以下各项的 Lync server 配置：</span><span class="sxs-lookup"><span data-stu-id="8129a-134">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="8129a-135">是否存档 IM、会议或二者。</span><span class="sxs-lookup"><span data-stu-id="8129a-135">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="8129a-136">是否为 Lync Server 部署实现关键模式。</span><span class="sxs-lookup"><span data-stu-id="8129a-136">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="8129a-137">选择 "Microsoft Exchange 集成" 选项以使用 Exchange 2013 存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="8129a-137">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="8129a-138">本部分后面将介绍这些 Lync Server 2013 存档配置选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-138">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="8129a-139">有关如何配置 Exchange In-Place 保留策略和设置以支持存档的信息，请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="8129a-139">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="8129a-140">使用 Lync Server 存档数据库存储时存档设置</span><span class="sxs-lookup"><span data-stu-id="8129a-140">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="8129a-141">如果要使用 Lync Server 存档数据库 (使用 SQL Server 数据库) 若要存档部署中任何用户的数据，可以配置 Lync Server 存档策略，以控制是否为这些用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-141">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="8129a-142">在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：</span><span class="sxs-lookup"><span data-stu-id="8129a-142">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="8129a-143">内部通信</span><span class="sxs-lookup"><span data-stu-id="8129a-143">Internal communications</span></span>

  - <span data-ttu-id="8129a-144">外部通信</span><span class="sxs-lookup"><span data-stu-id="8129a-144">External communications</span></span>

<span data-ttu-id="8129a-145">默认情况下，不会在任何 Lync Server 存档策略中为内部通信或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-145">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="8129a-146">您可以使用 Lync Server 2013 控制面板或使用 Lync Server 2013 命令行管理程序中的 cmdlet 来启用和禁用通信。</span><span class="sxs-lookup"><span data-stu-id="8129a-146">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="8129a-147">Lync Server 2013 存档策略包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="8129a-147">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="8129a-148">**全局存档策略**。</span><span class="sxs-lookup"><span data-stu-id="8129a-148">**Global Archiving policy**.</span></span> <span data-ttu-id="8129a-149">这是默认存档策略，适用于您的整个部署。</span><span class="sxs-lookup"><span data-stu-id="8129a-149">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="8129a-150">它是在您部署 Lync Server 2013 时创建的，默认情况下，它会禁用内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-150">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="8129a-151">您无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="8129a-151">You cannot delete this policy.</span></span> <span data-ttu-id="8129a-152">如果您选择删除选项，那么全局策略将重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="8129a-152">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="8129a-p110">**站点存档策略**。（可选）您可以通过为一个或多个特定站点创建和配置站点级别存档策略，来对该站点启用或禁用存档。当您创建站点级别存档策略时，默认情况下不启用存档。您可以删除任何您所创建的站点级别存档策略。站点级别存档策略会覆盖全局策略，但仅针对策略中指定的站点。例如，如果在全局策略中对内部和外部通信启用存档，并创建了一个对外部通信禁用存档的站点策略，则只能针对该站点存档内部通信。</span><span class="sxs-lookup"><span data-stu-id="8129a-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="8129a-p111">**用户存档策略**。（可选）您可以通过为一个或多个指定用户和用户组创建、配置和应用用户级别存档策略，来为这些特定用户和用户组启用或禁用存档。当您创建用户级别存档策略时，默认情况下不启用存档。您可以删除任何您所创建的用户级别存档策略，并且可以更改应用存档策略的用户和用户组。用户级别存档策略会覆盖全局策略和任何站点策略，但仅针对应用策略的用户和用户组。例如，如果在全局策略中对内部和外部通信禁用存档，并创建了一个对内部和外部通信启用存档的站点级别策略，然后创建了一个对外部通信禁用存档的用户级别策略，那么将为所有站点用户存档外部和内部通信，但是不包括那些应用了用户级别策略的用户，将仅为这些用户存档内部通信。</span><span class="sxs-lookup"><span data-stu-id="8129a-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="8129a-165">有关在部署存档时如何设置初始存档策略的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-165">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="8129a-166">有关在部署后使用存档策略启用和禁用通信的详细信息，请参阅操作文档中的 [管理 Lync Server 2013 中的内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-166">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8129a-167">如果同时实现两个 Lync Server 2013 存档数据库并启用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖 Lync Server 存档策略，但仅适用于托管在 Exchange 2013 上并将其邮箱置于 In-Place 保留状态的用户。</span><span class="sxs-lookup"><span data-stu-id="8129a-167">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8129a-168">Lync 存档取决于 Microsoft Exchange In-Place 仅保留策略。</span><span class="sxs-lookup"><span data-stu-id="8129a-168">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="8129a-169">有哪些可供选择的配置存档选项？</span><span class="sxs-lookup"><span data-stu-id="8129a-169">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="8129a-170">除了使用策略启用和禁用存档以外，您还可以选择可针对整个部署（或针对特定站点和池）配置的其他存档选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-170">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="8129a-171">您可以使用一个或多个存档配置来控制大多数存档选项，这些配置在 Lync Server 2013 控制面板中可用，但也有另一个仅适用于使用 Lync Server 2013 命令行管理程序的配置的选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-171">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="8129a-172">Lync Server 2013 控制面板中提供的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="8129a-172">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="8129a-173">每个存档配置提供以下选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-173">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="8129a-p115">在部署存档时自动创建全局配置，可以对全局配置进行配置，但不能删除它。如果您选择删除全局配置，那么设置将重置为默认值。您可以创建多个站点和池配置，与全局配置一起控制存档设置。对于全局配置和每个站点及池配置，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="8129a-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="8129a-178">禁用存档、仅针对即时消息 (IM) 启用存档或同时针对 IM 和会议启用存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-178">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="8129a-179">配置在 Lync Server 发生故障时阻止 IM 和会议会话的关键模式。</span><span class="sxs-lookup"><span data-stu-id="8129a-179">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="8129a-180">故障包括以下几种类型：</span><span class="sxs-lookup"><span data-stu-id="8129a-180">Failures include the following:</span></span>
    
      - <span data-ttu-id="8129a-181">**即时消息**。</span><span class="sxs-lookup"><span data-stu-id="8129a-181">**IM**.</span></span> <span data-ttu-id="8129a-182">Lync Server 存储服务出现问题。</span><span class="sxs-lookup"><span data-stu-id="8129a-182">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="8129a-183">在此情况下，为启用存档的用户阻止 IM。</span><span class="sxs-lookup"><span data-stu-id="8129a-183">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="8129a-p118">**会议**。故障可能是文件共享不可用或存储服务出现问题。在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。</span><span class="sxs-lookup"><span data-stu-id="8129a-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="8129a-187">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="8129a-187">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="8129a-188">指定使用 Microsoft Exchange Server 2013 集成以使用 Exchange 2013 存储存档数据，而不是设置单独的 SQL Server 数据库来存储 Lync Server 2013 存档数据。</span><span class="sxs-lookup"><span data-stu-id="8129a-188">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="8129a-p119">配置存档数据的清除选项。这包括指定何时清除存档数据，可以是以下任意时间：</span><span class="sxs-lookup"><span data-stu-id="8129a-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="8129a-191">在您指定的特定天数之后</span><span class="sxs-lookup"><span data-stu-id="8129a-191">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="8129a-192">导出存档数据之后 (包括已上传到 Exchange 的数据（如果启用了 Microsoft Exchange 集成) ）。</span><span class="sxs-lookup"><span data-stu-id="8129a-192">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8129a-193">如果启用 Microsoft Exchange 集成，请清除驻留在 Exchange 2013 上的用户并将其邮箱置于 In-Place 保留状态由 Exchange 控制。</span><span class="sxs-lookup"><span data-stu-id="8129a-193">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="8129a-194">仅对存储在 Lync Server 文件共享上的会议文件进行了限定。</span><span class="sxs-lookup"><span data-stu-id="8129a-194">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="8129a-195">如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。</span><span class="sxs-lookup"><span data-stu-id="8129a-195">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="8129a-196">默认情况下不启用任何存档选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-196">By default, no archiving options are enabled.</span></span> <span data-ttu-id="8129a-197">您可以使用 Lync Server 2013 控制面板管理存档配置。</span><span class="sxs-lookup"><span data-stu-id="8129a-197">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="8129a-198">您可以指定以下存档配置：</span><span class="sxs-lookup"><span data-stu-id="8129a-198">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="8129a-199">**全局存档配置**。</span><span class="sxs-lookup"><span data-stu-id="8129a-199">**Global Archiving configuration**.</span></span> <span data-ttu-id="8129a-200">这是默认存档配置，并且适用于您的整个部署。</span><span class="sxs-lookup"><span data-stu-id="8129a-200">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="8129a-201">它是在您部署 Lync Server 2013 时创建的，并且默认情况下不启用存档功能。</span><span class="sxs-lookup"><span data-stu-id="8129a-201">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="8129a-202">可以修改全局配置，但无法删除它。</span><span class="sxs-lookup"><span data-stu-id="8129a-202">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="8129a-203">如果您为配置选择删除选项，则全局配置将重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="8129a-203">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="8129a-p123">**站点存档配置**。（可选）您可以通过为单个站点创建和配置站点级别存档配置来为一个或多个特定站点配置存档。站点级别存档配置仅在您创建它后才会存在。您可以修改或删除任何站点级别存档配置。站点级别存档配置会覆盖全局配置，但仅针对站点级别配置中指定的站点。例如，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点配置，那么仅会为该站点存档会议，而不会为组织的其他站点存档会议。</span><span class="sxs-lookup"><span data-stu-id="8129a-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="8129a-p124">**池存档配置**。（可选）您可以通过为单个池创建和配置池级别配置来为一个或多个特定池指定存档设置。池级别存档配置仅在您创建它后才会存在。您可以修改或删除任何池级别存档配置。池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。例如，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为站点的 IM 和会议启用存档的站点配置，然后创建了一个仅为 IM 启用存档的池级别配置，那么将为该站点的所有用户存档 IM 和会议通信，但是不包括那些驻留在池级别配置中指定的池中的用户。对于贵组织中的所有其他用户，仅针对 IM 启用存档。</span><span class="sxs-lookup"><span data-stu-id="8129a-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="8129a-217">有关在部署存档时如何设置初始存档配置的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置存档选项](lync-server-2013-configuring-archiving-options.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-217">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="8129a-218">有关在部署后使用存档策略启用和禁用通信的详细信息，请参阅 Operations 文档中的 [管理在 Lync Server 2013 中为组织、网站和池管理存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-218">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="8129a-219">仅在 Windows PowerShell 中可用的存档选项</span><span class="sxs-lookup"><span data-stu-id="8129a-219">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="8129a-220">使用 Lync Server 2013 命令行管理程序，可以使用 cmdlet 实现在 Lync Server 2013 控制面板中不可用的选项。</span><span class="sxs-lookup"><span data-stu-id="8129a-220">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="8129a-221">这些选项包括：</span><span class="sxs-lookup"><span data-stu-id="8129a-221">These options include the following:</span></span>

  - <span data-ttu-id="8129a-222">**存档重复消息**。</span><span class="sxs-lookup"><span data-stu-id="8129a-222">**Archive duplicate messages**.</span></span> <span data-ttu-id="8129a-223">有关详细信息，请参阅操作文档中的 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 和 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="8129a-223">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="8129a-224">**导出存档数据**。</span><span class="sxs-lookup"><span data-stu-id="8129a-224">**Export archived data**.</span></span> <span data-ttu-id="8129a-225">有关详细信息，请参阅 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="8129a-225">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="8129a-226">如何访问存档数据？</span><span class="sxs-lookup"><span data-stu-id="8129a-226">How Do I Access Archived Data?</span></span>

<span data-ttu-id="8129a-227">存档数据的访问取决于数据的存储位置：</span><span class="sxs-lookup"><span data-stu-id="8129a-227">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="8129a-228">**Microsoft Exchange 存储**。</span><span class="sxs-lookup"><span data-stu-id="8129a-228">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="8129a-229">如果选择 "Exchange 集成" 选项，Lync Server 会在 Exchange 2013 存储中为驻留在 Exchange 2013 上的所有用户，以及将其邮箱置于 In-Place 保留状态的 Exchange 存储中的存档内容。</span><span class="sxs-lookup"><span data-stu-id="8129a-229">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8129a-230">存档数据存储在用户邮箱的 "可恢复的项目" 文件夹中，该文件夹通常对用户不可见，并且只能由具有 Exchange **发现管理** 角色的用户进行搜索。</span><span class="sxs-lookup"><span data-stu-id="8129a-230">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="8129a-231">Exchange 启用联合搜索和发现（如果部署了 SharePoint）。</span><span class="sxs-lookup"><span data-stu-id="8129a-231">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="8129a-232">有关存储在 Exchange 中的数据的存储、保留和发现的更多详细信息，请参阅 Exchange 2013 和 SharePoint 文档。</span><span class="sxs-lookup"><span data-stu-id="8129a-232">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="8129a-233">**Lync Server 存储**。</span><span class="sxs-lookup"><span data-stu-id="8129a-233">**Lync Server storage**.</span></span> <span data-ttu-id="8129a-234">如果设置 Lync Server 2013 存档数据库以存储 Lync Server 数据，Lync Server 会将存档内容放在 Lync Server 存档数据库中， (SQL Server) 数据库中的所有未驻留在 Exchange 2013 中的用户，以及未将其邮箱置于 In-Place 保留状态的用户。</span><span class="sxs-lookup"><span data-stu-id="8129a-234">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8129a-235">虽然此数据是不可搜索的，但可以采用可通过其他工具搜索的格式导出此数据。</span><span class="sxs-lookup"><span data-stu-id="8129a-235">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="8129a-236">有关导出存档数据库中存储的数据的详细信息，请参阅操作文档中的在 [Lync Server 2013 中导出存档的数据](lync-server-2013-exporting-archived-data.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-236">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="8129a-237">有关 Lync Server 2013 和 Exchange 2013 如何协同工作的更多详细信息，请参阅可支持性文档中的 [Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="8129a-237">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

