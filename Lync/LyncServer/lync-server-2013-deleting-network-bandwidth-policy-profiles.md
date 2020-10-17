---
title: Lync Server 2013：删除网络带宽策略配置文件
description: Lync Server 2013：删除网络带宽策略配置文件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552658"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="c8e33-103">在 Lync Server 2013 中删除网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c8e33-103">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8e33-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c8e33-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c8e33-105">作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="c8e33-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c8e33-106">在 Microsoft Lync Server 2013 中，仅可为音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="c8e33-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c8e33-107">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="c8e33-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c8e33-108">您可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8e33-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c8e33-109">请使用下列过程删除网络带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8e33-109">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="c8e33-110">有关创建或修改网络带宽策略配置文件的详细信息，请参阅 [在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c8e33-110">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="c8e33-111">删除带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c8e33-111">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c8e33-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c8e33-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8e33-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c8e33-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8e33-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="c8e33-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8e33-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“带宽策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8e33-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c8e33-116">在“带宽策略”\*\*\*\* 页上，单击要删除的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8e33-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8e33-p103">可一次性删除多个配置文件。要执行此操作，请按住 Ctrl 键，同时选择多个配置文件。或者，要选择全部配置文件，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c8e33-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c8e33-120">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8e33-120">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c8e33-121">不能删除与网络站点关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8e33-121">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="c8e33-122">只有先删除配置文件与网络站点之间的关联，然后才能将配置文件删除。</span><span class="sxs-lookup"><span data-stu-id="c8e33-122">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="c8e33-123">有关如何修改网络站点的详细信息，请参阅 <A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中创建或修改网络站点</A>。</span><span class="sxs-lookup"><span data-stu-id="c8e33-123">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8e33-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e33-124">See Also</span></span>


[<span data-ttu-id="c8e33-125">在 Lync Server 2013 中创建或修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c8e33-125">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="c8e33-126">在 Lync Server 2013 中查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="c8e33-126">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="c8e33-127">在 Lync Server 2013 中配置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="c8e33-127">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="c8e33-128">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c8e33-128">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

