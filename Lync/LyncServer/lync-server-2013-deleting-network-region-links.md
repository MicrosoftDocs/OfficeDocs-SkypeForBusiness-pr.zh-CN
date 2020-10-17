---
title: Lync Server 2013：删除网络区域链接
description: Lync Server 2013：删除网络区域链接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545328"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="b01af-103">删除 Lync Server 2013 中的网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b01af-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b01af-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b01af-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b01af-105">您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b01af-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b01af-106">网络内的区域通过物理广域网 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="b01af-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="b01af-107">您可以使用 Lync Server 控制面板删除两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="b01af-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="b01af-108">有关创建或修改网络区域链接的详细信息，请参阅 [在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="b01af-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="b01af-109">删除网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b01af-109">To delete a network region link</span></span>

1.  <span data-ttu-id="b01af-110">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b01af-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b01af-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b01af-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b01af-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="b01af-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b01af-113">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域链接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b01af-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b01af-114">在“区域链接”\*\*\*\* 页上，单击要删除的区域链接。</span><span class="sxs-lookup"><span data-stu-id="b01af-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b01af-p103">可一次性删除多个区域链接。要执行此操作，请按住 Ctrl 键，同时选择多个区域链接。或者，要选择全部区域链接，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b01af-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b01af-118">从“编辑”\*\*\*\* 菜单中选择“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b01af-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="b01af-119">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b01af-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b01af-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b01af-120">See Also</span></span>


[<span data-ttu-id="b01af-121">在 Lync Server 2013 中配置网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b01af-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

