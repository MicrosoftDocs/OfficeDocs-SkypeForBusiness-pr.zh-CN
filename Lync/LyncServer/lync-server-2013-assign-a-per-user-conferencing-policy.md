---
title: 'Lync Server 2013: 分配每用户会议策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837918"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="c3fd9-102">在 Lync Server 2013 中分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="c3fd9-103">会议策略是您可以在 Lync Server "控制面板" 中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="c3fd9-104">部署一个或多个每用户会议策略是可选的。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-104">Deploying one or more per-user conferencing policies is optional.</span></span> <span data-ttu-id="c3fd9-105">您也可以仅部署全局级别的会议策略或网站级别的会议策略。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-105">You can also deploy only a global-level conferencing policy or site-level conferencing policy.</span></span> <span data-ttu-id="c3fd9-106">如果你确实要部署每用户策略, 则必须将它们显式分配给用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span> <span data-ttu-id="c3fd9-107">会议用户权利和权限自动默认为在未分配特定网站级或每用户策略时全局级别会议策略中定义的用户。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-107">Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="c3fd9-108">创建至少一个每用户会议策略后, 请使用本主题中的过程分配策略, 该策略指定你希望服务器授予由特定用户组织的会议的用户权利和权限。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="c3fd9-109">有关所有可用会议策略设置的列表, 请参阅[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="c3fd9-110">有关创建会议策略的详细信息, 请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="c3fd9-111">分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="c3fd9-112">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3fd9-113">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c3fd9-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c3fd9-115">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c3fd9-116">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="c3fd9-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="c3fd9-117">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="c3fd9-118">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="c3fd9-119">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="c3fd9-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="c3fd9-120">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="c3fd9-121">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="c3fd9-122">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="c3fd9-123">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="c3fd9-124">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="c3fd9-125">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-125">Click **Find**.</span></span>

6.  <span data-ttu-id="c3fd9-126">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="c3fd9-127">如果想要将同一每用户会议策略应用于多个用户, 请在搜索结果中选择 "多个用户", 然后单击 "<STRONG>操作</STRONG>", 然后单击 "<STRONG>分配策略</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="c3fd9-128">在 "**分配策略**" 下的 "**会议策略**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="c3fd9-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="c3fd9-129">由于有多个策略可在 "<STRONG>分配策略</STRONG>" 中进行配置, 因此默认情况下为对话框中的每个策略选中 " <STRONG> &lt;保持&gt; </STRONG>原样"。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="c3fd9-130">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="c3fd9-131">选择\*\* \<"\>自动\*\*" 允许 Lync Server 2013 自动选择全局级别策略, 或选择 "网站级别策略" (如果已定义)。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="c3fd9-132">单击您以前在 "**会议策略**" 页面上定义的每用户会议策略的名称。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="c3fd9-133">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="c3fd9-134">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c3fd9-135">使用 Windows PowerShell Cmdlet 分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c3fd9-136">每用户会议策略可以使用 Windows PowerShell 和 CsConferencingPolicy cmdlet 进行分配。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="c3fd9-137">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c3fd9-138">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="c3fd9-139">将每用户会议策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="c3fd9-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="c3fd9-140">以下命令将每用户会议策略 RedmondConferencingPolicy 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="c3fd9-141">将每用户会议策略分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="c3fd9-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="c3fd9-142">此命令将每用户会议策略 HRConferencingPolicy 分配给工作人力资源部门的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="c3fd9-143">有关此命令中使用的 LdapFilter 参数的详细信息, 请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="c3fd9-144">取消分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="c3fd9-145">以下命令取消之前分配给 Ken Myer 的任何每用户会议策略。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-145">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="c3fd9-146">取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="c3fd9-147">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="c3fd9-148">有关详细信息, 请参阅[CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c3fd9-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3fd9-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3fd9-149">See Also</span></span>


[<span data-ttu-id="c3fd9-150">在 Lync Server 2013 中创建或修改会议策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="c3fd9-151">在 Lync Server 2013 中分配每个用户的策略</span><span class="sxs-lookup"><span data-stu-id="c3fd9-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

