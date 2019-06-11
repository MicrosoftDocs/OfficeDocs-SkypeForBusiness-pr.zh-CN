---
title: 'Lync Server 2013: 创建或修改网络子网'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="dc9de-102">在 Lync Server 2013 中创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="dc9de-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc9de-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dc9de-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dc9de-104">为了确定属于该子网的主机的地理位置, 网络子网必须与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="dc9de-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="dc9de-105">可以使用 Lync Server "控制面板" 配置子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="dc9de-106">从 Lync Server 控制面板中, 您可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="dc9de-107">有关删除网络子网的详细信息, 请参阅[在 Lync Server 2013 中删除网络子网](lync-server-2013-deleting-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9de-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="dc9de-108">在大多数部署呼叫许可控制 (CAC) 的 Microsoft Lync Server 2013 中, 通常会有大量子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="dc9de-109">因此, 通常最好从 Lync Server 命令行管理程序中配置子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="dc9de-110">从这里, 你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。</span><span class="sxs-lookup"><span data-stu-id="dc9de-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="dc9de-111">通过将这些 cmdlet 结合使用, 你可以从逗号分隔值 (.csv) 文件中读取子网设置, 并同时创建多个子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="dc9de-112">有关如何从 .csv 文件创建子网的示例, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="dc9de-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="dc9de-113">创建网络子网</span><span class="sxs-lookup"><span data-stu-id="dc9de-113">To create a network subnet</span></span>

1.  <span data-ttu-id="dc9de-114">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="dc9de-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc9de-115">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="dc9de-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc9de-116">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9de-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc9de-117">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="dc9de-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc9de-118">在 "**子网**" 页面上, 单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="dc9de-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="dc9de-119">在 "**新建子网**" 中, 在 "**子网 ID** " 字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="dc9de-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="dc9de-120">这必须是 IP 地址 (例如, 174.11.12.0), 并且它必须是子网定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="dc9de-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="dc9de-121">在 "**掩码**" 字段中, 输入从1到32的数字值。</span><span class="sxs-lookup"><span data-stu-id="dc9de-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc9de-122">此值是要应用到正在创建的子网的位掩码。</span><span class="sxs-lookup"><span data-stu-id="dc9de-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="dc9de-123">在 "**网络站点 ID**" 中, 选择此子网所属的站点。</span><span class="sxs-lookup"><span data-stu-id="dc9de-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="dc9de-124">可选在 "**说明**" 字段中键入一个值, 以提供有关无法单独以名称表示的该子网的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc9de-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="dc9de-125">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="dc9de-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="dc9de-126">修改网络子网</span><span class="sxs-lookup"><span data-stu-id="dc9de-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="dc9de-127">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="dc9de-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc9de-128">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="dc9de-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc9de-129">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9de-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc9de-130">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="dc9de-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc9de-131">在 "**子网**" 页面上, 单击要修改的子网。</span><span class="sxs-lookup"><span data-stu-id="dc9de-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="dc9de-132">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc9de-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="dc9de-133">在 "**编辑子网**" 页面上, 您可以修改位掩码、关联的网络站点或说明。</span><span class="sxs-lookup"><span data-stu-id="dc9de-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="dc9de-134">如果您修改了位掩码, 请记住子网 ID 必须仍然是子网定义的 IP 地址范围中的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="dc9de-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="dc9de-135">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="dc9de-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc9de-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc9de-136">See Also</span></span>


[<span data-ttu-id="dc9de-137">在 Lync Server 2013 中删除网络子网</span><span class="sxs-lookup"><span data-stu-id="dc9de-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="dc9de-138">关于 Lync Server 2013 中的网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="dc9de-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="dc9de-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc9de-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="dc9de-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc9de-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="dc9de-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc9de-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="dc9de-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc9de-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

