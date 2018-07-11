---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要： 阅读本主题可了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。
ms.openlocfilehash: 8db3bda71cb27ec059dcf4c73f8d4754ffcb8b2d
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246654"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="43219-103">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="43219-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="43219-104">**摘要：** 阅读此主题以了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="43219-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="43219-105">业务 Server 2015 Enterprise Edition 或 Standard Edition，可以使用 Skype 安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="43219-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="43219-106">要求取决于您已安装的业务服务器 2015 Skype 的是哪个版本，以及您的业务的性能要求。</span><span class="sxs-lookup"><span data-stu-id="43219-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="43219-107">Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="43219-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="43219-108">持久聊天包含前端组件以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="43219-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="43219-109">部署持久聊天服务器之前，您必须确保满足以下硬件和软件要求：</span><span class="sxs-lookup"><span data-stu-id="43219-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="43219-110">满足最低要求以支持 Skype 业务服务器 2015年、 持久聊天服务器、 数据库服务器和文件服务器的硬件。</span><span class="sxs-lookup"><span data-stu-id="43219-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="43219-111">有关详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43219-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="43219-112">支持的操作系统和数据库软件。</span><span class="sxs-lookup"><span data-stu-id="43219-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="43219-113">有关支持的操作系统和数据库软件和窗口的详细信息更新要求，请参阅[业务服务器 2015年的 Skype 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43219-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="43219-114">Skype 业务 Server 2015 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="43219-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="43219-115">前端服务器是基础的会话初始协议 (SIP) 路由，这将使计算机运行 Persistent Chat Server 和持久聊天功能之间的通信可能。</span><span class="sxs-lookup"><span data-stu-id="43219-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="43219-116">消息队列软件。</span><span class="sxs-lookup"><span data-stu-id="43219-116">Message Queuing software.</span></span> <span data-ttu-id="43219-117">如果部署 Persistent Chat Server 和持久聊天合规性服务，使用。</span><span class="sxs-lookup"><span data-stu-id="43219-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="43219-118">以下各节介绍对于 Persistent Chat Server 和存储的持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="43219-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="43219-119">前端服务器要求</span><span class="sxs-lookup"><span data-stu-id="43219-119">Front End Server requirements</span></span>

<span data-ttu-id="43219-120">前端服务器要求取决于是否为业务 Server 2015 Enterprise Edition 或 Standard Edition 部署与 Skype 的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="43219-120">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="43219-121">如果您业务 Server 2015 Enterprise Edition 部署与 Skype 的持久聊天服务器，则可以部署持久聊天服务器前端服务器中的企业版池的一个或多个独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="43219-121">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="43219-122">您不能将持久聊天前端服务器上的 Skype 并置的业务 Server 2015 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="43219-122">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="43219-123">单个持久聊天服务器前端服务器可支持 20,000 活动用户。</span><span class="sxs-lookup"><span data-stu-id="43219-123">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="43219-124">您可以将持久聊天服务器池具有最多 4 从而支持 80,000 个并发用户，总计的活动前端。</span><span class="sxs-lookup"><span data-stu-id="43219-124">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="43219-125">如果您业务 Server 2015 Standard Edition 部署与 Skype 的持久聊天服务器，可以与前端服务器的持久聊天将并置。</span><span class="sxs-lookup"><span data-stu-id="43219-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="43219-126">此单服务器部署可最多支持 20,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="43219-126">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="43219-127">持久聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="43219-127">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="43219-128">持久聊天服务器需要 SQL Server 数据库软件存储聊天室的历史记录和内容、 配置数据、 用户设置数据和其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="43219-128">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="43219-129">（可选），它使用的持久聊天合规性数据库来存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="43219-129">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="43219-130">持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。</span><span class="sxs-lookup"><span data-stu-id="43219-130">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="43219-131">如果您安装持久聊天服务器与 Skype 业务 Server 2015 Enterprise Edition，以确保获得最佳性能，建议您在安装的持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="43219-131">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="43219-132">如果您安装持久聊天服务器与 Skype 业务 Server 2015 Standard edition，您可以部署持久聊天存储后端服务器上的本地 SQL Server Express 实例。</span><span class="sxs-lookup"><span data-stu-id="43219-132">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="43219-133">持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于的 SQL Server 或不同 SQL 服务器上的同一实例中。</span><span class="sxs-lookup"><span data-stu-id="43219-133">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="43219-134">为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。</span><span class="sxs-lookup"><span data-stu-id="43219-134">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="43219-135">对服务器平台的持久聊天数据库服务器需要 Skype 的相同硬件业务服务器 2015年后端数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="43219-135">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="43219-136">有关详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43219-136">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="43219-137">在数据库服务器上，确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="43219-137">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="43219-138">Microsoft SQL Server 2016，并且您必须运行与 Skype 业务 Server 累积更新 7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="43219-138">Microsoft SQL Server 2016, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="43219-139">我们建议将运行 SQL Server 2016 带有最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="43219-139">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="43219-140">有关如何安装 Microsoft SQL Server 2016 的详细信息，请参阅[安装 SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="43219-140">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="43219-141">Microsoft SQL Server 2012 （64 位版本），以及我们建议最新的 service pack 的运行。</span><span class="sxs-lookup"><span data-stu-id="43219-141">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="43219-142">有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅[安装 SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。</span><span class="sxs-lookup"><span data-stu-id="43219-142">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

- <span data-ttu-id="43219-143">Microsoft SQL Server 2008 R2 （64 位版本），以及我们建议最新的 service pack 的运行。</span><span class="sxs-lookup"><span data-stu-id="43219-143">Microsoft SQL Server 2008 R2 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="43219-144">有关如何安装 Microsoft SQL Server 2008 R2 的详细信息，请参阅[SQL Server 安装 (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702)。</span><span class="sxs-lookup"><span data-stu-id="43219-144">For details about how to install Microsoft SQL Server 2008 R2, see [SQL Server Installation (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702).</span></span> 
    
## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="43219-145">持久聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="43219-145">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="43219-146">有关获取证书的详细信息，创建 SQL Server 数据库和创建文件存储，请参阅[部署的 Skype 的业务服务器 2015年](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="43219-146">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="43219-147">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="43219-147">For more information</span></span>

<span data-ttu-id="43219-148">有关硬件和软件要求的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="43219-148">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="43219-149">Skype for Business Server 2015 的服务器要求</span><span class="sxs-lookup"><span data-stu-id="43219-149">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="43219-150">Skype for Business Server 2015 的环境要求</span><span class="sxs-lookup"><span data-stu-id="43219-150">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

