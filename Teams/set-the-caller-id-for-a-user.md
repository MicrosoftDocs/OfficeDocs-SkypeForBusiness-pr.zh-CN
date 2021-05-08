---
title: 为用户设置来电显示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解Microsoft 365 Office 365呼叫者 ID (用户分配的电话号码) 呼叫线路 ID。 可以更改或阻止用户的来电显示。
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117150"
---
# <a name="set-the-caller-id-for-a-user"></a>为用户设置来电显示
电话系统和Microsoft 365 Office 365提供默认呼叫者 ID，即用户分配的电话号码。 你可以为用户更改或阻止来电显示（也称为主叫号码）。 可以通过访问"如何在组织中使用来电显示"，详细了解如何在组织中 [使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
> [!TIP]
> 不能阻止当前在 Skype for Business Online 中的传入呼叫。 
  
你可以更改以下设置：
  
> [!NOTE]
> [!注释] 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。
  
- **更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。
    
    > [!NOTE]
    > [!注释] 如果要使用  _Service_ 参数，必须指定有效的服务号码。
  
- **阻止其出站来电显示** 你可以阻止传出呼叫者 ID 在用户的传出 PSTN 呼叫上发送。 执行此操作将阻止其电话号码显示在被呼叫者的电话上。
    
- **阻止其来电显示** 你可以阻止用户接收任何传入 PSTN 呼叫的来电显示。
    
> [!IMPORTANT]
> [!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。 
  
默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。
  
要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>设置你的来电显示策略设置

> [!NOTE]
> 对于 Skype for Business Online 中所有的呼叫者 ID 设置，必须使用 Windows PowerShell 并且不能使用Skype for Business **管理中心**。 
  
### <a name="start-powershell"></a>启动 PowerShell

- 打开Windows PowerShell命令提示符并运行以下命令：

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>查看你组织中的所有来电显示策略设置

- 若要查看组织的所有来电显示策略设置，请运行：

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  请参阅 [Get-CsCallingLineIdentity 的更多示例和详细信息](/powershell/module/skype/Get-CsCallingLineIdentity)。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>为你的组织创建新的来电显示策略


- 若要创建新的调用方 ID 策略，将调用方 ID 设置为匿名，请运行：
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 在所有情况下，在"服务号码"字段不应包含初始"+"。

  请参阅 [New-CsCallingLineIdentity 的更多示例和详细信息](/powershell/module/skype/New-CsCallingLineIdentity)。
    
- 若要将创建的新策略应用到 Amos Marble，请运行：
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  请参阅有关 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet 的更多信息。
    
如果已创建策略，可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet 更改现有策略，然后使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet 将设置应用到用户。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>对其进行设置以阻止传入来电显示

- 若要阻止传入来电显示，请运行：
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  请参阅 [Set-CsCallingLineIdentity 的更多示例和详细信息](/powershell/module/skype/Set-CsCallingLineIdentity)。
    
- 若要将创建的策略设置应用到组织中用户，请运行：
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    请参阅有关 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet 的更多信息。
    
### <a name="remove-a-caller-id-policy"></a>删除来电显示策略

要删除组织的策略，请运行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
要删除用户的策略，请运行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[更多关于呼叫线路 ID 和主叫方名称的信息](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
