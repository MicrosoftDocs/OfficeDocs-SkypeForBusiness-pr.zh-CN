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
description: 了解如何使用 PSTN Microsoft Teams中心或Windows PowerShell PSTN 呼叫拨号 (创建和管理) 。
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046229"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="2bcfb-103">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="2bcfb-103">Create and manage dial plans</span></span>

<span data-ttu-id="2bcfb-104">为组织规划拨号计划并找出需要为呼叫路由创建的所有规范化规则后，即可创建拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="2bcfb-105">使用具有有效 Teams 许可证的管理员帐户，Microsoft Teams管理中心或Windows PowerShell创建和管理拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2bcfb-106">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="2bcfb-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="2bcfb-107">创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="2bcfb-107">Create a dial plan</span></span>

1. <span data-ttu-id="2bcfb-108">在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **拨号计划"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2bcfb-109">单击 **"** 添加"，然后输入拨号计划的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="2bcfb-110">![显示用于创建拨号计划的"添加"页面的屏幕截图](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="2bcfb-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="2bcfb-111">在 **"拨号计划详细信息**"下，指定外部拨号前缀（如果用户需要拨打一个或多个前导 (例如，9) 才能获取外部线路。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="2bcfb-112">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-112">To do this:</span></span>
    1. <span data-ttu-id="2bcfb-113">在" **外部拨号前缀** "框中，输入外部拨号前缀。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="2bcfb-114">前缀可以是最多四个字符 (#、\*和 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="2bcfb-115">打开 **"优化设备拨号"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="2bcfb-116">如果指定外部拨号前缀，则还必须启用此设置才能应用前缀，以便可以在组织外部进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="2bcfb-117">在 **"规范化规则**"下，为拨号计划配置 [和关联一](what-are-dial-plans.md#normalization-rules) 个或多个规范化规则。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="2bcfb-118">每个拨号计划必须至少有一个与之关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="2bcfb-119">为此，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="2bcfb-120">若要创建新的规范化规则并将其与拨号计划关联，请单击 **"添加**"，然后定义规则。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="2bcfb-121">若要编辑已与拨号计划关联的规范化规则，请单击规则名称左侧选择规则，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="2bcfb-122">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="2bcfb-123">若要从拨号计划中删除规范化规则，请单击规则名称左侧选择规则，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="2bcfb-124">按需要的顺序排列规范化规则。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="2bcfb-125">单击 **"上\*\*\*\*移"或**"下移"以更改规则在列表中的位置。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2bcfb-126">Teams从上到下遍历规范化规则列表，并使用与拨号号码匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="2bcfb-127">如果设置了拨号计划，以便拨号号码可以匹配多个规范化规则，请确保限制性较强的规则在限制性较少的规则上方排序。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="2bcfb-128">如果设置一个将拨号号码规范化而不使用"+"的拨号计划，则呼叫服务将尝试使用租户和区域拨号计划规则再次规范化该号码。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="2bcfb-129">为了避免双规范化，建议所有规范化规则都将导致数字以"+"开始。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="2bcfb-130">如果需要，直接 [路由](direct-routing-translate-numbers.md) 客户可以使用中继转换规则删除"+"。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="2bcfb-131">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-131">Click **Save**.</span></span>
7. <span data-ttu-id="2bcfb-132">如果要测试拨号计划，请在"测试拨号计划"下输入电话号码，然后单击"测试 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="2bcfb-133">编辑拨号计划</span><span class="sxs-lookup"><span data-stu-id="2bcfb-133">Edit a dial plan</span></span>

1. <span data-ttu-id="2bcfb-134">在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **拨号计划"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2bcfb-135">通过单击拨号计划名称左侧选择拨号计划，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2bcfb-136">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="2bcfb-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="2bcfb-137">向用户分配拨号计划</span><span class="sxs-lookup"><span data-stu-id="2bcfb-137">Assign a dial plan to users</span></span>

<span data-ttu-id="2bcfb-138">你以分配策略的相同方式分配拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="2bcfb-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bcfb-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="2bcfb-140">启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bcfb-140">Start PowerShell</span></span>
- <span data-ttu-id="2bcfb-141">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="2bcfb-142">创建和管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="2bcfb-142">Create and manage your dial plans</span></span>

<span data-ttu-id="2bcfb-143">你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="2bcfb-144">使用单个 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2bcfb-144">Using single cmdlets</span></span>

- <span data-ttu-id="2bcfb-145">要创建新的拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2bcfb-146">有关其他示例和参数，请参阅 [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2bcfb-147">若要编辑现有拨号计划的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2bcfb-148">有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2bcfb-149">要向拨号计划中添加用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="2bcfb-150">有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2bcfb-151">要查看拨号计划中的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="2bcfb-152">有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2bcfb-153">要删除拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="2bcfb-154">有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2bcfb-155">要查看有效拨号计划的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2bcfb-156">有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="2bcfb-157">要测试拨号计划的有效设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2bcfb-158">有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="2bcfb-159">使用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="2bcfb-159">Using a PowerShell script</span></span>

<span data-ttu-id="2bcfb-160">运行此操作可删除与租户拨号计划关联的规范化规则，而无需先删除租户拨号计划：</span><span class="sxs-lookup"><span data-stu-id="2bcfb-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="2bcfb-161">运行此脚本即可将下列规范化规则添加到名为 RedmondDialPlan 的现有租户拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="2bcfb-162">运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="2bcfb-163">若要同时检查现有的规范化规则，确定要删除的规则，然后使用其索引将其删除，请运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-163">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="2bcfb-164">该组规范化规则以索引 0 开头。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-164">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="2bcfb-165">我们要删除 3 位数的规范化规则，则索引为 1。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-165">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="2bcfb-166">运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="2bcfb-167">运行此操作，从具有托管主机的所有用户中删除任何分配的 TenantDialPlan sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="2bcfb-168">运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-168">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="2bcfb-169">首先需要将本地拨号计划保存到 .xml 文件，然后使用它创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-169">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="2bcfb-170">运行此操作，将本地拨号计划保存到 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="2bcfb-171">运行此脚本创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2bcfb-171">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="2bcfb-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="2bcfb-172">Related topics</span></span>

- [<span data-ttu-id="2bcfb-173">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="2bcfb-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="2bcfb-174">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="2bcfb-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="2bcfb-175">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="2bcfb-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="2bcfb-176">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="2bcfb-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="2bcfb-177">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="2bcfb-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="2bcfb-178">[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2bcfb-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="2bcfb-179">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="2bcfb-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
