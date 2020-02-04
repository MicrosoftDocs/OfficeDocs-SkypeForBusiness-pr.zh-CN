---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="87088-102">部署试点 Edge Server</span><span class="sxs-lookup"><span data-stu-id="87088-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87088-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="87088-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="87088-104">本主题重点介绍在部署 Lync Server 2013 Edge 服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="87088-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="87088-105">Lync Server 2013 的部署和配置过程非常类似于 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="87088-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="87088-106">本部分仅重点介绍您在试验池部署中应考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="87088-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="87088-107">有关详细步骤，请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" （介绍部署过程），还提供外部用户访问的配置信息。</span><span class="sxs-lookup"><span data-stu-id="87088-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="87088-108">通过 "**定义新的边缘池**" 向导导航时，请查看以下步骤中所示的关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="87088-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="87088-109">请注意，仅显示 "**定义新边缘池**" 向导的几个页面。</span><span class="sxs-lookup"><span data-stu-id="87088-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="87088-110">**定义边缘池**</span><span class="sxs-lookup"><span data-stu-id="87088-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="87088-111">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="87088-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="87088-112">导航到 Lync Server 2013 节点。</span><span class="sxs-lookup"><span data-stu-id="87088-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="87088-113">右键单击 "**边缘池**"，然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="87088-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="87088-114">![定义 "新建边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定义 "新建边缘池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="87088-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="87088-115">边缘池可以是**多台计算机池**或**单个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="87088-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="87088-116">![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 "边缘池 FQDN" 对话框")</span><span class="sxs-lookup"><span data-stu-id="87088-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="87088-117">在 "**选择功能**" 页面上，不要启用联盟或 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="87088-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="87088-118">联合身份验证和 XMPP 联合身份验证当前通过旧版 Lync Server 2010 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="87088-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="87088-119">将在迁移的后续阶段配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="87088-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="87088-120">!["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg ""选择功能" 对话框")</span><span class="sxs-lookup"><span data-stu-id="87088-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="87088-121">接下来，继续完成以下向导页：**外部 fqdn**、**定义内部 Ip 地址**以及**定义外部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="87088-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="87088-122">在 "**定义下一个跃点**" 页面上，选择 Lync Server 2010 Edge 池的下一跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="87088-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="87088-123">!["定义下一跃点" 对话框](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg ""定义下一跃点" 对话框")</span><span class="sxs-lookup"><span data-stu-id="87088-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="87088-124">此时，在 "**关联前端或中介池**" 页面上，不要将池与此边界池关联。</span><span class="sxs-lookup"><span data-stu-id="87088-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="87088-125">外部媒体流量当前通过旧版 Lync Server 2010 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="87088-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="87088-126">将在迁移的后续阶段配置此设置。</span><span class="sxs-lookup"><span data-stu-id="87088-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="87088-127">!["关联前端池" 对话框](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg ""关联前端池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="87088-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="87088-128">单击 "**完成**"，然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="87088-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="87088-129">按照部署文档中[Lync server 2013 的安装边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤操作，将文件安装在新的边缘服务器上，配置证书，然后启动服务。</span><span class="sxs-lookup"><span data-stu-id="87088-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="87088-130">请务必遵循部署文档中[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)主题中的指南。</span><span class="sxs-lookup"><span data-stu-id="87088-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="87088-131">本部分仅提供了有关安装这些服务器角色时的配置设置指南。</span><span class="sxs-lookup"><span data-stu-id="87088-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="87088-132">现在，你应该与 Lync Server 2013 Edge 服务器部署并行部署旧版 Lync Server 2010 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="87088-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="87088-133">验证两个部署是否正常运行，服务是否已启动，并且你可以在迁移到下一阶段之前管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="87088-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

