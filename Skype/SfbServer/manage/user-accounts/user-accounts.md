---
title: 管理用户帐户的 Skype 业务服务器 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文各部分描述如何启用、 暂时禁用或删除 Active Directory 用户 Skype 业务服务器 2015年个。
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a><span data-ttu-id="b3c3b-103">管理用户帐户的 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="b3c3b-103">Manage user accounts for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b3c3b-104">本文各部分描述如何启用、 暂时禁用或删除 Active Directory 用户 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b3c3b-105">有关如何启用 Active Directory 用户的信息，请参阅[创建新用户帐户](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="b3c3b-106">有关如何删除 Active Directory 用户的信息，请参阅[删除用户帐户](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>
  
<span data-ttu-id="b3c3b-107">维护期间，应执行这些过程，供业务使用 Skype 时最低。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="b3c3b-108">这完成每日或每周的时间表取决于组织的需要。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span> 
  
<span data-ttu-id="b3c3b-109">本文包含以下过程：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-109">This article contains the following procedures:</span></span>
  
- [<span data-ttu-id="b3c3b-110">若要搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-110">To search for one or more users</span></span>](user-accounts.md#Search)
    
- [<span data-ttu-id="b3c3b-111">添加并启用新的 Skype 业务服务器 2015年用户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-111">Add and enable a new Skype for Business Server 2015 user</span></span>](user-accounts.md#Add)
    
- [<span data-ttu-id="b3c3b-112">禁用或重新启用以前为 Skype 业务服务器启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)
    
- [<span data-ttu-id="b3c3b-113">禁用用户的企业语音</span><span class="sxs-lookup"><span data-stu-id="b3c3b-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)
    
- [<span data-ttu-id="b3c3b-114">删除业务服务器管理外壳有 Skype 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="b3c3b-115">若要搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-115">To search for one or more users</span></span>
<span data-ttu-id="b3c3b-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-116"></span></span>

<span data-ttu-id="b3c3b-117">搜索查询的结果可用于配置业务服务器 2015年的 Active Directory 用户 Skype。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server 2015.</span></span> <span data-ttu-id="b3c3b-118">可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>
  
<span data-ttu-id="b3c3b-119">可以搜索用户使用 Skype 业务服务器控件面板或 Active Directory 用户和计算机管理单元中。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="b3c3b-120">下面的过程介绍如何使用 Skype 业务服务器的控制面板来搜索用户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3c3b-121">在与中央林拓扑环境中，搜索结果可能不准确时由用户的电子邮件地址搜索用户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="b3c3b-122">相反，您可以通过指定 SIP 地址前缀，例如，sip： 名称来搜索用户、 添加搜索筛选器和选择 SIP 地址包含一个部分的电子邮件地址，或使用**Get CSUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>
  
1. <span data-ttu-id="b3c3b-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b3c3b-124">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3c3b-125">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-125">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b3c3b-126">在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 SAM 帐户名的第一部分中，SIP 地址，或线形 URI 以搜索，然后单击**查找**所需的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b3c3b-127">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-127">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="b3c3b-128">a.</span><span class="sxs-lookup"><span data-stu-id="b3c3b-128">a.</span></span> <span data-ttu-id="b3c3b-129">单击上面的**搜索结果**，在屏幕的右上角的展开箭头按钮，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
   <span data-ttu-id="b3c3b-130">b.</span><span class="sxs-lookup"><span data-stu-id="b3c3b-130">b.</span></span> <span data-ttu-id="b3c3b-131">通过键入或单击下拉列表中选择一个用户属性中的箭头来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
   <span data-ttu-id="b3c3b-132">c.</span><span class="sxs-lookup"><span data-stu-id="b3c3b-132">c.</span></span> <span data-ttu-id="b3c3b-133">在**等于**列表中单击**等于**或**不等于**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
   <span data-ttu-id="b3c3b-134">d.</span><span class="sxs-lookup"><span data-stu-id="b3c3b-134">d.</span></span> <span data-ttu-id="b3c3b-135">在文本框中，键入要用来筛选搜索结果的搜索条件，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>
    
6. <span data-ttu-id="b3c3b-136">搜索结果将显示在**搜索结果**下。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="b3c3b-137">可以选择任何或所有用户的列表中，并在您都选择的用户上执行配置任务。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a><span data-ttu-id="b3c3b-138">添加并启用新的 Skype 业务服务器 2015年用户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-138">Add and enable a new Skype for Business Server 2015 user</span></span>
<span data-ttu-id="b3c3b-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-139"></span></span>

<span data-ttu-id="b3c3b-140">启用 Active Directory 用户和计算机中的用户帐户之后, 可以使用 Skype 业务服务器的控制面板来创建并启用新 Skype 业务服务器 2015年用户帐户通过 Active Directory 用户向 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server 2015 user accounts by adding an Active Directory user to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b3c3b-141">您还可以使用 cmdlet，专门[启用 CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>
  
1. <span data-ttu-id="b3c3b-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b3c3b-143">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b3c3b-144">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b3c3b-145">单击**启用用户**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-145">Click **Enable users**.</span></span>
    
5. <span data-ttu-id="b3c3b-146">在**新的 Lync Server 用户**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-146">On the **New Lync Server User** dialog, click **Add**.</span></span>
    
6. <span data-ttu-id="b3c3b-147">在**搜索用户**框中，键入全部或名称的第一部分，显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名称、 电子邮件地址、 用户主体名称 (UPN) 或 Active Directory 用户帐户所需的电话号码然后单击**寻找**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>
    
7. <span data-ttu-id="b3c3b-148">在表中，选择您想要添加到 Skype 的业务服务器 2015，的帐户，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-148">In the table, select the account you want to add to Skype for Business Server 2015, and then click **OK**.</span></span>
    
8. <span data-ttu-id="b3c3b-149">将用户分配到池、 指定任何附加的详细信息，并将策略分配到用户所需，，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="b3c3b-150">禁用或重新启用以前为 Skype 业务服务器启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="b3c3b-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-151"></span></span>

<span data-ttu-id="b3c3b-152">可以使用下面的过程而不会丢失您为用户帐户配置的业务服务器设置为 Skype 业务服务器禁用 Skype 在以前已启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="b3c3b-153">因为您不会丢失业务服务器用户帐户设置的 Skype，您可以重新启用以前已启用的用户帐户再次而无需重新配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span> 
  
1. <span data-ttu-id="b3c3b-154">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b3c3b-155">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3c3b-156">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-156">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b3c3b-157">在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您想要禁用或重新启用，行的第一个部分中然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b3c3b-158">在表中，单击您想要禁用或重新启用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-158">In the table, click the user account that you want to disable or re-enable.</span></span>
    
6. <span data-ttu-id="b3c3b-159">在**操作**菜单上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-159">On the **Action** menu, do one of the following:</span></span>
    
   - <span data-ttu-id="b3c3b-160">要暂时禁用用户帐户 Skype 业务服务器，请单击**暂时禁用 Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>
    
   - <span data-ttu-id="b3c3b-161">若要启用业务服务器的 Skype 的用户帐户，请单击**重新启用的 Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="b3c3b-162">使用 Windows Powershell 禁用或重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="b3c3b-163">用户帐户可以暂时禁用，然后稍后再重新启用，通过**一组 CsUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b3c3b-164">可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b3c3b-165">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b3c3b-166">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-166">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account"></a><span data-ttu-id="b3c3b-167">要禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-167">To disable a user account</span></span>

- <span data-ttu-id="b3c3b-168">若要暂时禁用用户帐户，请将已启用属性的值为 False ($False)</span><span class="sxs-lookup"><span data-stu-id="b3c3b-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="b3c3b-169">例如：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-169">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="b3c3b-170">若要重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-170">To re-enable a user account</span></span>

- <span data-ttu-id="b3c3b-171">要重新启用已禁用的用户帐户，设置为 True ($True) 的已启用属性的值。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="b3c3b-172">例如：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-172">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="b3c3b-173">有关详细信息，请参阅[设置 CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="b3c3b-174">禁用用户的企业语音</span><span class="sxs-lookup"><span data-stu-id="b3c3b-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="b3c3b-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-175"></span></span>

<span data-ttu-id="b3c3b-176">使用以下过程禁用用户帐户启用的 Skype 业务服务器 2015年企业语音。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server 2015.</span></span>
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="b3c3b-177">针对企业语音禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="b3c3b-178">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b3c3b-179">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3c3b-180">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-180">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b3c3b-181">在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b3c3b-182">在表中，单击您想要启用的企业语音的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="b3c3b-183">在“编辑”****菜单上，单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-183">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="b3c3b-184">在**编辑 Lync 服务器用户**页上，在**电话**中，单击除**企业语音**之外的任何选项。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b3c3b-185">若要限制用户只能进行音频或视频呼叫使用 Lync 下**电话**，, 请单击**禁用音频/视频**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span> 
  
8. <span data-ttu-id="b3c3b-186">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-186">Click **Commit**.</span></span>
    
<span data-ttu-id="b3c3b-187">现在，用户不能使用企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="b3c3b-188">相关的信息：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-188">Related information:</span></span> <br/>[<span data-ttu-id="b3c3b-189">企业语音和移动性</span><span class="sxs-lookup"><span data-stu-id="b3c3b-189">Enterprise Voice and mobility</span></span>](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="b3c3b-190">启用用户的 Skype 在企业语音的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="b3c3b-190">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="b3c3b-191">Skype 的业务服务器 2015年管理外壳程序</span><span class="sxs-lookup"><span data-stu-id="b3c3b-191">Skype for Business Server 2015 Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="b3c3b-192">删除业务服务器管理外壳有 Skype 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="b3c3b-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-193"></span></span>

<span data-ttu-id="b3c3b-194">可以使用以下过程可在 Skype 业务服务器 2015年移除以前添加的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-194">You can use the following procedure to remove a previously added user account in Skype for Business Server 2015.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b3c3b-195">删除用户将导致丢失您的用户帐户配置的任何设置。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="b3c3b-196">如果您想要临时改为禁用的用户帐户，请参阅[禁用或重新启用以前为 Skype 业务服务器的已启用用户帐户](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span> 
  
1. <span data-ttu-id="b3c3b-197">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b3c3b-198">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3c3b-199">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-199">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b3c3b-200">在**搜索用户**框中，键入全部或显示名称、 名字、 姓氏、 安全帐户管理器 (SAM) 帐户名、 SIP 地址或统一资源标识符 (URI) 的用户帐户，您想要禁用或重新启用，行的第一个部分中然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b3c3b-201">在表中，单击要删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-201">In the table, click the user account that you want to remove.</span></span>
    
6. <span data-ttu-id="b3c3b-202">在**操作**菜单，选择**从 Lync Server 中删除**，和一个对话框显示框。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>
    
7. <span data-ttu-id="b3c3b-203">从对话框中，选择**确定**以删除用户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-203">From the dialog box, select **OK** to remove the user.</span></span>
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="b3c3b-204">删除用户帐户与 Windows Powershell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b3c3b-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="b3c3b-205">通过禁用 CsUser cmdlet，您可以删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="b3c3b-206">从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="b3c3b-207">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b3c3b-208">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-208">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-user-account"></a><span data-ttu-id="b3c3b-209">若要删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c3b-209">To remove a user account</span></span>
<span data-ttu-id="b3c3b-210">若要删除一个用户帐户，请使用禁用 CsUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="b3c3b-211">例如：</span><span class="sxs-lookup"><span data-stu-id="b3c3b-211">For example:</span></span>
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
<span data-ttu-id="b3c3b-212">有关详细信息，请参阅[禁用 CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b3c3b-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3c3b-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3c3b-213">See also</span></span>
<span data-ttu-id="b3c3b-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="b3c3b-214"></span></span>

#### 

[<span data-ttu-id="b3c3b-215">启用 CsUser</span><span class="sxs-lookup"><span data-stu-id="b3c3b-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[<span data-ttu-id="b3c3b-216">禁用-CsUser</span><span class="sxs-lookup"><span data-stu-id="b3c3b-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

