---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95831fc6b6c43c6b4a1944187447fe3ff83f1d14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503109"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="83904-102">连接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="83904-102">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83904-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="83904-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="83904-104">每个 Survivable 分支设备 (SBA) 都与一个前端池相关联，该前端池充当 SBA 的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="83904-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="83904-105">当将前端池迁移到 Lync Server 2013 时，在升级池时，SBA 必须与 Lync Server 2010 前端池解除关联，一旦将池迁移到 Lync Server 2013，则 SBA 可以与升级后的前端池重新关联。</span><span class="sxs-lookup"><span data-stu-id="83904-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="83904-106">这包括从拓扑生成器中的旧版 Lync Server 2010 拓扑中删除 SBA，然后将 SBA 添加到 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="83904-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="83904-107">驻留在旧 Lync Server 2010 SBA 上的用户必须先移到另一个前端池，然后才能从拓扑中删除 SBA。</span><span class="sxs-lookup"><span data-stu-id="83904-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="83904-108">将 SBA 添加到 Lync Server 2013 拓扑后，这些用户即可移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="83904-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="83904-109">这些步骤概括如下：</span><span class="sxs-lookup"><span data-stu-id="83904-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="83904-110">将驻留在旧版 SBA Lync Server 2010 的分支用户移动到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="83904-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="83904-111">从旧版 Lync Server 2010 拓扑中删除 SBA，以将现有的前端池作为备份注册器断开连接。</span><span class="sxs-lookup"><span data-stu-id="83904-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="83904-112">将 SBA 添加到 Lync Server 2013 拓扑，并将此新的前端池配置为备份注册器。</span><span class="sxs-lookup"><span data-stu-id="83904-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="83904-113">将分支用户移动到新的 Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="83904-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="83904-114">**将 Lync Server 2010 SBA 分支站点添加到您的拓扑**</span><span class="sxs-lookup"><span data-stu-id="83904-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="83904-115">打开“拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="83904-116">在左窗格中右键单击“分支站点”\*\*\*\*，然后单击“新建分支站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="83904-117">在“定义新的分支站点”\*\*\*\* 对话框中，单击“名称”\*\*\*\*，然后键入分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="83904-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="83904-118">（可选）单击“说明”\*\*\*\*，然后为分支站点键入有一定含义的说明。</span><span class="sxs-lookup"><span data-stu-id="83904-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="83904-119">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-119">Click **Next**.</span></span>

6.  <span data-ttu-id="83904-120">（可选）在下一个“定义新的分支站点”\*\*\*\* 对话框中，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="83904-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="83904-121">单击“市/县”\*\*\*\*，然后键入分支站点所在的市/县的名称。</span><span class="sxs-lookup"><span data-stu-id="83904-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="83904-122">单击“国家/地区”\*\*\*\*，然后键入分支站点所在的国家或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="83904-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="83904-123">单击“国家/地区代码”\*\*\*\*，然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="83904-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="83904-124">单击“下一步”\*\*\*\*，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="83904-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="83904-p102">如果在此站点使用的是 Lync 2010 Survivable Branch Appliance 或 Lync 2010 Survivable Branch Server，确保取消选中“此向导关闭后将打开新建 Survivable 向导”\*\*\*\* 选项。单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="83904-127">若要将旧版 Lync Server 2010 SBA 与 Lync Server 2013 前端池相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83904-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="83904-128">展开已创建的分支站点。</span><span class="sxs-lookup"><span data-stu-id="83904-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="83904-129">右键单击“Lync Server 2010”\*\*\*\*，然后单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="83904-130">单击“Survivable Branch Appliance…”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83904-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="83904-131">按照打开的向导中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="83904-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="83904-132">有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="83904-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83904-133">Lync Server 2010 Survivable 分支设备仅可与 Lync Server 2010 监视存储关联。</span><span class="sxs-lookup"><span data-stu-id="83904-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="83904-134">如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”\*\*\*\* 复选框，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83904-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="83904-135">对要添加到拓扑的每个分支站点重复之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="83904-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

