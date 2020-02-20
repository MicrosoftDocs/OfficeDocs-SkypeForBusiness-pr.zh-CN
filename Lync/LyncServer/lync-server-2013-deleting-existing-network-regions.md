---
title: Lync Server 2013：删除现有网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94b3614dcf2b09ab96b2deede70554f1d3e6f50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="6559a-102">在 Lync Server 2013 中删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="6559a-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6559a-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6559a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6559a-104">网络区域将跨多个地理区域的网络的各个部分相互连接起来。</span><span class="sxs-lookup"><span data-stu-id="6559a-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6559a-105">每个网络区域都必须与中央站点关联。</span><span class="sxs-lookup"><span data-stu-id="6559a-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="6559a-106">中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="6559a-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="6559a-107">您可以使用 Lync Server 控制面板配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="6559a-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="6559a-108">网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="6559a-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="6559a-109">在 Lync Server 控制面板中，您可以创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="6559a-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="6559a-110">使用此主题可删除现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="6559a-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="6559a-111">有关创建或修改现有网络区域的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="6559a-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="6559a-112">删除网络区域</span><span class="sxs-lookup"><span data-stu-id="6559a-112">To delete a network region</span></span>

1.  <span data-ttu-id="6559a-113">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6559a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6559a-114">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6559a-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6559a-115">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6559a-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6559a-116">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6559a-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="6559a-117">在“区域”\*\*\*\* 页上，单击要删除的区域。</span><span class="sxs-lookup"><span data-stu-id="6559a-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6559a-p103">可一次性删除多个区域。要执行此操作，请按住 Ctrl 键，同时选择多个区域。或者，要选择全部区域，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6559a-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="6559a-121">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6559a-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="6559a-122">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6559a-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6559a-p104">如果网络区域与某个网络站点关联，则不能删除该网络区域。如果尝试删除与某个站点关联的区域，您将收到错误消息。要查看区域是否与任何站点关联，请选择相应的区域，然后单击“编辑”<STRONG></STRONG>菜单中的“显示详细信息”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6559a-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6559a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6559a-126">See Also</span></span>


[<span data-ttu-id="6559a-127">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="6559a-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

