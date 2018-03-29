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
description: 摘要： 请阅读本主题，以了解有关硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015年。
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="565c3-103">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="565c3-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="565c3-104">**摘要：**阅读本主题以了解有关硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="565c3-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="565c3-105">持久的聊天服务器可以安装与 Skype 业务服务器 2015年企业版或标准版。</span><span class="sxs-lookup"><span data-stu-id="565c3-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="565c3-106">要求取决于您安装业务服务器 2015年的 Skype 的是哪个版本，以及您的业务的性能要求。</span><span class="sxs-lookup"><span data-stu-id="565c3-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="565c3-107">Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="565c3-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="565c3-108">持久聊天包含前端组件以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="565c3-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="565c3-109">在部署持续聊天服务器之前，必须确保符合以下硬件和软件要求：</span><span class="sxs-lookup"><span data-stu-id="565c3-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="565c3-110">满足最低要求，以支持 Skype 业务服务器 2015年、 持久聊天服务器、 数据库服务器和文件服务器的硬件。</span><span class="sxs-lookup"><span data-stu-id="565c3-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="565c3-111">有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="565c3-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="565c3-112">支持的操作系统和数据库软件。</span><span class="sxs-lookup"><span data-stu-id="565c3-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="565c3-113">有关受支持的操作系统和数据库软件和 Windows 更新要求、[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="565c3-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="565c3-114">Skype 业务服务器 2015年前端服务器。</span><span class="sxs-lookup"><span data-stu-id="565c3-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="565c3-115">前端服务器是为会话启动协议 (SIP) 路由，这样有可能持久聊天服务器和持久聊天功能运行的计算机之间的通信的基础。</span><span class="sxs-lookup"><span data-stu-id="565c3-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="565c3-116">消息队列软件。</span><span class="sxs-lookup"><span data-stu-id="565c3-116">Message Queuing software.</span></span> <span data-ttu-id="565c3-117">如果部署，使用持久聊天服务器和持久聊天的法规遵从性服务。</span><span class="sxs-lookup"><span data-stu-id="565c3-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="565c3-118">以下各节描述持久聊天服务器和存储的持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="565c3-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="565c3-119">前端服务器要求</span><span class="sxs-lookup"><span data-stu-id="565c3-119">Front End Server requirements</span></span>

<span data-ttu-id="565c3-120">前结束服务器要求取决于是否为业务服务器 2015年企业版或标准版部署 Skype 的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="565c3-120">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="565c3-121">如果业务服务器 2015年企业版部署 Skype 的持久聊天服务器，您可以部署持续聊天服务器前端服务器在企业版池中的一个或多个独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="565c3-121">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="565c3-122">不能为业务服务器 2015年前端服务器布置持久聊天前端服务器在 Skype 上。</span><span class="sxs-lookup"><span data-stu-id="565c3-122">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="565c3-123">一个持久聊天服务器前端服务器可支持 20000 个活动用户。</span><span class="sxs-lookup"><span data-stu-id="565c3-123">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="565c3-124">您可以持久聊天服务器池与从而支持 80000 并发用户的总数将达 4 活动前结束。</span><span class="sxs-lookup"><span data-stu-id="565c3-124">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="565c3-125">如果业务服务器 2015年标准版部署 Skype 的持久聊天服务器，可以布置与前端服务器持续聊天。</span><span class="sxs-lookup"><span data-stu-id="565c3-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="565c3-126">此单服务器部署可最多支持 20,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="565c3-126">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="565c3-127">持久的聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="565c3-127">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="565c3-128">持久的聊天服务器需要 SQL Server 数据库软件，以存储聊天室历史和内容、 配置数据、 用户设置数据和其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="565c3-128">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="565c3-129">（可选），它使用持久聊天的法规遵从性数据库存储符合性数据。</span><span class="sxs-lookup"><span data-stu-id="565c3-129">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="565c3-130">持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。</span><span class="sxs-lookup"><span data-stu-id="565c3-130">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="565c3-131">如果您正在安装持久聊天服务器使用 Skype 业务服务器 2015年企业版，以确保获得最佳性能，建议您安装永久聊天文件存储区。</span><span class="sxs-lookup"><span data-stu-id="565c3-131">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="565c3-132">如果您正在安装持久聊天服务器使用 Skype 业务服务器 2015年标准版，您可以部署持续聊天存储后端服务器上的 SQL Server Express 的本地实例。</span><span class="sxs-lookup"><span data-stu-id="565c3-132">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="565c3-133">持续聊天数据库 (mgc) 和法规遵从性数据库 (mgccomp) 可以位于相同的或不同的 SQL 服务器上的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="565c3-133">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="565c3-134">为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。</span><span class="sxs-lookup"><span data-stu-id="565c3-134">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="565c3-135">持续聊天的数据库服务器的服务器平台需要业务服务器 2015年后端数据库服务器为 Skype 相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="565c3-135">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="565c3-136">有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="565c3-136">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="565c3-137">在数据库服务器上，确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="565c3-137">On the database server, be sure that one of the following software applications is installed:</span></span>
  
- <span data-ttu-id="565c3-138">Microsoft SQL Server 2012年。</span><span class="sxs-lookup"><span data-stu-id="565c3-138">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="565c3-139">有关如何安装 Microsoft SQL Server 2012年的详细信息，请参阅[安装 SQL Server 2012年](https://go.microsoft.com/fwlink/p/?LinkID=248559)。</span><span class="sxs-lookup"><span data-stu-id="565c3-139">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>
    
- <span data-ttu-id="565c3-140">Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="565c3-140">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="565c3-141">有关如何安装 Microsoft SQL Server 2008 R2 的详细信息，请参阅[SQL Server 安装 (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702)。</span><span class="sxs-lookup"><span data-stu-id="565c3-141">For details about how to install Microsoft SQL Server 2008 R2, see [SQL Server Installation (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702).</span></span>
    
## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="565c3-142">持久的聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="565c3-142">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="565c3-143">有关获取证书的详细信息，创建 SQL Server 数据库中，并创建文件存储区，请参阅[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="565c3-143">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="565c3-144">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="565c3-144">For more information</span></span>

<span data-ttu-id="565c3-145">有关硬件和软件要求的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="565c3-145">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="565c3-146">业务服务器 2015 Skype 的的服务要求</span><span class="sxs-lookup"><span data-stu-id="565c3-146">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="565c3-147">环境要求为 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="565c3-147">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

