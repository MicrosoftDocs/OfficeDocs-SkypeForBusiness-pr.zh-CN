---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：阅读本主题，了解 Skype for business Server 2015 中持久聊天服务器的硬件和软件要求。
ms.openlocfilehash: cba3b340710e4c5ed041c085f39f1a4cc209a789
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815750"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="9cdb9-103">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="9cdb9-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9cdb9-104">**摘要：** 阅读本主题，了解 Skype for business Server 2015 中持久聊天服务器的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9cdb9-105">持久聊天服务器可以与 Skype for business Server 2015 企业版或标准版一起安装。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="9cdb9-106">要求取决于你已安装的 Skype for business Server 2015 版本以及你的企业的性能要求。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="9cdb9-107">Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="9cdb9-108">持久聊天包含前端组件以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="9cdb9-109">在部署持久聊天服务器之前，必须确保满足以下硬件和软件要求：</span><span class="sxs-lookup"><span data-stu-id="9cdb9-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="9cdb9-110">满足最低要求以支持 Skype for Business Server 2015、持久聊天服务器、数据库服务器和文件服务器的硬件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="9cdb9-111">有关详细信息，请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="9cdb9-112">支持的操作系统和数据库软件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="9cdb9-113">有关受支持的操作系统和数据库软件以及 Windows 更新要求的详细信息，请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="9cdb9-114">Skype for Business 服务器2015前端服务器。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="9cdb9-115">前端服务器是会话初始协议（SIP）路由的基础，用于在运行持久聊天服务器的计算机与可能的持久聊天功能之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="9cdb9-116">消息队列软件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-116">Message Queuing software.</span></span> <span data-ttu-id="9cdb9-117">如果已部署，则为持久聊天服务器和持久聊天合规性服务使用。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="9cdb9-118">以下部分介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="9cdb9-119">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9cdb9-120">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="9cdb9-121">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9cdb9-122">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="9cdb9-123">前端服务器要求</span><span class="sxs-lookup"><span data-stu-id="9cdb9-123">Front End Server requirements</span></span>

<span data-ttu-id="9cdb9-124">前端服务器要求取决于您是否要部署 Skype for business Server 2015 企业版或标准版的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="9cdb9-125">如果要为 Skype for Business Server 2015 企业版部署持久聊天服务器，可以在企业版池中的一台或多台独立计算机上部署持久聊天服务器前端服务器。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="9cdb9-126">您不能在 Skype for Business Server 2015 前端服务器上 collocate 持久聊天前端服务器。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="9cdb9-127">单个持久聊天服务器前端服务器可以支持20000活动用户。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="9cdb9-128">你可以拥有最多4个活动前端的持久聊天服务器池，从而支持总共80000并发用户。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="9cdb9-129">如果你要部署 Skype for business Server 2015 标准版的持久聊天服务器，你可以与前端服务器 collocate 持久聊天。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="9cdb9-130">此单服务器部署可最多支持 20,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="9cdb9-131">持久聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="9cdb9-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="9cdb9-132">持久聊天服务器要求 SQL Server 数据库软件存储聊天室历史记录和内容、配置数据、用户预配数据以及其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="9cdb9-133">或者，它使用持久聊天合规数据库来存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="9cdb9-134">持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="9cdb9-135">如果要在 Skype for Business Server 2015 企业版中安装持久聊天服务器，以确保获得最佳性能，建议安装持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="9cdb9-136">如果你要安装 Skype for Business Server 2015 标准版的持久聊天服务器，你可以在本地 SQL Server Express 实例上部署持久的聊天应用商店后端服务器。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="9cdb9-137">持久聊天数据库（mgc）和合规性数据库（mgccomp）可以位于 SQL Server 的同一实例中，也可以位于不同的 SQL Server 上。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="9cdb9-138">为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="9cdb9-139">持久聊天数据库服务器的服务器平台需要与 Skype for Business Server 2015 后端数据库服务器相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="9cdb9-140">有关信息，请参阅 [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="9cdb9-141">在数据库服务器上，确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="9cdb9-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="9cdb9-142">Microsoft SQL Server 2017 和最新服务包。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="9cdb9-143">Microsoft SQL Server 2016 Service Pack 1，必须运行 Skype for Business Server 累积更新7或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="9cdb9-144">我们建议使用最新的 service pack 运行 SQL Server 2016。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="9cdb9-145">有关如何安装 Microsoft SQL Server 2016 的详细信息，请参阅[安装 SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="9cdb9-146">Microsoft SQL Server 2014，必须运行 Skype for Business Server 累积更新6或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="9cdb9-147">我们建议使用最新的 service pack 运行 SQL Server 2014。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="9cdb9-148">有关如何安装 Microsoft SQL Server 2014 的详细信息，请参阅[安装 SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="9cdb9-149">Microsoft SQL Server 2012 （64位版），我们建议使用最新的 service pack 运行。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="9cdb9-150">有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅[安装 SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="9cdb9-151">持久聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="9cdb9-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="9cdb9-152">有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅[部署 Skype For Business Server 2015](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdb9-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="9cdb9-153">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="9cdb9-153">For more information</span></span>

<span data-ttu-id="9cdb9-154">有关硬件和软件要求的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="9cdb9-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="9cdb9-155">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9cdb9-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="9cdb9-156">Environmental requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9cdb9-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

