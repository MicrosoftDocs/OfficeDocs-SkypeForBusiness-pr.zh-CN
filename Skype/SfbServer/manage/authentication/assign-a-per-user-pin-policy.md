---
title: 在 Skype for Business Server 中分配每用户 PIN 策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：为 Skype for Business Server 阶段 AV 和 OAuth 证书。
ms.openlocfilehash: a5cd533dccffb878fad7d7562ded3da301fc0ce3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096828"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="c8b5b-103">在 Skype for Business Server 中分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="c8b5b-104">**摘要：** 为 Skype for Business Server 阶段 AV 和 OAuth 证书。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8b5b-105">电话拨入式会议个人标识号 (PIN) 策略是可在 Skype for Business Server 控制面板中配置的用户帐户的单个设置之一。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="c8b5b-p101">部署一个或多个每用户 PIN 策略是可选的。还可以只部署一个全局级别的 PIN 策略或站点级别的 PIN 策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。未分配特定的站点级别或每用户策略时，用户在电话拨入式会议中使用 PIN 的权限将自动默认为全局级别的 PIN 策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="c8b5b-110">创建至少一个每用户 PIN 策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器对特定用户创建和使用的 PIN 施加的约束。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="c8b5b-111">分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="c8b5b-112">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c8b5b-113">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c8b5b-114">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c8b5b-115">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="c8b5b-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="c8b5b-116">在“搜索用户”框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="c8b5b-117">如果具有保存的查询，请单击“打开查询”图标，使用“打开”对话框来检索该查询（.usf 文件），然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c8b5b-118">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="c8b5b-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c8b5b-119">a.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-119">a.</span></span> <span data-ttu-id="c8b5b-120">单击“添加筛选器”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c8b5b-121">b.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-121">b.</span></span> <span data-ttu-id="c8b5b-122">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c8b5b-123">c.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-123">c.</span></span> <span data-ttu-id="c8b5b-124">在“等于”下拉列表中，单击运算符（例如“等于”或“不等于”）。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c8b5b-125">d.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-125">d.</span></span> <span data-ttu-id="c8b5b-126">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8b5b-127">要向查询中添加附加搜索子句，请单击“添加筛选器”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c8b5b-128">e.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-128">e.</span></span> <span data-ttu-id="c8b5b-129">单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="c8b5b-130">在搜索结果中单击某个用户，再单击“操作”，然后单击“分配策略”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8b5b-131">如果您希望将相同的每用户 PIN 策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”，然后单击“分配策略”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="c8b5b-132">在“分配策略”中的“PIN 策略”下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c8b5b-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8b5b-133">由于可以使用"分配策略"对话框配置多个策略，因此默认情况下会为对话框内每个策略选择 **\<Keep as is\>** 策略。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="c8b5b-134">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="c8b5b-135">允许 Skype for Business Server 自动选择全局级别的策略或站点级别策略（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="c8b5b-136">单击之前在“PIN 策略”页中定义的每用户 PIN 策略的名称。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="c8b5b-137">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="c8b5b-138">完成后，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8b5b-139">使用 cmdlet Per-User分配Windows PowerShell PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8b5b-140">可以使用 Windows PowerShell 和 **Grant-CsPinPolicy** cmdlet 分配每用户 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="c8b5b-141">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8b5b-142">有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8b5b-143">此过程在 Skype for Business Server 中是相同的。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="c8b5b-144">为单个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="c8b5b-145">以下命令为用户 Ken Myer 分配每用户 PIN 策略 RedmondPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="c8b5b-146">为多个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="c8b5b-147">以下命令为工作于 Redmond 市的所有用户分配每用户 PIN 策略 RedmondUsersPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c8b5b-148">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="c8b5b-149">取消分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="c8b5b-p110">以下命令取消分配之前分配给 Ken Myer 的任何每用户 PIN 策略。取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="c8b5b-153">有关详细信息，请参阅 [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8b5b-153">For details, see [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8b5b-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8b5b-154">See also</span></span>

[<span data-ttu-id="c8b5b-155">在 Skype for Business Server 中创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="c8b5b-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)