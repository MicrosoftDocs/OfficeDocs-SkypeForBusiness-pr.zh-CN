---
title: Lync Server 2013：支持的服务器迁移路径和共存方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="13804-102">Lync Server 2013 中支持的服务器迁移路径和共存方案</span><span class="sxs-lookup"><span data-stu-id="13804-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13804-103">_**主题上次修改时间：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="13804-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="13804-104">Lync Server 2013 支持从以下任一项进行迁移：</span><span class="sxs-lookup"><span data-stu-id="13804-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="13804-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="13804-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="13804-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="13804-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="13804-107">不支持从运行这两个以前版本的环境迁移。</span><span class="sxs-lookup"><span data-stu-id="13804-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="13804-108">不支持从早期版本（如 Microsoft Office 通信服务器2007或实时通信服务器2005）进行迁移。</span><span class="sxs-lookup"><span data-stu-id="13804-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="13804-109">如果以前的部署包含群组聊天，则必须单独迁移。</span><span class="sxs-lookup"><span data-stu-id="13804-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="13804-110">迁移方法</span><span class="sxs-lookup"><span data-stu-id="13804-110">Migration Methods</span></span>

<span data-ttu-id="13804-111">支持迁移所有 Lync Server 拓扑和服务器角色。</span><span class="sxs-lookup"><span data-stu-id="13804-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="13804-112">你可以从一个拓扑迁移到不同拓扑，包括从标准版服务器到企业版 server。</span><span class="sxs-lookup"><span data-stu-id="13804-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="13804-113">Lync Server 2013 仅支持以下迁移方法：</span><span class="sxs-lookup"><span data-stu-id="13804-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="13804-114">**并行迁移。**</span><span class="sxs-lookup"><span data-stu-id="13804-114">**Side-by-side migration.**</span></span> <span data-ttu-id="13804-115">在并行迁移中，Lync Server 2013 与现有 Microsoft Lync Server 2010 或 Office 通信服务器 2007 R2 部署一起部署，然后你将操作转移到新服务器并将用户移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="13804-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="13804-116">在迁移期间，此方法需要其他服务器平台，包括硬件和软件，并且新配置中的系统名称和池名称不同。</span><span class="sxs-lookup"><span data-stu-id="13804-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="13804-117">如果需要回滚到以前的版本，你可以将操作转移回以前的服务器。</span><span class="sxs-lookup"><span data-stu-id="13804-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="13804-118">不支持跨 Active Directory 域服务林进行迁移。</span><span class="sxs-lookup"><span data-stu-id="13804-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="13804-119">推荐的迁移路径是分段方法。</span><span class="sxs-lookup"><span data-stu-id="13804-119">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="13804-120">有关从早期版本迁移的详细信息，包括组件部署的相应阶段，请参阅迁移文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="13804-120">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="13804-121">从 Lync Server 2010 迁移到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13804-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="13804-122">从 Office Communications Server 2007 R2 迁移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13804-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="13804-123">从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="13804-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="13804-124">共存方案</span><span class="sxs-lookup"><span data-stu-id="13804-124">Coexistence Scenarios</span></span>

<span data-ttu-id="13804-125">Lync Server 2013 可与 Lync Server 2010 部署或 Office 通信服务器的组件共存，以 2007 R2 部署。</span><span class="sxs-lookup"><span data-stu-id="13804-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="13804-126">不支持同时通过 Lync Server 2010 和 Office 通信服务器同时部署 lync Server 2013 和 Office 通信服务器 2007 R2 （所有三个版本的并发部署）。</span><span class="sxs-lookup"><span data-stu-id="13804-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="13804-127">在分阶段迁移期间，以前的 Lync Server 2010 或 Office 通信服务器 2007 R2 部署与新的 Lync Server 2013 部署临时 coexists，混合版本路由支持将受到限制。</span><span class="sxs-lookup"><span data-stu-id="13804-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="13804-128">有关详细信息，请参阅迁移文档。</span><span class="sxs-lookup"><span data-stu-id="13804-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="13804-129">你必须使用运行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 的单独和不同的计算机来2013数据库实例。</span><span class="sxs-lookup"><span data-stu-id="13804-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="13804-130">你无法对用于 Lync Server 2010 或 Office 通信服务器 2007 R2 前端池的 Lync Server 2013 前端池使用相同的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="13804-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="13804-131">如果在拓扑生成器中为已部署 Lync Server 2010 或 Office 通信服务器 2007 R2 的部署定义和配置 Lync Server 2013，拓扑生成器将不允许定义已在中使用的 Lync Server 2013 实例拓扑。</span><span class="sxs-lookup"><span data-stu-id="13804-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="13804-132">拓扑生成器将显示以下消息，通知你此问题： "服务器\[\]的 sql server FQDN 已包含一个 sql 实例托管角色 ' 用户存储 '。"</span><span class="sxs-lookup"><span data-stu-id="13804-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13804-133">如果你打算部署 Lync Server 2013 部署中新的服务器角色，应首先升级你的现有部署，如迁移文档和部署文档中所述，然后部署新的服务器角色，如中所述。规划文档和部署文档。</span><span class="sxs-lookup"><span data-stu-id="13804-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="13804-134">如果你正在迁移早期版本的群组聊天，请在完成从 Lync Server 2010 或 Office 通信服务器 2007 R2 迁移所有其他组件的过程后，将其迁移到最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="13804-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="13804-135">有关 Lync Server 2010 或 Office 通信服务器 2007 R2 和 Lync Server 2013 组件的共存和迁移的特定共存要求和其他详细信息，请参阅迁移文档中的[从 Lync server 2010 迁移到 Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)和[从 Office 通信服务器 2007 R2 迁移到 lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 。</span><span class="sxs-lookup"><span data-stu-id="13804-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="13804-136">有关客户端的混合版本支持的详细信息，请参阅[Lync Server 2013 中以前的部署支持的客户端](lync-server-2013-supported-clients-from-previous-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="13804-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

