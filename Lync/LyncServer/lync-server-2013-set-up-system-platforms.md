---
title: Lync Server 2013：设置系统平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="1fa33-102">在 Lync Server 2013 中设置系统平台</span><span class="sxs-lookup"><span data-stu-id="1fa33-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa33-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1fa33-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1fa33-104">在开始部署持久聊天服务器之前，必须在满足服务器上的系统要求的硬件上安装所需操作系统：</span><span class="sxs-lookup"><span data-stu-id="1fa33-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="1fa33-105">有关运行 Lync Server 2013、数据库服务器和文件服务器的服务器支持的硬件的详细信息，请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa33-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="1fa33-106">有关受支持的操作系统和数据库软件的详细信息，请参阅支持文档中的[Lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa33-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="1fa33-107">有关 Windows 更新要求的详细信息，请参阅支持文档中[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa33-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="1fa33-108">持久聊天服务器前端服务器**PersistentChatService**可在 Lync Server 2013 Enterprise Edition 池中的一个或多个独立计算机上部署。</span><span class="sxs-lookup"><span data-stu-id="1fa33-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="1fa33-109">不能在 Lync Server 企业版前端服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="1fa33-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="1fa33-110">引导程序可以部署持久聊天服务器，就像其他 Lync 服务器角色一样。</span><span class="sxs-lookup"><span data-stu-id="1fa33-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="1fa33-111">**用于文件上传/下载的持久聊天 Web 服务**和**用于聊天室管理的持久聊天 web 服务**是在 Lync Server 2013 前端服务器上部署的 web 组件。</span><span class="sxs-lookup"><span data-stu-id="1fa33-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="1fa33-112">单个持久聊天服务器前端服务器可以支持20000活动用户。</span><span class="sxs-lookup"><span data-stu-id="1fa33-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="1fa33-113">你可以拥有最多4个活动前端的持久聊天服务器池，同时支持80000并发用户总数。</span><span class="sxs-lookup"><span data-stu-id="1fa33-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="1fa33-114">持久的聊天后端服务器 " **PersistentChatStore**" 存储聊天室和类别。</span><span class="sxs-lookup"><span data-stu-id="1fa33-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="1fa33-115">我们建议你在企业版池中的专用 SQL Server 后端服务器上安装**PersistentChatStore** ;虽然我们支持在同一 SQL Server 实例上 collocating Lync Server 2013 后端服务器和**PersistentChatStore** 。</span><span class="sxs-lookup"><span data-stu-id="1fa33-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="1fa33-116">如果你的组织需要合规性支持，你可以使用拓扑生成器安装它。</span><span class="sxs-lookup"><span data-stu-id="1fa33-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="1fa33-117">持久聊天服务器合规性服务与持久聊天服务器前端服务器安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="1fa33-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="1fa33-118">需要单独的数据库才能实现合规性。</span><span class="sxs-lookup"><span data-stu-id="1fa33-118">A separate database is required for compliance.</span></span> <span data-ttu-id="1fa33-119">有关持久聊天服务器的合规性要求的详细信息，请参阅规划文档中的[Lync server 2013 中的 "持久聊天服务器计划](lync-server-2013-planning-for-persistent-chat-server.md)"。</span><span class="sxs-lookup"><span data-stu-id="1fa33-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="1fa33-120">每个拓扑至少需要安装有 Lync Server 2013 的服务器和安装有 SQL Server 数据库软件的服务器。</span><span class="sxs-lookup"><span data-stu-id="1fa33-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="1fa33-121">拓扑生成器支持多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="1fa33-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="1fa33-122">按照相同的部署说明部署多个持久聊天服务器池，就像在部署文档中[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)的任何池一样。</span><span class="sxs-lookup"><span data-stu-id="1fa33-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1fa33-123">您也可以将持久聊天服务器与 Lync Server 2013 标准版一起部署。</span><span class="sxs-lookup"><span data-stu-id="1fa33-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="1fa33-124">在这种情况下， **PersistentChatService**前端服务器在标准版服务器上 collocated，并且你可以在本地 SQL Server Express 实例上部署**PersistentChatStore**后端服务器。</span><span class="sxs-lookup"><span data-stu-id="1fa33-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1fa33-125">我们不支持持久聊天服务器&nbsp;标准版提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="1fa33-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="1fa33-126">性能和规模将受到限制。</span><span class="sxs-lookup"><span data-stu-id="1fa33-126">Performance and scale will be limited.</span></span> <span data-ttu-id="1fa33-127">此外，我们仅支持新的持久聊天&nbsp;服务器标准版服务器部署。</span><span class="sxs-lookup"><span data-stu-id="1fa33-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="1fa33-128">我们不支持将 Lync Server 2010、群组聊天服务器升级到 Lync Server 2013&nbsp;持久聊天服务器&nbsp;标准版。</span><span class="sxs-lookup"><span data-stu-id="1fa33-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1fa33-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fa33-129">See Also</span></span>


[<span data-ttu-id="1fa33-130">Lync Server 2013 中的其他服务器支持和要求</span><span class="sxs-lookup"><span data-stu-id="1fa33-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="1fa33-131">支持的适用于 Lync Server 2013 的硬件</span><span class="sxs-lookup"><span data-stu-id="1fa33-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="1fa33-132">Lync Server 2013 中的服务器软件和基础结构支持</span><span class="sxs-lookup"><span data-stu-id="1fa33-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="1fa33-133">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="1fa33-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="1fa33-134">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa33-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

