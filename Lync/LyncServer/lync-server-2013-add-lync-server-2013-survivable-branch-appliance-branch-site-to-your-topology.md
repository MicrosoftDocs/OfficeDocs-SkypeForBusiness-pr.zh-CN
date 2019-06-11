---
title: 将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="48cb4-102">将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="48cb4-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48cb4-103">_**主题上次修改时间:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="48cb4-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="48cb4-104">Microsoft Lync Server 2013 Survivable 分支装置 (SBA) 无法与 Microsoft Lync Server 2010 前端池关联作为备份注册机构。</span><span class="sxs-lookup"><span data-stu-id="48cb4-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="48cb4-105">SBA 必须与 Microsoft Lync Server 2013 前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="48cb4-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="48cb4-106">这些步骤假设 Microsoft Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="48cb4-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="48cb4-107">在中心站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="48cb4-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="48cb4-108">将分支站点添加到 Microsoft Lync Server 2013 SBA 到拓扑</span><span class="sxs-lookup"><span data-stu-id="48cb4-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="48cb4-109">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="48cb4-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="48cb4-110">在控制台树中, 展开中心网站, 展开 "**分支网站**", 然后单击 "**新建分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="48cb4-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="48cb4-111">在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入新分支网站的名称。</span><span class="sxs-lookup"><span data-stu-id="48cb4-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="48cb4-112">可选单击 "**说明**", 然后为分支网站键入有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="48cb4-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="48cb4-113">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="48cb4-113">Click **Next**.</span></span>

6.  <span data-ttu-id="48cb4-114">可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:</span><span class="sxs-lookup"><span data-stu-id="48cb4-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="48cb4-115">单击 "**城市**", 然后键入分支站点所在城市的名称。</span><span class="sxs-lookup"><span data-stu-id="48cb4-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="48cb4-116">单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="48cb4-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="48cb4-117">单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="48cb4-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="48cb4-118">单击 "**下一步**", 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="48cb4-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="48cb4-119">如果在此网站上使用 Survivable 分支装置或 Survivable 分支服务器, 请确保选中 "**此向导关闭时打开新的 Survivable 向导**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="48cb4-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="48cb4-120">如果你未在此网站上使用 Survivable 分支装置或 Survivable 分支服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="48cb4-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="48cb4-121">单击 "**完成**", 然后按照向导中打开的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="48cb4-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="48cb4-122">有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="48cb4-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="48cb4-123">对要添加到拓扑中的每个分支站点重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="48cb4-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48cb4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48cb4-124">See Also</span></span>


[<span data-ttu-id="48cb4-125">在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="48cb4-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="48cb4-126">在 Lync Server 2013 中为分支站点定义 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="48cb4-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="48cb4-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cb4-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="48cb4-128">在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干</span><span class="sxs-lookup"><span data-stu-id="48cb4-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

