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
ms.openlocfilehash: a6c394d3535acb9b1842ac49f13eda1459d68c95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514505"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="afb71-102">Lync Server 2013 中的电话拨入式会议配置先决条件和权限</span><span class="sxs-lookup"><span data-stu-id="afb71-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afb71-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="afb71-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="afb71-104">电话拨入式会议是 Lync Server 2013 会议工作负荷的可选组件。</span><span class="sxs-lookup"><span data-stu-id="afb71-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="afb71-105">在您使用拓扑生成器设计拓扑并设置前端池或 Standard Edition server 时，您需要安装的组件才能配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="afb71-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="afb71-106">本主题介绍配置电话拨入式会议之前需要完成的任务。</span><span class="sxs-lookup"><span data-stu-id="afb71-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="afb71-107">本节假定您已阅读与会议工作负荷和电话拨入式会议相关的规划部分。</span><span class="sxs-lookup"><span data-stu-id="afb71-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="afb71-108">电话拨入式会议配置先决条件</span><span class="sxs-lookup"><span data-stu-id="afb71-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="afb71-109">电话拨入式会议需要以下 Lync Server 2013 组件：</span><span class="sxs-lookup"><span data-stu-id="afb71-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="afb71-110">统一通信应用程序服务 (UCAS)（称为“应用程序服务”\*\*）</span><span class="sxs-lookup"><span data-stu-id="afb71-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="afb71-111">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="afb71-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="afb71-112">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="afb71-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="afb71-113">电话拨入式会议设置网页</span><span class="sxs-lookup"><span data-stu-id="afb71-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="afb71-114">至少一个 Lync Server 2013 中介服务器和至少一个 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="afb71-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="afb71-115">当您使用拓扑生成器定义和发布拓扑，然后部署前端池或 Standard Edition server 时，可以部署这些组件。</span><span class="sxs-lookup"><span data-stu-id="afb71-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="afb71-116">如果要部署企业语音，应先部署它，然后再配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="afb71-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="afb71-117">如果不部署企业语音，则可以在部署前端池或 Standard Edition Server 时，将中介服务器和公共交换电话网络 (PSTN) 网关部署。</span><span class="sxs-lookup"><span data-stu-id="afb71-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="afb71-118">如果要从 Office 通信服务器 2007 R2 升级到 Lync Server 2013，请在您计划用于承载 Lync Server 2013 会议的每个池中部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="afb71-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="afb71-119">有关迁移电话拨入式会议的详细信息，请参阅 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="afb71-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="afb71-120">本节假定您已执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="afb71-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="afb71-121">如果要迁移到 Lync Server 2013，请将最新的更新应用到 Office 通信服务器 2007 R2 环境。</span><span class="sxs-lookup"><span data-stu-id="afb71-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="afb71-122">使用拓扑生成器来设计和配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="afb71-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="afb71-123">指定会议工作负荷时，已选择电话拨入式会议选项。</span><span class="sxs-lookup"><span data-stu-id="afb71-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="afb71-124">有关定义拓扑的详细信息，请参阅部署文档中的在 [Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md) 。</span><span class="sxs-lookup"><span data-stu-id="afb71-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="afb71-125">已发布拓扑，并已设置前端池或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="afb71-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="afb71-126">有关发布拓扑和安装 Lync Server 2013 的详细信息，请参阅部署文档中的 [部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="afb71-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="afb71-127">安装发布的拓扑时，电话拨入式会议设置网页将作为 Web 服务的一部分安装在前端服务器或 Standard Edition Server 上。</span><span class="sxs-lookup"><span data-stu-id="afb71-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="afb71-128">如果您在部署 Lync Server 2013 之后在拓扑生成器中更改文件存储的路径，则需要重新启动会议助理和会议通知应用程序才能使用新路径。</span><span class="sxs-lookup"><span data-stu-id="afb71-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="afb71-129">部署了企业语音。</span><span class="sxs-lookup"><span data-stu-id="afb71-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="afb71-130">如果不部署企业语音，请在 Enterprise Edition 前端服务器或 Standard Edition 服务器上并置中介服务器，或者部署了独立的中介服务器，并且部署了 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="afb71-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="afb71-131">有关部署企业语音的详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md) 。</span><span class="sxs-lookup"><span data-stu-id="afb71-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="afb71-132">有关安装独立中介服务器和 PSTN 网关的详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) 。</span><span class="sxs-lookup"><span data-stu-id="afb71-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="afb71-133">下面的流程图显示配置电话拨入式会议之前必须执行的步骤，以及配置电话拨入式会议时需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="afb71-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="afb71-134">**部署电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="afb71-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="afb71-135">![电话拨入式会议部署流程图](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "电话拨入式会议部署流程图")</span><span class="sxs-lookup"><span data-stu-id="afb71-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="afb71-136">电话拨入式会议权限</span><span class="sxs-lookup"><span data-stu-id="afb71-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="afb71-137">要配置电话拨入式会议，需要使用以下管理工具：</span><span class="sxs-lookup"><span data-stu-id="afb71-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="afb71-138">Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="afb71-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="afb71-139">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="afb71-139">Lync Server Management Shell</span></span>

<span data-ttu-id="afb71-140">使用这些管理工具配置电话拨入式会议设置、拨号计划、策略以及其他电话拨入式会议所需的设置。</span><span class="sxs-lookup"><span data-stu-id="afb71-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="afb71-141">配置电话拨入式会议需要以下任一管理角色，具体取决于任务：</span><span class="sxs-lookup"><span data-stu-id="afb71-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="afb71-142">**CsVoiceAdministrator**    此管理员角色可以创建、配置和管理与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="afb71-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="afb71-143">**CsUserAdministrator**    此管理员角色可以为用户启用和禁用 Lync Server，并将现有策略（如会议策略和 PIN 策略）分配给用户。</span><span class="sxs-lookup"><span data-stu-id="afb71-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="afb71-144">**CsAdministrator**    此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="afb71-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afb71-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afb71-145">See Also</span></span>


[<span data-ttu-id="afb71-146">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="afb71-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

