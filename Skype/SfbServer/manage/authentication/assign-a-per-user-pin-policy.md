---
title: 在 Skype for Business Server 2015 中分配每用户 PIN 策略
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要： 用于业务服务器 2015年的 Skype 阶段 AV 和 OAuth 证书。
ms.openlocfilehash: a103d6463a02cd00d71769b8f86b43fae514a19d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504955"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="75767-103">在 Skype for Business Server 2015 中分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-103">Assign a per-user PIN policy in Skype for Business Server 2015</span></span>

<span data-ttu-id="75767-104">**摘要：** 为业务服务器 2015 Skype 的阶段 AV 和 OAuth 证书。</span><span class="sxs-lookup"><span data-stu-id="75767-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75767-105">电话拨入式会议个人标识号 (pin) 策略是可以为业务 Server Control Panel Skype 中配置的用户帐户的各项设置之一。</span><span class="sxs-lookup"><span data-stu-id="75767-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="75767-p101">部署一个或多个每用户 PIN 策略是可选的。还可以只部署一个全局级别的 PIN 策略或站点级别的 PIN 策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。未分配特定的站点级别或每用户策略时，用户在电话拨入式会议中使用 PIN 的权限将自动默认为全局级别的 PIN 策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="75767-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="75767-110">创建至少一个每用户 PIN 策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器对特定用户创建和使用的 PIN 施加的约束。</span><span class="sxs-lookup"><span data-stu-id="75767-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="75767-111">分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="75767-112">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="75767-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="75767-113">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="75767-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="75767-114">在左导航栏中，单击“用户”****。</span><span class="sxs-lookup"><span data-stu-id="75767-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="75767-115">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="75767-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="75767-116">在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。</span><span class="sxs-lookup"><span data-stu-id="75767-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="75767-117">如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。</span><span class="sxs-lookup"><span data-stu-id="75767-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="75767-118">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="75767-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="75767-119">a.</span><span class="sxs-lookup"><span data-stu-id="75767-119">a.</span></span> <span data-ttu-id="75767-120">单击“添加筛选器”****。</span><span class="sxs-lookup"><span data-stu-id="75767-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="75767-121">b.</span><span class="sxs-lookup"><span data-stu-id="75767-121">b.</span></span> <span data-ttu-id="75767-122">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="75767-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="75767-123">c.</span><span class="sxs-lookup"><span data-stu-id="75767-123">c.</span></span> <span data-ttu-id="75767-124">在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。</span><span class="sxs-lookup"><span data-stu-id="75767-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="75767-125">d.</span><span class="sxs-lookup"><span data-stu-id="75767-125">d.</span></span> <span data-ttu-id="75767-126">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="75767-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="75767-127">要向查询中添加附加搜索子句，请单击“添加筛选器”****。</span><span class="sxs-lookup"><span data-stu-id="75767-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="75767-128">e。</span><span class="sxs-lookup"><span data-stu-id="75767-128">e.</span></span> <span data-ttu-id="75767-129">单击“查找”****。</span><span class="sxs-lookup"><span data-stu-id="75767-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="75767-130">在搜索结果中单击某个用户，再单击“操作”****，然后单击“分配策略”****。</span><span class="sxs-lookup"><span data-stu-id="75767-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="75767-131">如果您希望将相同的每用户 PIN 策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”****，然后单击“分配策略”****。</span><span class="sxs-lookup"><span data-stu-id="75767-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="75767-132">在“分配策略”**** 中的“PIN 策略”**** 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="75767-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="75767-133">由于存在您可以使用**分配策略**对话框中，配置的多个策略**\<保持原样\>** 默认情况下，在对话框中的每个策略处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="75767-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="75767-134">如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="75767-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="75767-135">允许业务服务器 2015 自动选择全局级别策略的 Skype 或，如果已定义站点级别的策略。</span><span class="sxs-lookup"><span data-stu-id="75767-135">Allow Skype for Business Server 2015 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="75767-136">单击之前在“PIN 策略”**** 页中定义的每用户 PIN 策略的名称。</span><span class="sxs-lookup"><span data-stu-id="75767-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="75767-137">为帮助您确定要分配的策略，请在单击策略名称后单击“查看”**** 以查看策略中定义的用户权限。</span><span class="sxs-lookup"><span data-stu-id="75767-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="75767-138">完成后，单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="75767-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75767-139">使用 Windows PowerShell Cmdlet 分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75767-140">您可以使用 Windows PowerShell 和**Grant-cspinpolicy** cmdlet 分配每用户 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="75767-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="75767-141">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="75767-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75767-142">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="75767-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="75767-143">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="75767-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="75767-144">为单个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="75767-145">以下命令为用户 Ken Myer 分配每用户 PIN 策略 RedmondPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="75767-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="75767-146">为多个用户分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="75767-147">以下命令为工作于 Redmond 市的所有用户分配每用户 PIN 策略 RedmondUsersPinPolicy。</span><span class="sxs-lookup"><span data-stu-id="75767-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="75767-148">有关 LdapFilter 参数在此命令中使用的详细信息，请参阅[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="75767-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="75767-149">取消分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="75767-p110">以下命令取消分配之前分配给 Ken Myer 的任何每用户 PIN 策略。取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="75767-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="75767-153">有关详细信息，请参阅[Grant-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="75767-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75767-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75767-154">See also</span></span>

[<span data-ttu-id="75767-155">为业务服务器 2015 Skype 创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="75767-155">Create a new PIN policy in Skype for Business Server 2015</span></span>](create-a-new-pin-policy.md)