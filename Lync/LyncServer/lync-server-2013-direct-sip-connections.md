---
title: 'Lync Server 2013: 直接 SIP 连接'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1decdfd4c755ea1788d088a4b539d8c555987f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="ac846-102">Lync Server 2013 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="ac846-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac846-103">_**主题上次修改时间:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="ac846-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="ac846-104">您可以使用*直接 SIP 连接*将 Lync Server 连接到下列任一操作:</span><span class="sxs-lookup"><span data-stu-id="ac846-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="ac846-105">IP-PBX (有关详细信息, 请参阅[Lync Server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md))。</span><span class="sxs-lookup"><span data-stu-id="ac846-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="ac846-106">PSTN 网关 (有关详细信息, 请参阅[Lync Server 2013 中的 PSTN 网关部署选项](lync-server-2013-pstn-gateway-deployment-options.md))。</span><span class="sxs-lookup"><span data-stu-id="ac846-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="ac846-107">若要实现直接 SIP 连接, 请遵循与实现 SIP 主干基本相同的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="ac846-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="ac846-108">在这两种情况下, 通过使用中介服务器的外部接口实现连接。</span><span class="sxs-lookup"><span data-stu-id="ac846-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="ac846-109">唯一的区别是, 你可以将 SIP 中继连接到外部实体 (如 ITSP 网关), 并将直接 SIP 连接连接到本地网络内的内部实体, 如 IP PBX 或公共交换电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="ac846-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac846-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac846-110">In This Section</span></span>

  - [<span data-ttu-id="ac846-111">Lync Server 2013 中的直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="ac846-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="ac846-112">Lync Server 2013 中的 PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="ac846-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

