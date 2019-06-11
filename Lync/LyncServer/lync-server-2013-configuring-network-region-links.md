---
title: 'Lync Server 2013: 配置网络区域链接'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895c85a80d3e5a7fadee3dccad25f9d89f04028a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="10613-102">在 Lync Server 2013 中配置网络区域链接</span><span class="sxs-lookup"><span data-stu-id="10613-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10613-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10613-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10613-104">你可以配置两个网络区域之间的链接作为呼叫许可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="10613-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="10613-105">网络中的区域通过物理广域网络 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="10613-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="10613-106">你可以使用 Lync Server 控制面板定义两个网络区域之间的链接, 并设置这些区域之间的音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="10613-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="10613-107">有关删除现有网络区域链接的详细信息, 请参阅[在 Lync Server 2013 中删除网络区域链接](lync-server-2013-deleting-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="10613-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="10613-108">创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="10613-108">To create a network region link</span></span>

1.  <span data-ttu-id="10613-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="10613-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10613-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="10613-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10613-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="10613-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10613-112">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="10613-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="10613-113">在 "**区域链接**" 页面上, 单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="10613-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="10613-114">在 "**新区域链接**" 中, 在 "**名称**" 字段中键入值。</span><span class="sxs-lookup"><span data-stu-id="10613-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10613-115">此值在 Lync Server 2013 部署中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="10613-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="10613-116">从 "**网络区域\#1** " 下拉列表中, 选择要链接的两个区域之一。</span><span class="sxs-lookup"><span data-stu-id="10613-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="10613-117">从 "**网络区域\#2** " 下拉列表中, 选择要链接的其他区域。</span><span class="sxs-lookup"><span data-stu-id="10613-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="10613-118">此区域必须与为 "网络区域\#1" 选择的区域不同。</span><span class="sxs-lookup"><span data-stu-id="10613-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="10613-119">可选如果您想要对这些区域之间的音频或视频通话设置带宽限制, 请从 "**带宽策略**" 下拉列表中选择一个带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="10613-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="10613-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="10613-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="10613-121">修改网络区域链接</span><span class="sxs-lookup"><span data-stu-id="10613-121">To modify a network region link</span></span>

1.  <span data-ttu-id="10613-122">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="10613-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10613-123">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="10613-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10613-124">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="10613-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10613-125">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="10613-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="10613-126">在 "**区域链接**" 页面上, 单击要修改的区域链接。</span><span class="sxs-lookup"><span data-stu-id="10613-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="10613-127">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10613-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="10613-128">在 "**编辑区域" 链接**中, 可以修改链接的区域或此链接的 "带宽策略" 配置文件。</span><span class="sxs-lookup"><span data-stu-id="10613-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="10613-129">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="10613-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10613-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10613-130">See Also</span></span>


[<span data-ttu-id="10613-131">删除 Lync Server 2013 中的网络区域链接</span><span class="sxs-lookup"><span data-stu-id="10613-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="10613-132">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="10613-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="10613-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="10613-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="10613-134">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="10613-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="10613-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="10613-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
