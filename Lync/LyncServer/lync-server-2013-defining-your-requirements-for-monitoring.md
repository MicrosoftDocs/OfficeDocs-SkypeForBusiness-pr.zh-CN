---
title: Lync Server 2013：定义您的监控要求
description: Lync Server 2013：定义监视的要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df121fd0cb5e7c0d39676f83ba2ea628d2e5587e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545378"
---
# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="8d368-103">定义在 Lync Server 2013 中进行监视的要求</span><span class="sxs-lookup"><span data-stu-id="8d368-103">Defining your requirements for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d368-104">_**上次修改的主题：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="8d368-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="8d368-105">简化了在 Microsoft Lync Server 2013 中进行监视的部署和安装还简化了定义组织的监控要求时所涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="8d368-105">Streamlining the deployment and installation of monitoring in Microsoft Lync Server 2013 has also streamlined the processes involved in defining your organization's requirements for monitoring.</span></span> <span data-ttu-id="8d368-106">然而，在开始安装和配置 Lync Server 2013 之前，还应解决几个关键问题：</span><span class="sxs-lookup"><span data-stu-id="8d368-106">Nevertheless, there are still several key issues that should be addressed before you begin to install and configure Lync Server 2013:</span></span>

<span data-ttu-id="8d368-107">**您要监视哪种类型的数据？**</span><span class="sxs-lookup"><span data-stu-id="8d368-107">**What type of data do you want to monitor?**</span></span> <span data-ttu-id="8d368-108">Lync Server 2013 使您能够监视两种不同类型的数据：呼叫详细记录 (CDR) 数据和 (QoE) 数据的体验质量。</span><span class="sxs-lookup"><span data-stu-id="8d368-108">Lync Server 2013 enables you to monitor two different types of data: call detailing recording (CDR) data and Quality of Experience (QoE) data.</span></span> <span data-ttu-id="8d368-109">呼叫详细信息记录提供了一种跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫）的使用方式的方法。即时消息 (IM) ;文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。</span><span class="sxs-lookup"><span data-stu-id="8d368-109">Call detail recording provides a way for you to track the usage of Lync Server features such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="8d368-110">此信息可帮助您了解 (使用哪些 Lync Server 功能，哪些功能未) ，还会提供有关这些功能的使用时间的信息。</span><span class="sxs-lookup"><span data-stu-id="8d368-110">This information helps you know which Lync Server features are being used (and which ones are not) and also provides information as to when these features are being used.</span></span> <span data-ttu-id="8d368-111">使用经验丰富的数据，可以维护组织中发出的音频和视频呼叫质量的记录，包括网络数据包丢失次数、背景噪音和 "抖动" (数据包延迟中的差异) 的情况。</span><span class="sxs-lookup"><span data-stu-id="8d368-111">Quality of Experience data allows you to maintain a record of the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

<span data-ttu-id="8d368-112">如果选择在 Lync Server 2013 中启用监控，则可以同时启用 CDR 监控和 QoE 监控，也可以选择启用一种监控类型，同时使其他类型保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="8d368-112">If you choose to enable monitoring in Lync Server 2013 you can enable both CDR monitoring and QoE monitoring, or you can choose to enable one type of monitoring while leaving the other type disabled.</span></span> <span data-ttu-id="8d368-113">例如，假设用户仅使用即时消息和文件传输，不进行音频或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="8d368-113">For example, suppose your users only use instant messaging and file transfers, and do not make audio or video calls.</span></span> <span data-ttu-id="8d368-114">在这种情况下，可能没有理由启用 QoE 监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-114">In that case, there might be little reason to enable QoE monitoring.</span></span> <span data-ttu-id="8d368-115">同样，Lync Server 还便于在部署监控后启用和禁用监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-115">Likewise, Lync Server makes it easy to enable and disable monitoring after monitoring has been deployed.</span></span> <span data-ttu-id="8d368-116">例如，您可能选择部署监控但最初禁用 QoE 监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-116">For example, you might choose to deploy monitoring but initially leave QoE monitoring disabled.</span></span> <span data-ttu-id="8d368-117">如果用户开始遇到音频或视频呼叫问题，您可以启用 QoE 监控并使用该数据帮助排查和解决这些问题</span><span class="sxs-lookup"><span data-stu-id="8d368-117">If your users begin to experience problems with audio or video calls you could then enable QoE monitoring and use that data to help you troubleshoot and resolve those problems.</span></span>

<span data-ttu-id="8d368-118">在安装 Lync server 和安装 Lync Server 后安装监视时，没有特别优势 (或缺点) 安装 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8d368-118">There is no particular advantage (or disadvantage) to installing monitoring at the same time you install Lync Server vs. installing monitoring after Lync Server has been installed.</span></span> <span data-ttu-id="8d368-119">需要谨记的一点是，在安装监控之前，必须选择一台计算机来承载后端监控存储，并且必须在该计算机上安装和配置支持的 SQL Server 版本，之后才能将该计算机用于监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-119">The one point to keep in mind is that, before you install monitoring, you must select a computer to host the backend monitoring store, and a supported version of SQL Server must be installing and configured on that computer before that computer can be used for monitoring.</span></span> <span data-ttu-id="8d368-120">如果已在计算机上安装了 SQL Server，并且该计算机已准备好使用，则可以在安装 Lync Server 的同时安装监视。</span><span class="sxs-lookup"><span data-stu-id="8d368-120">If you have already installed SQL Server on a computer and that computer is ready for use then you can install monitoring at the same time you install Lync Server.</span></span> <span data-ttu-id="8d368-121">如果没有后端计算机准备就绪，则可以继续安装 Lync Server，然后在后端计算机准备好使用时安装监视。</span><span class="sxs-lookup"><span data-stu-id="8d368-121">If you do not have a backend computer ready then you can proceed to install Lync Server by itself, then install monitoring whenever the backend computer is ready for use.</span></span>

<span data-ttu-id="8d368-122">**想要何时安装监控？**</span><span class="sxs-lookup"><span data-stu-id="8d368-122">**When do you want to install monitoring?**</span></span> <span data-ttu-id="8d368-123">可以在安装和配置 Lync Server 2013 时安装和配置监控;Lync Server 部署向导将向您提供在安装过程中将前端池与监控数据库相关联的机会。</span><span class="sxs-lookup"><span data-stu-id="8d368-123">Monitoring can be installed and configured at the same time you install and configured Lync Server 2013; the Lync Server Deployment Wizard will provide you with the opportunity to associate your Front End pools with a monitoring database during setup.</span></span> <span data-ttu-id="8d368-124">或者，也可以在安装 Lync Server 本身后安装监视;可以通过使用拓扑生成器将前端池和服务器与监控数据库关联，然后发布修订后的拓扑来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="8d368-124">Alternatively, you can install monitoring after Lync Server itself has been installed; this can be done by using Topology Builder to associate your Front End pools and servers with a monitoring database, and then publishing the revised topology.</span></span>

<span data-ttu-id="8d368-125">**需要多少个后端监控数据库？**</span><span class="sxs-lookup"><span data-stu-id="8d368-125">**How many backend monitoring databases do you need?**</span></span> <span data-ttu-id="8d368-126">单个监视数据库可以支持成千上万个用户 (为 Microsoft Lync Server 2010，据此估计，并置数据库的监视和存档可支持240000用户) 。</span><span class="sxs-lookup"><span data-stu-id="8d368-126">A single monitoring database can support tens of thousands of users (for Microsoft Lync Server 2010, it was estimated that a collocated database for both monitoring and archiving could support 240,000 users).</span></span> <span data-ttu-id="8d368-127">此外，一个监控数据库可以被多个前端池使用；如果组织中有三个前端池，则可以将全部三个池与同一后端存储关联。</span><span class="sxs-lookup"><span data-stu-id="8d368-127">In addition, a single monitoring database can be used by multiple Front End pools; if you have three Front End pools in your organization then you could associate all three of those pools with the same backend store.</span></span>

<span data-ttu-id="8d368-p107">这就意味着，对于许多组织来说，数据库容量并不是确定所需后端监控数据库数量时的决定因素。相反，网络速度可能是更重要的考虑事项。假设您有三个前端池，但其中一个池位于慢速网络连接。在这种情况下，您可能想要使用两个监控数据库：一个数据库为网络连接良好的两个池提供服务，另一个数据库为网络连接较慢的池提供服务。</span><span class="sxs-lookup"><span data-stu-id="8d368-p107">This simply means that, for many organizations, database capacity will not be the deciding factor when determining the number of backend monitoring databases that will be required. Instead, a more important consideration could be network speed. Suppose you have three Front End pools, but one of those pools is located across a slow network connection. In that case, you might want to use two monitoring databases: one database to service the two pools with the good network connection, and a separate database to service the pool with the slower network connection.</span></span>

<span data-ttu-id="8d368-132">在规划您的监控基础结构时，还应考虑 Lync Server 2013 支持使用镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="8d368-132">When planning your monitoring infrastructure you should also take into account that Lync Server 2013 supports the use of mirror databases.</span></span> <span data-ttu-id="8d368-133">“数据库镜像”提供了同时维护两个数据库副本，且每个数据库位于不同服务器上的方式。</span><span class="sxs-lookup"><span data-stu-id="8d368-133">"Database mirroring" provides a way for you to simultaneously maintain two copies of a database, with each database residing on a different server.</span></span> <span data-ttu-id="8d368-134">任何时候将数据写入主数据库，相同的数据也会写入镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="8d368-134">Any time data is written to a primary database that same data is also written to the mirror database.</span></span> <span data-ttu-id="8d368-135">如果主数据库应失败或因其他原因而变得不可用，可以使用简单的 Lync Server PowerShell 命令 "故障转移" 到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="8d368-135">If the primary database should fail or otherwise become unavailable, you can "fail over" to the mirror database by using a simple Lync Server PowerShell command.</span></span> <span data-ttu-id="8d368-136">例如：</span><span class="sxs-lookup"><span data-stu-id="8d368-136">For example:</span></span>

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

<span data-ttu-id="8d368-137">这对于规划来说很重要，仅仅因为镜像需要将所需数据库数量翻倍：除了各个主数据库，还需要第二个数据库作为镜像。</span><span class="sxs-lookup"><span data-stu-id="8d368-137">This is important for planning purposes simply because mirroring will require you to double your required number of databases: in addition to each primary database you will need a second database to act as the mirror.</span></span>

<span data-ttu-id="8d368-138">**你的 Lync Server 网站是否需要自己的自定义监视配置？**</span><span class="sxs-lookup"><span data-stu-id="8d368-138">**Do your Lync Server sites need their own custom monitoring configurations?**</span></span> <span data-ttu-id="8d368-139">安装 Lync Server 2013 时，还会安装 CDR 和 QoE 配置设置的全局集合;这些全局集合使您能够将相同的 CDR 和 QoE 设置应用于整个组织。</span><span class="sxs-lookup"><span data-stu-id="8d368-139">When you install Lync Server 2013 you also install global collections of CDR and QoE configuration settings; these global collections give you the ability to apply the same CDR and QoE settings to your entire organization.</span></span> <span data-ttu-id="8d368-140">这在许多情况下将足够：比如通常您会想要为所有用户启用 CDR 监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-140">In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.</span></span>

<span data-ttu-id="8d368-141">但是，有时也可能需要对不同的网站应用不同的设置。</span><span class="sxs-lookup"><span data-stu-id="8d368-141">However, there might also be times when you want to apply different settings to different sites.</span></span> <span data-ttu-id="8d368-142">例如，您可能希望在 Redmond 网站中同时使用 CDR 和 QoE 监控，但仅在都柏林网站中使用 CDR 监控。</span><span class="sxs-lookup"><span data-stu-id="8d368-142">For example, perhaps you want to use both CDR and QoE monitoring in your Redmond site, but only use CDR monitoring in your Dublin site.</span></span> <span data-ttu-id="8d368-143">同样，您可能希望在 Redmond 网站中保留60天的监控数据，但只需在都柏林网站中维护此类型的数据30天。</span><span class="sxs-lookup"><span data-stu-id="8d368-143">Likewise, you might want to retain monitoring data for 60 days in the Redmond site but only need to maintain this type of data for 30 days in the Dublin site.</span></span> <span data-ttu-id="8d368-144">Lync Server 2013 允许您在网站范围创建单独的 CDR 和 QoE 配置设置集合;这使您能够以不同的方式管理每个网站。</span><span class="sxs-lookup"><span data-stu-id="8d368-144">Lync Server 2013 allows you to create separate collections of CDR and QoE configuration settings at the site scope; that enables you to manage each site differently.</span></span> <span data-ttu-id="8d368-145"> (这包括启用和禁用监控，以及配置管理设置，如保留数据的时间。 ) </span><span class="sxs-lookup"><span data-stu-id="8d368-145">(This includes both enabling and disabling monitoring as well as configuring management settings such as how long data is to be retained.)</span></span>

<span data-ttu-id="8d368-p111">请注意，您既可以在部署监控前也可以在部署监控后做出此决定。例如，您可以先部署监控，然后使用全局设置管理整个组织。如果以后改变主意，例如可以为 Redmond 站点创建单独的设置集合，然后使用这些设置管理 Redmond 的监控。（在站点作用域内应用的设置始终优先于在全局作用域内应用的设置。）如果您再次改变主意，只需删除应用于 Redmond 站点的配置设置。删除站点设置集合后，全局设置集合将自动应用于该站点。</span><span class="sxs-lookup"><span data-stu-id="8d368-p111">Note that you can make this decision before you deploy monitoring or after you deploy monitoring. For example, you can deploy monitoring and then manage the entire organization by using the global settings. If you later change your mind, you can create a separate collection of settings for, say, the Redmond site, and then use those settings to manage monitoring for Redmond. (Settings applied at the site scope always take precedence over settings applied at the global scope.) If you change your mind again, you can simply delete the configuration settings applied to the Redmond site. When a collection of site settings is removed then the global collection of settings will automatically be applied to that site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

