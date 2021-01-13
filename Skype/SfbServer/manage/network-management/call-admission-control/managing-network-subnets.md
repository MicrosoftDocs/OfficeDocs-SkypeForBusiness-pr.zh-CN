---
title: 管理网络子网
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。 因此，最好从 Skype for Business Server 命令行管理程序 配置子网。
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816392"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="5999f-104">在 Skype for Business Server 中管理网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="5999f-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 管理网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="5999f-106">在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5999f-107">因此，最好从 Skype for Business Server 命令行管理程序 配置子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="5999f-108">使用本文中的各节查看网络子网信息，或创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="5999f-109">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="5999f-109">View network subnet information</span></span> 

<span data-ttu-id="5999f-110">您可使用以下过程查看网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="5999f-111">在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="5999f-112">查看网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-112">To view a network subnet</span></span>

1.  <span data-ttu-id="5999f-113">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="5999f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5999f-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5999f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5999f-115">在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**</span><span class="sxs-lookup"><span data-stu-id="5999f-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5999f-116">在“子网”页上，单击要查看的子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5999f-117">一次只能查看一个子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="5999f-118">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="5999f-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5999f-119">使用 cmdlet 查看网络子网Windows PowerShell信息</span><span class="sxs-lookup"><span data-stu-id="5999f-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5999f-120">网络子网信息可通过使用 Windows PowerShell 和 Get-CsNetworkSubnet cmdlet 进行查看。</span><span class="sxs-lookup"><span data-stu-id="5999f-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5999f-121">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5999f-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="5999f-122">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="5999f-122">To view network subnet information</span></span>

  - <span data-ttu-id="5999f-123">若要查看有关所有网络子网的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="5999f-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="5999f-124">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="5999f-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="5999f-125">有关详细信息，请参阅 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5999f-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="5999f-126">创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-126">Create or modify network subnets</span></span> 

<span data-ttu-id="5999f-127">网络子网必须与一个网络站点关联，以便确定属于此子网的主机的地理位置。</span><span class="sxs-lookup"><span data-stu-id="5999f-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="5999f-128">可以使用 Skype for Business Server 控制面板配置子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="5999f-129">在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5999f-130">在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5999f-131">因此，最好从 Skype for Business Server 命令行管理程序 配置子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5999f-132">可以从中调用 **New-CsNetworkSubnet** 与 Windows PowerShell cmdlet **Import-CSV**。</span><span class="sxs-lookup"><span data-stu-id="5999f-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5999f-133">通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5999f-134">有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="5999f-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="5999f-135">创建网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-135">To create a network subnet</span></span>

1.  <span data-ttu-id="5999f-136">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="5999f-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5999f-137">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5999f-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5999f-138">在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**</span><span class="sxs-lookup"><span data-stu-id="5999f-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5999f-139">在“子网”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="5999f-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="5999f-p107">在“新建子网”的“子网 ID”字段中输入值。该值必须是一个 IP 地址（例如 174.11.12.0），并且必须是子网所定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="5999f-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="5999f-142">在“掩码”字段中，输入一个 1 到 32 之间的数值。</span><span class="sxs-lookup"><span data-stu-id="5999f-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="5999f-143">该值是要应用于正在创建的子网的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5999f-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="5999f-144">在“网络站点 ID”中，选择该子网归属的站点。</span><span class="sxs-lookup"><span data-stu-id="5999f-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="5999f-145">（可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该子网的信息。</span><span class="sxs-lookup"><span data-stu-id="5999f-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="5999f-146">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="5999f-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="5999f-147">修改网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="5999f-148">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="5999f-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5999f-149">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5999f-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5999f-150">在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**</span><span class="sxs-lookup"><span data-stu-id="5999f-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5999f-151">在“子网”页上，单击要修改的子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="5999f-152">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="5999f-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5999f-p108">在“编辑子网”页上，可以修改位掩码、关联的网络站点或说明。如果要修改位掩码，请牢记子网 ID 必须仍为子网所定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="5999f-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="5999f-155">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="5999f-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="5999f-156">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-156">Delete network subnets</span></span>

<span data-ttu-id="5999f-157">您可以使用以下过程删除子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="5999f-158">在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5999f-159">在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5999f-160">因此，最好从 Skype for Business Server 命令行管理程序 配置子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5999f-161">可以从中调用 **New-CsNetworkSubnet** 与 Windows PowerShell cmdlet **Import-CSV**。</span><span class="sxs-lookup"><span data-stu-id="5999f-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5999f-162">通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5999f-163">有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="5999f-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="5999f-164">删除网络子网</span><span class="sxs-lookup"><span data-stu-id="5999f-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="5999f-165">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="5999f-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5999f-166">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5999f-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5999f-167">在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**</span><span class="sxs-lookup"><span data-stu-id="5999f-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5999f-168">在“子网”页上，单击要删除的子网。</span><span class="sxs-lookup"><span data-stu-id="5999f-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5999f-p111">您可以一次删除多个子网。为执行此操作，请按住 CTRL 键，同时选择多个子网。或者，要选择所有子网，请单击“编辑”菜单上的“全选”。</span><span class="sxs-lookup"><span data-stu-id="5999f-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="5999f-172">在“编辑”菜单中，单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="5999f-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5999f-173">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="5999f-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="5999f-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5999f-174">See Also</span></span>

[<span data-ttu-id="5999f-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5999f-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="5999f-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5999f-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="5999f-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5999f-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="5999f-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5999f-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
