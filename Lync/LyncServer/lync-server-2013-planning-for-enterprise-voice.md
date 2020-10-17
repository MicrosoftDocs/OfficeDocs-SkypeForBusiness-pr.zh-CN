---
title: Lync Server 2013：规划企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 324798f36a92a81a1f210a173cf9e3e0efa00aca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513569"
---
# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6e804-102">在 Lync Server 2013 中规划企业语音</span><span class="sxs-lookup"><span data-stu-id="6e804-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e804-103">_**上次修改的主题：** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e804-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="6e804-104">企业语音的部署过程取决于您现有的拓扑、基础结构和您要支持的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="6e804-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="6e804-105">所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。</span><span class="sxs-lookup"><span data-stu-id="6e804-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="6e804-106">通常，无论您是否要为每个网站提供语音功能的冗余和故障转移，请考虑您要部署的网站的类型和数量以及它们的地理位置、每个网站的呼叫量、连接网站的网络链接的类型，以及是否要为每个网站提供语音功能的冗余和故障转移，以及是否要使用现有的 PBX 设备。</span><span class="sxs-lookup"><span data-stu-id="6e804-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="6e804-107">在您将 Lync Server 通信软件作为一个整体进行规划时，应考虑一些需要考虑的事项，如高可用性。</span><span class="sxs-lookup"><span data-stu-id="6e804-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="6e804-108">此部分中的主题将根据需要对这些注意事项进行讨论。</span><span class="sxs-lookup"><span data-stu-id="6e804-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="6e804-109">规划注意事项</span><span class="sxs-lookup"><span data-stu-id="6e804-109">Planning Considerations</span></span>

<span data-ttu-id="6e804-110">有关与特定企业语音功能或部署方案或组件的部署相关的规划决策，请参阅本节中的主题。</span><span class="sxs-lookup"><span data-stu-id="6e804-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="6e804-111">在 Lync Server 2013 中定义对企业语音的要求</span><span class="sxs-lookup"><span data-stu-id="6e804-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="6e804-112">估计 Lync Server 2013 的语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="6e804-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="6e804-113">Lync Server 2013 中的高级企业语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="6e804-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="6e804-114">Lync Server 2013 中的企业语音所需组件</span><span class="sxs-lookup"><span data-stu-id="6e804-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="6e804-115">在 Lync Server 2013 中规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="6e804-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6e804-116">在 Lync Server 2013 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="6e804-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="6e804-117">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="6e804-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="6e804-118">在 Lync Server 2013 中规划紧急服务 (E9-1-1) </span><span class="sxs-lookup"><span data-stu-id="6e804-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="6e804-119">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="6e804-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="6e804-120">规划 Lync Server 2013 的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="6e804-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="6e804-121">在 Lync Server 2013 中规划 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="6e804-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="6e804-122">在 Lync Server 2013 中规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="6e804-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6e804-123">Lync Server 2013 中的企业语音部署指南</span><span class="sxs-lookup"><span data-stu-id="6e804-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="6e804-124">Lync Server 2013 中的企业语音部署过程概述</span><span class="sxs-lookup"><span data-stu-id="6e804-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="6e804-125">将用户移动到 Lync Server 2013 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="6e804-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="6e804-126">Lync Server 2013 中的 lync PreCall 诊断工具</span><span class="sxs-lookup"><span data-stu-id="6e804-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

