---
title: Lync Server 2013：配置增强型 9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e171d2d3d72675d194a8272dfca1e2f24b8fa150
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="79fef-102">在 Lync Server 2013 中配置增强型 9-1-1</span><span class="sxs-lookup"><span data-stu-id="79fef-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79fef-103">_**主题上次修改时间：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="79fef-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="79fef-p101">增强型 9-1-1 (E9-1-1) 是一种紧急通知功能，可以将呼叫者的电话号码与某个市政地址或街道地址相关联。使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。</span><span class="sxs-lookup"><span data-stu-id="79fef-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="79fef-106">若要支持 E9-1，Lync Server 2013 必须能够正确地将某个位置与客户端相关联，并确保使用此信息将紧急呼叫路由到最近的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="79fef-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="79fef-107">有关规划 E9 部署的详细信息，请参阅[Lync Server 2013 中的 "规划紧急服务（E9-1-1）](lync-server-2013-planning-for-emergency-services-e9-1-1.md)"。</span><span class="sxs-lookup"><span data-stu-id="79fef-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79fef-108">Lync Server 2013 仅支持美国境内的 E9-1。</span><span class="sxs-lookup"><span data-stu-id="79fef-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="79fef-109">若要部署 E9，您需要配置到合格的 E9 服务提供商的 SIP 连接，或将紧急位置识别号码（ELIN）网关部署到基于交换机的公共电话（PSTN）的 E9-1-1 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="79fef-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="79fef-110">有关详细信息，请参阅<A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync server 2013 中的增强9-1-1 （E9-1）和中介服务器</A>。</span><span class="sxs-lookup"><span data-stu-id="79fef-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="79fef-111">有关配置中继连接的详细信息，请参阅<A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中使用 "媒体绕过" 配置主干</A>。</span><span class="sxs-lookup"><span data-stu-id="79fef-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79fef-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="79fef-112">In This Section</span></span>

  - [<span data-ttu-id="79fef-113">在 Lync Server 2013 中配置 E9-1 个语音路由</span><span class="sxs-lookup"><span data-stu-id="79fef-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="79fef-114">在 Lync Server 2013 中创建位置策略</span><span class="sxs-lookup"><span data-stu-id="79fef-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="79fef-115">在 Lync Server 2013 中配置 E9-1 的网站信息</span><span class="sxs-lookup"><span data-stu-id="79fef-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="79fef-116">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79fef-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="79fef-117">在 Lync Server 2013 中配置高级 E9-1-1 功能</span><span class="sxs-lookup"><span data-stu-id="79fef-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

