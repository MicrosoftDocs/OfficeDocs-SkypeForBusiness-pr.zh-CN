---
title: 将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad708f2f37b95d970f9c9585730c015ff6798f6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521459"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="ac0e6-102">将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="ac0e6-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac0e6-103">_**上次修改的主题：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="ac0e6-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="ac0e6-104">Microsoft Lync Server 2013 Survivable 分支装置 (SBA) 不能与 Microsoft Lync Server 2010 前端池关联，作为备份注册器。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="ac0e6-105">SBA 必须与 Microsoft Lync Server 2013 前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="ac0e6-106">这些步骤假设 Microsoft Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="ac0e6-107">请在中央站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="ac0e6-108">将分支站点添加到 Microsoft Lync Server 2013 SBA 到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="ac0e6-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="ac0e6-109">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ac0e6-110">在控制台树中，展开中央站点，再展开“分支站点”\*\*\*\*，然后单击“新建分支站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="ac0e6-111">在“定义新的分支站点”\*\*\*\* 对话框中，单击“名称”\*\*\*\*，然后键入新分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="ac0e6-112">（可选）单击“说明”\*\*\*\*，然后为分支站点键入有一定含义的说明。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="ac0e6-113">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-113">Click **Next**.</span></span>

6.  <span data-ttu-id="ac0e6-114">（可选）在下一个“定义新的分支站点”\*\*\*\* 对话框中，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="ac0e6-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="ac0e6-115">单击“市/县”\*\*\*\*，然后键入分支站点所在的市/县的名称。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ac0e6-116">单击“国家/地区”\*\*\*\*，然后键入分支站点所在的国家或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ac0e6-117">单击“国家/地区代码”\*\*\*\*，然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="ac0e6-118">单击“下一步”\*\*\*\*，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ac0e6-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ac0e6-119">如果在此网站上使用的是 Survivable 分支设备或 Survivable 分支服务器，请确保选中 " **关闭此向导时打开新的 Survivable 向导** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="ac0e6-120">如果未在此站点上使用 Survivable 分支设备或 Survivable 分支服务器，请清除 " **关闭此向导时打开新的 Survivable 向导** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="ac0e6-121">单击“完成”\*\*\*\*，然后按照打开的向导中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ac0e6-122">有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="ac0e6-123">对要添加到拓扑的每个分支站点重复之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="ac0e6-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac0e6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0e6-124">See Also</span></span>


[<span data-ttu-id="ac0e6-125">在 Lync Server 2013 中定义 Survivable 分支设备或服务器</span><span class="sxs-lookup"><span data-stu-id="ac0e6-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="ac0e6-126">在 Lync Server 2013 中为分支站点定义 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="ac0e6-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="ac0e6-127">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="ac0e6-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ac0e6-128">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="ac0e6-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

