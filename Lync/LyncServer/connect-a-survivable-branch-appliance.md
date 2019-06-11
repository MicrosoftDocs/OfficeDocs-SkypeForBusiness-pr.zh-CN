---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="44cfc-102">连接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="44cfc-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44cfc-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="44cfc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="44cfc-104">每个 Survivable 分支装置 (SBA) 都与一个前端池相关联, 该池充当 SBA 的备份注册机构。</span><span class="sxs-lookup"><span data-stu-id="44cfc-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="44cfc-105">当将前端池迁移到 Lync Server 2013 时, SBA 必须在池升级时与 Lync Server 2010 前端池解除关联, 一旦池迁移到 Lync Server 2013 后, SBA 可以与升级的前端池重新关联。</span><span class="sxs-lookup"><span data-stu-id="44cfc-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="44cfc-106">这包括从拓扑生成器中的旧 Lync Server 2010 拓扑中删除 SBA, 然后将 SBA 添加到 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="44cfc-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="44cfc-107">驻留在旧 Lync Server 2010 SBA 上的用户必须首先将其移动到另一个前端池, 然后才能从拓扑结构中删除 SBA。</span><span class="sxs-lookup"><span data-stu-id="44cfc-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="44cfc-108">一旦将 SBA 添加到 Lync Server 2013 拓扑, 这些用户就可以移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="44cfc-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="44cfc-109">下面总结了这些步骤:</span><span class="sxs-lookup"><span data-stu-id="44cfc-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="44cfc-110">将驻留在旧版 SBA Lync Server 2010 的分支用户移动到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="44cfc-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="44cfc-111">从旧版 Lync Server 2010 拓扑中删除 SBA, 以将现有的前端池作为备份注册机构断开连接。</span><span class="sxs-lookup"><span data-stu-id="44cfc-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="44cfc-112">将 SBA 添加到 Lync Server 2013 拓扑, 并将此新的前端池配置为备份注册机构。</span><span class="sxs-lookup"><span data-stu-id="44cfc-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="44cfc-113">将分支用户移动到新的 Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="44cfc-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="44cfc-114">**将 Lync Server 2010 SBA 分支网站添加到拓扑**</span><span class="sxs-lookup"><span data-stu-id="44cfc-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="44cfc-115">打开**拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="44cfc-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="44cfc-116">在左窗格中, 右键单击 "**分支站点**", 然后单击 "**新建分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="44cfc-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="44cfc-117">在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入分支网站的名称。</span><span class="sxs-lookup"><span data-stu-id="44cfc-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="44cfc-118">可选单击 "**说明**", 然后为分支网站键入有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="44cfc-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="44cfc-119">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="44cfc-119">Click **Next**.</span></span>

6.  <span data-ttu-id="44cfc-120">可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:</span><span class="sxs-lookup"><span data-stu-id="44cfc-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="44cfc-121">单击 "**城市**", 然后键入分支站点所在城市的名称。</span><span class="sxs-lookup"><span data-stu-id="44cfc-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="44cfc-122">单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="44cfc-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="44cfc-123">单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="44cfc-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="44cfc-124">单击 "**下一步**", 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="44cfc-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="44cfc-125">如果您在此站点使用 Lync 2010 Survivable 分支设备或服务器, 请务必取消选中 "**关闭此向导时打开新 Survivable 向导**" 选项。</span><span class="sxs-lookup"><span data-stu-id="44cfc-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="44cfc-126">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="44cfc-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="44cfc-127">要将旧版 Lync Server 2010 SBA 关联到 Lync Server 2013 前端池, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="44cfc-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="44cfc-128">展开已创建的分支站点。</span><span class="sxs-lookup"><span data-stu-id="44cfc-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="44cfc-129">右键单击 " **Lync Server 2010** ", 然后单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="44cfc-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="44cfc-130">单击 " **Survivable 分支装置 ...** "</span><span class="sxs-lookup"><span data-stu-id="44cfc-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="44cfc-131">按照向导中打开的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="44cfc-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="44cfc-132">有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="44cfc-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44cfc-133">Lync Server 2010 Survivable 分支设备只能与 Lync Server 2010 Monitoring Store 相关联。</span><span class="sxs-lookup"><span data-stu-id="44cfc-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="44cfc-134">如果未在此网站使用 Survivable 分支装置或服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="44cfc-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="44cfc-135">对要添加到拓扑中的每个分支网站重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="44cfc-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

