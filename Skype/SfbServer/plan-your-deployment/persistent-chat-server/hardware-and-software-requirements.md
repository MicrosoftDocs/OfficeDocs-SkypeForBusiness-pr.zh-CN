---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求。
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834532"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="4309d-103">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="4309d-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4309d-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="4309d-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4309d-105">持久聊天服务器可以与 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition 一起安装。</span><span class="sxs-lookup"><span data-stu-id="4309d-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="4309d-106">要求取决于已安装的 Skype for Business Server 2015 版本，以及企业的性能要求。</span><span class="sxs-lookup"><span data-stu-id="4309d-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="4309d-107">Enterprise Edition 可支持多达 80，000 个并发用户;Standard Edition 可支持最多 20，000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="4309d-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="4309d-108">持久聊天包括前端组件和后端SQL组件。</span><span class="sxs-lookup"><span data-stu-id="4309d-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="4309d-109">在部署持久聊天服务器之前，必须确保满足以下硬件和软件要求：</span><span class="sxs-lookup"><span data-stu-id="4309d-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="4309d-110">满足支持 Skype for Business Server 2015、持久聊天服务器、数据库服务器和文件服务器的最低要求的硬件。</span><span class="sxs-lookup"><span data-stu-id="4309d-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="4309d-111">有关详细信息，请参阅 [Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4309d-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="4309d-112">支持的操作系统和数据库软件。</span><span class="sxs-lookup"><span data-stu-id="4309d-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="4309d-113">有关受支持的操作系统和数据库软件以及 Windows 更新要求的详细信息，请参阅 [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)的服务器要求。</span><span class="sxs-lookup"><span data-stu-id="4309d-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="4309d-114">Skype for Business Server 2015 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="4309d-115">前端服务器是会话初始协议 (SIP) 路由的基础，这使运行持久聊天服务器的计算机与持久聊天功能之间的通信成为可能。</span><span class="sxs-lookup"><span data-stu-id="4309d-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="4309d-116">消息队列软件。</span><span class="sxs-lookup"><span data-stu-id="4309d-116">Message Queuing software.</span></span> <span data-ttu-id="4309d-117">由持久聊天服务器和持久聊天合规性服务使用（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="4309d-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="4309d-118">以下各节介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="4309d-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="4309d-119">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="4309d-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4309d-120">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="4309d-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="4309d-121">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="4309d-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="4309d-122">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="4309d-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="4309d-123">前端服务器要求</span><span class="sxs-lookup"><span data-stu-id="4309d-123">Front End Server requirements</span></span>

<span data-ttu-id="4309d-124">前端服务器要求取决于是使用 Skype for Business Server 2015 Enterprise Edition 还是 Standard Edition 部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="4309d-125">如果要使用 Skype for Business Server 2015 Enterprise Edition 部署持久聊天服务器，可以在 Enterprise Edition 池中的一台或多台独立计算机上部署持久聊天服务器前端服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="4309d-126">无法在 Skype for Business Server 2015 前端服务器上并排持久聊天前端服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="4309d-127">单个持久聊天服务器前端服务器可支持 20，000 个活动用户。</span><span class="sxs-lookup"><span data-stu-id="4309d-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="4309d-128">您的持久聊天服务器池最多具有 4 个活动前端，因此总共支持 80，000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="4309d-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="4309d-129">如果要将持久聊天服务器与 Skype for Business Server 2015 Standard Edition 一起部署，可以将持久聊天与前端服务器并排。</span><span class="sxs-lookup"><span data-stu-id="4309d-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="4309d-130">此单服务器部署最多支持 20，000 个用户。</span><span class="sxs-lookup"><span data-stu-id="4309d-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="4309d-131">持久聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="4309d-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="4309d-132">持久聊天服务器SQL Server数据库软件来存储聊天室历史记录和内容、配置数据、用户设置数据和其他相关元数据。</span><span class="sxs-lookup"><span data-stu-id="4309d-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="4309d-133">（可选）它使用持久聊天合规性数据库存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="4309d-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="4309d-134">持久聊天数据库可以与后端数据库并SQL Server，甚至可以与SQL实例并并。</span><span class="sxs-lookup"><span data-stu-id="4309d-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="4309d-135">如果要使用 Skype for Business Server 2015 Enterprise Edition 安装持久聊天服务器，为了确保最佳性能，建议您安装持久聊天文件存储。</span><span class="sxs-lookup"><span data-stu-id="4309d-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="4309d-136">如果要使用 Skype for Business Server 2015 Standard Edition 安装持久聊天服务器，可以在本地 SQL Server Express 实例上部署持久聊天存储后端服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="4309d-137">持久聊天 (mgc) 和合规性数据库 (mgccomp) 可以位于 SQL Server 实例中，也可以位于不同的 SQL 服务器上。</span><span class="sxs-lookup"><span data-stu-id="4309d-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="4309d-138">若要准备数据库服务器平台，请确保每台计算机都满足硬件要求，然后安装必备软件。</span><span class="sxs-lookup"><span data-stu-id="4309d-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="4309d-139">持久聊天数据库服务器的服务器平台需要与 Skype for Business Server 2015 后端服务器相同的硬件数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="4309d-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="4309d-140">有关详细信息，请参阅 [Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4309d-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="4309d-141">在数据库服务器，请确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="4309d-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="4309d-142">Microsoft SQL Server Service Pack 的 2017 版本。</span><span class="sxs-lookup"><span data-stu-id="4309d-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="4309d-143">Microsoft SQL Server Service Pack 1 的 2016 版本，必须运行 Skype for Business Server 累积更新 7 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4309d-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="4309d-144">我们建议在 2016 SQL Server Service Pack 运行 2016。</span><span class="sxs-lookup"><span data-stu-id="4309d-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="4309d-145">若要详细了解如何安装 Microsoft SQL Server 2016，请参阅 Install [SQL Server 2016。](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)</span><span class="sxs-lookup"><span data-stu-id="4309d-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="4309d-146">Microsoft SQL Server 2014，并且必须使用 Skype for Business Server 累积更新 6 或更高版本运行。</span><span class="sxs-lookup"><span data-stu-id="4309d-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="4309d-147">我们建议在 2014 SQL Server Service Pack 运行 2014。</span><span class="sxs-lookup"><span data-stu-id="4309d-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="4309d-148">若要详细了解如何安装 Microsoft SQL Server 2014，请参阅 Install [SQL Server 2014。](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)</span><span class="sxs-lookup"><span data-stu-id="4309d-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="4309d-149">Microsoft SQL Server 2012 (64 位) ，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4309d-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="4309d-150">若要详细了解如何安装 Microsoft SQL Server 2012，请参阅 Install [SQL Server 2012。](https://go.microsoft.com/fwlink/p/?LinkID=248559)</span><span class="sxs-lookup"><span data-stu-id="4309d-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="4309d-151">持久聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="4309d-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="4309d-152">有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅[部署 Skype for Business Server 2015。](../../deploy/deploy.md)</span><span class="sxs-lookup"><span data-stu-id="4309d-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="4309d-153">详细信息</span><span class="sxs-lookup"><span data-stu-id="4309d-153">For more information</span></span>

<span data-ttu-id="4309d-154">有关硬件和软件要求详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4309d-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="4309d-155">Skype for Business Server 2015 的服务器要求</span><span class="sxs-lookup"><span data-stu-id="4309d-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="4309d-156">Skype for Business Server 2015 的环境要求</span><span class="sxs-lookup"><span data-stu-id="4309d-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

