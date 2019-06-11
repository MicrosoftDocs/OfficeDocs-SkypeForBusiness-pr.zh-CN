---
title: 验证 Lync Server 2010 环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="158f3-102">验证 Lync Server 2010 环境</span><span class="sxs-lookup"><span data-stu-id="158f3-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="158f3-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="158f3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="158f3-104">在使用 Lync Server 2010 在共存状态中部署 Lync Server 2013 之前, 需要验证是否已配置并启动 Lync Server 2010 服务。</span><span class="sxs-lookup"><span data-stu-id="158f3-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="158f3-105">在部署 Lync Server 2013 试验池之前, 请务必确定旧版环境中存在的关键服务和功能。</span><span class="sxs-lookup"><span data-stu-id="158f3-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="158f3-106">在使用旧版 XMPP 部署在共存状态中部署 Microsoft Lync Server 2013 XMPP 之前, 需要验证旧的 XMPP 服务是否已配置并启动, 并确定旧版 XMPP 配置支持的联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="158f3-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="158f3-107">验证旧版 Lync Server 2010 部署需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="158f3-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="158f3-108">验证是否已启动 Lync Server 2010 服务</span><span class="sxs-lookup"><span data-stu-id="158f3-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="158f3-109">在 Lync Server 2010 中查看拓扑和用户。</span><span class="sxs-lookup"><span data-stu-id="158f3-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="158f3-110">验证联盟和边缘服务器设置。</span><span class="sxs-lookup"><span data-stu-id="158f3-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="158f3-111">验证 XMPP 服务和联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="158f3-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="158f3-112">**验证是否已启动 Lync Server 2010 服务**</span><span class="sxs-lookup"><span data-stu-id="158f3-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="158f3-113">从 Lync Server 2010 前端服务器, 导航到 "管理工具\\服务" 小程序。</span><span class="sxs-lookup"><span data-stu-id="158f3-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="158f3-114">验证以下服务是否在前端服务器上运行:</span><span class="sxs-lookup"><span data-stu-id="158f3-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="158f3-115">![前端服务器上运行的服务列表](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端服务器上运行的服务列表")</span><span class="sxs-lookup"><span data-stu-id="158f3-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="158f3-116">**在 Lync Server "控制面板" 中查看 Lync Server 2010 拓扑**</span><span class="sxs-lookup"><span data-stu-id="158f3-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="158f3-117">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="158f3-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="158f3-118">打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="158f3-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="158f3-119">选择 "**拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="158f3-119">Select **Topology**.</span></span> <span data-ttu-id="158f3-120">验证是否列出了 Lync Server 2010 部署中的各种服务器。</span><span class="sxs-lookup"><span data-stu-id="158f3-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="158f3-121">![Lync Server 2010 控制面板拓扑页面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制面板拓扑页面")</span><span class="sxs-lookup"><span data-stu-id="158f3-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="158f3-122">**在 Lync Server "控制面板" 中查看 Lync Server 2010 用户**</span><span class="sxs-lookup"><span data-stu-id="158f3-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="158f3-123">打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="158f3-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="158f3-124">选择 "**用户**", 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="158f3-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="158f3-125">验证 "**注册机构池**" 列是否指向列出的每个用户的 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="158f3-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="158f3-126">![Lync Server 2010 "控制面板", 其中列出了用户](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 \"控制面板\", 其中列出了用户")</span><span class="sxs-lookup"><span data-stu-id="158f3-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="158f3-127">**验证 Lync Server 2010 Edge 和联盟设置**</span><span class="sxs-lookup"><span data-stu-id="158f3-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="158f3-128">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="158f3-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="158f3-129">**从现有部署中选择 "下载拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="158f3-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="158f3-130">选择文件名, 并使用默认的 tbxml 文件类型保存拓扑。</span><span class="sxs-lookup"><span data-stu-id="158f3-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="158f3-131">展开 Lync Server 2010 节点以显示部署中的各种服务器角色。</span><span class="sxs-lookup"><span data-stu-id="158f3-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="158f3-132">选择 "网站" 节点并验证是否设置了 "**网站联合" 路由分配**值。</span><span class="sxs-lookup"><span data-stu-id="158f3-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="158f3-133">![拓扑生成器、站点联合身份验证路线](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓扑生成器、站点联合身份验证路线")</span><span class="sxs-lookup"><span data-stu-id="158f3-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="158f3-134">接下来, 选择 "标准版服务器" 或 "企业版前端池"。</span><span class="sxs-lookup"><span data-stu-id="158f3-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="158f3-135">确定是否已针对 "**关联**" 下的媒体配置了 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="158f3-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="158f3-136">![拓扑生成器, 显示服务器和池](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "拓扑生成器, 显示服务器和池")</span><span class="sxs-lookup"><span data-stu-id="158f3-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="158f3-137">最后, 选择 "边缘" 池并确定下一个跃点池是否在**下一个跃点选择**下配置。</span><span class="sxs-lookup"><span data-stu-id="158f3-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="158f3-138">![拓扑生成器, 下一跃点选择](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓扑生成器, 下一跃点选择")</span><span class="sxs-lookup"><span data-stu-id="158f3-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="158f3-139">**验证旧版 XMPP 联盟合作伙伴配置**</span><span class="sxs-lookup"><span data-stu-id="158f3-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="158f3-140">从旧的 XMPP 服务器中, 导航到 "管理\\工具服务" 小程序。</span><span class="sxs-lookup"><span data-stu-id="158f3-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="158f3-141">验证是否已启动 Office 通信服务器 XMPP 网关服务。</span><span class="sxs-lookup"><span data-stu-id="158f3-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="158f3-142">![Office 通信服务器 XMPP 网关服务](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通信服务器 XMPP 网关服务")</span><span class="sxs-lookup"><span data-stu-id="158f3-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

