---
title: Lync Server 2013：创建或修改网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67d4fedf5931a85772e42a87fb80c382a364ae96
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="cd6db-102">在 Lync Server 2013 中创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="cd6db-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd6db-103">_**上次修改的主题：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="cd6db-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="cd6db-104">网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="cd6db-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="cd6db-105">您可以使用 Microsoft Lync Server 2013 控制面板配置网站并将其与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="cd6db-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="cd6db-106">例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="cd6db-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="cd6db-107">必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。</span><span class="sxs-lookup"><span data-stu-id="cd6db-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="cd6db-108">在 Lync Server 控制面板中，您可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="cd6db-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="cd6db-109">使用下面的过程可创建或修改网络站点。</span><span class="sxs-lookup"><span data-stu-id="cd6db-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="cd6db-110">有关删除现有网络站点的详细信息，请参阅[在 Lync Server 2013 中删除现有网络站点](lync-server-2013-deleting-an-existing-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="cd6db-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="cd6db-111">创建网络站点</span><span class="sxs-lookup"><span data-stu-id="cd6db-111">To create a network site</span></span>

1.  <span data-ttu-id="cd6db-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cd6db-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd6db-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd6db-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd6db-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="cd6db-116">在“站点”\*\*\*\* 页上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="cd6db-117">在“新建站点”\*\*\*\* 的“名称”\*\*\*\* 字段中，键入此站点的名称。</span><span class="sxs-lookup"><span data-stu-id="cd6db-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd6db-118">站点名称在 Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cd6db-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="cd6db-119">在“区域”\*\*\*\* 下拉列表中，选择与此站点关联的网络区域。</span><span class="sxs-lookup"><span data-stu-id="cd6db-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="cd6db-120">（可选）如果要对此站点的音频或视频呼叫设置带宽限制，请从“带宽策略”\*\*\*\* 下拉列表中选择具有相应设置的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="cd6db-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd6db-121">在“网络配置”<STRONG></STRONG>组的“策略配置文件”<STRONG></STRONG>页上，可以查看可用带宽策略配置文件的详细信息，或创建新的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="cd6db-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="cd6db-122">有关详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中创建或修改带宽策略配置文件</A>。</span><span class="sxs-lookup"><span data-stu-id="cd6db-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="cd6db-123">（可选）如果要为此站点提供位置设置，请从“位置策略”\*\*\*\* 下拉列表中选择位置策略。</span><span class="sxs-lookup"><span data-stu-id="cd6db-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd6db-124">位置策略会将特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置分配给站点。</span><span class="sxs-lookup"><span data-stu-id="cd6db-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="cd6db-125">在“网络配置”<STRONG></STRONG>组的“位置策略”<STRONG></STRONG>页上，可以查看可用位置策略的详细信息，或创建新的位置策略。</span><span class="sxs-lookup"><span data-stu-id="cd6db-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="cd6db-126">有关详细信息，请参阅<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置策略信息</A>。</span><span class="sxs-lookup"><span data-stu-id="cd6db-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="cd6db-127">（可选）在“说明”\*\*\*\* 字段中键入值，用以提供仅通过名称无法表达的更多有关该站点的信息。</span><span class="sxs-lookup"><span data-stu-id="cd6db-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="cd6db-128">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd6db-129">创建新网络站点时，不要使用“关联子网”<STRONG></STRONG>表。</span><span class="sxs-lookup"><span data-stu-id="cd6db-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="cd6db-130">创建或修改子网时，会将子网与站点相关联。</span><span class="sxs-lookup"><span data-stu-id="cd6db-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="cd6db-131">有关详细信息，请参阅<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中创建或修改网络子网</A>。</span><span class="sxs-lookup"><span data-stu-id="cd6db-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="cd6db-132">修改网络站点</span><span class="sxs-lookup"><span data-stu-id="cd6db-132">To modify a network site</span></span>

1.  <span data-ttu-id="cd6db-133">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cd6db-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd6db-134">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd6db-135">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd6db-136">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="cd6db-137">在“站点”\*\*\*\* 页上，单击要修改的站点。</span><span class="sxs-lookup"><span data-stu-id="cd6db-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="cd6db-138">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="cd6db-p107">在“编辑站点”\*\*\*\* 页上，可以修改与站点关联的说明、区域、带宽策略配置文件以及位置策略。有关详细信息，请参阅本主题前面的“创建网络站点”一节。</span><span class="sxs-lookup"><span data-stu-id="cd6db-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="cd6db-141">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-141">Click **Commit**.</span></span>

<span data-ttu-id="cd6db-p108">不能修改此页面中的“关联子网”\*\*\*\* 表。关联子网列表仅供参考，以使您注意修改站点设置时将影响的子网。</span><span class="sxs-lookup"><span data-stu-id="cd6db-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="cd6db-144">删除网络站点</span><span class="sxs-lookup"><span data-stu-id="cd6db-144">To delete a network site</span></span>

1.  <span data-ttu-id="cd6db-145">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cd6db-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd6db-146">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd6db-147">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="cd6db-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd6db-148">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="cd6db-149">在“站点”\*\*\*\* 页上，单击要删除的站点。</span><span class="sxs-lookup"><span data-stu-id="cd6db-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd6db-p110">可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="cd6db-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="cd6db-153">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="cd6db-154">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd6db-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="cd6db-p111">不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”<STRONG></STRONG>菜单中的“显示详细信息”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="cd6db-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd6db-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd6db-158">See Also</span></span>


[<span data-ttu-id="cd6db-159">删除 Lync Server 2013 中的现有网络站点</span><span class="sxs-lookup"><span data-stu-id="cd6db-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="cd6db-160">新 CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="cd6db-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="cd6db-161">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="cd6db-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="cd6db-162">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="cd6db-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="cd6db-163">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="cd6db-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

