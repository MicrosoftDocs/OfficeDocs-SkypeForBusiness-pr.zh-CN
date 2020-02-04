---
title: 电话拨入式会议配置的先决条件和权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="dcc87-102">Lync Server 2013 中电话拨入式会议配置的先决条件和权限</span><span class="sxs-lookup"><span data-stu-id="dcc87-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcc87-103">_**主题上次修改时间：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="dcc87-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="dcc87-104">电话拨入式会议是 Lync Server 2013 会议工作负荷的可选组件。</span><span class="sxs-lookup"><span data-stu-id="dcc87-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="dcc87-105">在你使用拓扑生成器设计拓扑，然后设置你的前端池或标准版服务器之前，你需要安装的组件才能配置拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="dcc87-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="dcc87-106">本主题介绍了在配置拨入式会议之前需要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="dcc87-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="dcc87-107">本部分假设你已阅读与会议工作负荷和电话拨入式会议相关的计划部分。</span><span class="sxs-lookup"><span data-stu-id="dcc87-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="dcc87-108">电话拨入式会议配置先决条件</span><span class="sxs-lookup"><span data-stu-id="dcc87-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="dcc87-109">电话拨入式会议需要以下 Lync Server 2013 组件：</span><span class="sxs-lookup"><span data-stu-id="dcc87-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="dcc87-110">统一通信应用程序服务 (UCAS)（称为“*应用程序服务*”）</span><span class="sxs-lookup"><span data-stu-id="dcc87-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="dcc87-111">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="dcc87-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="dcc87-112">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="dcc87-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="dcc87-113">电话拨入式会议设置网页</span><span class="sxs-lookup"><span data-stu-id="dcc87-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="dcc87-114">至少一个 Lync Server 2013 中介服务器和至少一个 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="dcc87-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="dcc87-115">在使用拓扑生成器定义和发布拓扑，然后部署前端池或标准版服务器时，可部署这些组件。</span><span class="sxs-lookup"><span data-stu-id="dcc87-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="dcc87-116">如果要部署企业语音，则应在配置拨入式会议之前部署它。</span><span class="sxs-lookup"><span data-stu-id="dcc87-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="dcc87-117">如果不部署企业语音，则可以在部署前端池或标准版服务器时部署中介服务器和公共交换式电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="dcc87-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="dcc87-118">如果要从 Office 通信服务器 2007 R2 升级到 Lync Server 2013，请在你计划用于托管 Lync Server 2013 会议的每个池中部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="dcc87-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="dcc87-119">有关迁移拨入式会议的详细信息，请参阅<A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="dcc87-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="dcc87-120">本部分假设你已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="dcc87-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="dcc87-121">如果要迁移到 Lync Server 2013，请将最新更新应用到 Office 通信服务器 2007 R2 环境。</span><span class="sxs-lookup"><span data-stu-id="dcc87-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="dcc87-122">使用拓扑生成器设计和配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="dcc87-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="dcc87-123">在指定会议工作负荷时，您选择了 "电话拨入式会议" 选项。</span><span class="sxs-lookup"><span data-stu-id="dcc87-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="dcc87-124">有关定义拓扑的详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)"。</span><span class="sxs-lookup"><span data-stu-id="dcc87-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="dcc87-125">发布了拓扑，并设置了前端池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="dcc87-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="dcc87-126">有关发布拓扑和安装 Lync Server 2013 的详细信息，请参阅部署文档中的 "[部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="dcc87-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dcc87-127">安装已发布的拓扑时，"电话拨入式会议设置" 网页安装在前端服务器或标准版服务器上，作为 Web 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="dcc87-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="dcc87-128">如果在部署 Lync Server 2013 后更改拓扑生成器中文件存储的路径，则需要重新启动会议助理和会议公告应用程序才能使用新路径。</span><span class="sxs-lookup"><span data-stu-id="dcc87-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="dcc87-129">已部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="dcc87-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="dcc87-130">如果您不是在部署企业语音，您可以在企业版前端服务器或标准版服务器上 collocated 中介服务器，或者部署了一个独立的中介服务器，并且部署了 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="dcc87-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="dcc87-131">有关部署企业语音的详细信息，请参阅部署文档中的[Lync Server 2013 中的 "部署企业语音](lync-server-2013-deploying-enterprise-voice.md)"。</span><span class="sxs-lookup"><span data-stu-id="dcc87-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="dcc87-132">有关安装独立中介服务器和 PSTN 网关的详细信息，请参阅部署文档中的在[Lync Server 2013 中部署中介服务器和定义对等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)。</span><span class="sxs-lookup"><span data-stu-id="dcc87-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="dcc87-133">以下流程图显示了在配置拨入式会议之前必须执行的步骤以及配置电话拨入式会议所执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="dcc87-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="dcc87-134">**部署电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="dcc87-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="dcc87-135">![电话拨入式会议部署流程图](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "电话拨入式会议部署流程图")</span><span class="sxs-lookup"><span data-stu-id="dcc87-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="dcc87-136">电话拨入式会议权限</span><span class="sxs-lookup"><span data-stu-id="dcc87-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="dcc87-137">要配置电话拨入式会议，您需要使用以下管理工具：</span><span class="sxs-lookup"><span data-stu-id="dcc87-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="dcc87-138">Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="dcc87-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="dcc87-139">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="dcc87-139">Lync Server Management Shell</span></span>

<span data-ttu-id="dcc87-140">使用这些管理工具配置电话拨入式会议设置，以及拨入式会议所需的拨号计划、策略和其他设置。</span><span class="sxs-lookup"><span data-stu-id="dcc87-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="dcc87-141">配置拨入式会议需要以下任何管理角色，具体取决于任务：</span><span class="sxs-lookup"><span data-stu-id="dcc87-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="dcc87-142">**CsVoiceAdministrator**   此管理员角色可以创建、配置和管理与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="dcc87-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="dcc87-143">**CsUserAdministrator**   此管理员角色可为用户启用和禁用 Lync Server 的用户，并将现有策略（如会议策略和 PIN 策略）分配给用户。</span><span class="sxs-lookup"><span data-stu-id="dcc87-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="dcc87-144">**CsAdministrator**   此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="dcc87-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcc87-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcc87-145">See Also</span></span>


[<span data-ttu-id="dcc87-146">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="dcc87-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

