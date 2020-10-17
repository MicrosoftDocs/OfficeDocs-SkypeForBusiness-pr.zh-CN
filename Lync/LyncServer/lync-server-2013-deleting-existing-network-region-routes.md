---
title: Lync Server 2013：删除现有网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525389"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="f704f-102">在 Lync Server 2013 中删除现有网络区域路由</span><span class="sxs-lookup"><span data-stu-id="f704f-102">Deleting existing network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f704f-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f704f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f704f-104">呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。</span><span class="sxs-lookup"><span data-stu-id="f704f-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f704f-105">虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。</span><span class="sxs-lookup"><span data-stu-id="f704f-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f704f-106">您可以使用 Lync Server 控制面板配置网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="f704f-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="f704f-107">从 Lync Server 控制面板中，您可以创建、修改或删除网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="f704f-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="f704f-108">使用本主题可删除现有网络区域路由。</span><span class="sxs-lookup"><span data-stu-id="f704f-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="f704f-109">有关创建或修改网络区域路由的详细信息，请参阅 [在 Lync Server 2013 中创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="f704f-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="f704f-110">删除网络区域路由</span><span class="sxs-lookup"><span data-stu-id="f704f-110">To delete a network region route</span></span>

1.  <span data-ttu-id="f704f-111">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f704f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f704f-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f704f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f704f-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="f704f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f704f-114">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f704f-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f704f-115">在“区域路由”\*\*\*\* 页上，单击要删除的区域路由。</span><span class="sxs-lookup"><span data-stu-id="f704f-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f704f-p103">可一次性删除多个区域路由。要执行此操作，请按住 Ctrl 键，同时选择多个区域路由。或者，要选择全部区域路由，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f704f-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="f704f-119">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f704f-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f704f-120">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f704f-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f704f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f704f-121">See Also</span></span>


[<span data-ttu-id="f704f-122">在 Lync Server 2013 中创建或修改网络区域路由</span><span class="sxs-lookup"><span data-stu-id="f704f-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="f704f-123">[配置网络区域路由](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f704f-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="f704f-124">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f704f-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="f704f-125">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f704f-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="f704f-126">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f704f-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="f704f-127">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="f704f-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

