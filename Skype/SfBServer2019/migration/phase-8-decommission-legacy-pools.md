---
title: 第8阶段取消授权旧版池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: 以下主题提供了更新 DNS 条目、移动内容管理服务器、取消池以及从旧部署中停用和删除服务器和池的指南。 不需要本部分中列出的所有过程。 阅读文档并确定要使用的解除授权过程。
ms.openlocfilehash: 2398e9ce681edc2bba9f4f93d54f39d727bdb75e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813100"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="bd522-105">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="bd522-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="bd522-106">以下主题提供了更新 DNS 条目、移动内容管理服务器、取消池以及从旧部署中停用和删除服务器和池的指南。</span><span class="sxs-lookup"><span data-stu-id="bd522-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="bd522-107">不需要本部分中列出的所有过程。</span><span class="sxs-lookup"><span data-stu-id="bd522-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="bd522-108">阅读文档并确定要使用的解除授权过程。</span><span class="sxs-lookup"><span data-stu-id="bd522-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="bd522-109">有关删除服务器和服务器角色的过时但详尽的文章，以及用于取消部署的分步指南，请下载[卸载 Microsoft Lync server 并删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="bd522-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="bd522-110">有关迁移和升级 Microsoft 统一通信托管 API （UCMA）应用程序的信息，请参阅解除旧版环境之前，请参阅[UCMA 应用程序：共存、迁移和升级方案](https://go.microsoft.com/fwlink/p/?LinkId=269555)。</span><span class="sxs-lookup"><span data-stu-id="bd522-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bd522-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd522-111">In this section</span></span>

> [<span data-ttu-id="bd522-112">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="bd522-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="bd522-113">将旧式安装中心管理服务器移动到 Skype for business Server 2019</span><span class="sxs-lookup"><span data-stu-id="bd522-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="bd522-114">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="bd522-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="bd522-115">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="bd522-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="bd522-116">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="bd522-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="bd522-117">删除企业版前端服务器或标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="bd522-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="bd522-118">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="bd522-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

