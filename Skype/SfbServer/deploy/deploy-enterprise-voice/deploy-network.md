---
title: 在 Skype for Business 中部署网络区域、站点和子网
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 在 Skype for Business Server 中创建或修改网络区域、网络站点以及关联网络子网。 所有这些功能都用于高级企业语音功能：媒体旁路、呼叫允许控制和基于位置的路由。
ms.openlocfilehash: adfcf418fd2b1ef607947687afb766fee6b64715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103518"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="ad31d-104">在 Skype for Business 中部署网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="ad31d-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="ad31d-105">在 Skype for Business Server 中创建或修改网络区域、网络站点以及关联网络子网。</span><span class="sxs-lookup"><span data-stu-id="ad31d-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="ad31d-106">所有这些功能都用于高级企业语音功能：媒体旁路、呼叫允许控制和基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="ad31d-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="ad31d-107">高级企业语音包括[呼叫](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)允许控制、[媒体旁](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)路、基于位置的[路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)和[E9-1-1。](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)</span><span class="sxs-lookup"><span data-stu-id="ad31d-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="ad31d-108">这些功能都要求创建网络区域、网络站点和子网。</span><span class="sxs-lookup"><span data-stu-id="ad31d-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="ad31d-109">例如，所有这些功能都要求拓扑中的每个子网与特定网络站点关联，并且每个网络站点必须与一个网络区域关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="ad31d-110">有关这些条款详细信息，请参阅 Network [settings for the advanced 企业语音 features in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="ad31d-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="ad31d-111">呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：</span><span class="sxs-lookup"><span data-stu-id="ad31d-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="ad31d-112">呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="ad31d-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="ad31d-113">如果计划部署呼叫允许控制，则必须在 [Skype for Business Server](create-bandwidth-policy-profiles.md) 中创建带宽策略配置文件，然后才能配置网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="ad31d-114">E9-1-1 要求为每个站点指定位置策略。</span><span class="sxs-lookup"><span data-stu-id="ad31d-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="ad31d-115">如果计划部署 E9-1-1，则必须在 [Skype for Business Server](create-location-policies.md) 中创建位置策略，然后才能配置网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="ad31d-116">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="ad31d-116">Create or modify a Network Region</span></span>

<span data-ttu-id="ad31d-117">如果已经为这些功能之一创建了网络区域，则无需创建新的网络区域;其他高级企业语音功能将使用相同的网络区域。</span><span class="sxs-lookup"><span data-stu-id="ad31d-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="ad31d-118">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="ad31d-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ad31d-119">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ad31d-120">使用 Skype for Business Server 命令行管理程序创建网络区域</span><span class="sxs-lookup"><span data-stu-id="ad31d-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ad31d-121">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ad31d-122">运行 New-CsNetworkRegion cmdlet 创建网络区域：</span><span class="sxs-lookup"><span data-stu-id="ad31d-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="ad31d-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ad31d-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="ad31d-124">此示例创建了一个称为"NorthAmerica"的网络区域，该区域与站点 ID 为 CHICAGO 的中央站点相关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="ad31d-125">要为拓扑完成网络区域的创建，请使用每个网络区域的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ad31d-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ad31d-126">使用 Skype for Business Server 控制面板创建网络区域</span><span class="sxs-lookup"><span data-stu-id="ad31d-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ad31d-127">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad31d-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ad31d-128">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ad31d-129">单击“区域”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-129">Click **Region**.</span></span>

4. <span data-ttu-id="ad31d-130">单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-130">Click **New**.</span></span>

5. <span data-ttu-id="ad31d-131">在“新建区域”页上，单击“名称”，然后键入网络区域的名称。</span><span class="sxs-lookup"><span data-stu-id="ad31d-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="ad31d-132">单击“中央站点”，然后单击列表中的某个中央站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="ad31d-133">或者，单击“说明”，然后键入其他信息以描述此网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="ad31d-134">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-134">Click **Commit**.</span></span>

9. <span data-ttu-id="ad31d-135">要为拓扑完成网络区域的创建，请使用其他区域的设置重复步骤 4 至 8。</span><span class="sxs-lookup"><span data-stu-id="ad31d-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ad31d-136">使用 Skype for Business Server 命令行管理程序修改网络区域</span><span class="sxs-lookup"><span data-stu-id="ad31d-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ad31d-137">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ad31d-138">运行 Set-CsNetworkRegion cmdlet 修改现有网络区域：</span><span class="sxs-lookup"><span data-stu-id="ad31d-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="ad31d-139">例如：</span><span class="sxs-lookup"><span data-stu-id="ad31d-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="ad31d-140">本示例通过更改说明修改了 ("NorthAmerica"的现有网络区域) 创建。</span><span class="sxs-lookup"><span data-stu-id="ad31d-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="ad31d-141">如果"NorthAmerica"区域存在说明，此命令会用此值覆盖它;如果尚未设置说明，则此命令将设置它。</span><span class="sxs-lookup"><span data-stu-id="ad31d-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="ad31d-142">要修改其他网络区域，请使用其他区域的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ad31d-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ad31d-143">使用 Skype for Business Server 控制面板修改网络区域</span><span class="sxs-lookup"><span data-stu-id="ad31d-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ad31d-144">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad31d-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ad31d-145">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ad31d-146">单击“区域”导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ad31d-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="ad31d-147">在表中，单击要修改的网络区域。</span><span class="sxs-lookup"><span data-stu-id="ad31d-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="ad31d-148">单击“编辑”，然后单击“显示详细信息...”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="ad31d-149">在 **"编辑区域** "页上，根据情况更改此网络区域设置的值。</span><span class="sxs-lookup"><span data-stu-id="ad31d-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="ad31d-150">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-150">Click **Commit**.</span></span>

8. <span data-ttu-id="ad31d-151">要完成网络区域的修改，请使用其他区域的设置重复步骤 4 至 7。</span><span class="sxs-lookup"><span data-stu-id="ad31d-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="ad31d-152">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="ad31d-152">Create or modify a network site</span></span>

<span data-ttu-id="ad31d-153">如果已经为这些功能之一创建了网络站点，则无需创建新的网络站点;其他高级企业语音功能将使用相同的网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="ad31d-154">但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="ad31d-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="ad31d-155">例如，如果已为 E9-1-1 创建网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="ad31d-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ad31d-156">使用 Skype for Business Server 命令行管理程序创建网络站点</span><span class="sxs-lookup"><span data-stu-id="ad31d-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ad31d-157">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ad31d-158">运行 New-CsNetworkSite cmdlet 创建网络站点：</span><span class="sxs-lookup"><span data-stu-id="ad31d-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="ad31d-159">例如：</span><span class="sxs-lookup"><span data-stu-id="ad31d-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="ad31d-160">本示例中，您创建了一个称为"Chicago"的网络站点，该站点位于"NorthAmerica"网络区域。</span><span class="sxs-lookup"><span data-stu-id="ad31d-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad31d-161">为了成功运行此命令，NorthAmerica 网络区域必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="ad31d-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="ad31d-162">要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ad31d-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ad31d-163">使用 Skype for Business Server 控制面板创建网络站点</span><span class="sxs-lookup"><span data-stu-id="ad31d-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ad31d-164">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad31d-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ad31d-165">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ad31d-166">单击“站点”导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ad31d-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="ad31d-167">单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-167">Click **New**.</span></span>

5. <span data-ttu-id="ad31d-168">在“新建站点”页上，单击“名称”，然后键入网络站点的名称。</span><span class="sxs-lookup"><span data-stu-id="ad31d-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="ad31d-169">单击“区域”，然后单击列表中的某个区域。</span><span class="sxs-lookup"><span data-stu-id="ad31d-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="ad31d-170">或者，单击“带宽策略”，然后单击列表中的某个带宽策略。</span><span class="sxs-lookup"><span data-stu-id="ad31d-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad31d-171">只有在站点上部署呼叫允许控制时才需要带宽策略。</span><span class="sxs-lookup"><span data-stu-id="ad31d-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="ad31d-172">或者，单击“位置策略”，然后单击列表中的某个位置策略。</span><span class="sxs-lookup"><span data-stu-id="ad31d-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad31d-173">只有在站点上部署 E9-1-1 时才需要位置策略。</span><span class="sxs-lookup"><span data-stu-id="ad31d-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="ad31d-174">或者，单击“说明”，然后键入其他信息以描述此网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="ad31d-175">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-175">Click **Commit**.</span></span>

11. <span data-ttu-id="ad31d-176">要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。</span><span class="sxs-lookup"><span data-stu-id="ad31d-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ad31d-177">使用 Skype for Business Server 命令行管理程序修改网络站点</span><span class="sxs-lookup"><span data-stu-id="ad31d-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ad31d-178">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ad31d-179">运行 Set-CsNetworkSite cmdlet 修改网络站点：</span><span class="sxs-lookup"><span data-stu-id="ad31d-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="ad31d-180">例如：</span><span class="sxs-lookup"><span data-stu-id="ad31d-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="ad31d-181">此示例中，名为"Albuquerque"的站点将移动到"NorthAmerica"网络区域。</span><span class="sxs-lookup"><span data-stu-id="ad31d-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="ad31d-182">要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。</span><span class="sxs-lookup"><span data-stu-id="ad31d-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad31d-p110">尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="ad31d-185">要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ad31d-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ad31d-186">使用 Skype for Business Server 控制面板修改网络站点</span><span class="sxs-lookup"><span data-stu-id="ad31d-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ad31d-187">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad31d-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ad31d-188">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ad31d-189">单击“站点”导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ad31d-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="ad31d-190">在表中，单击要修改的网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="ad31d-191">单击“编辑”，然后单击“显示详细信息...”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="ad31d-192">在 **"编辑站点** "页上，根据情况更改此网络站点的设置的值。</span><span class="sxs-lookup"><span data-stu-id="ad31d-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="ad31d-193">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-193">Click **Commit**.</span></span>

8. <span data-ttu-id="ad31d-194">要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。</span><span class="sxs-lookup"><span data-stu-id="ad31d-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="ad31d-195">将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="ad31d-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="ad31d-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="ad31d-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="ad31d-197">网络内每个子网都必须与特定网络站点关联，因为子网信息用于确定启动新会话时终结点所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="ad31d-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="ad31d-198">当会话每一方的位置已知时，高级企业语音功能可以应用该信息来确定如何处理呼叫设置或路由。</span><span class="sxs-lookup"><span data-stu-id="ad31d-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="ad31d-199">必须将部署中音频/视频边缘服务器的所有已配置公共 IP 地址添加到网络配置设置中。</span><span class="sxs-lookup"><span data-stu-id="ad31d-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="ad31d-200">这些 IP 地址是作为掩码为 32 的子网进行添加的。</span><span class="sxs-lookup"><span data-stu-id="ad31d-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="ad31d-201">关联的网络站点应与相应的已配置网络站点相对应。</span><span class="sxs-lookup"><span data-stu-id="ad31d-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="ad31d-202">例如，与中央站点芝加哥的 A/V 边缘服务对应的公用 IP 地址是 NetworkSiteID Chicago。</span><span class="sxs-lookup"><span data-stu-id="ad31d-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ad31d-203">使用 Skype for Business Server 命令行管理程序将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="ad31d-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ad31d-204">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ad31d-205">运行 **New-CsNetworkSubnet** cmdlet 将子网与网络站点相关联：</span><span class="sxs-lookup"><span data-stu-id="ad31d-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="ad31d-206">例如：</span><span class="sxs-lookup"><span data-stu-id="ad31d-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="ad31d-207">此示例在子网 172.11.12.13 和网络站点"Chicago"之间创建了关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="ad31d-208">为拓扑中的所有子网重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ad31d-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="ad31d-209">通过导入 CSV 文件将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="ad31d-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="ad31d-p113">创建包含要添加的所有子网的 CSV 文件。例如，创建名为 **subnet.csv** 并包含以下内容的文件：</span><span class="sxs-lookup"><span data-stu-id="ad31d-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="ad31d-212">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="ad31d-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="ad31d-213">运行以下 cmdlet 以导入 **subnet.csv，然后将** 其内容存储在 Lync Server 管理存储中：</span><span class="sxs-lookup"><span data-stu-id="ad31d-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ad31d-214">使用 Skype for Business Server 控制面板将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="ad31d-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ad31d-215">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad31d-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ad31d-216">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ad31d-217">单击“子网”导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ad31d-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="ad31d-218">单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-218">Click **New**.</span></span>

5. <span data-ttu-id="ad31d-219">在“新建子网”页上，单击“子网 ID”，然后键入由要与网络站点关联的子网定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="ad31d-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="ad31d-220">单击“掩码”，然后键入要应用于子网的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ad31d-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="ad31d-221">单击“网络站点 ID”，然后选择要向其中添加此子网的站点的站点 ID。</span><span class="sxs-lookup"><span data-stu-id="ad31d-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad31d-222">如果尚未创建网络站点，该列表将为空。</span><span class="sxs-lookup"><span data-stu-id="ad31d-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="ad31d-223">有关过程的详细信息，请参阅[Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="ad31d-223">For details about the procedure, see [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site).</span></span> <span data-ttu-id="ad31d-224">还可以通过运行 **Get-CsNetworkSite** cmdlet 检索部署的站点 ID。</span><span class="sxs-lookup"><span data-stu-id="ad31d-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="ad31d-225">有关详细信息，请参阅 Skype for Business Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="ad31d-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="ad31d-226">（可选）单击“说明”，然后键入其他信息来说明此子网。</span><span class="sxs-lookup"><span data-stu-id="ad31d-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="ad31d-227">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="ad31d-227">Click **Commit**.</span></span>

<span data-ttu-id="ad31d-228">重复这些步骤以向网络站点中添加其他子网。</span><span class="sxs-lookup"><span data-stu-id="ad31d-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="ad31d-229">生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="ad31d-230">该警报在 8 小时内只产生一次。</span><span class="sxs-lookup"><span data-stu-id="ad31d-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="ad31d-231">相关的警报信息和示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad31d-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="ad31d-232">**源**：CS 带宽策略服务（核心）</span><span class="sxs-lookup"><span data-stu-id="ad31d-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="ad31d-233">**事件数**：36034</span><span class="sxs-lookup"><span data-stu-id="ad31d-233">**Event number**: 36034</span></span>

 <span data-ttu-id="ad31d-234">**级别**：2</span><span class="sxs-lookup"><span data-stu-id="ad31d-234">**Level**: 2</span></span>

 <span data-ttu-id="ad31d-235">**说明**：未配置以下 IP 地址的子网，或者 \<List of IP Addresses\> 子网未与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="ad31d-236">**原因**：网络配置设置中缺少相应 IP 地址的子网，或子网未与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="ad31d-237">**解决方案**：将与 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网与一个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="ad31d-p116">例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：</span><span class="sxs-lookup"><span data-stu-id="ad31d-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="ad31d-240">确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 相关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 相关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="ad31d-241">确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="ad31d-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad31d-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad31d-242">See also</span></span>
<span data-ttu-id="ad31d-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="ad31d-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="ad31d-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ad31d-244">New-CsNetworkRegion</span></span>](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ad31d-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ad31d-245">Get-CsNetworkRegion</span></span>](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ad31d-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ad31d-246">Set-CsNetworkRegion</span></span>](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ad31d-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ad31d-247">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ad31d-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ad31d-248">New-CsNetworkSubnet</span></span>](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ad31d-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ad31d-249">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ad31d-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ad31d-250">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ad31d-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ad31d-251">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)