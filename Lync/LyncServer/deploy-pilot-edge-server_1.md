---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="006a5-102">部署试点 Edge Server</span><span class="sxs-lookup"><span data-stu-id="006a5-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="006a5-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="006a5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="006a5-104">本主题重点介绍在部署 Lync Server 2013 Edge 服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="006a5-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="006a5-105">本部分仅重点介绍你应考虑的要点, 作为试点边缘池部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="006a5-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="006a5-106">有关详细步骤, 请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" (介绍部署过程), 还提供外部用户访问的配置信息。</span><span class="sxs-lookup"><span data-stu-id="006a5-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="006a5-107">通过 "**定义新的边缘池**" 向导导航时, 请查看以下步骤中所示的关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="006a5-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="006a5-108">请注意, 仅显示 "**定义新边缘池**" 向导的几个页面。</span><span class="sxs-lookup"><span data-stu-id="006a5-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="006a5-109">**定义边缘池**</span><span class="sxs-lookup"><span data-stu-id="006a5-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="006a5-110">使用拓扑生成器打开 "引导池" 拓扑。</span><span class="sxs-lookup"><span data-stu-id="006a5-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="006a5-111">导航到 Lync Server 2013 节点。</span><span class="sxs-lookup"><span data-stu-id="006a5-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="006a5-112">右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="006a5-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="006a5-113">![定义 "新建边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定义 \"新建边缘池\" 对话框")</span><span class="sxs-lookup"><span data-stu-id="006a5-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="006a5-114">边缘池可以是**多台计算机池**或**单个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="006a5-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="006a5-115">![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 \"边缘池 FQDN\" 对话框")</span><span class="sxs-lookup"><span data-stu-id="006a5-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="006a5-116">在 "**选择功能**" 页面上, 不要启用联盟或 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="006a5-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="006a5-117">联盟和 XMPP 联合身份验证当前通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="006a5-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="006a5-118">将在迁移的后续阶段配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="006a5-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="006a5-119">!["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "\"选择功能\" 对话框")</span><span class="sxs-lookup"><span data-stu-id="006a5-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="006a5-120">接下来, 继续完成以下向导页:**选择 "IP 选项**"、"**外部 fqdn**"、"**定义内部 Ip 地址**" 和 "**定义外部 ip 地址**"。</span><span class="sxs-lookup"><span data-stu-id="006a5-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="006a5-121">在 "**定义下一个跃点**" 页面上, 选择 Lync Server 2013 Edge 池的下一跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="006a5-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="006a5-122">!["定义新的边缘池" 对话框, 下一个跃点池列表](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "\"定义新的边缘池\" 对话框, 下一个跃点池列表")</span><span class="sxs-lookup"><span data-stu-id="006a5-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="006a5-123">在 "**关联前端池**" 页面上, 请不要在此时间将池与此边界池关联。</span><span class="sxs-lookup"><span data-stu-id="006a5-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="006a5-124">外部媒体流量当前通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="006a5-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="006a5-125">将在迁移的后续阶段配置此设置。</span><span class="sxs-lookup"><span data-stu-id="006a5-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="006a5-126">"![定义新的边缘池" 对话框]"(images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "定义新的边缘池\" 对话框")</span><span class="sxs-lookup"><span data-stu-id="006a5-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="006a5-127">单击 "**完成**", 然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="006a5-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="006a5-128">按照部署文档中[Lync server 2013 的安装边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤操作, 将文件安装在新的边缘服务器上, 配置证书, 然后启动服务。</span><span class="sxs-lookup"><span data-stu-id="006a5-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="006a5-129">请务必遵循部署文档中[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)主题中的指南。</span><span class="sxs-lookup"><span data-stu-id="006a5-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="006a5-130">本部分仅提供了有关安装这些服务器角色时的配置设置指南。</span><span class="sxs-lookup"><span data-stu-id="006a5-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="006a5-131">现在, 你应该有一个旧式 Office 通信服务器 2007 R2 Edge 服务器部署, 该部署由 BackCompatSite 的存在以及与 Lync Server 2013 Edge 服务器部署同时进行指示。</span><span class="sxs-lookup"><span data-stu-id="006a5-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="006a5-132">将联盟配置为使用 Office 通信服务器 2007 R2 控制器。</span><span class="sxs-lookup"><span data-stu-id="006a5-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="006a5-133">验证两个部署是否正常运行, 服务是否已启动, 并且你可以在迁移到下一阶段之前管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="006a5-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="006a5-134">![显示 OCS 边缘服务器的拓扑生成器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "显示 OCS 边缘服务器的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="006a5-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

