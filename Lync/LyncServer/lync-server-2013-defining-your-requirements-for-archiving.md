---
title: Lync Server 2013：定义组织的存档要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c56f3-102">在 Lync Server 2013 中定义组织的存档要求</span><span class="sxs-lookup"><span data-stu-id="c56f3-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c56f3-103">_**主题上次修改时间：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c56f3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c56f3-104">如果你的组织必须遵循合规性规定，你可以部署存档以启用对 Lync Server 2013 即时消息（IM）和会议（会议）的存档支持。</span><span class="sxs-lookup"><span data-stu-id="c56f3-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="c56f3-105">有关可存档的内容类型的详细信息，请参阅规划文档中[Lync Server 2013 中的存档概述](lync-server-2013-overview-of-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c56f3-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="c56f3-106">若要实现存档，首先需要确定如何满足组织对存档的要求。</span><span class="sxs-lookup"><span data-stu-id="c56f3-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="c56f3-107">这需要确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="c56f3-107">This requires determining the following:</span></span>

  - <span data-ttu-id="c56f3-108">**何时部署存档**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="c56f3-109">你可以将存档部署为你的初始 Lync Server 2013 部署的一部分，也可以将其添加到现有部署。</span><span class="sxs-lookup"><span data-stu-id="c56f3-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="c56f3-110">通过使用拓扑生成器将其添加到拓扑，然后发布拓扑来部署存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="c56f3-p104">**存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。</span><span class="sxs-lookup"><span data-stu-id="c56f3-p104">**Whether to archive internal or external communications**. You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both. You can specify these options for your entire organization, or you can specify them for specific sites and pools. By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c56f3-115">如果你使用 Microsoft Exchange 集成来存储存档的数据，Exchange 设置将控制是否存档 Lync 通信。</span><span class="sxs-lookup"><span data-stu-id="c56f3-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="c56f3-116">如果你的部署包含多个林，则必须在 Lync Server 和 Exchange 之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="c56f3-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="c56f3-117">仅适用于 Lync 策略控制内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="c56f3-118">对于 Exchange 集成的存档，这两个都将存档或不存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="c56f3-119">**为什么要启用存档**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-119">**Why enable Archiving**.</span></span> <span data-ttu-id="c56f3-120">你可以在全局级别为整个部署启用和禁用存档，并且你可以启用和禁用特定网站和用户的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="c56f3-121">在每个级别，指定是否启用 IM 会话（对等）、会议（这是多方会话）的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="c56f3-122">默认情况下，禁用存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="c56f3-123">**您的组织中的用户的重要存档方式**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="c56f3-124">如果存档在你的组织中是任务关键型的，则可以指定 Lync Server 2013 在 "关键" 模式下运行，这将在存档失败时阻止 IM 和会议会话。</span><span class="sxs-lookup"><span data-stu-id="c56f3-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="c56f3-125">例如：</span><span class="sxs-lookup"><span data-stu-id="c56f3-125">For example:</span></span>
    
      - <span data-ttu-id="c56f3-126">如果存档服务暂时无法将消息发送到数据库队列或将消息插入到数据库中，则将在部署中阻止 IM 和会议功能，直到还原存档支持。</span><span class="sxs-lookup"><span data-stu-id="c56f3-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="c56f3-127">如果会议用户上载文件，但无法将文件复制到存档文件存储，则在部署中将阻止会议功能，直到问题得到解决，但不阻止 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="c56f3-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="c56f3-128">你可以在全局级别、网站级别和池级别配置此选项。</span><span class="sxs-lookup"><span data-stu-id="c56f3-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="c56f3-129">默认情况下，不启用关键模式。</span><span class="sxs-lookup"><span data-stu-id="c56f3-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="c56f3-130">**是否使用 Microsoft Exchange 集成**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="c56f3-131">此选项将存档存储与 Exchange 2013 存储集成，以便您的 Lync 服务器存档数据和 Exchange 2013 存档数据将一起存储在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="c56f3-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="c56f3-132">你可以使用 Microsoft Exchange 集成来存储托管在 Exchange 2013 上的用户的存档数据（如果其邮箱已放在原地保留）。</span><span class="sxs-lookup"><span data-stu-id="c56f3-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="c56f3-133">如果您没有 Exchange 2013 部署，或者如果您不希望与之集成，或者如果您有任何 Lync 用户未托管在 Exchange 2013 上，则可以通过使用 SQL Server 从 Lync 通信存储已存档的数据来部署单独的存档数据库。</span><span class="sxs-lookup"><span data-stu-id="c56f3-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="c56f3-134">你可以在全局级别、网站级别和池级别配置 Microsoft Exchange 集成选项。</span><span class="sxs-lookup"><span data-stu-id="c56f3-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="c56f3-135">默认情况下，不启用 Microsoft Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="c56f3-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="c56f3-136">**如何管理存档数据**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="c56f3-137">存档数据库不适用于长期保留，并且 Lync Server 2013 不会为存档的数据提供电子发现（搜索）解决方案，因此需要将数据移动到其他存储。</span><span class="sxs-lookup"><span data-stu-id="c56f3-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="c56f3-138">Lync Server 提供了一种会话导出工具，可用于导出已存档的数据，这将创建已存档数据的可搜索脚本。</span><span class="sxs-lookup"><span data-stu-id="c56f3-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="c56f3-139">对于全局策略以及你创建的每个网站和用户策略，你可以启用数据清除并指定下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c56f3-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="c56f3-140">在特定天数后清除导出的存档数据并存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="c56f3-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="c56f3-141">您可以指定的最少天数是一天。</span><span class="sxs-lookup"><span data-stu-id="c56f3-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="c56f3-142">可以指定的最大天数为2562天。</span><span class="sxs-lookup"><span data-stu-id="c56f3-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="c56f3-143">仅清除导出的存档数据。</span><span class="sxs-lookup"><span data-stu-id="c56f3-143">Purge exported archiving data only.</span></span> <span data-ttu-id="c56f3-144">此选项清除由会话导出工具导出并标记为可安全删除的所有记录。</span><span class="sxs-lookup"><span data-stu-id="c56f3-144">This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="c56f3-145">你可以在全局级别、网站级别和池级别配置此选项。</span><span class="sxs-lookup"><span data-stu-id="c56f3-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="c56f3-146">默认情况下，不启用清除。</span><span class="sxs-lookup"><span data-stu-id="c56f3-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="c56f3-147">你可以使用以下方法控制存档：</span><span class="sxs-lookup"><span data-stu-id="c56f3-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="c56f3-148">**存档策略**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-148">**Archiving policies**.</span></span> <span data-ttu-id="c56f3-149">使用一个或多个存档策略启用和禁用内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="c56f3-150">默认情况下，不启用任何存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="c56f3-151">你可以使用默认全局策略在部署中启用或禁用内部通信、外部通信或两者的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="c56f3-152">您不能删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="c56f3-152">You cannot delete the global policy.</span></span> <span data-ttu-id="c56f3-153">你可以指定一个或多个可选的网站策略，以便为特定网站启用或禁用内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="c56f3-154">你还可以指定一个或多个用户策略来启用或禁用特定用户和用户组的存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="c56f3-155">用户级策略替代网站策略。</span><span class="sxs-lookup"><span data-stu-id="c56f3-155">User-level policies override site policies.</span></span> <span data-ttu-id="c56f3-156">网站级别策略替代全局级别策略。</span><span class="sxs-lookup"><span data-stu-id="c56f3-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="c56f3-157">用户级策略仅针对配置为使用该策略的特定用户执行。</span><span class="sxs-lookup"><span data-stu-id="c56f3-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="c56f3-158">只有当至少一个参与者的策略配置为启用存档时，才会存档组即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="c56f3-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c56f3-159">如果使用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖驻留在 Exchange 2013 服务器上的所有用户的 Lync Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="c56f3-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="c56f3-160">**存档配置**。</span><span class="sxs-lookup"><span data-stu-id="c56f3-160">**Archiving configurations**.</span></span> <span data-ttu-id="c56f3-161">你可以使用一个或多个存档配置来指定本主题前面所述的大部分存档选项，除了允许存档内部和外部通信（使用存档策略进行配置），如本文中所述。上一个项目符号）。</span><span class="sxs-lookup"><span data-stu-id="c56f3-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="c56f3-162">存档配置包括默认全局配置和可选网站和池配置。</span><span class="sxs-lookup"><span data-stu-id="c56f3-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="c56f3-163">您不能删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="c56f3-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="c56f3-164">池级配置替代网站级别的配置。</span><span class="sxs-lookup"><span data-stu-id="c56f3-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="c56f3-165">网站级配置替代全局级别配置。</span><span class="sxs-lookup"><span data-stu-id="c56f3-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="c56f3-166">作为需求分析的一部分，你需要确定如何配置全局存档配置和全局存档策略。</span><span class="sxs-lookup"><span data-stu-id="c56f3-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="c56f3-167">你还需要确定任何网站级存档配置、池级存档配置、网站级存档策略和用户级存档策略的要求。</span><span class="sxs-lookup"><span data-stu-id="c56f3-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="c56f3-168">如果你为一个前端池或标准版服务器部署存档，则应该为部署中的所有其他前端池和标准版服务器启用它。</span><span class="sxs-lookup"><span data-stu-id="c56f3-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="c56f3-169">你需要执行此操作，因为需要存档其通信的用户可以被邀请到其他池中托管的组 IM 对话或会议。</span><span class="sxs-lookup"><span data-stu-id="c56f3-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="c56f3-170">如果在托管对话或会议的池上未启用存档，则可能不会存档所有会议数据。</span><span class="sxs-lookup"><span data-stu-id="c56f3-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="c56f3-171">存档仍将适用于启用存档的用户和所有 IM 消息，但会议内容和事件可能不会存档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c56f3-172">若要在维护组织的安全标准的同时启用管理任务委派，Lync Server&nbsp;2013 使用基于角色的访问控制（RBAC）。</span><span class="sxs-lookup"><span data-stu-id="c56f3-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="c56f3-173">利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。</span><span class="sxs-lookup"><span data-stu-id="c56f3-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="c56f3-174">若要配置 Lync 存档策略和存档配置，必须将用户分配给 CsArchivingAdministrator 角色（除非直接在部署存档的服务器上执行配置，而不是从另一台计算机远程执行配置）。</span><span class="sxs-lookup"><span data-stu-id="c56f3-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="c56f3-175">有关 RBAC 的详细信息，请参阅规划文档中<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的 "规划基于角色的访问控制</A>"。</span><span class="sxs-lookup"><span data-stu-id="c56f3-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="c56f3-176">有关存档部署所需的用户权利、权限和角色的列表，请参阅<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</A>，该清单可在 "规划文档" 和 "部署" 文档中提供。</span><span class="sxs-lookup"><span data-stu-id="c56f3-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="c56f3-177">如果你使用 Microsoft Exchange 集成，则 Exchange 策略的配置需要相应的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c56f3-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="c56f3-178">有关详细信息，请参阅 Exchange 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="c56f3-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

