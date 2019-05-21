---
title: 管理 Skype for business Server 的用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的部分介绍了如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。
ms.openlocfilehash: 83ab64415b21d37f12d3768feeb39b11491787af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275106"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="490af-103">管理 Skype for business Server 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="490af-104">本文中的部分介绍了如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="490af-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="490af-105">有关如何启用 Active Directory 用户的信息, 请参阅[创建新的用户帐户](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="490af-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="490af-106">有关如何删除 Active Directory 用户的信息, 请参阅[删除用户帐户](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="490af-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="490af-107">当使用 Skype for business 时, 应在维护窗口期间执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="490af-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="490af-108">无论是按每天还是按周计划完成, 都将根据您的组织的需求确定。</span><span class="sxs-lookup"><span data-stu-id="490af-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="490af-109">本文包含以下过程:</span><span class="sxs-lookup"><span data-stu-id="490af-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="490af-110">搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="490af-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="490af-111">添加和启用新的 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="490af-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="490af-112">禁用或重新启用以前为 Skype for Business 服务器启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="490af-113">禁用企业语音的用户</span><span class="sxs-lookup"><span data-stu-id="490af-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="490af-114">使用 Skype for Business 服务器命令行管理程序删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="490af-115">搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="490af-115">To search for one or more users</span></span>
<span data-ttu-id="490af-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-116"></span></span>

<span data-ttu-id="490af-117">你可以使用搜索查询的结果为 Skype for business 服务器配置 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="490af-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="490af-118">可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。</span><span class="sxs-lookup"><span data-stu-id="490af-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="490af-119">您可以使用 Skype for Business 服务器控制面板或 Active Directory 用户和计算机管理单元搜索用户。</span><span class="sxs-lookup"><span data-stu-id="490af-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="490af-120">以下过程介绍了如何使用 Skype for Business 服务器控制面板搜索用户。</span><span class="sxs-lookup"><span data-stu-id="490af-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="490af-121">在具有中央林拓扑的环境中, 当您按用户的电子邮件地址搜索用户时, 搜索结果可能不准确。</span><span class="sxs-lookup"><span data-stu-id="490af-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="490af-122">而是可以通过指定 SIP 地址前缀 (例如 sip: name、添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址) 搜索用户, 或使用**move-csuser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="490af-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="490af-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="490af-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="490af-124">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="490af-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="490af-125">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="490af-126">在 "**搜索用户**" 框中, 键入要搜索的用户帐户的所有或第一部分的显示名称、名字、姓氏、SAM 帐户名称、SIP 地址或行 URI, 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="490af-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="490af-127">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="490af-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="490af-128">a.</span><span class="sxs-lookup"><span data-stu-id="490af-128">a.</span></span> <span data-ttu-id="490af-129">单击 "**搜索结果**" 上方屏幕右上角的展开箭头按钮, 然后单击 "**添加筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="490af-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="490af-130">b.</span><span class="sxs-lookup"><span data-stu-id="490af-130">b.</span></span> <span data-ttu-id="490af-131">通过键入或单击下拉列表中的箭头来输入用户属性, 以选择用户属性。</span><span class="sxs-lookup"><span data-stu-id="490af-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="490af-132">c.</span><span class="sxs-lookup"><span data-stu-id="490af-132">c.</span></span> <span data-ttu-id="490af-133">在 "**等于**" 列表中, 单击 "**等于**或**不等于**"。</span><span class="sxs-lookup"><span data-stu-id="490af-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="490af-134">d.</span><span class="sxs-lookup"><span data-stu-id="490af-134">d.</span></span> <span data-ttu-id="490af-135">在 "文本" 框中, 键入要用于筛选搜索结果的搜索条件, 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="490af-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="490af-136">搜索结果将显示在 "**搜索结果**" 下。</span><span class="sxs-lookup"><span data-stu-id="490af-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="490af-137">您可以选择列表中的任意用户或所有用户, 并在所选用户上执行配置任务。</span><span class="sxs-lookup"><span data-stu-id="490af-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="490af-138">添加和启用新的 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="490af-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="490af-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-139"></span></span>

<span data-ttu-id="490af-140">在 Active Directory 用户和计算机中启用用户帐户后, 您可以使用 Skype for business Server 控制面板创建并启用新的 Skype for business 服务器用户帐户, 方法是将 Active Directory 用户添加到 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="490af-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="490af-141">你还可以使用 cmdlet, 特别是[Enable-move-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="490af-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="490af-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="490af-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="490af-143">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="490af-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="490af-144">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="490af-145">单击 "**启用用户**"。</span><span class="sxs-lookup"><span data-stu-id="490af-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="490af-146">在 "**新建 Lync Server 用户**" 对话框中, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="490af-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="490af-147">在 "**搜索用户**" 框中, 键入所需的 Active Directory 用户帐户的所有或第一部分名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、电子邮件地址、用户主体名称 (UPN) 或电话号码, 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="490af-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="490af-148">在表中, 选择要添加到 Skype for business 服务器的帐户, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="490af-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="490af-149">将用户分配到池, 指定任何其他详细信息, 并将策略分配给所需的用户, 然后单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="490af-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="490af-150">禁用或重新启用以前为 Skype for Business 服务器启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="490af-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-151"></span></span>

<span data-ttu-id="490af-152">你可以使用以下过程在 Skype for Business Server 中禁用以前启用的用户帐户, 而不会丢失为用户帐户配置的 Skype for Business 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="490af-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="490af-153">由于您不会丢失 Skype for Business 服务器用户帐户设置, 您可以重新启用以前启用的用户帐户, 而无需重新配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="490af-154">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="490af-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="490af-155">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="490af-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="490af-156">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="490af-157">在 "**搜索用户**" 框中, 键入要禁用或重新启用的用户帐户的全部或第一部分的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、SIP 地址或行统一资源标识符 (URI)。然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="490af-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="490af-158">在表中, 单击要禁用或重新启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="490af-159">在 "**操作**" 菜单上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="490af-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="490af-160">若要暂时禁用 Skype for business 服务器的用户帐户, 请单击 " **Lync Server 暂时禁用**"。</span><span class="sxs-lookup"><span data-stu-id="490af-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="490af-161">若要启用 Skype for business Server 的用户帐户, 请单击 " **Lync Server 重新启用**"。</span><span class="sxs-lookup"><span data-stu-id="490af-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="490af-162">使用 Windows Powershell 禁用或重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="490af-163">用户帐户可以暂时禁用, 然后在稍后通过使用**move-csuser** cmdlet 重新启用。</span><span class="sxs-lookup"><span data-stu-id="490af-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="490af-164">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="490af-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="490af-165">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="490af-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="490af-166">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="490af-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="490af-167">禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-167">To disable a user account</span></span>

- <span data-ttu-id="490af-168">若要暂时禁用用户帐户, 请将 Enabled 属性的值设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="490af-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="490af-169">例如：</span><span class="sxs-lookup"><span data-stu-id="490af-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="490af-170">重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-170">To re-enable a user account</span></span>

- <span data-ttu-id="490af-171">若要重新启用已禁用的用户帐户, 请将 Enabled 属性的值设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="490af-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="490af-172">例如：</span><span class="sxs-lookup"><span data-stu-id="490af-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="490af-173">有关详细信息, 请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="490af-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="490af-174">禁用企业语音的用户</span><span class="sxs-lookup"><span data-stu-id="490af-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="490af-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-175"></span></span>

<span data-ttu-id="490af-176">使用以下过程可为 Skype for business 服务器启用的用户帐户禁用企业语音。</span><span class="sxs-lookup"><span data-stu-id="490af-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="490af-177">禁用企业语音的用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="490af-178">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="490af-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="490af-179">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="490af-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="490af-180">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="490af-181">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="490af-182">在表中, 单击要为企业语音启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="490af-183">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="490af-184">在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下, 单击除**企业语音**之外的任何选项。</span><span class="sxs-lookup"><span data-stu-id="490af-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="490af-185">若要限制用户使用 Lync 进行音频或视频呼叫, 请在 "**电话服务**" 下, 单击 "**音频/视频已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="490af-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="490af-186">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="490af-186">Click **Commit**.</span></span>

<span data-ttu-id="490af-187">用户现在无法使用企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="490af-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="490af-188">相关信息:</span><span class="sxs-lookup"><span data-stu-id="490af-188">Related information:</span></span> <br/>[<span data-ttu-id="490af-189">企业语音和移动性</span><span class="sxs-lookup"><span data-stu-id="490af-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="490af-190">在 Skype for business 服务器中启用企业语音用户</span><span class="sxs-lookup"><span data-stu-id="490af-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="490af-191">Skype for Business Server 管理程序</span><span class="sxs-lookup"><span data-stu-id="490af-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="490af-192">使用 Skype for Business 服务器命令行管理程序删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="490af-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-193"></span></span>

<span data-ttu-id="490af-194">你可以使用以下过程在 Skype for Business Server 中删除以前添加的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="490af-195">删除用户将导致你丢失为用户帐户配置的任何设置。</span><span class="sxs-lookup"><span data-stu-id="490af-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="490af-196">如果想要暂时禁用用户帐户, 请参阅[禁用或重新启用以前为 Skype for Business 服务器启用的用户帐户](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="490af-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="490af-197">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="490af-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="490af-198">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="490af-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="490af-199">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="490af-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="490af-200">在 "**搜索用户**" 框中, 键入要禁用或重新启用的用户帐户的全部或第一部分的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、SIP 地址或行统一资源标识符 (URI)。然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="490af-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="490af-201">在表中, 单击要删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="490af-202">在 "**操作**" 菜单上, 选择 "**从 Lync Server 中删除**", 将出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="490af-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="490af-203">从对话框中, 选择 **"确定"** 以删除用户。</span><span class="sxs-lookup"><span data-stu-id="490af-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="490af-204">使用 Windows Powershell cmdlet 删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="490af-205">你可以使用 Move-csuser cmdlet 删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="490af-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="490af-206">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="490af-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="490af-207">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="490af-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="490af-208">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="490af-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="490af-209">删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="490af-209">To remove a user account</span></span>
<span data-ttu-id="490af-210">若要删除用户帐户, 请使用 Disable-Move-csuser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="490af-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="490af-211">例如：</span><span class="sxs-lookup"><span data-stu-id="490af-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="490af-212">有关详细信息, 请参阅 Disable cmdlet 的帮助主题[move-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="490af-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="490af-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="490af-213">See also</span></span>
<span data-ttu-id="490af-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="490af-214"></span></span>

[<span data-ttu-id="490af-215">Enable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="490af-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="490af-216">Disable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="490af-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
