---
title: Lync Server 2013：部署中介服务器和定义对等方
description: Lync Server 2013：部署中介服务器和定义对等方。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545228"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="f3582-103">在 Lync Server 2013 中部署中介服务器和定义对等方</span><span class="sxs-lookup"><span data-stu-id="f3582-103">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3582-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f3582-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f3582-105">在前端池中提供了企业语音工作负载、电话拨入式会议和高级企业语音应用程序 (响应组应用程序、呼叫寄存应用程序、呼叫允许控制 (CAC) ) 等。</span><span class="sxs-lookup"><span data-stu-id="f3582-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="f3582-106">在 Lync Server 2013 中，中介服务器的功能内置于前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="f3582-106">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="f3582-107">不再需要单独的独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f3582-107">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="f3582-108">前端池可以与受支持的网关直接通信， (公开交换的电话网络 (PSTN) 网关或 IP PBX) ，从而消除了中介服务器充当中介的需求。</span><span class="sxs-lookup"><span data-stu-id="f3582-108">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="f3582-109">唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。</span><span class="sxs-lookup"><span data-stu-id="f3582-109">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="f3582-110">若要将企业语音基础结构连接到 SIP 中继提供程序，必须部署单独的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f3582-110">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="f3582-111">Lync Server (前端池或独立中介服务器上的中介服务器组件之间的连接) 并将网关定义为称为 *中继*的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="f3582-111">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="f3582-112">本节中的主题介绍如何定义中继，以及在连接到 SIP 中继的情况下，如何部署独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f3582-112">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f3582-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f3582-113">In This Section</span></span>

  - [<span data-ttu-id="f3582-114">在 Lync Server 2013 的拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="f3582-114">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="f3582-115">在 Lync Server 2013 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="f3582-115">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="f3582-116">在 Lync Server 2013 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="f3582-116">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="f3582-117">在 Lync Server 2013 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="f3582-117">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f3582-118">相关部分</span><span class="sxs-lookup"><span data-stu-id="f3582-118">Related Sections</span></span>

[<span data-ttu-id="f3582-119">在 Lync Server 2013 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="f3582-119">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

