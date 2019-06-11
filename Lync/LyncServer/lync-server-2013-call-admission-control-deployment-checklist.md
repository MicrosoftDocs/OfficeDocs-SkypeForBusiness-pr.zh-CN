---
title: 'Lync Server 2013: 呼叫许可控制部署清单'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="192a2-102">Lync Server 2013 的 "呼叫许可控制" 部署清单</span><span class="sxs-lookup"><span data-stu-id="192a2-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="192a2-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="192a2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="192a2-104">使用以下清单验证是否已完成部署呼叫许可控制 (CAC) 的所有必要配置任务。</span><span class="sxs-lookup"><span data-stu-id="192a2-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="192a2-105">如果部署了一个或多个边缘服务器, 则每个外部接口 IP 地址都必须添加到网络配置设置中的子网列表中, 位掩码为32。</span><span class="sxs-lookup"><span data-stu-id="192a2-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="192a2-106">还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。</span><span class="sxs-lookup"><span data-stu-id="192a2-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="192a2-107">不需要边缘服务器实现 CAC。</span><span class="sxs-lookup"><span data-stu-id="192a2-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="192a2-108">确保可以通过 Lync Server 控制面板或通过运行在[Lync server 2013 的 "启用呼叫许可控制](lync-server-2013-enable-call-admission-control.md)" 中指定的 cmdlet 来启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="192a2-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="192a2-109">确保已在所有中央站点启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="192a2-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="192a2-110">这可以通过拓扑生成器完成。</span><span class="sxs-lookup"><span data-stu-id="192a2-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="192a2-111">如果发布时生成警告，*请勿*忽略该警告。</span><span class="sxs-lookup"><span data-stu-id="192a2-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="192a2-112">确保已在网络配置设置中配置在企业网络中管理的所有子网。</span><span class="sxs-lookup"><span data-stu-id="192a2-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="192a2-113">如果[将子网与 Lync Server 2013 中的网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md), 则还必须将每个子网与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="192a2-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="192a2-114">确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="192a2-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

