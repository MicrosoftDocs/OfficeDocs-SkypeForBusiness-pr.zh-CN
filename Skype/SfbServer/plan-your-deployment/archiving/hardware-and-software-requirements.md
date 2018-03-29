---
title: Skype for Business Server 2015 中的存档的硬件和软件要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 摘要： 请阅读本主题，以了解有关硬件和软件要求的存档在 Skype 业务服务器 2015年。
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="7818e-103">Skype for Business Server 2015 中的存档的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="7818e-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7818e-104">**摘要：**阅读本主题以了解有关硬件和软件要求的存档在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="7818e-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7818e-105">Skype 业务服务器 2015年存档现在位于前端角色中，因此您不需要安装单独的服务器。</span><span class="sxs-lookup"><span data-stu-id="7818e-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="7818e-106">但是，执行此操作，需要考虑以下要求：</span><span class="sxs-lookup"><span data-stu-id="7818e-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="7818e-107">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="7818e-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="7818e-108">必备软件要求</span><span class="sxs-lookup"><span data-stu-id="7818e-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="7818e-109">数据存储要求</span><span class="sxs-lookup"><span data-stu-id="7818e-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="7818e-110">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="7818e-110">Infrastructure requirements</span></span>

<span data-ttu-id="7818e-111">Skype 的业务服务器归档基础架构的要求是一样的 Skype 业务服务器的部署。</span><span class="sxs-lookup"><span data-stu-id="7818e-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="7818e-112">有关详细信息，请参阅[您的业务环境的 Skype 的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="7818e-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="7818e-113">必备软件要求</span><span class="sxs-lookup"><span data-stu-id="7818e-113">Prerequisite software requirements</span></span>

<span data-ttu-id="7818e-114">存档的 Skype 业务服务器的前提条件是比早期版本的 Lync Server 简单由于以下原因：</span><span class="sxs-lookup"><span data-stu-id="7818e-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="7818e-115">因为存档不再是一个服务器角色，您不需要安装单独的服务器进行存档。</span><span class="sxs-lookup"><span data-stu-id="7818e-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="7818e-116">而是在每个 Enterprise Edition 前端池和每台 Standard Edition 服务器上自动安装和激活统一数据收集代理。</span><span class="sxs-lookup"><span data-stu-id="7818e-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="7818e-117">您需要使用拓扑生成器启用和发布存档拓扑。</span><span class="sxs-lookup"><span data-stu-id="7818e-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="7818e-118">归档使用 Skype 业务服务器用于临时存储会议内容的文件，因此不会设置一个单独的文件存储存档的文件存储。</span><span class="sxs-lookup"><span data-stu-id="7818e-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="7818e-119">在 Skype 业务服务器，Microsoft 消息队列不需要。</span><span class="sxs-lookup"><span data-stu-id="7818e-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="7818e-120">数据存储要求</span><span class="sxs-lookup"><span data-stu-id="7818e-120">Data Storage requirements</span></span>

<span data-ttu-id="7818e-p104">您需要为存档存储设置基础结构。这包括选择以下一个或两个选项：</span><span class="sxs-lookup"><span data-stu-id="7818e-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="7818e-123">**Microsoft Exchange 存储**。</span><span class="sxs-lookup"><span data-stu-id="7818e-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="7818e-124">会议内容文件（比如 PowerPoint 演示文稿）都作为附件进行存档。</span><span class="sxs-lookup"><span data-stu-id="7818e-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="7818e-125">如果您想要存储 Skype 业务与法规遵从性的 Exchange 数据的存档数据，必须使用您的 Exchange 部署的 Exchange，并确保最大存储容量支持会议内容文件的存储。</span><span class="sxs-lookup"><span data-stu-id="7818e-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="7818e-126">您必须部署 Exchange 部署和启用存档使用 Microsoft Exchange 集成选项之前。</span><span class="sxs-lookup"><span data-stu-id="7818e-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="7818e-127">如果您选择使用 Exchange 存储，您不需要部署单独的 SQL Server 数据库的存档，除非您的业务用户没有驻留在 Exchange 服务器有 Skype。</span><span class="sxs-lookup"><span data-stu-id="7818e-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="7818e-128">如果您部署存档使用 Microsoft Exchange 集成选项，Skype 业务存档数据仅用于驻留在您的 Exchange 服务器的用户交换法规遵从性数据一起存储。</span><span class="sxs-lookup"><span data-stu-id="7818e-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="7818e-129">**Skype 业务服务器存档存储**。</span><span class="sxs-lookup"><span data-stu-id="7818e-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="7818e-130">为没有驻留在 Exchange 服务器的用户提供支持或如果您不想使用 Microsoft Exchange 集成选项，您必须部署使用的是 SQL Server 数据库的存档存储。</span><span class="sxs-lookup"><span data-stu-id="7818e-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="7818e-131">Skype 业务服务器支持下面的 SQL Server 的 64 位版本：</span><span class="sxs-lookup"><span data-stu-id="7818e-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="7818e-132">Microsoft SQL Server 2008 R2 企业</span><span class="sxs-lookup"><span data-stu-id="7818e-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="7818e-133">Microsoft SQL Server 2008 R2 标准</span><span class="sxs-lookup"><span data-stu-id="7818e-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="7818e-134">Microsoft SQL Server 2012年企业</span><span class="sxs-lookup"><span data-stu-id="7818e-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="7818e-135">Microsoft SQL Server 2012年标准</span><span class="sxs-lookup"><span data-stu-id="7818e-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="7818e-136">Microsoft SQL Server 2014年企业</span><span class="sxs-lookup"><span data-stu-id="7818e-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="7818e-137">Microsoft SQL Server 2014年标准</span><span class="sxs-lookup"><span data-stu-id="7818e-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7818e-138">Microsoft SQL Server Express 版本不支持存档。</span><span class="sxs-lookup"><span data-stu-id="7818e-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="7818e-139">不支持 32 位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7818e-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="7818e-140">其他 SQL Server 要求和限制，请参阅[您的业务环境的 Skype 的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="7818e-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="7818e-141">您必须设置然后再部署和启用存档的 SQL Server 平台。</span><span class="sxs-lookup"><span data-stu-id="7818e-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="7818e-142">如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。</span><span class="sxs-lookup"><span data-stu-id="7818e-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="7818e-143">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="7818e-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="7818e-144">有关 SQL Server 的详细信息，请参阅[SQL Server 技术中心](https://go.microsoft.com/fwlink/p/?linkID=129045)。</span><span class="sxs-lookup"><span data-stu-id="7818e-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="7818e-145">存档带来的负载提升可能非常显著。</span><span class="sxs-lookup"><span data-stu-id="7818e-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="7818e-146">因此，您应该确保磁盘空间适合前端服务器在其启用存档。</span><span class="sxs-lookup"><span data-stu-id="7818e-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

