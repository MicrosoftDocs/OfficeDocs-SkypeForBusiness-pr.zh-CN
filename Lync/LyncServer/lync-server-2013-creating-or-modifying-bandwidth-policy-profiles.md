---
title: Lync Server 2013：创建或修改带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="a054e-102">在 Lync Server 2013 中创建或修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="a054e-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a054e-103">_**主题上次修改时间：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a054e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a054e-104">作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="a054e-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="a054e-105">在 Microsoft Lync Server 2013 中，只有音频和视频形式可以分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="a054e-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="a054e-106">你可以设置整体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="a054e-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="a054e-107">你可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="a054e-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="a054e-108">每个带宽策略配置文件都可以与一个或多个网络网站相关联。</span><span class="sxs-lookup"><span data-stu-id="a054e-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="a054e-109">使用以下过程创建或修改带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="a054e-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="a054e-110">若要删除带宽策略配置文件，请参阅[在 Lync Server 2013 中删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a054e-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="a054e-111">创建新的带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="a054e-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="a054e-112">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a054e-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a054e-113">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a054e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a054e-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a054e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a054e-115">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。</span><span class="sxs-lookup"><span data-stu-id="a054e-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="a054e-116">在 "**带宽策略**" 页面上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="a054e-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="a054e-117">在**新的带宽策略配置文件**中，在 "**名称**" 字段中键入名称。</span><span class="sxs-lookup"><span data-stu-id="a054e-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="a054e-118">此名称在所有带宽策略配置文件中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a054e-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="a054e-119">在 "**音频限制**" 字段中，键入一个数字值。</span><span class="sxs-lookup"><span data-stu-id="a054e-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="a054e-120">此值表示为所有音频连接分配的最大带宽量（以 kbps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="a054e-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="a054e-121">在 "**音频会话限制**" 字段中输入一个数字值。</span><span class="sxs-lookup"><span data-stu-id="a054e-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="a054e-122">此值表示为单个音频连接分配的最大带宽量（以 kbps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="a054e-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="a054e-123">此值必须为40或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a054e-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="a054e-124">在 "**视频限制**" 字段中输入一个数字值。</span><span class="sxs-lookup"><span data-stu-id="a054e-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="a054e-125">此值表示为所有视频连接分配的最大带宽量（以 kbps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="a054e-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="a054e-126">在 "**视频会话限制**" 字段中输入一个数字值。</span><span class="sxs-lookup"><span data-stu-id="a054e-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="a054e-127">此值表示为单个视频连接分配的最大带宽量（以 kbps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="a054e-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="a054e-128">此值必须为100或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a054e-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="a054e-129">可选在 "**说明**" 字段中键入一个值，以提供有关无法单独以名称表示的此带宽策略配置文件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a054e-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="a054e-130">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a054e-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a054e-131">创建新的带宽策略配置文件不会自动强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="a054e-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="a054e-132">必须首先将策略配置文件与网站相关联。</span><span class="sxs-lookup"><span data-stu-id="a054e-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="a054e-133">有关如何将策略配置文件与网站相关联的详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中创建或修改网络站点</A>。</span><span class="sxs-lookup"><span data-stu-id="a054e-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="a054e-134">修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="a054e-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="a054e-135">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a054e-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a054e-136">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a054e-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a054e-137">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a054e-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a054e-138">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。</span><span class="sxs-lookup"><span data-stu-id="a054e-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="a054e-139">在 "**带宽策略**" 页面上，单击要修改的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="a054e-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="a054e-140">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a054e-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a054e-141">在 "**编辑带宽策略配置文件**" 页面上，根据需要修改字段（有关详细信息，请参阅本主题前面的 "创建带宽策略配置文件" 部分）。</span><span class="sxs-lookup"><span data-stu-id="a054e-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="a054e-142">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a054e-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a054e-143">修改带宽策略配置文件时，它将立即更新与此带宽策略配置文件相关联的所有网络站点的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="a054e-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a054e-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a054e-144">See Also</span></span>


[<span data-ttu-id="a054e-145">删除 Lync Server 2013 中的网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="a054e-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="a054e-146">在 Lync Server 2013 中配置呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="a054e-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="a054e-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="a054e-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="a054e-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="a054e-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="a054e-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="a054e-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

