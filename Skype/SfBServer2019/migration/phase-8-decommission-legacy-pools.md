---
title: 第8阶段取消旧池的授权
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: 以下主题提供了有关更新 DNS 条目、移动内容管理服务器、取消池以及从旧部署中停用和删除服务器和池的指南。 并非本节中列出的所有过程都是必需的。 请阅读本文档并确定要使用的停用过程。
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753690"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="819cd-105">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="819cd-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="819cd-106">以下主题提供了有关更新 DNS 条目、移动内容管理服务器、取消池以及从旧部署中停用和删除服务器和池的指南。</span><span class="sxs-lookup"><span data-stu-id="819cd-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="819cd-107">并非本节中列出的所有过程都是必需的。</span><span class="sxs-lookup"><span data-stu-id="819cd-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="819cd-108">请阅读本文档并确定要使用的停用过程。</span><span class="sxs-lookup"><span data-stu-id="819cd-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="819cd-109">有关删除服务器和服务器角色的已发布但不详尽的文章，以及有关解除部署的分步指南，请下载[卸载 Microsoft Lync server 并删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="819cd-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="819cd-110">有关迁移和升级 Microsoft 统一通信托管 API （UCMA）应用程序的信息，请参阅[UCMA 应用程序：共存、迁移和升级方案](https://go.microsoft.com/fwlink/p/?LinkId=269555)，在取消旧环境的迁移和升级。</span><span class="sxs-lookup"><span data-stu-id="819cd-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="819cd-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="819cd-111">In this section</span></span>

> [<span data-ttu-id="819cd-112">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="819cd-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="819cd-113">将旧版安装中心管理服务器移动到 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="819cd-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="819cd-114">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="819cd-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="819cd-115">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="819cd-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="819cd-116">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="819cd-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="819cd-117">删除 Enterprise Edition 前端服务器或 Standard Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="819cd-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="819cd-118">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="819cd-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

