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
ms.openlocfilehash: 50cdbaf9fd1e5ae10eca20c0f547dce29d606983
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902017"
---
# <a name="create-and-manage-dial-plans"></a>创建并管理拨号计划

在为您的组织规划拨号计划并查明需要为呼叫路由创建的所有规范化规则后，您就可以创建拨号计划了。 你可以使用 Microsoft 团队管理中心或 Windows PowerShell 创建和管理拨号计划。  

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

### <a name="create-a-dial-plan"></a>创建拨号计划

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **拨号计划**"。
2. 单击 "**添加**"，然后输入拨号计划的名称和说明。
    ![显示用于创建拨号计划的 "添加" 页面的屏幕截图](media/create-dial-plan.png)
3. 在 "**拨号计划详细信息**" 下，如果用户需要拨一个或多个附加前导数字（例如9）来获取外部线路，请指定外部拨号前缀。 要执行此操作：
    1. 在 "**外部拨号前缀**" 框中，输入外部拨号前缀。 前缀最多可包含四个字符（#、* 和0-9）。
    2. 启用已**优化的设备拨号**。 如果你指定外部拨号前缀，还必须启用此设置以应用前缀，以便可以在你的组织外部进行呼叫。
4. 在 "**规范化规则**" 下，为拨号计划配置和关联一个或多个[规范化规则](what-are-dial-plans.md#normalization-rules)。 每个拨号计划必须至少有一个与之关联的规范化规则。  若要执行此操作，请执行下列一项或多项操作：
    - 若要创建新的规范化规则并将其与拨号计划相关联，请单击 "**添加**"，然后定义规则。
    - 若要编辑已与拨号计划关联的规范化规则，请通过单击规则名称左侧的规则选择规则，然后单击 "**编辑**"。 进行所需的更改，然后单击 "**保存**"。
    - 若要从拨号计划中删除规范化规则，请通过单击规则名称左侧的规则选择规则，然后单击 "**删除**"。
5. 按所需顺序排列规范化规则。 单击 "**上移**" 或 "**下移**" 更改列表中规则的位置。

    > [!NOTE]
    > 团队从上到下遍历规范化规则列表，并使用与所拨号码匹配的第一个规则。 如果您设置了一个拨号计划，以便已拨号码可以匹配多个规范化规则，请确保更严格的规则在限制性较少的规则之上排序。

6. 单击“**保存**”。
7. 如果要测试拨号计划，请在 "**测试拨号计划**" 下输入电话号码，然后单击 "**测试**"。

### <a name="edit-a-dial-plan"></a>编辑拨号计划

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **拨号计划**"。
2. 通过单击拨号计划名称左侧的 "拨号计划"，然后单击 "**编辑**" 来选择它。
3. 进行所需的更改，然后单击 "**保存**"。

### <a name="add-users-to-a-dial-plan"></a>将用户添加到拨号计划

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。
2. 通过单击显示名称来选择用户。
3. 选择 "**策略**" 选项卡。
4. 单击分配的策略右侧的 "**编辑**"。
5. 从 "**拨号计划**" 下拉菜单中，选择要分配给用户的拨号计划，然后单击 "**应用**"。

## <a name="using-powershell"></a>使用 PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>验证并启动远程 PowerShell

 **检查你是否正在运行 Windows PowerShell 版本3.0 或更高版本**
  
1. 若要验证运行的是版本3.0 或更高版本，请执行以下操作： "**开始" 菜单** > **Windows PowerShell**。
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有版本3.0 或更高版本，请下载并安装 Windows PowerShell 更新。 请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。 出现提示时，请重新启动计算机。
    
4. 你还需要安装适用于 Skype for business Online 的 Windows PowerShell 模块，使你能够创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。 你可以在[Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)中下载此模块，该模块仅在64位计算机上受支持。 如果出现提示，请重新启动计算机。
    
若要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接到所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。
  
 **启动 Windows PowerShell 会话**
  
1. 单击 "**启动** > **Windows PowerShell**"。
    
2. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>创建和管理您的拨号计划

你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。
  
#### <a name="using-single-cmdlets"></a>使用单个 cmdlet

- 要创建新的拨号计划，请运行：
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)。
    
- 若要编辑现有拨号计划的设置，请运行：
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)。
    
- 要向拨号计划中添加用户，请运行：
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)。
    
- 要查看拨号计划中的设置，请运行：
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。
    
- 要删除拨号计划，请运行：
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。
    
- 要查看有效拨号计划的设置，请运行：
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)。
    
- 要测试拨号计划的有效设置，请运行：
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。
    
#### <a name="using-a-powershell-script"></a>使用 PowerShell 脚本

运行此操作以删除与租户拨号计划关联的规范化规则，而无需先删除租户拨号计划：
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

如果你还希望检查现有的规范化规则，确定要删除哪个规则，然后使用其索引将其删除，请运行以下操作。 该组规范化规则以索引 0 开头。 我们要删除 3 位数的规范化规则，则索引为 1。
  
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

运行此操作以从具有 HostingProvider 的 sipfed.online.lync.com 的所有用户中删除任何分配的 TenantDialPlan。
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。 您需要先将本地拨号计划保存到 .xml 文件，然后使用它创建新的租户拨号计划。
  
运行此操作以将本地拨号计划保存到 .xml 文件。
  
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
- [关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)
- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
- [紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams PowerShell 概览](teams-powershell-overview.md)
