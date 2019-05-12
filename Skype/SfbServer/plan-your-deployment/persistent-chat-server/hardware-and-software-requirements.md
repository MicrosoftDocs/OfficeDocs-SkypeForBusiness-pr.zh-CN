---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要： 阅读本主题可了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。
ms.openlocfilehash: 26c434bd915ab7b19aa096e47e469f5b6c16dd6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924449"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="aed06-103">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="aed06-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aed06-104">**摘要：** 阅读此主题以了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="aed06-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="aed06-105">业务 Server 2015 Enterprise Edition 或 Standard Edition，可以使用 Skype 安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="aed06-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="aed06-106">要求取决于您已安装的业务服务器 2015 Skype 的是哪个版本，以及您的业务的性能要求。</span><span class="sxs-lookup"><span data-stu-id="aed06-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="aed06-107">Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="aed06-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="aed06-108">持久聊天包含前端组件以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="aed06-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="aed06-109">部署持久聊天服务器之前，您必须确保满足以下硬件和软件要求：</span><span class="sxs-lookup"><span data-stu-id="aed06-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="aed06-110">满足最低要求以支持 Skype 业务服务器 2015年、 持久聊天服务器、 数据库服务器和文件服务器的硬件。</span><span class="sxs-lookup"><span data-stu-id="aed06-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="aed06-111">有关详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aed06-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="aed06-112">支持的操作系统和数据库软件。</span><span class="sxs-lookup"><span data-stu-id="aed06-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="aed06-113">有关支持的操作系统和数据库软件和窗口的详细信息更新要求，请参阅[业务服务器 2015年的 Skype 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aed06-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="aed06-114">Skype 业务 Server 2015 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="aed06-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="aed06-115">前端服务器是基础的会话初始协议 (SIP) 路由，这将使计算机运行 Persistent Chat Server 和持久聊天功能之间的通信可能。</span><span class="sxs-lookup"><span data-stu-id="aed06-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="aed06-116">消息队列软件。</span><span class="sxs-lookup"><span data-stu-id="aed06-116">Message Queuing software.</span></span> <span data-ttu-id="aed06-117">如果部署 Persistent Chat Server 和持久聊天合规性服务，使用。</span><span class="sxs-lookup"><span data-stu-id="aed06-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="aed06-118">以下各节介绍对于 Persistent Chat Server 和存储的持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="aed06-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="aed06-119">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="aed06-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aed06-120">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="aed06-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="aed06-121">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="aed06-121">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="aed06-122">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="aed06-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="aed06-123">前端服务器要求</span><span class="sxs-lookup"><span data-stu-id="aed06-123">Front End Server requirements</span></span>

<span data-ttu-id="aed06-124">前端服务器要求取决于是否为业务 Server 2015 Enterprise Edition 或 Standard Edition 部署与 Skype 的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="aed06-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="aed06-125">如果您业务 Server 2015 Enterprise Edition 部署与 Skype 的持久聊天服务器，则可以部署持久聊天服务器前端服务器中的企业版池的一个或多个独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="aed06-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="aed06-126">您不能将持久聊天前端服务器上的 Skype 并置的业务 Server 2015 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="aed06-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="aed06-127">单个持久聊天服务器前端服务器可支持 20,000 活动用户。</span><span class="sxs-lookup"><span data-stu-id="aed06-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="aed06-128">您可以将持久聊天服务器池具有最多 4 从而支持 80,000 个并发用户，总计的活动前端。</span><span class="sxs-lookup"><span data-stu-id="aed06-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="aed06-129">如果您业务 Server 2015 Standard Edition 部署与 Skype 的持久聊天服务器，可以与前端服务器的持久聊天将并置。</span><span class="sxs-lookup"><span data-stu-id="aed06-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="aed06-130">此单服务器部署可最多支持 20,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="aed06-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="aed06-131">持久聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="aed06-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="aed06-132">持久聊天服务器需要 SQL Server 数据库软件存储聊天室的历史记录和内容、 配置数据、 用户设置数据和其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="aed06-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="aed06-133">（可选），它使用的持久聊天合规性数据库来存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="aed06-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="aed06-134">持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。</span><span class="sxs-lookup"><span data-stu-id="aed06-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="aed06-135">如果您安装持久聊天服务器与 Skype 业务 Server 2015 Enterprise Edition，以确保获得最佳性能，建议您在安装的持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="aed06-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="aed06-136">如果您安装持久聊天服务器与 Skype 业务 Server 2015 Standard edition，您可以部署持久聊天存储后端服务器上的本地 SQL Server Express 实例。</span><span class="sxs-lookup"><span data-stu-id="aed06-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="aed06-137">持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于的 SQL Server 或不同 SQL 服务器上的同一实例中。</span><span class="sxs-lookup"><span data-stu-id="aed06-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="aed06-138">为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。</span><span class="sxs-lookup"><span data-stu-id="aed06-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="aed06-139">对服务器平台的持久聊天数据库服务器需要 Skype 的相同硬件业务服务器 2015年后端数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="aed06-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="aed06-140">有关信息，请参阅 [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aed06-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="aed06-141">在数据库服务器上，确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="aed06-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="aed06-142">最新的 service pack 的 Microsoft SQL Server 2017。</span><span class="sxs-lookup"><span data-stu-id="aed06-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="aed06-143">使用 Service Pack 1 和您的 Microsoft SQL Server 2016 必须与 Skype 运行，业务 Server 累积更新 7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aed06-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="aed06-144">我们建议将运行 SQL Server 2016 带有最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="aed06-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="aed06-145">有关如何安装 Microsoft SQL Server 2016 的详细信息，请参阅[安装 SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="aed06-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="aed06-146">Microsoft SQL Server 2014，并且您必须运行与 Skype 业务 Server 累积更新 6 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aed06-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="aed06-147">我们建议最新的 service pack 运行 SQL Server 2014。</span><span class="sxs-lookup"><span data-stu-id="aed06-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="aed06-148">有关如何安装 Microsoft SQL Server 2014 的详细信息，请参阅[安装 SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。</span><span class="sxs-lookup"><span data-stu-id="aed06-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="aed06-149">Microsoft SQL Server 2012 （64 位版本），以及我们建议最新的 service pack 的运行。</span><span class="sxs-lookup"><span data-stu-id="aed06-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="aed06-150">有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅[安装 SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。</span><span class="sxs-lookup"><span data-stu-id="aed06-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="aed06-151">持久聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="aed06-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="aed06-152">有关获取证书的详细信息，创建 SQL Server 数据库和创建文件存储，请参阅[部署的 Skype 的业务服务器 2015年](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="aed06-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="aed06-153">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="aed06-153">For more information</span></span>

<span data-ttu-id="aed06-154">有关硬件和软件要求的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="aed06-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="aed06-155">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aed06-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="aed06-156">Environmental requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aed06-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

