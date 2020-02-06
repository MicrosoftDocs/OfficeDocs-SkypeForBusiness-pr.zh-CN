---
title: 管理网络子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在大多数部署呼叫许可控制（CAC）的 Skype for business 服务器中，通常会有大量子网。 因此，通常最好从 Skype for Business Server 命令行管理程序配置子网。
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817461"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="e3c05-104">在 Skype for Business Server 中管理网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="e3c05-105">你可以使用 Skype for Business 服务器控制面板或 Skype for Business Server Management Shell 管理网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="e3c05-106">在大多数部署呼叫许可控制（CAC）的 Skype for business 服务器中，通常会有大量子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="e3c05-107">因此，通常最好从 Skype for Business Server 命令行管理程序配置子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="e3c05-108">使用本文中的部分可查看网络子网信息或创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="e3c05-109">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="e3c05-109">View network subnet information</span></span> 

<span data-ttu-id="e3c05-110">你可以使用以下过程查看网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="e3c05-111">在 "Skype for Business 服务器" 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="e3c05-112">查看网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-112">To view a network subnet</span></span>

1.  <span data-ttu-id="e3c05-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3c05-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3c05-114">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3c05-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e3c05-115">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3c05-116">在 "**子网**" 页面上，单击要查看的子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="e3c05-117">一次只能查看一个子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="e3c05-118">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3c05-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e3c05-119">使用 Windows PowerShell cmdlet 查看网络子网配置信息</span><span class="sxs-lookup"><span data-stu-id="e3c05-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e3c05-120">可使用 Windows PowerShell 和 CsNetworkSubnet cmdlet 查看网络子网信息。</span><span class="sxs-lookup"><span data-stu-id="e3c05-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="e3c05-121">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="e3c05-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="e3c05-122">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="e3c05-122">To view network subnet information</span></span>

  - <span data-ttu-id="e3c05-123">若要查看有关所有网络子网的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e3c05-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="e3c05-124">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="e3c05-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="e3c05-125">有关详细信息，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e3c05-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="e3c05-126">创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-126">Create or modify network subnets</span></span> 

<span data-ttu-id="e3c05-127">为了确定属于该子网的主机的地理位置，网络子网必须与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="e3c05-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="e3c05-128">您可以使用 Skype for Business 服务器控制面板配置子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="e3c05-129">在 "Skype for Business 服务器" 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="e3c05-130">在大多数部署呼叫许可控制（CAC）的 Skype for business 服务器中，通常会有大量子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="e3c05-131">因此，通常最好从 Skype for Business Server 命令行管理程序配置子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e3c05-132">从这里，你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。</span><span class="sxs-lookup"><span data-stu-id="e3c05-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="e3c05-133">通过将这些 cmdlet 结合使用，你可以从逗号分隔值（.csv）文件中读取子网设置，并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="e3c05-134">有关如何从 .csv 文件创建子网的示例，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="e3c05-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="e3c05-135">创建网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-135">To create a network subnet</span></span>

1.  <span data-ttu-id="e3c05-136">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3c05-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3c05-137">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3c05-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e3c05-138">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3c05-139">在 "**子网**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="e3c05-140">在 "**新建子网**" 中，在 "**子网 ID** " 字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="e3c05-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="e3c05-141">这必须是 IP 地址（例如，174.11.12.0），并且它必须是子网定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="e3c05-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="e3c05-142">在 "**掩码**" 字段中，输入从1到32的数字值。</span><span class="sxs-lookup"><span data-stu-id="e3c05-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e3c05-143">此值是要应用到正在创建的子网的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e3c05-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="e3c05-144">在 "**网络站点 ID**" 中，选择此子网所属的站点。</span><span class="sxs-lookup"><span data-stu-id="e3c05-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="e3c05-145">可选在 "**说明**" 字段中键入一个值，以提供有关无法单独以名称表示的该子网的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e3c05-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="e3c05-146">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e3c05-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="e3c05-147">修改网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="e3c05-148">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3c05-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3c05-149">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3c05-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e3c05-150">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3c05-151">在 "**子网**" 页面上，单击要修改的子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="e3c05-152">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3c05-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e3c05-153">在 "**编辑子网**" 页面上，您可以修改位掩码、关联的网络站点或说明。</span><span class="sxs-lookup"><span data-stu-id="e3c05-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="e3c05-154">如果您修改了位掩码，请记住子网 ID 必须仍然是子网定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="e3c05-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="e3c05-155">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e3c05-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="e3c05-156">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-156">Delete network subnets</span></span>

<span data-ttu-id="e3c05-157">可以使用以下过程删除子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="e3c05-158">在 "Skype for Business 服务器" 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="e3c05-159">在大多数部署呼叫许可控制（CAC）的 Skype for business 服务器中，通常会有大量子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="e3c05-160">因此，通常最好从 Skype for Business Server 命令行管理程序配置子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e3c05-161">从这里，你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。</span><span class="sxs-lookup"><span data-stu-id="e3c05-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="e3c05-162">通过将这些 cmdlet 结合使用，你可以从逗号分隔值（.csv）文件中读取子网设置，并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="e3c05-163">有关如何从 .csv 文件创建子网的示例，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="e3c05-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="e3c05-164">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="e3c05-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="e3c05-165">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3c05-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3c05-166">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3c05-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e3c05-167">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3c05-168">在 "**子网**" 页面上，单击要删除的子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="e3c05-169">您可以一次删除多个子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="e3c05-170">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个子网。</span><span class="sxs-lookup"><span data-stu-id="e3c05-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="e3c05-171">或者，若要选择所有子网，请单击 "**编辑**" 菜单上的 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="e3c05-172">在 "**编辑**" 菜单上，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e3c05-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e3c05-173">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e3c05-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="e3c05-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3c05-174">See Also</span></span>

[<span data-ttu-id="e3c05-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3c05-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="e3c05-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3c05-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="e3c05-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3c05-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="e3c05-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3c05-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
