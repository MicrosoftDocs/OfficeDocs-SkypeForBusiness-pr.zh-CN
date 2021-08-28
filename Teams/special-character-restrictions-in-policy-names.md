---
title: Teams 策略中的特殊字符限制
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 查看策略名称中的特殊字符存在哪些问题，以及可以执行哪些措施来修复它。
ms.openlocfilehash: c06c5053452c1c55c9e8de09d6b18dd5e97deaca
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589604"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 策略中采用了哪些特殊字数限制？

**不能创建或** 编辑消息 (会议等) 在管理中心中名称中具有特殊字符Microsoft Teams策略。 

如果策略名称包含特殊字符，则管理中心管理这些Microsoft Teams受到限制。 **因此，我们强烈建议策略名称不要包含特殊字符**。 

已使用 PowerShell 创建的策略名称在 Teams 中可用于会议和消息传送，可以使用特殊字符，例如 @、#、$。 但是，如果要在管理中心内更改Microsoft Teams策略，则不能。 

如果策略包含特殊字符，则需要使用 Windows PowerShell (永久) 编辑策略，或在 Microsoft Teams 管理中心中创建新策略，其设置与旧策略相同，并将其分配给同一组用户。

## <a name="to-remove-special-characters"></a>删除特殊字符

**步骤 1 - 使用 PowerShell 建立远程连接。**
> [!NOTE]
> Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。
>
> 如果使用[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**步骤 2 - 获取旧策略的设置并捕获输出。**

> [!NOTE]
> 此示例适用于消息 [传送](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 策略。  对于其他策略类型，步骤相同，但必须使用正确的 cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步骤 3 - 创建新策略。**

可以使用管理中心或 PowerShell 使用相同的设置Microsoft Teams策略。

运行此操作会创建一个新策略，但需要通过查看 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 并运行它来添加正确的设置：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步骤 4 - 分配策略。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
有关此 cmdlet 的信息，请参阅[Grant-CsTeamsMessagingPolicy。](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**步骤 5 - 删除旧策略。**

这会删除包含特殊字符的旧策略。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
有关此 cmdlet 详细信息，请参阅[Remove-CsTeamsMessagingPolicy。](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

如果此命令成功，则操作完成。 如果上述命令返回错误，这是因为旧策略已分配给用户，因此需要运行 从策略中删除所有分配的用户：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365或Office 365单点管理，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要使用 powerShell Office 365？](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell应用程序相比，Microsoft 365 管理中心在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > 使用 Windows PowerShell Online 的 Skype for Business 模块可以创建连接到 Windows PowerShell Online 和 Microsoft Teams 的远程Skype for Business会话。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
