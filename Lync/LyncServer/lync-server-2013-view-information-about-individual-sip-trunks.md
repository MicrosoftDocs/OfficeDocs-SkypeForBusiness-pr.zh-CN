---
title: Lync Server 2013：查看有关单个 SIP 中继的信息
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
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="4c906-102">在 Lync Server 2013 中查看有关单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4c906-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c906-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4c906-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4c906-104">SIP 中继用于通过公共交换电话网络连接 Lync Server 2013 语音 over IP 电话网络。</span><span class="sxs-lookup"><span data-stu-id="4c906-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="4c906-105">在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。</span><span class="sxs-lookup"><span data-stu-id="4c906-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="4c906-106">因此，PSTN 网关和 SIP 中继基本上完全相同。</span><span class="sxs-lookup"><span data-stu-id="4c906-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="4c906-107">对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="4c906-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="4c906-108">但是，在 Lync Server 2013 中，多个中继现在可以分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。</span><span class="sxs-lookup"><span data-stu-id="4c906-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="4c906-109">而这意味着管理员必须使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet，才能查看有关个别 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="4c906-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="4c906-110">CsTrunk cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="4c906-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4c906-111">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="4c906-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="4c906-112">查看所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4c906-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="4c906-113">以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="4c906-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="4c906-114">查看特定 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4c906-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="4c906-115">此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="4c906-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="4c906-116">查看分配到池的所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4c906-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="4c906-117">在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="4c906-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

