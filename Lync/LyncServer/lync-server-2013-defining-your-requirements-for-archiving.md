---
title: Lync Server 2013：定义存档要求
description: Lync Server 2013：定义存档要求。
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
ms.openlocfilehash: d6b9f3257c56241ce921a18e16932689053ef430
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545528"
---
# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0c36c-103">在 Lync Server 2013 中定义存档要求</span><span class="sxs-lookup"><span data-stu-id="0c36c-103">Defining your requirements for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c36c-104">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0c36c-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0c36c-105">如果您的组织必须遵循合规性管理法规，则可以部署存档以启用对 Lync Server 2013 即时消息 (IM) 和会议 (会议) 的存档支持。</span><span class="sxs-lookup"><span data-stu-id="0c36c-105">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="0c36c-106">有关可存档的内容类型的详细信息，请参阅规划文档中的 [Lync Server 2013 中的存档概述](lync-server-2013-overview-of-archiving.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c36c-106">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="0c36c-107">若要实现存档，您首先需要确定如何满足组织的存档要求。</span><span class="sxs-lookup"><span data-stu-id="0c36c-107">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="0c36c-108">这要求确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="0c36c-108">This requires determining the following:</span></span>

  - <span data-ttu-id="0c36c-109">**部署存档的时间**。</span><span class="sxs-lookup"><span data-stu-id="0c36c-109">**When to deploy Archiving**.</span></span> <span data-ttu-id="0c36c-110">您可以将存档部署为最初的 Lync Server 2013 部署的一部分，也可以将其添加到现有部署中。</span><span class="sxs-lookup"><span data-stu-id="0c36c-110">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="0c36c-111">通过使用拓扑生成器将存档添加到拓扑中，然后发布拓扑来部署存档。</span><span class="sxs-lookup"><span data-stu-id="0c36c-111">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="0c36c-p104">**存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p104">**Whether to archive internal or external communications**. You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both. You can specify these options for your entire organization, or you can specify them for specific sites and pools. By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c36c-116">如果使用 Microsoft Exchange 集成来存储存档数据，则 Exchange 设置将控制是否存档 Lync 通信。</span><span class="sxs-lookup"><span data-stu-id="0c36c-116">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="0c36c-117">如果您的部署包含多个林，则必须在 Lync Server 和 Exchange 之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="0c36c-117">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="0c36c-118">控制内部或外部通信的存档仅适用于 Lync 策略。</span><span class="sxs-lookup"><span data-stu-id="0c36c-118">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="0c36c-119">对于 Exchange 集成的存档，这两种存档都将存档或不存档。</span><span class="sxs-lookup"><span data-stu-id="0c36c-119">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="0c36c-p106">**为什么启用存档**。可以在全局级别对整个部署启用和禁用存档，也可以对特定网站和用户启用和禁用存档。在这些级别中的每一个级别，您可指定是否启用 IM 会话（对等）、会议（多方会话）的存档或同时启用二者的存档。默认情况下，禁用存档。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p106">**Why enable Archiving**. You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users. At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both. By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="0c36c-124">**存档对于组织中用户的重要性**。</span><span class="sxs-lookup"><span data-stu-id="0c36c-124">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="0c36c-125">如果存档在您的组织中是至关重要的，则可以指定 Lync Server 2013 在关键模式下运行，这将阻止 IM 和会议会话（如果存档失败）。</span><span class="sxs-lookup"><span data-stu-id="0c36c-125">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="0c36c-126">例如：</span><span class="sxs-lookup"><span data-stu-id="0c36c-126">For example:</span></span>
    
      - <span data-ttu-id="0c36c-127">如果存档服务临时无法向数据库队列发送消息或向数据库插入消息，则将在部署中阻止 IM 和会议功能，直到恢复存档支持。</span><span class="sxs-lookup"><span data-stu-id="0c36c-127">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="0c36c-128">如果会议用户上载某个文件，但该文件无法复制到存档文件存储，则在问题解决之前，将在部署中阻止会议功能，但不会阻止 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="0c36c-128">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="0c36c-p108">您可在全局级别、网站级别和池级别配置此选项。默认情况下，不会启用临界模式。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p108">You can configure this option at the global level, site level, and pool level. By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="0c36c-131">**是否使用 Microsoft Exchange 集成**。</span><span class="sxs-lookup"><span data-stu-id="0c36c-131">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="0c36c-132">此选项将存档存储与 Exchange 2013 存储集成，以便您的 Lync Server 存档数据和 Exchange 2013 存档数据将一起存储在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="0c36c-132">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="0c36c-133">您可以使用 Microsoft Exchange 集成来存储驻留在 Exchange 2013 上的用户的存档数据，前提是他们的邮箱已被置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="0c36c-133">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="0c36c-134">如果您没有 Exchange 2013 部署，或者您不希望将其与 exchange 2013 集成，或者如果您有任何 Lync 用户未驻留在 Exchange 上，则可以使用 SQL Server 来存储 Lync 通信中的存档数据，从而部署单独的存档数据库。</span><span class="sxs-lookup"><span data-stu-id="0c36c-134">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="0c36c-135">您可以在全局级别、站点级别和池级别配置 Microsoft Exchange 集成选项。</span><span class="sxs-lookup"><span data-stu-id="0c36c-135">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="0c36c-136">默认情况下，不会启用 Microsoft Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="0c36c-136">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="0c36c-137">**管理存档数据的方式**。</span><span class="sxs-lookup"><span data-stu-id="0c36c-137">**How archived data is to be managed**.</span></span> <span data-ttu-id="0c36c-138">存档数据库不适用于长期保留，并且 Lync Server 2013 不会为存档数据提供电子发现 (搜索) 解决方案，因此需要将数据移动到其他存储。</span><span class="sxs-lookup"><span data-stu-id="0c36c-138">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="0c36c-139">Lync Server 提供了可用于导出存档数据的会话导出工具，该工具可创建存档数据的可搜索脚本。</span><span class="sxs-lookup"><span data-stu-id="0c36c-139">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="0c36c-140">对于全局策略以及您创建的每个网站和用户策略，可启用数据清除并指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="0c36c-140">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="0c36c-p111">在特定天数之后，清除导出的存档数据和存储的存档数据。可以指定的最小天数为一天。可以指定的最大天数为 2562 天。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p111">Purge both exported archiving data and stored archiving data after a specific number of days. The minimum number of days that you can specify is one day. The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="0c36c-p112">仅清除导出的存档数据。此选项会清除会话导出工具已导出并标记为可安全删除的所有记录。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p112">Purge exported archiving data only. This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="0c36c-p113">您可在全局级别、网站级别和池级别配置此选项。默认情况下，不会启用清除。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p113">You can configure this option at the global level, site level, and pool level. By default, purging is not enabled.</span></span>

<span data-ttu-id="0c36c-148">使用以下方法控制存档：</span><span class="sxs-lookup"><span data-stu-id="0c36c-148">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="0c36c-p114">**存档策略**。您可使用一个或多个存档策略启用和禁用内部和外部通信的存档。默认情况下，不会启用任何存档。您可以使用默认全局策略在部署中启用或禁用内部通信、外部通信或这二者的存档。您无法删除全局策略。您可指定一个或多个可选网站策略来启用或禁用特定网站的内部和外部通信的存档。还可指定一个或多个用户策略来启用或禁用特定用户和用户组的存档。用户级别的策略将覆盖网站策略。网站级别的策略将覆盖全局级别的策略。仅可为配置为使用用户级别的策略的特定用户实现用户级别的策略。仅当至少一个参与者的策略配置为启用存档时，才会对组即时消息和会议进行存档。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p114">**Archiving policies**. You use one or more Archiving policies to enable and disable archiving of internal and external communications. By default, no archiving is enabled. You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy. You cannot delete the global policy. You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites. You can also specify one or more user policies to enable or disable Archiving for specific users and user groups. User-level policies override site policies. Site-level policies override the global-level policies. User-level policies are implemented only for the specific users who are configured to use the policy. Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c36c-160">如果使用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖驻留在 Exchange 2013 服务器上的所有用户的 Lync Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="0c36c-160">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="0c36c-p115">**存档配置**。您可使用一个或多个存档配置指定本主题之前介绍过的大部分存档选项，但启用内部和外部通信的存档除外（使用存档策略配置，如上一项中所述）。存档配置包括默认的全局配置和可选的网站和池配置。您无法删除全局配置。池级别的配置将覆盖网站级别的配置。网站级别的配置将覆盖全局级别的配置。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p115">**Archiving configurations**. You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet). Archiving configurations include the default global configuration and optional site and pool configurations. You cannot delete the global configuration. Pool-level configurations override site-level configurations. Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="0c36c-p116">作为需求分析的一部分，您需要确定如何配置全局存档配置和全局存档策略。您还需要确定对任何网站级别存档配置、池级别存档配置、网站级别存档策略和用户级别存档策略的要求。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p116">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy. You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="0c36c-p117">如果为一个前端池或 Standard Edition 服务器部署存档，则应该为部署中的所有其他前端池和 Standard Edition 服务器启用存档。需要执行此操作的原因是，需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载该对话或会议的池上没有启用存档，则可能无法存档所有会议数据。存档对于启用存档的用户和所有 IM 消息仍然有效，但可能无法存档会议内容和事件。</span><span class="sxs-lookup"><span data-stu-id="0c36c-p117">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment. You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived. Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c36c-173">为了能够在维护组织的安全标准的同时委派管理任务，Lync Server 2013 &nbsp; 使用基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="0c36c-173">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="0c36c-174">利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。</span><span class="sxs-lookup"><span data-stu-id="0c36c-174">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="0c36c-175">若要配置 Lync 存档策略和存档配置，必须将用户分配给 CsArchivingAdministrator 角色（除非直接在部署存档的服务器上完成配置，而不是通过其他计算机远程执行）。</span><span class="sxs-lookup"><span data-stu-id="0c36c-175">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="0c36c-176">有关 RBAC 的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="0c36c-176">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="0c36c-177">有关存档部署所需的用户权限、权限和角色的列表，请参阅 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存档的部署清单</A>，它在规划文档和部署文档中都可用。</span><span class="sxs-lookup"><span data-stu-id="0c36c-177">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="0c36c-178">如果使用 Microsoft Exchange 集成，则 Exchange 策略的配置需要适当的管理员权限和权限。</span><span class="sxs-lookup"><span data-stu-id="0c36c-178">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="0c36c-179">有关详细信息，请参阅 Exchange 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="0c36c-179">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

