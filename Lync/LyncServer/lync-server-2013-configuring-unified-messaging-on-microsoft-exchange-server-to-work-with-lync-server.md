---
title: Lync Server 2013：在 Microsoft Exchange Server 上配置统一消息以与 Lync Server 一起使用
description: Lync Server 2013：在 Microsoft Exchange Server 上配置统一消息以使用 Lync Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548238"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="92c36-103">在 Microsoft Exchange Server 上配置统一消息以使用 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92c36-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92c36-104">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="92c36-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="92c36-105">如果要使用 Exchange 统一消息 (UM) 为企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 中规划 Exchange 统一消息集成</A> ，然后按照本节中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="92c36-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="92c36-106">若要配置 Exchange 统一消息 (UM) 以使用企业语音，则需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="92c36-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="92c36-107">在运行 Exchange 统一消息的服务器上配置证书 (UM) 服务</span><span class="sxs-lookup"><span data-stu-id="92c36-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92c36-108">将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="92c36-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="92c36-109">如果不是，出站呼叫路由将无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="92c36-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="92c36-110">创建一个或多个 UM SIP URI 拨号计划，以及订阅者访问电话号码（根据需要），然后创建相应的 Lync Server 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="92c36-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="92c36-111">使用 **exchucutil.ps1** 脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="92c36-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="92c36-112">创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="92c36-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="92c36-113">创建 UM 智能寻线。</span><span class="sxs-lookup"><span data-stu-id="92c36-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="92c36-114">授予 Lync Server 2013 读取 UM Active Directory 域服务对象的权限。</span><span class="sxs-lookup"><span data-stu-id="92c36-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="92c36-115">创建 UM 自动助理对象。</span><span class="sxs-lookup"><span data-stu-id="92c36-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="92c36-116">创建订阅者访问对象。</span><span class="sxs-lookup"><span data-stu-id="92c36-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="92c36-117">为每个用户创建 SIP URI，并将用户与 UM SIP URI 拨号计划关联。</span><span class="sxs-lookup"><span data-stu-id="92c36-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="92c36-118">要求与建议</span><span class="sxs-lookup"><span data-stu-id="92c36-118">Requirements and Recommendations</span></span>

<span data-ttu-id="92c36-119">在开始之前，本节中的文档假定您已部署以下 Exchange 2013 角色：客户端访问和邮箱。</span><span class="sxs-lookup"><span data-stu-id="92c36-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="92c36-120">在 Microsoft Exchange Server 2013 中，Exchange UM 在这些服务器上作为一项服务运行。</span><span class="sxs-lookup"><span data-stu-id="92c36-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="92c36-121">有关部署 Exchange 2013 的详细信息，请参阅位于的 Exchange 2013 TechNet 库 [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="92c36-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="92c36-122">另外还需注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="92c36-122">Also note the following:</span></span>

  - <span data-ttu-id="92c36-123">如果 Exchange UM 安装在多个林中，则必须为每个 UM 林执行 Exchange Server 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="92c36-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="92c36-124">此外，必须将每个 UM 林配置为信任在其中部署 Lync Server 2013 的林，并且必须将部署 Lync Server 2013 的林配置为信任每个 UM 林。</span><span class="sxs-lookup"><span data-stu-id="92c36-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="92c36-125">在运行统一消息服务的 Exchange 服务器角色上以及运行 Lync Server 2013 的服务器上执行集成步骤。</span><span class="sxs-lookup"><span data-stu-id="92c36-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="92c36-126">在执行 Lync Server 2013 集成步骤之前，应执行 Exchange Server 统一消息集成步骤。</span><span class="sxs-lookup"><span data-stu-id="92c36-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92c36-127">若要查看在哪些服务器和管理员角色上执行哪些集成步骤，请参阅 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。</span><span class="sxs-lookup"><span data-stu-id="92c36-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="92c36-128">以下工具必须在每台运行 Exchange UM 的服务器上可用：</span><span class="sxs-lookup"><span data-stu-id="92c36-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="92c36-129">Exchange 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="92c36-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="92c36-130">脚本 **exchucutil.ps1**，它将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="92c36-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="92c36-131">为每个 Lync Server 2013 创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="92c36-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="92c36-132">为每个网关创建一个智能寻线。</span><span class="sxs-lookup"><span data-stu-id="92c36-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="92c36-133">每个查寻组的引导标识符指定与网关关联的前端池或 Standard Edition 服务器使用的 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="92c36-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="92c36-134">授予 Lync Server 2013 在 Active Directory 域服务中读取 Exchange UM 对象的权限。</span><span class="sxs-lookup"><span data-stu-id="92c36-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92c36-135">本部分内容</span><span class="sxs-lookup"><span data-stu-id="92c36-135">In This Section</span></span>

  - [<span data-ttu-id="92c36-136">在运行 Microsoft Exchange Server 统一消息的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="92c36-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="92c36-137">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</span><span class="sxs-lookup"><span data-stu-id="92c36-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

