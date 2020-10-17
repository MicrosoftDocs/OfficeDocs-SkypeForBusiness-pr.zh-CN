---
title: Lync Server 2013：呼叫允许控制部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e16c4c77876064ca0ab9210b96d7c13d68cc4218
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537239"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="fc583-102">Lync Server 2013 的呼叫允许控制部署清单</span><span class="sxs-lookup"><span data-stu-id="fc583-102">Call admission control deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc583-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fc583-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fc583-104">使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。</span><span class="sxs-lookup"><span data-stu-id="fc583-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="fc583-p101">如果已部署一台或多台边缘服务器，则必须将每个外部接口 IP 地址添加到网络配置设置中的子网列表，其中位掩码为 32。还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。</span><span class="sxs-lookup"><span data-stu-id="fc583-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc583-107">边缘服务器无需实现 CAC。</span><span class="sxs-lookup"><span data-stu-id="fc583-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="fc583-108">确保可以通过 Lync Server 控制面板或通过运行在 [Lync server 2013 中启用呼叫允许控制](lync-server-2013-enable-call-admission-control.md)中指定的 cmdlet 来启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="fc583-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="fc583-109">确保已在所有中央站点启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="fc583-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="fc583-110">可以通过拓扑生成器来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="fc583-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="fc583-111">如果发布时生成警告，*请勿* 忽略该警告。</span><span class="sxs-lookup"><span data-stu-id="fc583-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="fc583-112">确保已在网络配置设置中配置在企业网络中管理的所有子网。</span><span class="sxs-lookup"><span data-stu-id="fc583-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="fc583-113">如果将子网 [与 Lync Server 2013 中的网络站点](lync-server-2013-associate-a-subnet-with-a-network-site.md)关联，则还必须将每个子网与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="fc583-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="fc583-114">确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fc583-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

