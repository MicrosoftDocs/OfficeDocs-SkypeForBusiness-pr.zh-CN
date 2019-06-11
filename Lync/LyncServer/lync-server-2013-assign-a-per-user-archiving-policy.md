---
title: 'Lync Server 2013: 分配每用户存档策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82b2398002a1c2536c9a57b18f9276a9d138903
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837758"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="d9884-102">在 Lync Server 2013 中分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="d9884-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="d9884-103">存档策略是您可以在 Lync Server 2013 "控制面板" 中配置的用户帐户的个人设置之一。</span><span class="sxs-lookup"><span data-stu-id="d9884-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="d9884-104">部署一个或多个每用户存档策略是可选的。</span><span class="sxs-lookup"><span data-stu-id="d9884-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="d9884-105">你还可以仅部署全局级别的存档策略或网站级别的存档策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="d9884-106">如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="d9884-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="d9884-107">当未分配特定的网站级或每用户策略时, 将自动为全局级别的会议策略中定义的存档要求默认设置。</span><span class="sxs-lookup"><span data-stu-id="d9884-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="d9884-108">创建了至少一个每用户存档策略后, 请使用本主题中的过程分配适当指定特定用户的内部通信 (外部通信, 或两者) 是否将由服务器存档的策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="d9884-109">有关创建每用户存档策略的详细信息, 请参阅[在 Lync Server 2013 中创建存档策略, 以启用或禁用特定网站或用户的内部或外部通信的存档](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)。</span><span class="sxs-lookup"><span data-stu-id="d9884-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="d9884-110">分配每个用户的存档策略</span><span class="sxs-lookup"><span data-stu-id="d9884-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="d9884-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d9884-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9884-112">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d9884-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9884-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d9884-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9884-114">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d9884-115">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="d9884-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d9884-116">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d9884-117">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d9884-118">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="d9884-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d9884-119">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d9884-120">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="d9884-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d9884-121">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="d9884-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d9884-122">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="d9884-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="d9884-123">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d9884-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="d9884-124">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-124">Click **Find**.</span></span>

6.  <span data-ttu-id="d9884-125">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“分配策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="d9884-126">如果想要将同一每用户存档策略应用于多个用户, 请在搜索结果中选择 "多个用户", 然后单击 "<STRONG>操作</STRONG>", 然后单击 "<STRONG>分配策略</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="d9884-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="d9884-127">在 "**分配策略**" 下的 "**存档策略**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="d9884-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="d9884-128">由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置, 因此默认情况下为对话框中的每个策略选中 " <STRONG> &lt;保持&gt; </STRONG>原样"。</span><span class="sxs-lookup"><span data-stu-id="d9884-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="d9884-129">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="d9884-130">允许 Lync Server 2013 自动选择全局级别策略或网站级别策略 (如果已定义)。</span><span class="sxs-lookup"><span data-stu-id="d9884-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="d9884-131">单击您以前在 "**存档策略**" 页面上定义的每用户存档策略的名称。</span><span class="sxs-lookup"><span data-stu-id="d9884-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="d9884-132">若要帮助你确定要分配的策略, 请在单击策略名称后单击 "<STRONG>查看</STRONG>" 以查看策略中定义的用户权利和权限。</span><span class="sxs-lookup"><span data-stu-id="d9884-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="d9884-133">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9884-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d9884-134">使用 Windows PowerShell Cmdlet 分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="d9884-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d9884-135">你可以使用 Windows PowerShell 和**CsArchivingPolicy** cmdlet 分配每用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="d9884-136">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9884-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9884-137">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d9884-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="d9884-138">将每用户存档策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="d9884-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="d9884-139">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="d9884-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="d9884-140">将每用户存档策略分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="d9884-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="d9884-141">此命令将每用户存档策略 RedmondArchivingPolicy 分配给所有帐户驻留在注册机构池 atl-cs-001.litwareinc.com 的用户。</span><span class="sxs-lookup"><span data-stu-id="d9884-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d9884-142">有关此命令中使用的 Filter 参数的详细信息, 请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d9884-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="d9884-143">取消分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="d9884-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="d9884-144">以下命令取消之前分配给 Ken Myer 的任何每用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="d9884-145">取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="d9884-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="d9884-146">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="d9884-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="d9884-147">有关详细信息, 请参阅[CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d9884-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9884-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9884-148">See Also</span></span>


[<span data-ttu-id="d9884-149">在 Lync Server 2013 中创建存档策略, 以启用或禁用特定网站或用户的内部或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="d9884-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  


[<span data-ttu-id="d9884-150">在 Lync Server 2013 中分配每个用户的策略</span><span class="sxs-lookup"><span data-stu-id="d9884-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

