---
title: Lync Server 2013：配置呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dbf06-102">在 Lync Server 2013 中配置呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="dbf06-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbf06-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dbf06-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dbf06-104">呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。</span><span class="sxs-lookup"><span data-stu-id="dbf06-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="dbf06-105">CAC 仅控制音频和视频的实时流量，不会影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="dbf06-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="dbf06-106">如果默认 WAN 路径没有所需的带宽，CAC 可能会通过 Internet 路径路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="dbf06-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="dbf06-107">有关详细信息，请参阅规划文档中[Lync Server 2013 中的 "计划呼叫许可控制](lync-server-2013-planning-for-call-admission-control.md)"。</span><span class="sxs-lookup"><span data-stu-id="dbf06-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="dbf06-108">本部分提供了一组示例过程，这些过程演示了如何在网络中部署和管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="dbf06-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dbf06-109">在部署 CAC 之前，必须收集企业网络拓扑的所有必需信息，如示例所述：在规划文档中<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">收集 Lync Server 2013 中的呼叫许可控制要求</A>。</span><span class="sxs-lookup"><span data-stu-id="dbf06-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="dbf06-110">此外，请确保已安装并激活 CAC 组件，如在部署文档中的<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或标准版服务器</A>中所述。</span><span class="sxs-lookup"><span data-stu-id="dbf06-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dbf06-111">本部分中的所有 CAC 部署和管理示例均使用 Lync Server 命令行管理程序执行。</span><span class="sxs-lookup"><span data-stu-id="dbf06-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="dbf06-112">或者，也可以使用 Lync Server 控制面板的 "<STRONG>网络配置</STRONG>" 部分管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="dbf06-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dbf06-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="dbf06-113">In This Section</span></span>

  - [<span data-ttu-id="dbf06-114">在 Lync Server 2013 中配置 CAC 的网络区域</span><span class="sxs-lookup"><span data-stu-id="dbf06-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="dbf06-115">在 Lync Server 2013 中创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="dbf06-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="dbf06-116">在 Lync Server 2013 中配置 CAC 的网络站点</span><span class="sxs-lookup"><span data-stu-id="dbf06-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="dbf06-117">将子网与 Lync Server 2013 中的 CAC 的网络站点关联</span><span class="sxs-lookup"><span data-stu-id="dbf06-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="dbf06-118">在 Lync Server 2013 中创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="dbf06-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="dbf06-119">在 Lync Server 2013 中创建网络 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="dbf06-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="dbf06-120">在 Lync Server 2013 中创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="dbf06-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="dbf06-121">在 Lync Server 2013 中启用呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="dbf06-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="dbf06-122">Lync Server 2013 的 "呼叫许可控制" 部署清单</span><span class="sxs-lookup"><span data-stu-id="dbf06-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

