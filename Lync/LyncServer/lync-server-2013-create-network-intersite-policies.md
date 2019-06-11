---
title: 'Lync Server 2013: 创建网络站点间策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="5c528-102">在 Lync Server 2013 中创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="5c528-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c528-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5c528-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5c528-104">*网络站点间策略*定义具有直接 WAN 链接的站点之间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="5c528-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="5c528-105">有关详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:</span><span class="sxs-lookup"><span data-stu-id="5c528-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5c528-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5c528-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="5c528-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5c528-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="5c528-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5c528-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="5c528-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5c528-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5c528-110">只有当两个网络站点之间有直接交叉链接时,<EM>才</EM>需要网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="5c528-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="5c528-111">在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。</span><span class="sxs-lookup"><span data-stu-id="5c528-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="5c528-112">这两个网站需要应用相应带宽策略配置文件的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="5c528-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="5c528-113">下面的示例应用 20Mb\_链接配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c528-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="5c528-114">创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="5c528-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="5c528-115">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5c528-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5c528-116">运行 CsNetworkInterSitePolicy cmdlet 以创建网络站点间策略, 并为具有直接交叉链接的两个站点应用相应的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c528-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="5c528-117">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="5c528-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="5c528-118">根据需要重复步骤 2, 以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="5c528-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

