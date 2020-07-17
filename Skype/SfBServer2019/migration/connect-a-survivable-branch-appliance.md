---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 每个 Survivable 分支设备（SBA）都与一个前端池相关联，该前端池充当 SBA 的备份注册器。 当将前端池迁移到 Skype for business Server 2019 时，在升级池时，SBA 必须与前端池解除关联，一旦池迁移到 Skype for Business Server 2019，则 SBA 可以与升级后的前端池重新关联。 这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。 在从拓扑中删除 SBA 之前，必须首先将驻留在旧版 SBA 上的用户移到另一个前端池。 将 SBA 添加到 Skype for business Server 2019 拓扑后，这些用户即可移回 SBA。 这些步骤概括如下：
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751544"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="6da07-108">连接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6da07-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="6da07-109">每个 Survivable 分支设备（SBA）都与一个前端池相关联，该前端池充当 SBA 的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="6da07-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="6da07-110">将前端池迁移到 Skype for business Server 2019 时，在升级池时，SBA 必须与前端池解除关联。</span><span class="sxs-lookup"><span data-stu-id="6da07-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="6da07-111">将池迁移到 Skype for business Server 2019 后，可以将 SBA 重新关联到已升级的前端池。</span><span class="sxs-lookup"><span data-stu-id="6da07-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="6da07-112">这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。</span><span class="sxs-lookup"><span data-stu-id="6da07-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="6da07-113">在从拓扑中删除 SBA 之前，必须首先将驻留在旧版 SBA 上的用户移到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="6da07-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="6da07-114">将 SBA 添加到 Skype for business Server 2019 拓扑后，可以将这些用户移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="6da07-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="6da07-115">这些步骤概括如下：</span><span class="sxs-lookup"><span data-stu-id="6da07-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="6da07-116">将驻留在旧 SBA 上的分支用户移动到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="6da07-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="6da07-117">从旧版拓扑中删除 SBA，以将现有的前端池作为备份注册器断开连接。</span><span class="sxs-lookup"><span data-stu-id="6da07-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="6da07-118">将 SBA 添加到 Skype for business Server 2019 拓扑，并将此新的前端池配置为备份注册器。</span><span class="sxs-lookup"><span data-stu-id="6da07-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="6da07-119">将分支用户移动到新的 Skype for Business Server 2019 SBA。</span><span class="sxs-lookup"><span data-stu-id="6da07-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="6da07-120">将旧版 SBA 分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="6da07-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="6da07-121">打开“拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6da07-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="6da07-122">在左窗格中，右键单击 "**分支站点**"，然后单击 "**新建分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="6da07-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="6da07-123">在“定义新的分支站点”\*\*\*\* 对话框中，单击“名称”\*\*\*\*，然后键入分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="6da07-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="6da07-124">（可选）单击“说明”\*\*\*\*，然后为分支站点键入有一定含义的说明。</span><span class="sxs-lookup"><span data-stu-id="6da07-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="6da07-125">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6da07-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="6da07-126">（可选）在下一个“定义新的分支站点”\*\*\*\* 对话框中，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="6da07-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="6da07-127">单击“市/县”\*\*\*\*，然后键入分支站点所在的市/县的名称。</span><span class="sxs-lookup"><span data-stu-id="6da07-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="6da07-128">单击“国家/地区”\*\*\*\*，然后键入分支站点所在的国家或地区的名称。</span><span class="sxs-lookup"><span data-stu-id="6da07-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="6da07-129">单击“国家/地区代码”\*\*\*\*，然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="6da07-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="6da07-130">单击 "**下一步**"，然后，如果在此站点使用的是 Survivable 分支设备或服务器，请务必清除 "**关闭此向导时打开新 Survivable 向导**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6da07-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="6da07-131">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6da07-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="6da07-132">若要将旧版 SBA 与 Skype for business Server 2019 前端池相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6da07-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="6da07-133">展开已创建的分支站点。</span><span class="sxs-lookup"><span data-stu-id="6da07-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="6da07-134">右键单击旧版版本，然后单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="6da07-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="6da07-135">单击 " **Survivable 分支设备**"。</span><span class="sxs-lookup"><span data-stu-id="6da07-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="6da07-136">按照打开的向导中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="6da07-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="6da07-137">有关向导项的信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="6da07-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="6da07-138">Survivable 分支设备仅可与监控存储关联。</span><span class="sxs-lookup"><span data-stu-id="6da07-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="6da07-139">如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”\*\*\*\* 复选框，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6da07-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="6da07-140">对要添加到拓扑的每个分支站点重复之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="6da07-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

