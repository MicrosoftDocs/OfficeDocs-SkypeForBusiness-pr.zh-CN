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
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="21796-102">在 Lync Server 2013 中删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="21796-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21796-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="21796-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="21796-104">网络区域跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="21796-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="21796-105">每个网络区域必须与一个中心网站相关联。</span><span class="sxs-lookup"><span data-stu-id="21796-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="21796-106">中心网站是运行呼叫许可控制（CAC）带宽策略服务的数据中心网站。</span><span class="sxs-lookup"><span data-stu-id="21796-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="21796-107">可以使用 Lync Server "控制面板" 配置网络区域。</span><span class="sxs-lookup"><span data-stu-id="21796-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="21796-108">网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="21796-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="21796-109">从 Lync Server 控制面板中，您可以创建、修改或删除网络区域。</span><span class="sxs-lookup"><span data-stu-id="21796-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="21796-110">使用本主题删除现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="21796-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="21796-111">有关创建或修改现有网络区域的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="21796-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="21796-112">删除网络区域</span><span class="sxs-lookup"><span data-stu-id="21796-112">To delete a network region</span></span>

1.  <span data-ttu-id="21796-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="21796-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21796-114">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="21796-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21796-115">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="21796-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21796-116">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。</span><span class="sxs-lookup"><span data-stu-id="21796-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="21796-117">在 "**区域**" 页面上，单击要删除的区域。</span><span class="sxs-lookup"><span data-stu-id="21796-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21796-118">您可以一次删除多个区域。</span><span class="sxs-lookup"><span data-stu-id="21796-118">You can delete more than one region at a time.</span></span> <span data-ttu-id="21796-119">若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域。</span><span class="sxs-lookup"><span data-stu-id="21796-119">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="21796-120">或者，若要选择所有区域，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="21796-120">Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="21796-121">在 "**编辑**" 菜单上，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="21796-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="21796-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="21796-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="21796-123">如果网络区域与网络网站相关联，则无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="21796-123">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="21796-124">如果您尝试删除与网站相关联的区域，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="21796-124">If you attempt to remove a region associated with a site you will receive an error message.</span></span> <span data-ttu-id="21796-125">若要查看某个区域是否与任何网站相关联，请选择该区域，然后单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>显示详细信息</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="21796-125">To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21796-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21796-126">See Also</span></span>


[<span data-ttu-id="21796-127">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="21796-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

