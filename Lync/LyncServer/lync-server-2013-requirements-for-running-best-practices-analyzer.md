---
title: Lync Server 2013：运行最佳做法分析器的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac02b2f6c6f47a59663a414635eebe1d2e4ec851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="913de-102">在 Lync Server 2013 中运行最佳做法分析器的要求</span><span class="sxs-lookup"><span data-stu-id="913de-102">Requirements for running Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="913de-103">_**主题上次修改时间：** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="913de-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="913de-104">你可以使用 Lync Server 2013、最佳做法分析程序扫描 Lync Server 2013 环境。</span><span class="sxs-lookup"><span data-stu-id="913de-104">You can use Lync Server 2013, Best Practices Analyzer to scan your Lync Server 2013 environment.</span></span> <span data-ttu-id="913de-105">您不能使用它来扫描以前的环境，但可以使用该工具的以前版本来扫描这些环境。</span><span class="sxs-lookup"><span data-stu-id="913de-105">You cannot use it to scan previous environments, but you can use the previous versions of the tool to scan those environments.</span></span> <span data-ttu-id="913de-106">有关下载和使用适用于最佳做法分析器的 Lync Server 2010 和 Office 通信服务器 2007 R2 版本的详细信息，请参阅 "Lync Server 2010、最佳做法[http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358)分析器" at 和 "适用于 Office 通信服务器2007和 Office 通信服务器的最佳做法[http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651)分析程序" 2007 r2 "。</span><span class="sxs-lookup"><span data-stu-id="913de-106">For details about downloading and using the Lync Server 2010 and Office Communications Server 2007 R2 versions of Best Practices Analyzer, see "Lync Server 2010, Best Practices Analyzer" at [http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358) and "Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2" at [http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651).</span></span>

<span data-ttu-id="913de-107">开始扫描之前，应确保 Lync Server 2013 环境中的所有组件均已运行且处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="913de-107">Prior to starting your scan, you should ensure that all components in your Lync Server 2013 environment are running and online.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="913de-108">根据你的边缘服务器的配置和任何相关的外围网络设置（包括防火墙设置和权限），最佳做法分析器可能无法访问和扫描你的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="913de-108">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="913de-109">如果你在扫描中包含 Edge 服务器，并且报表指示访问 Edge 服务器时出现问题，你可能需要从扫描选项中删除边缘服务器并再次运行扫描，以便报表中不显示问题。</span><span class="sxs-lookup"><span data-stu-id="913de-109">If you include Edge Servers in your scan and the reports indicate that there is an issue with accessing Edge Servers, you might want to remove Edge Servers from the scan options and run the scan again so that the issues do not show up in the report.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

