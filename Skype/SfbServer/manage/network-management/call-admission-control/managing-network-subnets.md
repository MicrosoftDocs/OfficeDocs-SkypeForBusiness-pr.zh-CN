---
title: 管理网络子网
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。 因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198906"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="44494-104">在 Skype for Business Server 中管理网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="44494-105">您可用于任一 Skype 业务 Server Control Panel 或业务 Server 命令行管理程序 Skype 管理网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="44494-106">在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="44494-107">因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="44494-108">使用本文中的部分以查看网络子网信息或创建、 修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="44494-109">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="44494-109">View network subnet information</span></span> 

<span data-ttu-id="44494-110">您可以使用以下过程以查看网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="44494-111">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="44494-112">若要查看网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-112">To view a network subnet</span></span>

1.  <span data-ttu-id="44494-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="44494-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44494-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="44494-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="44494-115">在左侧的导航栏中，单击**网络配置**，然后单击**子网**。</span><span class="sxs-lookup"><span data-stu-id="44494-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="44494-116">在**子网**页上，单击您想要查看的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="44494-117">一次只能查看一个子网。</span><span class="sxs-lookup"><span data-stu-id="44494-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="44494-118">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44494-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="44494-119">通过使用 Windows PowerShell cmdlet 查看网络子网配置信息</span><span class="sxs-lookup"><span data-stu-id="44494-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="44494-120">可以使用 Windows PowerShell 和 Get-csnetworksubnet cmdlet 查看网络子网信息。</span><span class="sxs-lookup"><span data-stu-id="44494-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="44494-121">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44494-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="44494-122">若要查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="44494-122">To view network subnet information</span></span>

  - <span data-ttu-id="44494-123">若要查看有关所有网络子网的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="44494-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="44494-124">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="44494-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="44494-125">有关详细信息，请参阅[Get-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="44494-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="44494-126">创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-126">Create or modify network subnets</span></span> 

<span data-ttu-id="44494-127">为了确定属于此子网的主机的地理位置，必须与一个网络站点相关联网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="44494-128">您可以使用业务 Server Control Panel 的 Skype 配置子网。</span><span class="sxs-lookup"><span data-stu-id="44494-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="44494-129">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="44494-130">在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="44494-131">因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="44494-132">从中可以结合使用 Windows PowerShell cmdlet**导入 CSV**调用**New-csnetworksubnet** 。</span><span class="sxs-lookup"><span data-stu-id="44494-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="44494-133">通过一起使用这些 cmdlet，您可以阅读以逗号分隔值 (.csv) 文件中的子网设置，并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="44494-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="44494-134">有关如何从.csv 文件创建子网的示例，请参阅[New-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="44494-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="44494-135">创建网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-135">To create a network subnet</span></span>

1.  <span data-ttu-id="44494-136">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="44494-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44494-137">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="44494-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="44494-138">在左侧的导航栏中，单击**网络配置**，然后单击**子网**。</span><span class="sxs-lookup"><span data-stu-id="44494-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="44494-139">在**子网**页上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="44494-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="44494-140">在**新的子网**，输入**子网 ID**字段中的值。</span><span class="sxs-lookup"><span data-stu-id="44494-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="44494-141">这必须是 IP 地址 (例如，174.11.12.0)，并且必须由子网 IP 地址范围内的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="44494-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="44494-142">在**掩码**字段中，输入一个数值 1 到 32 之间。</span><span class="sxs-lookup"><span data-stu-id="44494-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="44494-143">此值为要应用于正在创建的子网的位掩码。</span><span class="sxs-lookup"><span data-stu-id="44494-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="44494-144">在**网络站点 ID**框中，选择该子网归属的站点。</span><span class="sxs-lookup"><span data-stu-id="44494-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="44494-145">（可选）在**说明**字段，以提供有关通过名称本身不能表示此子网的详细信息，请键入一个值。</span><span class="sxs-lookup"><span data-stu-id="44494-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="44494-146">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="44494-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="44494-147">修改网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="44494-148">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="44494-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44494-149">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="44494-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="44494-150">在左侧的导航栏中，单击**网络配置**，然后单击**子网**。</span><span class="sxs-lookup"><span data-stu-id="44494-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="44494-151">在**子网**页上，单击要修改的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="44494-152">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44494-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="44494-153">在**编辑子网**页上，您可以修改的位掩码，关联的网络站点或说明。</span><span class="sxs-lookup"><span data-stu-id="44494-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="44494-154">如果您修改的位掩码，请记住，子网 ID 仍必须定义的子网 IP 地址范围内的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="44494-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="44494-155">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="44494-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="44494-156">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-156">Delete network subnets</span></span>

<span data-ttu-id="44494-157">可以使用以下过程可删除子网。</span><span class="sxs-lookup"><span data-stu-id="44494-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="44494-158">从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="44494-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="44494-159">在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="44494-160">因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="44494-161">从中可以结合使用 Windows PowerShell cmdlet**导入 CSV**调用**New-csnetworksubnet** 。</span><span class="sxs-lookup"><span data-stu-id="44494-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="44494-162">通过一起使用这些 cmdlet，您可以阅读以逗号分隔值 (.csv) 文件中的子网设置，并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="44494-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="44494-163">有关如何从.csv 文件创建子网的示例，请参阅[New-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="44494-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="44494-164">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="44494-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="44494-165">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="44494-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44494-166">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="44494-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="44494-167">在左侧的导航栏中，单击**网络配置**，然后单击**子网**。</span><span class="sxs-lookup"><span data-stu-id="44494-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="44494-168">在**子网**页上，单击要删除的子网。</span><span class="sxs-lookup"><span data-stu-id="44494-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="44494-169">您可以一次删除多个子网。</span><span class="sxs-lookup"><span data-stu-id="44494-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="44494-170">若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个子网。</span><span class="sxs-lookup"><span data-stu-id="44494-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="44494-171">或者，若要选择的所有子网，请**选择全部**上单击**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="44494-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="44494-172">在**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="44494-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="44494-173">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="44494-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="44494-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44494-174">See Also</span></span>

[<span data-ttu-id="44494-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="44494-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="44494-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="44494-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="44494-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="44494-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="44494-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="44494-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
