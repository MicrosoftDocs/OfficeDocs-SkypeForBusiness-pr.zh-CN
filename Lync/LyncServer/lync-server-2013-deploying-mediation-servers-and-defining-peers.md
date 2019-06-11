---
title: Lync Server 2013：部署中介服务器和定义对等方
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="13a68-102">在 Lync Server 2013 中部署中介服务器和定义对等方</span><span class="sxs-lookup"><span data-stu-id="13a68-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13a68-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="13a68-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="13a68-104">企业语音工作负荷、电话拨入式会议和高级企业语音应用程序 (响应组应用程序、呼叫驻留应用程序、呼叫许可控制 (CAC) 等) 均可在前端池中使用。</span><span class="sxs-lookup"><span data-stu-id="13a68-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="13a68-105">在 Lync Server 2013 中, 中介服务器的功能内置于前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="13a68-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="13a68-106">不再需要单独的独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="13a68-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="13a68-107">前端池可以直接与支持的网关 (公共交换式电话网络 (PSTN) 网关或 IP PBX) 进行通信, 从而消除了将中介服务器用作中介的需要。</span><span class="sxs-lookup"><span data-stu-id="13a68-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="13a68-108">唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。</span><span class="sxs-lookup"><span data-stu-id="13a68-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="13a68-109">要将企业语音基础结构连接到 SIP 中继提供商, 必须部署单独的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="13a68-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="13a68-110">Lync Server (前端池或独立中介服务器上的中介服务器组件) 和网关之间的连接定义为称为*主干*的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="13a68-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="13a68-111">本部分中的主题介绍如何定义主干以及如何部署独立中介服务器 (如果你连接到 SIP 主干)。</span><span class="sxs-lookup"><span data-stu-id="13a68-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13a68-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="13a68-112">In This Section</span></span>

  - [<span data-ttu-id="13a68-113">在 Lync Server 2013 的拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="13a68-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="13a68-114">在 Lync Server 2013 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="13a68-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="13a68-115">在 Lync Server 2013 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="13a68-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="13a68-116">在 Lync Server 2013 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="13a68-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="13a68-117">相关部分</span><span class="sxs-lookup"><span data-stu-id="13a68-117">Related Sections</span></span>

[<span data-ttu-id="13a68-118">在 Lync Server 2013 中配置拨入式会议</span><span class="sxs-lookup"><span data-stu-id="13a68-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

