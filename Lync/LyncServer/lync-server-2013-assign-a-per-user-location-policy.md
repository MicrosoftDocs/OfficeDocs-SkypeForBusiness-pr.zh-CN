---
title: Lync Server 2013：分配每用户位置策略
description: Lync Server 2013：分配每用户位置策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559878"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="7dc4d-103">在 Lync Server 2013 中分配每用户位置策略</span><span class="sxs-lookup"><span data-stu-id="7dc4d-103">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="7dc4d-104">位置策略是您可以在 Lync Server 控制面板中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-104">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="7dc4d-p101">部署一个或多个每用户位置策略是可选的。还可以只部署一个全局级别的位置策略或子网级别的位置策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系对象。未分配特定的子网级别或每用户策略时，会自动默认使用全局级别位置策略中定义的增强型 9-1-1 (E9-1-1) 设置。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="7dc4d-109">创建至少一个每用户位置策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器应用于特定用户发出的紧急呼叫的设置。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-109">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="7dc4d-110">有关所有可用位置策略设置的列表，请参阅 [定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-110">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="7dc4d-111">有关创建位置策略的详细信息，请参阅 [在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-111">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="7dc4d-112">使用 Lync Server 控制面板分配每用户位置策略</span><span class="sxs-lookup"><span data-stu-id="7dc4d-112">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7dc4d-113">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7dc4d-114">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7dc4d-115">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7dc4d-116">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7dc4d-117">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="7dc4d-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="7dc4d-118">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="7dc4d-119">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="7dc4d-120">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="7dc4d-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="7dc4d-121">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="7dc4d-122">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="7dc4d-123">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="7dc4d-124">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="7dc4d-125">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="7dc4d-126">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-126">Click **Find**.</span></span>

6.  <span data-ttu-id="7dc4d-127">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="7dc4d-128">如果您希望将相同的每用户位置策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”<STRONG></STRONG>，然后单击“分配策略”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-128">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="7dc4d-129">在“分配策略”\*\*\*\* 中的“位置策略”\*\*\*\* 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7dc4d-129">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="7dc4d-130">由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置，因此默认情况下会为对话框中的每个策略选择 " <STRONG> &lt; &gt; 保持为</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-130">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="7dc4d-131">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="7dc4d-132">允许 Lync Server 2013 自动选择全局级别策略或子网级策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-132">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="7dc4d-133">单击先前通过运行 **New-CsLocationPolicy** cmdlet 定义的每用户位置策略的名称。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-133">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="7dc4d-134">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-134">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="7dc4d-135">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="7dc4d-136">使用 Lync Server 命令行管理程序 Cmdlet 分配 Per-User 位置策略</span><span class="sxs-lookup"><span data-stu-id="7dc4d-136">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="7dc4d-137">您可以使用 Grant-CsLocationPolicy cmdlet 分配每用户位置策略。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-137">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="7dc4d-138">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-138">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7dc4d-139">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="7dc4d-140">将每用户位置策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="7dc4d-140">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="7dc4d-141">以下命令将每用户位置策略 RedmondLocationPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-141">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="7dc4d-142">将每用户位置策略分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="7dc4d-142">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="7dc4d-143">此命令将每用户位置策略 AccountingDepartmentLocationPolicy 分配给就职于 Accounting 部门的所有用户。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-143">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="7dc4d-144">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅 [get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="7dc4d-145">取消分配每用户位置策略</span><span class="sxs-lookup"><span data-stu-id="7dc4d-145">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="7dc4d-p106">以下命令取消分配之前分配给 Ken Myer 的所有每用户位置策略。取消分配每用户策略后，将使用全局策略或其本地站点策略（如果存在）自动管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="7dc4d-149">有关详细信息，请参阅 [new-cslocationpolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7dc4d-149">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

