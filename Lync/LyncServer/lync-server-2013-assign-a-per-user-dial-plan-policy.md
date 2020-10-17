---
title: Lync Server 2013：分配每用户拨号计划策略
description: Lync Server 2013：分配每用户拨号计划策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 654c1f15ccb1efa4d1aa35d957df7a2654fa41d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559898"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="b65cb-103">在 Lync Server 2013 中分配每用户拨号计划策略</span><span class="sxs-lookup"><span data-stu-id="b65cb-103">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b65cb-p101">要完成企业语音用户或电话拨入式会议用户的用户帐户配置，必须为用户分配拨号计划。如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。如果要为所有启用企业语音的用户使用全局或站点拨号计划，可以跳过这一节。</span><span class="sxs-lookup"><span data-stu-id="b65cb-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="b65cb-107">使用 Lync Server 2013 控制面板分配拨号计划</span><span class="sxs-lookup"><span data-stu-id="b65cb-107">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="b65cb-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b65cb-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b65cb-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b65cb-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b65cb-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="b65cb-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b65cb-111">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65cb-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b65cb-112">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65cb-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="b65cb-113">在表中，单击要分配拨号计划的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b65cb-113">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="b65cb-114">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65cb-114">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="b65cb-115">在“编辑 Lync Server 用户”\*\*\*\* 页的“电话”\*\*\*\* 下，单击“企业语音”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65cb-115">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="b65cb-116">单击“拨号计划策略”\*\*\*\*，然后选择所需的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b65cb-116">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="b65cb-117">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65cb-117">Click **Commit**.</span></span>

<span data-ttu-id="b65cb-118">有关配置拨号计划的详细信息，请参阅 [在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="b65cb-118">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b65cb-119">使用 Windows PowerShell Cmdlet 分配 Per-User 的拨号计划</span><span class="sxs-lookup"><span data-stu-id="b65cb-119">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b65cb-120">您可以使用 Windows PowerShell 和 **grant-csdialplan** cmdlet 分配每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b65cb-120">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="b65cb-121">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b65cb-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b65cb-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="b65cb-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="b65cb-123">为单个用户分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="b65cb-123">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="b65cb-124">以下命令向用户 Ken Myer 分配每用户拨号计划 RedmondDialPlan。</span><span class="sxs-lookup"><span data-stu-id="b65cb-124">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="b65cb-125">将每用户拨号计划分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="b65cb-125">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="b65cb-126">此命令向在 Redmond 市工作的所有用户分配每用户拨号计划 RedmondDialPlan。</span><span class="sxs-lookup"><span data-stu-id="b65cb-126">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b65cb-127">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅 [get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="b65cb-127">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="b65cb-128">取消分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="b65cb-128">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="b65cb-p105">以下命令取消分配之前为 Ken Myer 分配的任何每用户拨号计划。在取消分配每用户拨号计划后，将通过以下方式自动管理 Ken Myer：使用全局拨号计划，使用其本地站点拨号计划（如果有）或使用分配给其注册器或 PSTN 网关的服务范围的拨号计划。服务范围的拨号计划优先于任何站点拨号计划，而站点拨号计划优先于全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b65cb-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b65cb-132">有关详细信息，请参阅 [grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b65cb-132">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b65cb-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b65cb-133">See Also</span></span>


[<span data-ttu-id="b65cb-134">在 Lync Server 2013 中配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="b65cb-134">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="b65cb-135">为 Lync Server 2013 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="b65cb-135">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

