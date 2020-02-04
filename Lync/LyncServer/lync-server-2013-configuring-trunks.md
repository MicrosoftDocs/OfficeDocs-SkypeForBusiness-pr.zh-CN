---
title: Lync Server 2013：配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="36606-102">在 Lync Server 2013 中配置中继</span><span class="sxs-lookup"><span data-stu-id="36606-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36606-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="36606-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="36606-104">作为企业语音部署的一部分，您可以在中介服务器和一个或多个以下对等方之间配置主干，以便为企业语音客户端和组织中的设备提供公共交换电话网络（PSTN）连接：</span><span class="sxs-lookup"><span data-stu-id="36606-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="36606-105">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="36606-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="36606-106">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="36606-106">PSTN gateway</span></span>

  - <span data-ttu-id="36606-107">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="36606-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="36606-108">有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 "规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)"。</span><span class="sxs-lookup"><span data-stu-id="36606-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36606-109">在开始中继配置之前，验证已创建拓扑，并且中介服务器及其对等已配置并与另一个关联。</span><span class="sxs-lookup"><span data-stu-id="36606-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="36606-110">有关详细信息，请参阅部署文档中<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 的拓扑生成器中的 "定义网关</A>"。</span><span class="sxs-lookup"><span data-stu-id="36606-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="36606-111">作为主干配置的一部分，你可以启用 Lync Server 2013 媒体绕过功能，这使媒体能够绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="36606-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="36606-112">中继可以使用或不启用媒体旁路进行配置，但我们强烈建议你启用它。</span><span class="sxs-lookup"><span data-stu-id="36606-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="36606-113">有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中规划媒体旁路</A>。</span><span class="sxs-lookup"><span data-stu-id="36606-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36606-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="36606-114">In This Section</span></span>

  - [<span data-ttu-id="36606-115">Lync Server 2013 中的多个中继支持</span><span class="sxs-lookup"><span data-stu-id="36606-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="36606-116">Lync Server 2013 中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="36606-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="36606-117">在 Lync Server 2013 中查看中继配置信息</span><span class="sxs-lookup"><span data-stu-id="36606-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="36606-118">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36606-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="36606-119">在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干</span><span class="sxs-lookup"><span data-stu-id="36606-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="36606-120">在 Lync Server 2013 中创建新的主干配置设置集合</span><span class="sxs-lookup"><span data-stu-id="36606-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="36606-121">删除 Lync Server 2013 中的现有 SIP 中继配置设置集合</span><span class="sxs-lookup"><span data-stu-id="36606-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="36606-122">在 Lync Server 2013 中修改 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="36606-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="36606-123">在 Lync Server 2013 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="36606-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="36606-124">在 Lync Server 2013 中查看有关单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="36606-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36606-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36606-125">See Also</span></span>


[<span data-ttu-id="36606-126">在 Lync Server 2013 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="36606-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="36606-127">在 Lync Server 2013 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="36606-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="36606-128">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="36606-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

