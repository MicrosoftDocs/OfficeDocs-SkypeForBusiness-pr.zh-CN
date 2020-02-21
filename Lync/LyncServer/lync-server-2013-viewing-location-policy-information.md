---
title: Lync Server 2013：查看位置策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ebd92944d02cf899ad6da60a586cd5ec24e9aa8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="b9817-102">在 Lync Server 2013 中查看位置策略信息</span><span class="sxs-lookup"><span data-stu-id="b9817-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9817-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b9817-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b9817-104">在 Lync Server 2013 中，可以使用位置策略将与增强的9-1-1 （E9-1）功能相关的设置应用于用户或联系人的位置设置。</span><span class="sxs-lookup"><span data-stu-id="b9817-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="b9817-105">位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="b9817-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="b9817-106">例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9817-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="b9817-107">您可以在 Lync Server 2013 控制面板中的 "**网络配置**" 组中配置位置策略。</span><span class="sxs-lookup"><span data-stu-id="b9817-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="b9817-108">从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="b9817-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="b9817-109">可使用以下过程查看位置策略的信息。</span><span class="sxs-lookup"><span data-stu-id="b9817-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="b9817-110">有关创建或修改位置策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b9817-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="b9817-111">查看位置策略的信息</span><span class="sxs-lookup"><span data-stu-id="b9817-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="b9817-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b9817-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b9817-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b9817-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b9817-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="b9817-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b9817-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“位置策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9817-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="b9817-116">在“位置策略”\*\*\*\* 页上，选择要修改的位置策略。</span><span class="sxs-lookup"><span data-stu-id="b9817-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="b9817-117">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9817-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9817-118">一次只能查看一个位置策略的信息。</span><span class="sxs-lookup"><span data-stu-id="b9817-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="b9817-p104">默认情况下，存在一个名为“全局”的策略，无法将其删除或进行重命名。但是，您可以修改“全局”策略。该策略将应用于所有用户和联系人，除非您创建站点策略或每用户策略。每用户策略必须应用于特定用户。</span><span class="sxs-lookup"><span data-stu-id="b9817-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9817-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9817-123">See Also</span></span>


[<span data-ttu-id="b9817-124">在 Lync Server 2013 中创建或修改位置策略</span><span class="sxs-lookup"><span data-stu-id="b9817-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="b9817-125">在 Lync Server 2013 中创建位置策略</span><span class="sxs-lookup"><span data-stu-id="b9817-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="b9817-126">在 Lync Server 2013 中创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="b9817-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="b9817-127">新 New-cslocationpolicy</span><span class="sxs-lookup"><span data-stu-id="b9817-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="b9817-128">New-cslocationpolicy</span><span class="sxs-lookup"><span data-stu-id="b9817-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="b9817-129">New-cslocationpolicy</span><span class="sxs-lookup"><span data-stu-id="b9817-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="b9817-130">New-cslocationpolicy</span><span class="sxs-lookup"><span data-stu-id="b9817-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

