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
ms.openlocfilehash: 80f5bf646dbed73beb7d9dd102e7e7b2bf802e49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="a0436-102">在 Lync Server 2013 中配置中继</span><span class="sxs-lookup"><span data-stu-id="a0436-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0436-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a0436-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a0436-104">作为企业语音部署的一部分，您可以在中介服务器和以下一个或多个对等方之间配置中继，为企业语音客户端和组织中的设备提供公共交换电话网络（PSTN）连接：</span><span class="sxs-lookup"><span data-stu-id="a0436-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="a0436-105">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="a0436-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="a0436-106">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="a0436-106">PSTN gateway</span></span>

  - <span data-ttu-id="a0436-107">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="a0436-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="a0436-108">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="a0436-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a0436-109">在开始中继配置之前，请确认已创建了拓扑，并且已将中介服务器及其对等方配置为与另一个关联。</span><span class="sxs-lookup"><span data-stu-id="a0436-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="a0436-110">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">拓扑生成器中定义网关在 Lync Server 2013</A>中。</span><span class="sxs-lookup"><span data-stu-id="a0436-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a0436-111">作为中继配置的一部分，您可以启用 Lync Server 2013 媒体旁路功能，该功能使媒体能够绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a0436-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="a0436-112">配置中继时可以启用媒体旁路，也可以不启用媒体旁路，但我们强烈建议您启用该功能。</span><span class="sxs-lookup"><span data-stu-id="a0436-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="a0436-113">有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中规划媒体旁路</A>。</span><span class="sxs-lookup"><span data-stu-id="a0436-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0436-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a0436-114">In This Section</span></span>

  - [<span data-ttu-id="a0436-115">Lync Server 2013 中的多中继支持</span><span class="sxs-lookup"><span data-stu-id="a0436-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="a0436-116">Lync Server 2013 中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="a0436-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="a0436-117">在 Lync Server 2013 中查看中继配置信息</span><span class="sxs-lookup"><span data-stu-id="a0436-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="a0436-118">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="a0436-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="a0436-119">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="a0436-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="a0436-120">在 Lync Server 2013 中创建一个新的中继配置设置集合</span><span class="sxs-lookup"><span data-stu-id="a0436-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="a0436-121">删除 Lync Server 2013 中现有的 SIP 中继配置设置集合</span><span class="sxs-lookup"><span data-stu-id="a0436-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="a0436-122">在 Lync Server 2013 中修改 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="a0436-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="a0436-123">在 Lync Server 2013 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="a0436-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="a0436-124">在 Lync Server 2013 中查看有关各个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="a0436-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0436-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0436-125">See Also</span></span>


[<span data-ttu-id="a0436-126">在 Lync Server 2013 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="a0436-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="a0436-127">在 Lync Server 2013 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="a0436-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="a0436-128">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="a0436-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

