---
title: Lync Server 2013：删除位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc554d24bc93b81969832c9d8d2b034d071760bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="fc78a-102">在 Lync Server 2013 中删除位置策略</span><span class="sxs-lookup"><span data-stu-id="fc78a-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc78a-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="fc78a-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="fc78a-104">在 Lync Server 2013 中，可以使用位置策略将与增强的9-1-1 （E9-1）功能相关的设置应用于用户或联系人的位置设置。</span><span class="sxs-lookup"><span data-stu-id="fc78a-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="fc78a-105">位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="fc78a-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="fc78a-106">例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="fc78a-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="fc78a-107">您可以在 Lync Server 2013 控制面板中的 "**网络配置**" 组中配置位置策略。</span><span class="sxs-lookup"><span data-stu-id="fc78a-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="fc78a-108">从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="fc78a-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="fc78a-109">使用以下过程删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="fc78a-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="fc78a-110">有关创建或修改位置策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="fc78a-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="fc78a-111">删除位置策略</span><span class="sxs-lookup"><span data-stu-id="fc78a-111">To delete a location policy</span></span>

1.  <span data-ttu-id="fc78a-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fc78a-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fc78a-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fc78a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fc78a-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="fc78a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fc78a-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“位置策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc78a-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="fc78a-116">在“位置策略”\*\*\*\* 页上，选择要删除的位置策略。</span><span class="sxs-lookup"><span data-stu-id="fc78a-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc78a-p104">可一次性删除多个位置策略。要执行此操作，请按住 Ctrl 键，同时选择多个策略。或者，要选中全部策略，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="fc78a-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="fc78a-120">在“编辑”\*\*\*\* 菜单上，单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc78a-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fc78a-121">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc78a-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fc78a-p105">无法删除“全局”位置策略。如果尝试删除“全局”策略，您将收到一条警告消息，而该策略将重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="fc78a-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc78a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc78a-124">See Also</span></span>


[<span data-ttu-id="fc78a-125">在 Lync Server 2013 中创建或修改位置策略</span><span class="sxs-lookup"><span data-stu-id="fc78a-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="fc78a-126">在 Lync Server 2013 中查看位置策略信息</span><span class="sxs-lookup"><span data-stu-id="fc78a-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

