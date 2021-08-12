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
ms.openlocfilehash: b578533bfd2b903fd29563897a2f9ed917b369c38955e631b4aba0cefaa025fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282865"
---
# <a name="create-and-manage-dial-plans"></a>创建并管理拨号计划

为组织规划拨号计划并找出需要为呼叫路由创建的所有规范化规则后，即可创建拨号计划。 使用具有有效 Teams 许可证的管理员帐户，Microsoft Teams管理中心或Windows PowerShell创建和管理拨号计划。  

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

### <a name="create-a-dial-plan"></a>创建拨号计划

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **拨号计划"。**
2. 单击 **"** 添加"，然后输入拨号计划的名称和说明。
    ![显示用于创建拨号计划的"添加"页面的屏幕截图](media/create-dial-plan.png)
3. 在 **"拨号计划详细信息**"下，指定外部拨号前缀（如果用户需要拨打一个或多个前导 (例如，9) 才能获取外部线路。 要执行此操作：
    1. 在" **外部拨号前缀** "框中，输入外部拨号前缀。 前缀可以是最多四个字符 (#、*和 0-9) 。
    2. 打开 **"优化设备拨号"。** 如果指定外部拨号前缀，则还必须启用此设置才能应用前缀，以便可以在组织外部进行呼叫。
4. 在 **"规范化规则**"下，为拨号计划配置 [和关联一](what-are-dial-plans.md#normalization-rules) 个或多个规范化规则。 每个拨号计划必须至少有一个与之关联的规范化规则。  为此，请执行以下一项或多项操作：
    - 若要创建新的规范化规则并将其与拨号计划关联，请单击 **"添加**"，然后定义规则。
    - 若要编辑已与拨号计划关联的规范化规则，请单击规则名称左侧选择规则，然后单击"编辑 **"。** 进行您需要的更改，然后单击"保存 **"。**
    - 若要从拨号计划中删除规范化规则，请单击规则名称左侧选择规则，然后单击"删除 **"。**
5. 按需要的顺序排列规范化规则。 单击 **"上****移"或**"下移"以更改规则在列表中的位置。

    > [!NOTE]
    > Teams从上到下遍历规范化规则列表，并使用与拨号号码匹配的第一个规则。 如果设置了拨号计划，以便拨号号码可以匹配多个规范化规则，请确保限制性较强的规则在限制性较少的规则上方排序。 如果设置一个将拨号号码规范化而不使用"+"的拨号计划，则呼叫服务将尝试使用租户和区域拨号计划规则再次规范化该号码。 为了避免双规范化，建议所有规范化规则都将导致数字以"+"开始。 如果需要，直接 [路由](direct-routing-translate-numbers.md) 客户可以使用中继转换规则删除"+"。 

6. 单击“**保存**”。
7. 如果要测试拨号计划，请在"测试拨号计划"下输入电话号码，然后单击"测试 **"。**

### <a name="edit-a-dial-plan"></a>编辑拨号计划

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **拨号计划"。**
2. 通过单击拨号计划名称左侧选择拨号计划，然后单击"编辑 **"。**
3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="assign-a-dial-plan-to-users"></a>向用户分配拨号计划

你以分配策略的相同方式分配拨号计划。 [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>使用 PowerShell
  
### <a name="start-powershell"></a>启动 PowerShell
- 打开Windows PowerShell命令提示符并运行以下命令：

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>创建和管理拨号计划

你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。
  
#### <a name="using-single-cmdlets"></a>使用单个 cmdlet

- 要创建新的拨号计划，请运行：
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)。
    
- 若要编辑现有拨号计划的设置，请运行：
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)。
    
- 要向拨号计划中添加用户，请运行：
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)。
    
- 要查看拨号计划中的设置，请运行：
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。
    
- 要删除拨号计划，请运行：
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。
    
- 要查看有效拨号计划的设置，请运行：
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)。
    
- 要测试拨号计划的有效设置，请运行：
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。
    
#### <a name="using-a-powershell-script"></a>使用 PowerShell 脚本

运行此操作可删除与租户拨号计划关联的规范化规则，而无需先删除租户拨号计划：
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
运行此脚本即可将下列规范化规则添加到名为 RedmondDialPlan 的现有租户拨号计划中。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

若要同时检查现有的规范化规则，确定要删除的规则，然后使用其索引将其删除，请运行以下代码。 该组规范化规则以索引 0 开头。 我们要删除 3 位数的规范化规则，则索引为 1。
  
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

运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

运行此操作，从具有托管主机的所有用户中删除任何分配的 TenantDialPlan sipfed.online.lync.com。
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。 首先需要将本地拨号计划保存到 .xml 文件，然后使用它创建新的租户拨号计划。
  
运行此操作，将本地拨号计划保存到 .xml 文件。
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

运行此脚本创建新的租户拨号计划。
  
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
    
## <a name="related-topics"></a>相关主题

- [什么是拨号计划？](what-are-dial-plans.md)
- [关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)
- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams PowerShell 概览](teams-powershell-overview.md)
