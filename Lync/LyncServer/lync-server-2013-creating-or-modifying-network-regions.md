---
title: Lync Server 2013：创建或修改网络区域
description: Lync Server 2013：创建或修改网络区域。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02a041272f0df27d2133ca26096caeb01816c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544028"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="746c9-103">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="746c9-103">Creating or modifying network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="746c9-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="746c9-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="746c9-105">网络区域将跨多个地理区域的网络的各个部分相互连接起来。</span><span class="sxs-lookup"><span data-stu-id="746c9-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="746c9-106">每个网络区域都必须与中央站点关联。</span><span class="sxs-lookup"><span data-stu-id="746c9-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="746c9-107">中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="746c9-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="746c9-108">您可以使用 Lync Server 控制面板配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="746c9-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="746c9-109">网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="746c9-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="746c9-110">在 Lync Server 控制面板中，您可以创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="746c9-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="746c9-111">使用此主题创建和修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="746c9-111">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="746c9-112">有关删除现有网络区域的详细信息，请参阅 [在 Lync Server 2013 中删除现有网络区域](lync-server-2013-deleting-existing-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="746c9-112">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="746c9-113">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="746c9-113">To create a network region</span></span>

1.  <span data-ttu-id="746c9-114">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="746c9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="746c9-115">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="746c9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="746c9-116">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="746c9-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="746c9-117">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="746c9-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="746c9-118">在 " **区域** " 页上，单击 " **新建**"。</span><span class="sxs-lookup"><span data-stu-id="746c9-118">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="746c9-119">在 " **新区域** " 页上，在 " **名称** " 字段中键入一个值。</span><span class="sxs-lookup"><span data-stu-id="746c9-119">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="746c9-120">此值在 Microsoft Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="746c9-120">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="746c9-121">从 " **中央站点** " 下拉列表中，选择此网络区域的中央站点。</span><span class="sxs-lookup"><span data-stu-id="746c9-121">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="746c9-122">默认情况下，" **启用音频备用路径** " 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="746c9-122">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="746c9-123">如果主路径中不存在足够的带宽，则此字段将确定是否通过备用路径路由音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="746c9-123">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="746c9-124">仅当需要关闭到 Internet 的卸载时，才清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="746c9-124">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="746c9-125">如果你的任何呼叫将成为 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。</span><span class="sxs-lookup"><span data-stu-id="746c9-125">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="746c9-126">默认情况下，" **启用视频备用路径** " 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="746c9-126">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="746c9-127">如果主路径中不存在足够的带宽，则此字段将确定是否通过备用路径路由视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="746c9-127">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="746c9-128">仅当需要关闭到 Internet 的卸载时，才清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="746c9-128">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="746c9-129">如果你的任何呼叫将成为 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。</span><span class="sxs-lookup"><span data-stu-id="746c9-129">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="746c9-130"> (可选) 在 " **说明** " 字段中键入一个值，以提供有关无法单独表示的此区域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="746c9-130">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="746c9-131">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="746c9-131">Click **Commit**.</span></span>

<span data-ttu-id="746c9-132">" **关联的网站** " 表不用于创建网络区域。</span><span class="sxs-lookup"><span data-stu-id="746c9-132">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="746c9-133">您在创建或修改网站时将网站与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="746c9-133">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="746c9-134">有关详细信息，请参阅 [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="746c9-134">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="746c9-135">修改网络区域</span><span class="sxs-lookup"><span data-stu-id="746c9-135">To modify a network region</span></span>

1.  <span data-ttu-id="746c9-136">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="746c9-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="746c9-137">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="746c9-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="746c9-138">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="746c9-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="746c9-139">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="746c9-139">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="746c9-140">在 " **区域** " 页上，单击要修改的区域。</span><span class="sxs-lookup"><span data-stu-id="746c9-140">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="746c9-141">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="746c9-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="746c9-142">在 " **编辑区域** " 页上，您可以修改用于启用和禁用音频和视频备用路径的设置，并更改说明 (有关详细信息，请参阅本主题前面的 "创建网络区域" 一节。</span><span class="sxs-lookup"><span data-stu-id="746c9-142">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="746c9-143">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="746c9-143">Click **Commit**.</span></span>

<span data-ttu-id="746c9-144">您无法修改此页面上的 **关联网站** 。</span><span class="sxs-lookup"><span data-stu-id="746c9-144">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="746c9-145">将提供相关网站的列表以供参考，以便您知道在修改区域设置时哪些网站将受到影响。</span><span class="sxs-lookup"><span data-stu-id="746c9-145">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="746c9-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="746c9-146">See Also</span></span>


[<span data-ttu-id="746c9-147">在 Lync Server 2013 中删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="746c9-147">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="746c9-148">在 Lync Server 2013 中配置 CAC 的网络区域</span><span class="sxs-lookup"><span data-stu-id="746c9-148">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="746c9-149">新 CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="746c9-149">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="746c9-150">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="746c9-150">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="746c9-151">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="746c9-151">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="746c9-152">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="746c9-152">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

