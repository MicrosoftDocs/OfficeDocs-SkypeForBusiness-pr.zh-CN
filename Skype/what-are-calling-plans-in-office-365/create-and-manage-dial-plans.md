---
title: "创建和管理拨号计划"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# 创建和管理拨号计划

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](7af17c94-5f8f-4452-ae1d-01f495b4dc94.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/7af17c94-5f8f-4452-ae1d-01f495b4dc94) 中查找本文的英文版本以便参考。
  
已为您的组织计划拨号计划，并想出需要呼叫路由创建的规范化规则的所有之后，您需要使用 Windows PowerShell 创建拨号计划和更改任何设置。
  
> [!注释]
> Skype for Business 管理中心不能用于创建和管理拨号计划。 
  
## 验证并启动远程 PowerShell

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. 若要验证运行的是 3.0 版本或更高版本：" **开始菜单**">" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
  
 **启动 Windows PowerShell 会话**
  
1. 从" **开始菜单**">" **Windows PowerShell**"。
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!注释]
    > 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

如果想要深入了解如何启动 Windows PowerShell，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。
  
## 创建并管理你的拨号计划

你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。
  
### 使用单个 cmdlet

- 要创建新的拨号计划，请运行：
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    有关其他示例和参数，请参阅 [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)。
    
- 若要对现有拨号计划中进行设置的更改，运行：
    
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
    
- 若要查看在拨号计划上的设置，请运行：
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)。
    
- 若要删除拨号计划，请运行：
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)。
    
- 若要查看有效拨号计划的设置，请运行：
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)。
    
- 要测试拨号计划的有效设置，请运行：
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)。
    
### 使用 PowerShell 脚本

运行此脚本即可删除与租户拨号计划关联的规范化规则，而不需要先删除租户拨号计划：
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

运行文档检查器将添加到现有的租户拨号计划下面的规范化规则命名 RedmondDialPlan。
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

运行以下命令时想要检查的现有的规范化规则，请确定哪一个要删除，并将其索引以将其删除。规范化规则数组开头索引 0。我们希望删除 3 位数规范化规则，因此，它是索引 1。
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

运行这些添加现有的内部部署拨号计划名 OPDP1 为租户拨号计划为您的组织。您需要首先保存在本地拨号计划到.xml 文件，并使用它来创建新的租户拨号计划。
  
运行文档检查器将保存到.xml 文件的本地拨号计划。
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

运行此脚本创建新的租户拨号计划。
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## 要了解有关 Windows PowerShell 的详细信息？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

