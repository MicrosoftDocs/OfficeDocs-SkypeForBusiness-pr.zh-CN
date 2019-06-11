---
title: 'Lync Server 2013: 创建或修改网络站点'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="33104-102">在 Lync Server 2013 中创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="33104-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33104-103">_**主题上次修改时间:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="33104-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="33104-104">网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="33104-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="33104-105">你可以使用 Microsoft Lync Server 2013 控制面板配置网站并将其与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="33104-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="33104-106">例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="33104-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="33104-107">必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。</span><span class="sxs-lookup"><span data-stu-id="33104-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="33104-108">在 Lync Server 控制面板中, 您可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="33104-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="33104-109">使用以下过程创建或修改网络网站。</span><span class="sxs-lookup"><span data-stu-id="33104-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="33104-110">有关删除现有网络网站的详细信息, 请参阅[在 Lync Server 2013 中删除现有网络网站](lync-server-2013-deleting-an-existing-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="33104-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="33104-111">创建网络网站</span><span class="sxs-lookup"><span data-stu-id="33104-111">To create a network site</span></span>

1.  <span data-ttu-id="33104-112">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="33104-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33104-113">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="33104-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33104-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="33104-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33104-115">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="33104-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="33104-116">在 "**网站**" 页面上, 单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="33104-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="33104-117">在 "**新建网站**" 中, 在 "**名称**" 字段中键入此网站的名称。</span><span class="sxs-lookup"><span data-stu-id="33104-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33104-118">网站名称在 Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="33104-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="33104-119">在 "**区域**" 下拉列表中, 选择要与此网站相关联的网络区域。</span><span class="sxs-lookup"><span data-stu-id="33104-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="33104-120">可选如果要对此网站的音频或视频呼叫设置带宽限制, 请从 "**带宽策略**" 下拉列表中选择具有相应设置的 "带宽策略配置文件"。</span><span class="sxs-lookup"><span data-stu-id="33104-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33104-121">你可以在 "<STRONG>网络配置</STRONG>" 组的 "<STRONG>策略配置文件</STRONG>" 页面上查看可用带宽策略配置文件的详细信息, 或者创建新的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="33104-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="33104-122">有关详细信息, 请参阅<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中创建或修改带宽策略配置文件</A>。</span><span class="sxs-lookup"><span data-stu-id="33104-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="33104-123">可选如果要为此网站提供位置设置, 请从 "**位置策略**" 下拉列表中选择一个位置策略。</span><span class="sxs-lookup"><span data-stu-id="33104-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33104-124">位置策略将特定的增强 9-1-1 (E9-1) 和客户端位置设置分配给该网站。</span><span class="sxs-lookup"><span data-stu-id="33104-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="33104-125">你可以从 "<STRONG>网络配置</STRONG>" 组的 "<STRONG>位置策略</STRONG>" 页查看可用位置策略的详细信息, 或者创建新的位置策略。</span><span class="sxs-lookup"><span data-stu-id="33104-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="33104-126">有关详细信息, 请参阅<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置策略信息</A>。</span><span class="sxs-lookup"><span data-stu-id="33104-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="33104-127">可选在 "**说明**" 字段中键入一个值, 以提供有关此网站的详细信息, 该信息不能单独以名称表示。</span><span class="sxs-lookup"><span data-stu-id="33104-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="33104-128">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="33104-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33104-129">创建新网络网站时, 请不要使用<STRONG>关联的子网</STRONG>表。</span><span class="sxs-lookup"><span data-stu-id="33104-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="33104-130">创建或修改子网时, 将子网与网站相关联。</span><span class="sxs-lookup"><span data-stu-id="33104-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="33104-131">有关详细信息, 请参阅<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中创建或修改网络子网</A>。</span><span class="sxs-lookup"><span data-stu-id="33104-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="33104-132">修改网络网站</span><span class="sxs-lookup"><span data-stu-id="33104-132">To modify a network site</span></span>

1.  <span data-ttu-id="33104-133">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="33104-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33104-134">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="33104-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33104-135">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="33104-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33104-136">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="33104-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="33104-137">在 "**网站**" 页面上, 单击要修改的网站。</span><span class="sxs-lookup"><span data-stu-id="33104-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="33104-138">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33104-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="33104-139">在 "**编辑网站**" 页面上, 您可以修改与该网站相关联的说明、区域、带宽策略配置文件和位置策略。</span><span class="sxs-lookup"><span data-stu-id="33104-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="33104-140">有关详细信息, 请参阅本主题前面的 "创建网络网站" 部分。</span><span class="sxs-lookup"><span data-stu-id="33104-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="33104-141">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="33104-141">Click **Commit**.</span></span>

<span data-ttu-id="33104-142">不能在此页面上修改**关联的子网**表。</span><span class="sxs-lookup"><span data-stu-id="33104-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="33104-143">将为参考提供关联子网的列表, 以便你在修改网站设置时知道将受到哪些子网的影响。</span><span class="sxs-lookup"><span data-stu-id="33104-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="33104-144">删除网络网站</span><span class="sxs-lookup"><span data-stu-id="33104-144">To delete a network site</span></span>

1.  <span data-ttu-id="33104-145">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="33104-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33104-146">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="33104-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33104-147">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="33104-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33104-148">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。</span><span class="sxs-lookup"><span data-stu-id="33104-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="33104-149">在 "**网站**" 页面上, 单击要删除的网站。</span><span class="sxs-lookup"><span data-stu-id="33104-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33104-150">您可以一次删除多个网站。</span><span class="sxs-lookup"><span data-stu-id="33104-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="33104-151">若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个网站。</span><span class="sxs-lookup"><span data-stu-id="33104-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="33104-152">或者, 若要选择 "所有网站", 请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="33104-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="33104-153">在 "**编辑**" 菜单上, 单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="33104-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="33104-154">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="33104-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="33104-155">如果网络站点与网络子网相关联, 则不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="33104-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="33104-156">如果您尝试删除与子网相关联的网站, 您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="33104-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="33104-157">若要查看某个网站是否与任何子网相关联, 请单击该网站, 然后单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>显示详细信息</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="33104-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33104-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33104-158">See Also</span></span>


[<span data-ttu-id="33104-159">在 Lync Server 2013 中删除现有网络网站</span><span class="sxs-lookup"><span data-stu-id="33104-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="33104-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33104-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="33104-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33104-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="33104-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33104-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="33104-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33104-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

