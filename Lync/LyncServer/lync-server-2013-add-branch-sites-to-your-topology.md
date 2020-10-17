---
title: Lync Server 2013：将分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521569"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="29780-102">在 Lync Server 2013 中向拓扑添加分支站点</span><span class="sxs-lookup"><span data-stu-id="29780-102">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29780-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="29780-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="29780-p101">分支站点代表通过 WAN 链路连接到总部的物理分支办公室。要将分支站点添加到 Lync 拓扑，请在中央站点执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="29780-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="29780-106">向拓扑中添加分支站点</span><span class="sxs-lookup"><span data-stu-id="29780-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="29780-107">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="29780-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="29780-108">在控制台树中，展开中央站点，右键单击“分支站点”\*\*\*\*，然后单击“新建分支站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="29780-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="29780-109">在“定义新的分支站点”\*\*\*\* 对话框中，单击“名称”\*\*\*\*，然后键入分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="29780-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="29780-110">（可选）单击“说明”\*\*\*\*，然后为分支站点键入有一定含义的说明。</span><span class="sxs-lookup"><span data-stu-id="29780-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="29780-111">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="29780-111">Click **Next**.</span></span>

6.  <span data-ttu-id="29780-112">（可选）在下一个“定义新的分支站点”\*\*\*\* 对话框中，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="29780-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="29780-113">单击“市/县”\*\*\*\*，然后键入分支站点所在的市/县的名称。</span><span class="sxs-lookup"><span data-stu-id="29780-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="29780-114">单击“国家/地区”\*\*\*\*，然后键入分支站点所在的国家或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="29780-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="29780-115">单击“国家/地区代码”\*\*\*\*，然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="29780-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="29780-116">单击“下一步”\*\*\*\*，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="29780-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="29780-117">如果在此网站上使用 Survivable 分支设备或服务器，请确保选中 "在 **此向导关闭时打开新 Survivable 向导** " 复选框，单击 " **完成**"，然后按照向导中打开的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="29780-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="29780-118">有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="29780-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="29780-119">如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”\*\*\*\* 复选框，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="29780-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="29780-120">对要添加到拓扑的每个分支站点重复之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="29780-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="29780-121">**下一步：**</span><span class="sxs-lookup"><span data-stu-id="29780-121">**Next step:**</span></span>

<span data-ttu-id="29780-122">对于 Survivable 分支装置或服务器： [在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="29780-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="29780-123">对于非复原 PSTN 连接：在 lync server 2013 中为 [分支站点定义 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)， [在 lync server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或 [在 lync server 2013 中配置不使用媒体旁路的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="29780-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

