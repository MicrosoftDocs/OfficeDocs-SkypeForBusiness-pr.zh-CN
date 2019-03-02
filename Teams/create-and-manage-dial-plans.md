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
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. '
ms.openlocfilehash: 388dd1bf037a506ca3936e89d66e01997e6ca208
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352855"
---
# <a name="create-and-manage-dial-plans"></a>创建并管理拨号计划

您已为您的组织计划拨号计划，并且想出了需要创建的呼叫路由的规范化规则的所有后，您需要使用 Windows PowerShell 创建拨号计划和更改任何设置。
  
> [!NOTE]
> [!注释] Skype for Business 管理中心不能用于创建和管理拨号计划。 
  
## <a name="verifying-and-starting-remote-powershell"></a>验证并启动远程 PowerShell

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
  
 **启动 Windows PowerShell 会话**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
  
## <a name="creating-and-managing-your-dial-plans"></a>创建并管理你的拨号计划

你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。
  
### <a name="using-single-cmdlets"></a>使用单个 cmdlet

- 要创建新的拨号计划，请运行：
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)。
    
- 要对现有拨号计划进行设置更改，请运行：
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)。
    
- 要向拨号计划中添加用户，请运行：
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)。
    
- 要查看拨号计划中的设置，请运行：
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)。
    
- 要删除拨号计划，请运行：
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)。
    
- 要查看有效拨号计划的设置，请运行：
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)。
    
- 要测试拨号计划的有效设置，请运行：
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)。
    
### <a name="using-a-powershell-script"></a>使用 PowerShell 脚本

运行此脚本即可删除与租户拨号计划关联的规范化规则，而不需要先删除租户拨号计划：
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
运行此脚本即可将下列规范化规则添加到名为 RedmondDialPlan 的现有租户拨号计划中。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

运行以下命令时要检查的现有的规范化规则，确定哪个要删除，并将其索引以便将其删除。规范化规则的数组开头索引值 0。我们希望删除 3 位数字表示规范化规则，以便索引 1。
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

运行此选项可删除所有用户拥有 HostingProvider sipfed.online.lync.com policyname。
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。 您需要先保存本地拨号计划到.xml 文件，然后使用它来创建新的租户拨号计划。
  
运行此选项可将内部部署拨号计划保存到的.xml 文件。
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

运行此脚本创建新的租户拨号计划。
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
