---
title: 'Lync Server 2013: 存档的工作原理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097b40ef4194a618c090e0d67f73583d6aa427b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="689c9-102">在 Lync Server 2013 中存档的工作方式</span><span class="sxs-lookup"><span data-stu-id="689c9-102">How Archiving works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="689c9-103">_**主题上次修改时间:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="689c9-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="689c9-104">Lync Server 2013 存档提供的选项可帮助你满足合规性需求。</span><span class="sxs-lookup"><span data-stu-id="689c9-104">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="689c9-105">若要以最有效地满足组织要求的方式实施和维护它, 应了解以下事项:</span><span class="sxs-lookup"><span data-stu-id="689c9-105">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="689c9-106">可以存档哪些信息。</span><span class="sxs-lookup"><span data-stu-id="689c9-106">What information can be archived.</span></span>

  - <span data-ttu-id="689c9-107">如何在部署中启用和禁用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-107">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="689c9-108">可配置的存档选项, 用于控制实施存档的方式。</span><span class="sxs-lookup"><span data-stu-id="689c9-108">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="689c9-109">哪些信息可以存档？</span><span class="sxs-lookup"><span data-stu-id="689c9-109">What Information Can Be Archived?</span></span>

<span data-ttu-id="689c9-110">可存档以下类型的内容:</span><span class="sxs-lookup"><span data-stu-id="689c9-110">The following types of content can be archived:</span></span>

  - <span data-ttu-id="689c9-111">对等即时消息</span><span class="sxs-lookup"><span data-stu-id="689c9-111">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="689c9-112">多方即时消息的会议</span><span class="sxs-lookup"><span data-stu-id="689c9-112">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="689c9-113">会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）</span><span class="sxs-lookup"><span data-stu-id="689c9-113">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="689c9-114">会议期间共享的白板和投票</span><span class="sxs-lookup"><span data-stu-id="689c9-114">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="689c9-115">以下类型的内容未存档:</span><span class="sxs-lookup"><span data-stu-id="689c9-115">The following types of content are not archived:</span></span>

  - <span data-ttu-id="689c9-116">对等文件传输</span><span class="sxs-lookup"><span data-stu-id="689c9-116">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="689c9-117">对等即时消息和会议的音频/视频</span><span class="sxs-lookup"><span data-stu-id="689c9-117">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="689c9-118">对等即时消息和会议的桌面和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="689c9-118">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="689c9-119">Lync 服务器也不会存档持久聊天对话。</span><span class="sxs-lookup"><span data-stu-id="689c9-119">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="689c9-120">若要存档持久聊天对话, 您必须启用和配置合规性服务, 该服务是可以使用 Microsoft Lync Server 2013、持久聊天服务器部署的组件。</span><span class="sxs-lookup"><span data-stu-id="689c9-120">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="689c9-121">有关详细信息, 请参阅规划文档中的在[Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="689c9-121">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="689c9-122">如何开始使用存档？</span><span class="sxs-lookup"><span data-stu-id="689c9-122">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="689c9-123">部署服务器时, 会自动在每台前端服务器上安装存档, 但除非配置存档, 否则不会启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-123">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it.</span></span> <span data-ttu-id="689c9-124">配置方式取决于部署存档的方式:</span><span class="sxs-lookup"><span data-stu-id="689c9-124">How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="689c9-125">**使用 Microsoft Exchange 集成进行存档。**</span><span class="sxs-lookup"><span data-stu-id="689c9-125">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="689c9-126">如果您有托管在 Exchange 2013 上的用户, 并且其邮箱已放在原地保留, 则您可以选择将 Lync Server 2013 存储与 Exchange 存储集成的选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-126">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="689c9-127">如果你选择 "Microsoft Exchange 集成" 选项, 则使用 Exchange 2013 策略和配置来控制这些用户的 Lync Server 2013 数据的存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-127">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="689c9-128">**使用 Lync Server 存档数据库进行存档。**</span><span class="sxs-lookup"><span data-stu-id="689c9-128">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="689c9-129">如果你的用户未托管在 Exchange 2013 上或未将其邮箱放置在原地保留中, 或者如果你不希望对部署中的任何用户或所有用户使用 Microsoft Exchange 集成, 则可以使用 SQL Server 部署 Lync Server 存档数据库 存储这些用户的存档数据。</span><span class="sxs-lookup"><span data-stu-id="689c9-129">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="689c9-130">在这种情况下, Lync Server 2013 存档策略和配置确定是否已启用存档以及如何实现存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-130">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="689c9-131">若要使用 Lync Server 2013, 必须向拓扑中添加相应的 SQL Server 数据库并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="689c9-131">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="689c9-132">使用 Microsoft Exchange 集成时的存档设置</span><span class="sxs-lookup"><span data-stu-id="689c9-132">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="689c9-133">如果用户托管在 Exchange 2013 上, 并且其邮箱已放在原地保留, 则可以选择 " **Microsoft Exchange 集成**" 选项 (如本节稍后部分所述), 以便为这些用户存档 Lync Server 2013, 然后控制通过指定 Exchange 就地保留策略和设置以及 Lync 服务器配置来控制以下内容, 为这些用户存档:</span><span class="sxs-lookup"><span data-stu-id="689c9-133">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="689c9-134">是存档 IM、会议还是同时存档两者。</span><span class="sxs-lookup"><span data-stu-id="689c9-134">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="689c9-135">是否为 Lync Server 部署实现关键模式。</span><span class="sxs-lookup"><span data-stu-id="689c9-135">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="689c9-136">选择 "Microsoft Exchange 集成" 选项以使用 Exchange 2013 存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="689c9-136">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="689c9-137">本部分后面将介绍这些 Lync Server 2013 存档配置选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-137">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="689c9-138">有关如何配置 Exchange 就地保留策略和设置以支持存档的信息, 请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="689c9-138">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="689c9-139">使用 Lync Server 存档数据库存储时的存档设置</span><span class="sxs-lookup"><span data-stu-id="689c9-139">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="689c9-140">如果要使用 Lync Server 存档数据库 (使用 SQL Server 数据库) 对部署中任何用户的数据进行存档, 则可以配置 Lync Server 存档策略来控制是否为这些用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-140">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="689c9-141">在每个存档策略中, 可以启用或禁用以下任一或全部的存档:</span><span class="sxs-lookup"><span data-stu-id="689c9-141">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="689c9-142">内部通信</span><span class="sxs-lookup"><span data-stu-id="689c9-142">Internal communications</span></span>

  - <span data-ttu-id="689c9-143">外部通信</span><span class="sxs-lookup"><span data-stu-id="689c9-143">External communications</span></span>

<span data-ttu-id="689c9-144">默认情况下, 不会为任何 Lync Server 存档策略中的内部通信或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-144">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="689c9-145">使用 Lync Server 2013 控制面板或在 Lync Server 2013 管理外壳程序中使用 cmdlet 启用和禁用通信。</span><span class="sxs-lookup"><span data-stu-id="689c9-145">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="689c9-146">Lync Server 2013 存档策略包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="689c9-146">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="689c9-147">**全局存档策略**。</span><span class="sxs-lookup"><span data-stu-id="689c9-147">**Global Archiving policy**.</span></span> <span data-ttu-id="689c9-148">这是默认存档策略, 适用于整个部署。</span><span class="sxs-lookup"><span data-stu-id="689c9-148">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="689c9-149">它是在你部署 Lync Server 2013 时创建的, 并且默认情况下, 将禁用内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-149">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="689c9-150">您不能删除此策略。</span><span class="sxs-lookup"><span data-stu-id="689c9-150">You cannot delete this policy.</span></span> <span data-ttu-id="689c9-151">如果你选择 "删除" 选项, 则全局策略将重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="689c9-151">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="689c9-152">**网站存档策略**。</span><span class="sxs-lookup"><span data-stu-id="689c9-152">**Site Archiving policy**.</span></span> <span data-ttu-id="689c9-153">或者, 你可以通过为网站创建和配置网站级别的存档策略来启用或禁用一个或多个特定网站的存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-153">Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site.</span></span> <span data-ttu-id="689c9-154">创建网站级存档策略时, 默认情况下不会启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-154">When you create a site-level Archiving policy, by default, archiving is not enabled.</span></span> <span data-ttu-id="689c9-155">你可以删除你创建的任何网站级存档策略。</span><span class="sxs-lookup"><span data-stu-id="689c9-155">You can delete any site-level Archiving policy that you create.</span></span> <span data-ttu-id="689c9-156">网站级别的存档策略会覆盖全局策略, 但仅适用于策略中指定的网站。</span><span class="sxs-lookup"><span data-stu-id="689c9-156">A site-level Archiving policy overrides the global policy, but only for the site specified in the policy.</span></span> <span data-ttu-id="689c9-157">例如, 如果在全局策略中启用了内部和外部通信的存档, 并创建了一个网站策略, 在其中禁用外部通信的存档, 则仅为该网站存档内部通信。</span><span class="sxs-lookup"><span data-stu-id="689c9-157">For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="689c9-158">**用户存档策略**。</span><span class="sxs-lookup"><span data-stu-id="689c9-158">**User Archiving policy**.</span></span> <span data-ttu-id="689c9-159">或者, 你可以通过为指定的用户和用户组创建、配置和应用用户级存档策略, 为一个或多个特定用户和用户组启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-159">Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups.</span></span> <span data-ttu-id="689c9-160">创建用户级存档策略时, 默认情况下不启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-160">When you create a user-level Archiving policy, by default, archiving is not enabled.</span></span> <span data-ttu-id="689c9-161">你可以删除你创建的任何用户级存档策略, 也可以更改存档策略应用于的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="689c9-161">You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to.</span></span> <span data-ttu-id="689c9-162">用户级存档策略将覆盖全局策略和任何网站策略, 但仅适用于要对其应用该策略的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="689c9-162">A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied.</span></span> <span data-ttu-id="689c9-163">例如, 如果您在全局策略中禁用了内部和外部通信的存档, 请创建一个网站级策略, 在其中启用内部和外部通信的存档, 然后创建禁用的用户级策略存档对于外部通信, 将对所有网站用户的外部通信和内部通信同时进行通信, 但对于应用用户级策略的用户而言, 只会存档内部通信。</span><span class="sxs-lookup"><span data-stu-id="689c9-163">For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="689c9-164">有关如何在部署存档时设置初始存档策略的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="689c9-164">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="689c9-165">有关在部署后使用存档策略启用和禁用通信的详细信息, 请参阅在操作文档中[管理 Lync Server 2013 中的内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="689c9-165">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="689c9-166">如果你实现 Lync Server 2013 存档数据库并启用 Microsoft Exchange 集成, Exchange 2013 策略将覆盖 Lync Server 存档策略, 但仅适用于托管在 Exchange 2013 并已将其邮箱置于原地保留的用户.</span><span class="sxs-lookup"><span data-stu-id="689c9-166">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="689c9-167">Lync 存档仅取决于 Microsoft Exchange 就地保留策略。</span><span class="sxs-lookup"><span data-stu-id="689c9-167">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="689c9-168">我有哪些选项用于配置存档？</span><span class="sxs-lookup"><span data-stu-id="689c9-168">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="689c9-169">除了使用策略和启用和禁用存档, 还可以为整个部署配置其他存档选项, 还可以针对特定网站和池进行配置。</span><span class="sxs-lookup"><span data-stu-id="689c9-169">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="689c9-170">你可以通过使用一个或多个存档配置来控制大多数存档选项, 这些配置在 Lync Server 2013 控制面板中可用, 但也有另一个仅适用于使用 Lync Server 2013 管理外壳程序配置的选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-170">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="689c9-171">"Lync Server 2013 控制面板" 中可用的存档配置选项</span><span class="sxs-lookup"><span data-stu-id="689c9-171">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="689c9-172">每个存档配置均提供以下选项:</span><span class="sxs-lookup"><span data-stu-id="689c9-172">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="689c9-173">全局级别配置在部署存档时自动创建, 并且可以配置但不能删除。</span><span class="sxs-lookup"><span data-stu-id="689c9-173">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted.</span></span> <span data-ttu-id="689c9-174">如果选择删除全局配置的选项, 则设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="689c9-174">If you select the option to delete the global configuration, the settings are reset to the default values.</span></span> <span data-ttu-id="689c9-175">你可以创建多个网站和池配置以及全局配置, 控制存档设置。</span><span class="sxs-lookup"><span data-stu-id="689c9-175">You can create multiple site and pool configurations that, together with the global configuration, control archiving settings.</span></span> <span data-ttu-id="689c9-176">对于全局配置以及每个网站和池配置, 您可以使用以下选项:</span><span class="sxs-lookup"><span data-stu-id="689c9-176">For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="689c9-177">禁用存档, 仅为即时消息 (IM) 启用存档, 或者启用即时消息和会议的存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-177">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="689c9-178">配置关键模式以在 Lync 服务器出现故障时阻止 IM 和会议会话。</span><span class="sxs-lookup"><span data-stu-id="689c9-178">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="689c9-179">失败包括以下几项:</span><span class="sxs-lookup"><span data-stu-id="689c9-179">Failures include the following:</span></span>
    
      - <span data-ttu-id="689c9-180">**即时消息**。</span><span class="sxs-lookup"><span data-stu-id="689c9-180">**IM**.</span></span> <span data-ttu-id="689c9-181">Lync Server 存储服务出现问题。</span><span class="sxs-lookup"><span data-stu-id="689c9-181">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="689c9-182">在此情况下，将阻止为存档启用的用户使用 IM。</span><span class="sxs-lookup"><span data-stu-id="689c9-182">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="689c9-183">**会议**。</span><span class="sxs-lookup"><span data-stu-id="689c9-183">**Conferencing**.</span></span> <span data-ttu-id="689c9-184">故障可能是文件共享不可用或存储服务出现问题。</span><span class="sxs-lookup"><span data-stu-id="689c9-184">A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="689c9-185">在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。</span><span class="sxs-lookup"><span data-stu-id="689c9-185">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="689c9-186">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="689c9-186">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="689c9-187">指定使用 Microsoft Exchange Server 2013 集成以使用 Exchange 2013 存储存档数据, 而不是设置单独的 SQL Server 数据库以存储 Lync Server 2013 存档数据。</span><span class="sxs-lookup"><span data-stu-id="689c9-187">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="689c9-188">配置存档数据的清除选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-188">Configure purging options for archived data.</span></span> <span data-ttu-id="689c9-189">这包括指定何时清除已存档的数据, 这可能是下列情况之一:</span><span class="sxs-lookup"><span data-stu-id="689c9-189">This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="689c9-190">指定天数后的特定天数</span><span class="sxs-lookup"><span data-stu-id="689c9-190">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="689c9-191">导出存档数据后 (包括已上载到 Exchange 的数据) (如果启用 Microsoft Exchange 集成)。</span><span class="sxs-lookup"><span data-stu-id="689c9-191">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="689c9-192">如果启用 Microsoft Exchange 集成, 请清除托管在 Exchange 2013 上的用户, 并将其邮箱置于就地保留状态由 Exchange 控制。</span><span class="sxs-lookup"><span data-stu-id="689c9-192">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="689c9-193">仅适用于会议文件的资格, 这些文件存储在 Lync Server 文件共享中。</span><span class="sxs-lookup"><span data-stu-id="689c9-193">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="689c9-194">如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。</span><span class="sxs-lookup"><span data-stu-id="689c9-194">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="689c9-195">默认情况下, 不启用任何存档选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-195">By default, no archiving options are enabled.</span></span> <span data-ttu-id="689c9-196">你可以使用 Lync Server 2013 控制面板管理存档配置。</span><span class="sxs-lookup"><span data-stu-id="689c9-196">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="689c9-197">你可以指定以下存档配置:</span><span class="sxs-lookup"><span data-stu-id="689c9-197">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="689c9-198">**全局存档配置**。</span><span class="sxs-lookup"><span data-stu-id="689c9-198">**Global Archiving configuration**.</span></span> <span data-ttu-id="689c9-199">这是默认存档配置, 适用于整个部署。</span><span class="sxs-lookup"><span data-stu-id="689c9-199">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="689c9-200">它是在部署 Lync Server 2013 时创建的, 默认情况下, 它不启用存档功能。</span><span class="sxs-lookup"><span data-stu-id="689c9-200">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="689c9-201">您可以修改全局配置, 但不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="689c9-201">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="689c9-202">如果为配置选择 "删除" 选项, 则全局配置将重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="689c9-202">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="689c9-203">**网站存档配置**。</span><span class="sxs-lookup"><span data-stu-id="689c9-203">**Site Archiving configuration**.</span></span> <span data-ttu-id="689c9-204">或者, 你可以通过为单个网站创建和配置网站级别的存档配置, 为一个或多个特定网站配置存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-204">Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site.</span></span> <span data-ttu-id="689c9-205">网站级别的存档配置仅在创建时才存在。</span><span class="sxs-lookup"><span data-stu-id="689c9-205">A site-level Archiving configuration exists only if you create it.</span></span> <span data-ttu-id="689c9-206">你可以修改或删除任何网站级存档配置。</span><span class="sxs-lookup"><span data-stu-id="689c9-206">You can modify or delete any site-level Archiving configuration.</span></span> <span data-ttu-id="689c9-207">网站级别的存档配置将覆盖全局配置, 但仅适用于网站级配置中指定的网站。</span><span class="sxs-lookup"><span data-stu-id="689c9-207">A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration.</span></span> <span data-ttu-id="689c9-208">例如, 如果仅为全局配置中的 IM 启用存档, 并创建可在其中为 IM 和会议同时启用存档的网站配置, 则仅为网站存档会议, 而不是组织的其余部分。</span><span class="sxs-lookup"><span data-stu-id="689c9-208">For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="689c9-209">**池存档配置**。</span><span class="sxs-lookup"><span data-stu-id="689c9-209">**Pool Archiving configuration**.</span></span> <span data-ttu-id="689c9-210">或者, 你可以通过为单个池创建和配置池级配置来指定一个或多个特定池的存档设置。</span><span class="sxs-lookup"><span data-stu-id="689c9-210">Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool.</span></span> <span data-ttu-id="689c9-211">池级别的存档配置仅在创建时才存在。</span><span class="sxs-lookup"><span data-stu-id="689c9-211">A pool-level Archiving configuration exists only if you create it.</span></span> <span data-ttu-id="689c9-212">你可以修改和删除任何池级别的存档配置。</span><span class="sxs-lookup"><span data-stu-id="689c9-212">You can modify and delete any pool-level Archiving configuration.</span></span> <span data-ttu-id="689c9-213">池级别的存档配置覆盖你可能已创建的全局配置和任何网站存档配置。</span><span class="sxs-lookup"><span data-stu-id="689c9-213">A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created.</span></span> <span data-ttu-id="689c9-214">例如, 如果仅为全局配置中的 IM 启用存档, 请创建网站级配置, 在该配置中, 你可以为网站的 IM 和会议启用存档, 然后创建池级别配置, 仅在其中启用存档IM, 将为网站的所有用户 (驻留在池级配置中指定的池中的用户除外) 的 IM 和会议存档通信。</span><span class="sxs-lookup"><span data-stu-id="689c9-214">For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration.</span></span> <span data-ttu-id="689c9-215">对于组织中的所有其他用户, 将仅为 IM 启用存档。</span><span class="sxs-lookup"><span data-stu-id="689c9-215">For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="689c9-216">有关如何在部署存档时设置初始存档配置的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "配置存档选项](lync-server-2013-configuring-archiving-options.md)"。</span><span class="sxs-lookup"><span data-stu-id="689c9-216">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="689c9-217">有关在部署后使用存档策略启用和禁用通信的详细信息, 请参阅操作文档中的 "[管理 Lync Server 2013 中的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)"。</span><span class="sxs-lookup"><span data-stu-id="689c9-217">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="689c9-218">仅在 Windows PowerShell 中可用的存档选项</span><span class="sxs-lookup"><span data-stu-id="689c9-218">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="689c9-219">使用 Lync Server 2013 命令行管理程序, 你可以使用 cmdlet 来实现 Lync Server 2013 控制面板中不可用的选项。</span><span class="sxs-lookup"><span data-stu-id="689c9-219">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="689c9-220">这些选项包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="689c9-220">These options include the following:</span></span>

  - <span data-ttu-id="689c9-221">**存档重复邮件**。</span><span class="sxs-lookup"><span data-stu-id="689c9-221">**Archive duplicate messages**.</span></span> <span data-ttu-id="689c9-222">有关详细信息, 请参阅操作文档中的 "[新建-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) " 和 "[设置 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) "。</span><span class="sxs-lookup"><span data-stu-id="689c9-222">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="689c9-223">**导出已存档的数据**。</span><span class="sxs-lookup"><span data-stu-id="689c9-223">**Export archived data**.</span></span> <span data-ttu-id="689c9-224">有关详细信息, 请参阅[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="689c9-224">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="689c9-225">如何访问已存档的数据？</span><span class="sxs-lookup"><span data-stu-id="689c9-225">How Do I Access Archived Data?</span></span>

<span data-ttu-id="689c9-226">存档数据的访问取决于数据的存储位置：</span><span class="sxs-lookup"><span data-stu-id="689c9-226">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="689c9-227">**Microsoft Exchange 存储**。</span><span class="sxs-lookup"><span data-stu-id="689c9-227">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="689c9-228">如果你选择 "Exchange 集成" 选项, Lync Server 将为托管在 Exchange 2013 上的所有用户在 Exchange 2013 存储中的存档内容, 并将其邮箱放在原地保留中。</span><span class="sxs-lookup"><span data-stu-id="689c9-228">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="689c9-229">已存档的数据存储在用户邮箱 "可恢复的项目" 文件夹中, 该文件夹通常对用户不可见, 并且只能由具有 Exchange**发现管理**角色的用户搜索。</span><span class="sxs-lookup"><span data-stu-id="689c9-229">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="689c9-230">如果部署了, Exchange 将启用联合搜索和发现, 以及 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="689c9-230">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="689c9-231">有关存储在 Exchange 中的数据的存储、保留和发现的更多详细信息, 请参阅 Exchange 2013 和 SharePoint 文档。</span><span class="sxs-lookup"><span data-stu-id="689c9-231">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="689c9-232">**Lync 服务器存储**。</span><span class="sxs-lookup"><span data-stu-id="689c9-232">**Lync Server storage**.</span></span> <span data-ttu-id="689c9-233">如果将 Lync server 2013 存档数据库设置为存储 Lync Server 数据, Lync Server 将把存档内容放在 Lync Server 存档数据库 (SQL Server 数据库) 中, 用于任何未驻留在 Exchange 2013 的用户, 并且未将其邮箱放在就地保留。</span><span class="sxs-lookup"><span data-stu-id="689c9-233">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="689c9-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span><span class="sxs-lookup"><span data-stu-id="689c9-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="689c9-235">有关导出存储在存档数据库中的数据的详细信息, 请参阅在操作文档中[导出 Lync Server 2013 中的存档数据](lync-server-2013-exporting-archived-data.md)。</span><span class="sxs-lookup"><span data-stu-id="689c9-235">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="689c9-236">有关 Lync Server 2013 和 Exchange 2013 如何协同工作的更多详细信息, 请参阅支持文档中[Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="689c9-236">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

