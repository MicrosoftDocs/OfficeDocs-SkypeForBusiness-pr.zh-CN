---
title: 为用户设置来电显示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 了解Microsoft 365 Office 365呼叫者 ID (用户分配的电话号码的默认呼叫) ，也称为呼叫线路 ID。 可以更改或阻止用户的来电显示。
ms.openlocfilehash: 9a69cf864cbf57d7ebf82ae079f88a888d3fc9f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613581"
---
# <a name="set-the-caller-id-for-a-user"></a>为用户设置来电显示

电话系统中Microsoft 365提供默认呼叫者 ID，即用户分配的电话号码。 你可以为用户更改或阻止来电显示（也称为主叫号码）。 可以通过访问"如何在组织中使用来电显示"，了解有关如何在组织中使用来电[显示功能。](how-can-caller-id-be-used-in-your-organization.md)
  
默认情况下，以下来电显示设置 **已关闭**。 这意味着，Teams呼叫 PSTN 电话时，可以看到该用户的电话号码。 可以更改这些设置，如下所示：
  
- **传出来电显示** 你可以将用户的来电显示（默认为用户的电话号码）替换为另一个电话号码。 例如，你可以将用户的来电显示从其电话号码更改为企业的主要电话号码，或者更改为法律部门的主要电话号码。 此外，您可以将呼叫 ID 号码设置为任何联机服务号码 (收费或免费) ，或者通过直接路由将本地电话号码设置为分配给 自动助理 或呼叫队列使用的资源帐户。
    
  > [!NOTE]
  > 若要使用 Service *参数，* 必须指定有效的服务编号。
  > 如果资源帐户编号在下拉列表中不可见，则需要使用 Teams PowerShell 模块 2.3.1 或更高版本中的 PowerShell cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。
  
- **阻止出站来电显示。** 你可以阻止传出呼叫者 ID 在用户的传出 PSTN 呼叫上发送。 执行此操作将阻止其电话号码显示在被呼叫者的电话上。
    
- **阻止传入来电显示。** 你可以阻止用户接收任何传入 PSTN 呼叫的来电显示。

- **将"呼叫方名称" (CNAM) 。** 对于你的Microsoft Teams，可以在出站 PSTN 呼叫上发送 CNAM。
    
> [!IMPORTANT]
> [!重要信息] 紧急呼叫始终发送用户的电话号码（来电显示号码）。 
  

  
若要详细了解这些设置及其使用方式，请参阅 [如何在组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>设置你的来电显示策略设置

> [!NOTE]
> 若要将呼叫方 ID 设置为资源帐户电话号码并设置呼叫方名称，请使用 Teams PowerShell 模块 2.3.1 或更高版本中的 PowerShell cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。  (管理中心.) 中目前Microsoft Teams这些选项不可用 

打开 Windows PowerShell 命令提示符并运行以下命令：

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>查看、创建和应用策略设置

1. 若要查看组织的所有来电显示策略设置，请运行：

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   有关详细信息，请参阅 [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity)。
    
2. 若要为组织创建新的来电显示策略，请使用 New-CsCallingIdentity cmdlet：
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    在所有情况下，在"服务号码"字段不应包含初始"+"。

   有关详细信息，请参阅 [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity)。
    
3. 使用 Grant-CsCallingIdentity cmdlet 应用创建的新策略。 例如，以下示例将新策略应用到用户 Amos Marble。
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   有关详细信息，请参阅 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet。
    

4. 如果要阻止传入的来电显示，请运行：
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   有关详细信息，请参阅 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity)。
    
5. 若要将创建的策略设置应用到组织中用户，请运行：
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   有关详细信息，请参阅 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity)。

6. 若要创建新的来电显示策略，将呼叫者 ID 设置到指定资源帐户的电话号码，将呼叫方名称设置为 Contoso：

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

如果已创建策略，可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet 更改现有策略，然后使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet 将设置应用于用户。
    
### <a name="remove-a-policy-setting"></a>删除策略设置

要删除组织的策略，请运行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
要删除用户的策略，请运行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用Microsoft 365单点管理来管理任务，从而简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
- [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [可能想要使用 Windows PowerShell 管理Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：
    
- [使用 Microsoft 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](./phone-number-calling-plans/port-order-overview.md)

[用于通话套餐的不同类型的电话号码](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[更多关于呼叫线路 ID 和主叫方名称的信息](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
