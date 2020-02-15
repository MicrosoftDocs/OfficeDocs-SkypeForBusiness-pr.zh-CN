---
title: 管理 Skype for Business Server 的用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各节介绍如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009635"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="1a688-103">管理 Skype for Business Server 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="1a688-104">本文中的各节介绍如何启用、暂时禁用或删除 Skype for Business Server 中的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="1a688-105">有关如何启用 Active Directory 用户的信息，请参阅[创建新用户帐户](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1a688-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="1a688-106">有关如何删除 Active Directory 用户的信息，请参阅[删除用户帐户](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1a688-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="1a688-107">当 Skype for Business 使用率最低时，应在维护时段内执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="1a688-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="1a688-108">您的组织的需求是否取决于每日或每周计划是否完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1a688-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="1a688-109">本文包含以下过程：</span><span class="sxs-lookup"><span data-stu-id="1a688-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="1a688-110">搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="1a688-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="1a688-111">添加和启用新的 Skype for Business Server 用户</span><span class="sxs-lookup"><span data-stu-id="1a688-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="1a688-112">禁用或重新启用之前为 Skype for business Server 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="1a688-113">为用户禁用企业语音</span><span class="sxs-lookup"><span data-stu-id="1a688-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="1a688-114">使用 Skype for Business Server 命令行管理程序删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="1a688-115">搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="1a688-115">To search for one or more users</span></span>
<span data-ttu-id="1a688-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-116"><a name="Search"> </a></span></span>

<span data-ttu-id="1a688-117">您可以使用搜索查询的结果为 Skype for business Server 配置 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="1a688-118">可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="1a688-119">您可以使用 Skype for Business Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="1a688-120">以下过程介绍如何使用 Skype for Business Server 控制面板搜索用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="1a688-121">在具有中央林拓扑的环境中，当您按用户的电子邮件地址搜索用户时，搜索结果可能不准确。</span><span class="sxs-lookup"><span data-stu-id="1a688-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="1a688-122">可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 **Get-CSUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a688-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="1a688-123">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a688-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="1a688-124">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1a688-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a688-125">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="1a688-126">在“搜索用户”\*\*\*\* 框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="1a688-127">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="1a688-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="1a688-128">a.</span><span class="sxs-lookup"><span data-stu-id="1a688-128">a.</span></span> <span data-ttu-id="1a688-129">单击“搜索结果”\*\*\*\* 上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="1a688-130">b.</span><span class="sxs-lookup"><span data-stu-id="1a688-130">b.</span></span> <span data-ttu-id="1a688-131">通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="1a688-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="1a688-132">c.</span><span class="sxs-lookup"><span data-stu-id="1a688-132">c.</span></span> <span data-ttu-id="1a688-133">在“等于”\*\*\*\* 列表中，单击“等于”\*\*\*\* 或“不等于”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="1a688-134">d.</span><span class="sxs-lookup"><span data-stu-id="1a688-134">d.</span></span> <span data-ttu-id="1a688-135">在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="1a688-p110">搜索结果将显示在“搜索结果”\*\*\*\* 下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。</span><span class="sxs-lookup"><span data-stu-id="1a688-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="1a688-138">添加和启用新的 Skype for Business Server 用户</span><span class="sxs-lookup"><span data-stu-id="1a688-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="1a688-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-139"><a name="Add"> </a></span></span>

<span data-ttu-id="1a688-140">在 Active Directory 用户和计算机中启用用户帐户后，可以使用 Skype for Business Server 控制面板通过将 Active Directory 用户添加到 Skype for business Server 来创建和启用新的 Skype for Business Server 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="1a688-141">您还可以使用 cmdlet，特别是[Enable-get-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1a688-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="1a688-142">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a688-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="1a688-143">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1a688-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a688-144">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="1a688-145">单击“启用用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="1a688-146">在“新建 Lync Server 用户”\*\*\*\* 对话框中，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="1a688-147">在“搜索用户”\*\*\*\* 框中，键入所需 Active Directory 用户帐户的完整的名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、电子邮件地址、用户主体名称 (UPN) 或电话号码，或这些内容的第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="1a688-148">在表中，选择要添加到 Skype for business Server 的帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1a688-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="1a688-149">将该用户分配给某个池，指定其他任何详细信息，并向所需用户分配策略，然后单击“启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="1a688-150">禁用或重新启用之前为 Skype for business Server 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="1a688-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="1a688-152">您可以使用以下过程在 Skype for Business Server 中禁用以前启用的用户帐户，而不会丢失为该用户帐户配置的 Skype for Business 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="1a688-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="1a688-153">由于您不会丢失 Skype for Business Server 用户帐户设置，因此您可以重新启用以前启用的用户帐户，而无需重新配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="1a688-154">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a688-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="1a688-155">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1a688-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a688-156">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="1a688-157">在“搜索用户”\*\*\*\* 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="1a688-158">在表中，单击要禁用或重新启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="1a688-159">在“操作”\*\*\*\* 菜单上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1a688-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="1a688-160">若要暂时禁用 Skype for business Server 的用户帐户，请单击 "为**Lync Server 暂时禁用**"。</span><span class="sxs-lookup"><span data-stu-id="1a688-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="1a688-161">若要为 Skype for business Server 启用用户帐户，请单击 "**为 Lync Server 重新启用**"。</span><span class="sxs-lookup"><span data-stu-id="1a688-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="1a688-162">使用 Windows Powershell 禁用或重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="1a688-163">可以暂时禁用用户帐户，然后再使用**get-csuser** cmdlet 重新启用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="1a688-164">您可以从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a688-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a688-165">有关使用远程 Windows PowerShell 连接到 Skype for business Server 的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="1a688-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1a688-166">Skype for Business Server 中的过程相同。</span><span class="sxs-lookup"><span data-stu-id="1a688-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="1a688-167">禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-167">To disable a user account</span></span>

- <span data-ttu-id="1a688-168">若要暂时禁用某一用户帐户，请将 Enabled 属性的值设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="1a688-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="1a688-169">例如：</span><span class="sxs-lookup"><span data-stu-id="1a688-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="1a688-170">重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-170">To re-enable a user account</span></span>

- <span data-ttu-id="1a688-171">若要重新启用已禁用的用户帐户，请将 Enabled 属性的值设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="1a688-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="1a688-172">例如：</span><span class="sxs-lookup"><span data-stu-id="1a688-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="1a688-173">有关详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1a688-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="1a688-174">为用户禁用企业语音</span><span class="sxs-lookup"><span data-stu-id="1a688-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="1a688-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="1a688-176">使用以下过程可为对 Skype for business Server 启用的用户帐户禁用企业语音。</span><span class="sxs-lookup"><span data-stu-id="1a688-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="1a688-177">为企业语音禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="1a688-178">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a688-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="1a688-179">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1a688-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a688-180">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="1a688-181">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="1a688-182">在表中，单击要为企业语音启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="1a688-183">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="1a688-184">在“编辑 Lync Server 用户”\*\*\*\* 页的“电话”\*\*\*\* 下，单击“企业语音”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a688-185">若要使用 Lync 限制用户进行音频或视频呼叫，请在 "**电话服务**" 下单击 "**音频/视频已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="1a688-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="1a688-186">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-186">Click **Commit**.</span></span>

<span data-ttu-id="1a688-187">用户现在无法使用企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="1a688-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="1a688-188">相关信息：</span><span class="sxs-lookup"><span data-stu-id="1a688-188">Related information:</span></span> <br/>[<span data-ttu-id="1a688-189">企业语音和移动性</span><span class="sxs-lookup"><span data-stu-id="1a688-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="1a688-190">在 Skype for Business Server 中为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="1a688-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="1a688-191">Skype for Business Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="1a688-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="1a688-192">使用 Skype for Business Server 命令行管理程序删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="1a688-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="1a688-194">您可以使用以下过程在 Skype for Business Server 中删除之前添加的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="1a688-195">移除用户将导致您丢失为用户帐户配置的所有设置。</span><span class="sxs-lookup"><span data-stu-id="1a688-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="1a688-196">如果要暂时禁用用户帐户，请参阅[disable or 重新启用之前为 Skype for Business Server 启用的用户帐户](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="1a688-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="1a688-197">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a688-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="1a688-198">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1a688-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a688-199">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="1a688-200">在“搜索用户”\*\*\*\* 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a688-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="1a688-201">在表中，单击要移除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="1a688-202">在“操作”\*\*\*\* 菜单上，选择“从 Lync Server 中删除”\*\*\*\*，然后将出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="1a688-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="1a688-203">从该对话框中，选择“确定”\*\*\*\* 来移除该用户。</span><span class="sxs-lookup"><span data-stu-id="1a688-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="1a688-204">使用 Windows Powershell cmdlet 删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="1a688-205">您可以使用 Get-csuser cmdlet 删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a688-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="1a688-206">此 cmdlet 可从 Skype for Business Server 命令行管理程序或远程会话 Windows PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="1a688-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="1a688-207">有关使用远程 Windows PowerShell 连接到 Skype for business Server 的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="1a688-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1a688-208">Skype for Business Server 中的过程相同。</span><span class="sxs-lookup"><span data-stu-id="1a688-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="1a688-209">删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a688-209">To remove a user account</span></span>
<span data-ttu-id="1a688-210">若要移除用户帐户，请使用 Disable-CsUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a688-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="1a688-211">例如：</span><span class="sxs-lookup"><span data-stu-id="1a688-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="1a688-212">有关详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1a688-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a688-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a688-213">See also</span></span>
<span data-ttu-id="1a688-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="1a688-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="1a688-215">Enable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="1a688-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="1a688-216">Disable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="1a688-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
