---
title: Lync Server 2013：向拓扑添加分支站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="9dbb0-102">在 Lync Server 2013 中向拓扑添加分支站点</span><span class="sxs-lookup"><span data-stu-id="9dbb0-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dbb0-103">_**主题上次修改时间:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9dbb0-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9dbb0-104">分支站点表示通过 WAN 链接连接到您的主办公室的物理分支机构。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="9dbb0-105">若要将分支站点添加到 Lync 拓扑中, 请在中心站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="9dbb0-106">将分支站点添加到拓扑</span><span class="sxs-lookup"><span data-stu-id="9dbb0-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="9dbb0-107">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync 服务器**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9dbb0-108">在控制台树中, 展开中心网站, 右键单击 "**分支网站**", 然后单击 "**新建分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="9dbb0-109">在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入分支网站的名称。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="9dbb0-110">可选单击 "**说明**", 然后为分支网站键入有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="9dbb0-111">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-111">Click **Next**.</span></span>

6.  <span data-ttu-id="9dbb0-112">可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:</span><span class="sxs-lookup"><span data-stu-id="9dbb0-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="9dbb0-113">单击 "**城市**", 然后键入分支站点所在城市的名称。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9dbb0-114">单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9dbb0-115">单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="9dbb0-116">单击 "**下一步**", 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="9dbb0-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="9dbb0-117">如果您在此站点使用 Survivable 分支装置或服务器, 请确保选中 "**此向导关闭时打开新的 Survivable 向导**" 复选框, 单击 "**完成**", 然后按照向导中打开的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="9dbb0-118">有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="9dbb0-119">如果未在此网站使用 Survivable 分支装置或服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="9dbb0-120">对要添加到拓扑中的每个分支站点重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="9dbb0-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="9dbb0-121">**下一步:**</span><span class="sxs-lookup"><span data-stu-id="9dbb0-121">**Next step:**</span></span>

<span data-ttu-id="9dbb0-122">对于 Survivable 分支装置或服务器:[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="9dbb0-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="9dbb0-123">对于非复原 PSTN 连接:[在 lync server 2013 中定义分支站点的 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), 在[lync server 2013 中使用 "媒体绕过" 配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)网, 或者[在 lync server 中配置不使用 "媒体旁路" 的 trunk 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="9dbb0-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

