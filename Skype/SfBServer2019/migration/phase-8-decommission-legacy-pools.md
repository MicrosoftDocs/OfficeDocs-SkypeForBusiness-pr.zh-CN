---
title: 第 8 的取消旧池的阶段
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: 以下主题提供了更新 DNS 条目、 移动 Content Management Server、 停用池和停用和删除服务器和池从旧部署指南。 并非所有本节中列出的过程都是必需的。 阅读的文档，并确定要使用哪些停用过程。
ms.openlocfilehash: 0e5c7bebeb0449f8fa71942f2ac68ff9d7eb017a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370758"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="3e0a3-105">第 8 阶段： 停用旧池</span><span class="sxs-lookup"><span data-stu-id="3e0a3-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="3e0a3-106">以下主题提供了更新 DNS 条目、 移动 Content Management Server、 停用池和停用和删除服务器和池从旧部署指南。</span><span class="sxs-lookup"><span data-stu-id="3e0a3-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="3e0a3-107">并非所有本节中列出的过程都是必需的。</span><span class="sxs-lookup"><span data-stu-id="3e0a3-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="3e0a3-108">阅读的文档，并确定要使用哪些停用过程。</span><span class="sxs-lookup"><span data-stu-id="3e0a3-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="3e0a3-109">在删除服务器和服务器角色和停用部署的分步指南过期，但详尽文章，下载[卸载 Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="3e0a3-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3e0a3-110">有关迁移和升级 Microsoft 统一通信托管 API (UCMA) 应用程序之前停用旧环境的信息，请参阅[UCMA 应用程序： 共存、 迁移和升级方案](https://go.microsoft.com/fwlink/p/?LinkId=269555)。</span><span class="sxs-lookup"><span data-stu-id="3e0a3-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3e0a3-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="3e0a3-111">In this section</span></span>

> [<span data-ttu-id="3e0a3-112">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="3e0a3-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="3e0a3-113">将旧安装中央管理服务器移动到 Skype 进行业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="3e0a3-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="3e0a3-114">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="3e0a3-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="3e0a3-115">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="3e0a3-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="3e0a3-116">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="3e0a3-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="3e0a3-117">删除 Enterprise Edition 前端服务器或 Standard Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="3e0a3-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="3e0a3-118">删除后端服务器上 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="3e0a3-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

