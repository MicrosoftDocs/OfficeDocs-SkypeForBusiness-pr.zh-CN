---
title: 创建并管理拨号计划
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: 了解如何使用 Microsoft 团队管理中心或 Windows PowerShell 创建和管理拨号计划（PSTN 呼叫拨号计划）。
ms.openlocfilehash: 966ac2e21d3bc57dd32a0b2732e0be285b9fdf0d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691338"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="c3ea6-103">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="c3ea6-103">Create and manage dial plans</span></span>

<span data-ttu-id="c3ea6-104">在为您的组织规划拨号计划并查明需要为呼叫路由创建的所有规范化规则后，您就可以创建拨号计划了。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="c3ea6-105">你可以使用 Microsoft 团队管理中心或 Windows PowerShell 创建和管理拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c3ea6-106">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c3ea6-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="c3ea6-107">创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="c3ea6-107">Create a dial plan</span></span>

1. <span data-ttu-id="c3ea6-108">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **拨号计划**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="c3ea6-109">单击 "**添加**"，然后输入拨号计划的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="c3ea6-110">![显示用于创建拨号计划的 "添加" 页面的屏幕截图](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="c3ea6-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="c3ea6-111">在 "**拨号计划详细信息**" 下，如果用户需要拨一个或多个附加前导数字（例如9）来获取外部线路，请指定外部拨号前缀。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="c3ea6-112">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-112">To do this:</span></span>
    1. <span data-ttu-id="c3ea6-113">在 "**外部拨号前缀**" 框中，输入外部拨号前缀。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="c3ea6-114">前缀最多可包含四个字符（#、\* 和0-9）。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="c3ea6-115">启用已**优化的设备拨号**。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="c3ea6-116">如果你指定外部拨号前缀，还必须启用此设置以应用前缀，以便可以在你的组织外部进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="c3ea6-117">在 "**规范化规则**" 下，为拨号计划配置和关联一个或多个[规范化规则](what-are-dial-plans.md#normalization-rules)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="c3ea6-118">每个拨号计划必须至少有一个与之关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="c3ea6-119">若要执行此操作，请执行下列一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="c3ea6-120">若要创建新的规范化规则并将其与拨号计划相关联，请单击 "**添加**"，然后定义规则。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="c3ea6-121">若要编辑已与拨号计划关联的规范化规则，请通过单击规则名称左侧的规则选择规则，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="c3ea6-122">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="c3ea6-123">若要从拨号计划中删除规范化规则，请通过单击规则名称左侧的规则选择规则，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="c3ea6-124">按所需顺序排列规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="c3ea6-125">单击 "**上移**" 或 "**下移**" 更改列表中规则的位置。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3ea6-126">团队从上到下遍历规范化规则列表，并使用与所拨号码匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="c3ea6-127">如果您设置了一个拨号计划，以便已拨号码可以匹配多个规范化规则，请确保更严格的规则在限制性较少的规则之上排序。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="c3ea6-128">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-128">Click **Save**.</span></span>
7. <span data-ttu-id="c3ea6-129">如果要测试拨号计划，请在 "**测试拨号计划**" 下输入电话号码，然后单击 "**测试**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="c3ea6-130">编辑拨号计划</span><span class="sxs-lookup"><span data-stu-id="c3ea6-130">Edit a dial plan</span></span>

1. <span data-ttu-id="c3ea6-131">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **拨号计划**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="c3ea6-132">通过单击拨号计划名称左侧的 "拨号计划"，然后单击 "**编辑**" 来选择它。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c3ea6-133">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="c3ea6-134">将用户添加到拨号计划</span><span class="sxs-lookup"><span data-stu-id="c3ea6-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="c3ea6-135">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-135">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="c3ea6-136">通过单击显示名称来选择用户。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-136">Select the user by clicking the display name.</span></span>
3. <span data-ttu-id="c3ea6-137">选择 "**策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-137">Select the **Policies** tab.</span></span>
4. <span data-ttu-id="c3ea6-138">单击分配的策略右侧的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-138">Click **Edit** to the right of Assigned policies.</span></span>
5. <span data-ttu-id="c3ea6-139">从 "**拨号计划**" 下拉菜单中，选择要分配给用户的拨号计划，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-139">From the **Dial plan** drop-down menu, select the dial plan you want to assign to the user and then click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="c3ea6-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3ea6-140">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="c3ea6-141">验证并启动远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3ea6-141">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="c3ea6-142">**检查你是否正在运行 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="c3ea6-142">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="c3ea6-143">若要验证运行的是版本3.0 或更高版本，请执行以下操作： "**开始" 菜单**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-143">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c3ea6-144">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-144">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c3ea6-145">如果你没有版本3.0 或更高版本，请下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-145">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="c3ea6-146">请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-146">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="c3ea6-147">出现提示时，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-147">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="c3ea6-148">你还需要安装适用于 Skype for business Online 的 Windows PowerShell 模块，使你能够创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-148">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="c3ea6-149">你可以在[Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)中下载此模块，该模块仅在64位计算机上受支持。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-149">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="c3ea6-150">如果出现提示，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-150">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="c3ea6-151">若要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-151">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="c3ea6-152">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="c3ea6-152">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="c3ea6-153">单击 "**启动**  >  **Windows PowerShell**"。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-153">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c3ea6-154">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-154">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3ea6-155">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-155">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="c3ea6-156">创建和管理您的拨号计划</span><span class="sxs-lookup"><span data-stu-id="c3ea6-156">Create and manage your dial plans</span></span>

<span data-ttu-id="c3ea6-157">你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-157">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="c3ea6-158">使用单个 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c3ea6-158">Using single cmdlets</span></span>

- <span data-ttu-id="c3ea6-159">要创建新的拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-159">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="c3ea6-160">有关其他示例和参数，请参阅 [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-160">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="c3ea6-161">若要编辑现有拨号计划的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-161">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="c3ea6-162">有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-162">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="c3ea6-163">要向拨号计划中添加用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-163">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="c3ea6-164">有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-164">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="c3ea6-165">要查看拨号计划中的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-165">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="c3ea6-166">有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-166">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="c3ea6-167">要删除拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-167">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="c3ea6-168">有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-168">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="c3ea6-169">要查看有效拨号计划的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-169">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="c3ea6-170">有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-170">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="c3ea6-171">要测试拨号计划的有效设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-171">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="c3ea6-172">有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-172">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="c3ea6-173">使用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="c3ea6-173">Using a PowerShell script</span></span>

<span data-ttu-id="c3ea6-174">运行此操作以删除与租户拨号计划关联的规范化规则，而无需先删除租户拨号计划：</span><span class="sxs-lookup"><span data-stu-id="c3ea6-174">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="c3ea6-175">运行此脚本即可将下列规范化规则添加到名为 RedmondDialPlan 的现有租户拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-175">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="c3ea6-176">运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-176">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="c3ea6-177">如果你还希望检查现有的规范化规则，确定要删除哪个规则，然后使用其索引将其删除，请运行以下操作。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-177">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="c3ea6-178">该组规范化规则以索引 0 开头。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-178">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="c3ea6-179">我们要删除 3 位数的规范化规则，则索引为 1。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-179">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="c3ea6-180">运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-180">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="c3ea6-181">运行此操作以从具有 HostingProvider 的 sipfed.online.lync.com 的所有用户中删除任何分配的 TenantDialPlan。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-181">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="c3ea6-182">运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-182">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="c3ea6-183">您需要先将本地拨号计划保存到 .xml 文件，然后使用它创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-183">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="c3ea6-184">运行此操作以将本地拨号计划保存到 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-184">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="c3ea6-185">运行此脚本创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c3ea6-185">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="c3ea6-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="c3ea6-186">Related topics</span></span>

- [<span data-ttu-id="c3ea6-187">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="c3ea6-187">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="c3ea6-188">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="c3ea6-188">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="c3ea6-189">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="c3ea6-189">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="c3ea6-190">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="c3ea6-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="c3ea6-191">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="c3ea6-191">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="c3ea6-192">[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c3ea6-192">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="c3ea6-193">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="c3ea6-193">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
