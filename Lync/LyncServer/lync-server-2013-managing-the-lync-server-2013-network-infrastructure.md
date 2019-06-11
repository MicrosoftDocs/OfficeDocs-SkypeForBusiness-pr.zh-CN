---
title: Lync Server 2013：管理 Lync Server 2013 网络基础结构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd95ac0259e86f3ac8fd39a09276bffa88cfc75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="d5ef4-102">管理 Lync Server 2013 网络基础结构</span><span class="sxs-lookup"><span data-stu-id="d5ef4-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5ef4-103">_**主题上次修改时间:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="d5ef4-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="d5ef4-104">Microsoft Lync Server 2013 包括对呼叫许可控制 (CAC) 和媒体旁路的支持。</span><span class="sxs-lookup"><span data-stu-id="d5ef4-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="d5ef4-105">若要实现这些功能, 必须配置区域、网站、子网等的网络, 以便在需要限制音频和视频传输的情况下管理带宽。</span><span class="sxs-lookup"><span data-stu-id="d5ef4-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="d5ef4-106">你还可以使用服务质量 (QoS) 网络技术帮助为音频和视频通信提供最佳的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="d5ef4-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="d5ef4-107">可以使用 Lync Server 控制面板设置和管理 CAC、媒体绕过和 QoS。</span><span class="sxs-lookup"><span data-stu-id="d5ef4-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="d5ef4-108">以下主题提供有关如何执行此操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="d5ef4-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5ef4-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="d5ef4-109">In This Section</span></span>

  - [<span data-ttu-id="d5ef4-110">在 Lync Server 2013 中管理服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="d5ef4-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="d5ef4-111">在 Lync Server 2013 中管理呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="d5ef4-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="d5ef4-112">Lync Server 2013 网络接口</span><span class="sxs-lookup"><span data-stu-id="d5ef4-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="d5ef4-113">阻止与 Lync Server 2013 的新连接进行服务器维护</span><span class="sxs-lookup"><span data-stu-id="d5ef4-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="d5ef4-114">Lync Server 2013 中的 Lync 呼叫质量方法</span><span class="sxs-lookup"><span data-stu-id="d5ef4-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="d5ef4-115">Lync Server 2013 中的关键运行状况指示器</span><span class="sxs-lookup"><span data-stu-id="d5ef4-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

