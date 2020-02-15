---
title: Lync Server 2013：删除现有网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b67dcb92fec16c31c2e2a6be780a29eb1eee295
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="4526f-102">删除 Lync Server 2013 中的现有网络站点</span><span class="sxs-lookup"><span data-stu-id="4526f-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4526f-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4526f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4526f-104">网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="4526f-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4526f-105">您可以使用 Lync Server 2013 控制面板配置网站并将其与区域相关联。</span><span class="sxs-lookup"><span data-stu-id="4526f-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4526f-106">例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="4526f-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4526f-107">必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。</span><span class="sxs-lookup"><span data-stu-id="4526f-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4526f-108">在 Lync Server 控制面板中，您可以创建、修改和删除网络站点。</span><span class="sxs-lookup"><span data-stu-id="4526f-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4526f-109">使用以下过程可删除现有网络站点。</span><span class="sxs-lookup"><span data-stu-id="4526f-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="4526f-110">有关创建或修改网络站点的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="4526f-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="4526f-111">删除网络站点</span><span class="sxs-lookup"><span data-stu-id="4526f-111">To delete a network site</span></span>

1.  <span data-ttu-id="4526f-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4526f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4526f-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4526f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4526f-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="4526f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4526f-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“站点”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4526f-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="4526f-116">在“站点”\*\*\*\* 页上，单击要删除的站点。</span><span class="sxs-lookup"><span data-stu-id="4526f-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4526f-p103">可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4526f-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4526f-120">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4526f-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4526f-121">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4526f-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4526f-p104">不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”<STRONG></STRONG>菜单中的“显示详细信息”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4526f-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

