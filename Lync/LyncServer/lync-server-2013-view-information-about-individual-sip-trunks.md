---
title: Lync Server 2013：查看有关各个 SIP 中继的信息
description: Lync Server 2013：查看有关各个 SIP 中继的信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569608"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="37904-103">在 Lync Server 2013 中查看有关各个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="37904-103">View information about individual SIP trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37904-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="37904-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="37904-105">SIP 中继用于通过公共交换电话网络连接 Lync Server 2013 Voice over IP phone 网络。</span><span class="sxs-lookup"><span data-stu-id="37904-105">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="37904-106">在产品的以前版本中，中继用于将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="37904-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="37904-107">因此，PSTN 网关和 SIP 中继本质上是相同的。</span><span class="sxs-lookup"><span data-stu-id="37904-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="37904-108">对于管理员而言，这意味着他们只需查看有关相关 PSTN 网关的信息即可查看有关单个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="37904-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="37904-109">但是，在 Lync Server 2013 中，现在可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。</span><span class="sxs-lookup"><span data-stu-id="37904-109">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="37904-110">反过来，这意味着管理员必须使用新的 [CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 才能查看有关单个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="37904-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="37904-111">Get-CsTrunk cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="37904-111">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="37904-112">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="37904-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="37904-113">查看所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="37904-113">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="37904-114">以下命令将返回有关您组织中使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="37904-114">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="37904-115">查看特定 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="37904-115">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="37904-116">此命令仅返回标识为 pstngateway：192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="37904-116">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="37904-117">查看分配到池的所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="37904-117">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="37904-118">在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="37904-118">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

