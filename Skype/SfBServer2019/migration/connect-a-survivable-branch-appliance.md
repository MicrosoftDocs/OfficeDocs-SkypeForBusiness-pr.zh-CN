---
title: 连接 Survivable Branch Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 每个 Survivable Branch Appliance (SBA) 与作为备份注册器 sba 关联的前端池相关联。 Sba 关联时升级池，一旦池已迁移至 Skype 的业务服务器 2019年同时必须从前端池解除关联前端池的业务服务器 2019，SBA 迁移到 Skype，可与已升级的前端 E 重新关联和池。 此步骤需要从拓扑生成器中将旧拓扑删除 sba 关联，然后将 SBA 添加到业务服务器 2019年拓扑的 Skype。 用户驻留在 SBA 必须首先将移动到另一个前端池的拓扑删除 sba 关联之前的传统上。 一旦 SBA 添加到业务服务器 2019年拓扑的 Skype，这些用户可以然后移回 sba。 这些步骤概括如下：
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373747"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="676be-108">连接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="676be-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="676be-109">每个 Survivable Branch Appliance (SBA) 与作为备份注册器 sba 关联的前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="676be-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="676be-110">时的前端池迁移到 Skype 的业务服务器 2019年，SBA 必须是解除关联的前端池升级池时。</span><span class="sxs-lookup"><span data-stu-id="676be-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="676be-111">池已迁移至 Skype 的业务服务器 2019年后，SBA 可重新与已升级的前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="676be-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="676be-112">此步骤需要从拓扑生成器中将旧拓扑删除 sba 关联，然后将 SBA 添加到业务服务器 2019年拓扑的 Skype。</span><span class="sxs-lookup"><span data-stu-id="676be-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="676be-113">用户驻留在 SBA 必须首先将移动到另一个前端池的拓扑删除 sba 关联之前的传统上。</span><span class="sxs-lookup"><span data-stu-id="676be-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="676be-114">SBA 添加到业务服务器 2019年拓扑的 Skype 后，这些用户可以移回 sba。</span><span class="sxs-lookup"><span data-stu-id="676be-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="676be-115">这些步骤概括如下：</span><span class="sxs-lookup"><span data-stu-id="676be-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="676be-116">将分支用户驻留在旧 sba 关联到另一个前端池上移动。</span><span class="sxs-lookup"><span data-stu-id="676be-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="676be-117">从要断开作为备份注册器的现有前端池将旧拓扑删除 SBA。</span><span class="sxs-lookup"><span data-stu-id="676be-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="676be-118">将 SBA 添加到业务服务器 2019年拓扑的 Skype 并作为备份注册器配置此新前端池。</span><span class="sxs-lookup"><span data-stu-id="676be-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="676be-119">为业务服务器 2019 SBA 将分支用户移动到新的 Skype。</span><span class="sxs-lookup"><span data-stu-id="676be-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="676be-120">将旧 SBA 分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="676be-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="676be-121">打开**拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="676be-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="676be-122">在左窗格中，右键单击**分支站点**，然后单击**新的分支站点**。</span><span class="sxs-lookup"><span data-stu-id="676be-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="676be-123">在**定义新的分支站点**对话框中，单击**名称**框中，然后键入分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="676be-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="676be-124">（可选）单击**说明**，然后键入分支站点的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="676be-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="676be-125">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="676be-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="676be-126">（可选）在下的**定义新的分支站点**对话框中，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="676be-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="676be-127">单击**市/县**，，然后键入分支站点所在的市/县的名称。</span><span class="sxs-lookup"><span data-stu-id="676be-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="676be-128">单击**国家/地区**，然后键入状态或分支站点所在的地区的名称。</span><span class="sxs-lookup"><span data-stu-id="676be-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="676be-129">单击**国家/地区代码**，然后键入分支站点所在的国家/地区的两位数呼叫代码。</span><span class="sxs-lookup"><span data-stu-id="676be-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="676be-130">单击**下一步**，，然后，如果在该站点上使用 Survivable Branch Appliance or Server，请确保清除**打开新建 Survivable 向导此向导关闭时**复选框。</span><span class="sxs-lookup"><span data-stu-id="676be-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="676be-131">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="676be-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="676be-132">将旧 sba 关联到业务 Server 2019 前端池的 Skype 关联起来：</span><span class="sxs-lookup"><span data-stu-id="676be-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="676be-133">展开已创建的分支站点。</span><span class="sxs-lookup"><span data-stu-id="676be-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="676be-134">在旧版本上，右键单击，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="676be-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="676be-135">单击**Survivable Branch Appliance**。</span><span class="sxs-lookup"><span data-stu-id="676be-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="676be-136">按照在打开的向导中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="676be-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="676be-137">有关向导项目的信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="676be-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="676be-138">Survivable Branch Appliance 仅可与监控存储相关联。</span><span class="sxs-lookup"><span data-stu-id="676be-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="676be-139">如果没有在该站点上使用 Survivable Branch Appliance or Server，清除**打开新建 Survivable 向导此向导关闭时**复选框，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="676be-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="676be-140">对于要向拓扑中添加每个分支站点重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="676be-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

