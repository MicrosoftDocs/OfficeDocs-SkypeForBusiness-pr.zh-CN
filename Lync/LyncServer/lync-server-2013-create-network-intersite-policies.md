---
title: Lync Server 2013：创建网络站点间策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7024aa0a9f5c5734762ed0accb6e1dc723f2b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="d4752-102">在 Lync Server 2013 中创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="d4752-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4752-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d4752-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d4752-104">\*\*“网络站点间策略”定义其间具有直接 WAN 链路的站点间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="d4752-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="d4752-105">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d4752-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d4752-106">新 New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="d4752-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="d4752-107">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="d4752-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="d4752-108">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="d4752-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="d4752-109">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="d4752-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d4752-110"><EM></EM>仅当两个网络站点之间具有直接交叉链接时，才需要网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="d4752-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="d4752-111">在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。</span><span class="sxs-lookup"><span data-stu-id="d4752-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="d4752-112">这两个站点需要可应用相应带宽策略配置文件的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="d4752-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="d4752-113">下面的示例应用 20Mb\_链接配置文件。</span><span class="sxs-lookup"><span data-stu-id="d4752-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="d4752-114">创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="d4752-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="d4752-115">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4752-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d4752-p102">运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略并为两个具有直接交叉链接的站点应用相应的带宽策略配置文件。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="d4752-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="d4752-118">根据需要重复步骤 2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="d4752-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

