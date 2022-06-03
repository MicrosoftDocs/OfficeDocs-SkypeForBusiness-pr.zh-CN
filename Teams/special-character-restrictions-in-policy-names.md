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
description: 查看策略名称中特殊字符存在哪些问题，以及可以执行哪些操作来修复它。
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860075"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 策略中采用了哪些特殊字数限制？

**无法为消息传送、会议等 (创建或编辑策略) Microsoft Teams管理中心名称中具有特殊字符**。 

如果策略名称包含特殊字符，则在管理Microsoft Teams管理中心管理这些策略时会受到限制。 **因此，我们强烈建议策略名称不包含特殊字符**。 

在Teams中使用 PowerShell 为会议和消息传递创建的策略名称可以具有特殊字符，例如 @，#，$。 但是，如果想要在Microsoft Teams管理中心对策略进行更改，则无法执行此操作。 

如果有具有特殊字符的策略，则需要使用Windows PowerShell (永远) 编辑策略，或者在Microsoft Teams管理中心使用与旧策略相同的设置创建新策略，并将其分配给同一组用户。

## <a name="to-remove-special-characters"></a>删除特殊字符

**步骤 1 - 与 PowerShell 建立远程连接。**
> [!NOTE]
> Skype for Business联机连接器目前是最新Teams PowerShell 模块的一部分。
>
> 如果使用最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype for Business Online Connector。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**步骤 2 - 获取旧策略的设置并捕获输出。**

> [!NOTE]
> 此示例适用于 [消息传送](/powershell/module/skype/get-csteamsmessagingpolicy) 策略。  对于其他策略类型，步骤相同，但必须使用正确的 cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步骤 3 - 创建新策略。**

可以使用Microsoft Teams管理中心或 PowerShell 创建具有相同设置的新策略。

运行此操作将为你创建新策略，但需要通过查看 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) 并运行它来添加正确的设置：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步骤 4 - 分配策略。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
有关此 cmdlet 的详细信息，请参阅 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) 。

**步骤 5 - 删除旧策略。**

这将删除具有特殊字符的旧策略。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
有关此 cmdlet 的详细信息，请参阅 [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) 。

如果此命令成功，则已完成。 如果上述命令返回错误，是因为旧策略分配给用户，因此需要运行以从策略中删除所有分配的用户：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理Microsoft 365或Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell？](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用Windows PowerShell管理Microsoft 365或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell在速度、简单性和工作效率方面具有许多优势，而不是仅使用Microsoft 365 管理中心，例如每次对许多用户进行设置更改时。 通过以下主题了解这些优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Skype for Business Online 的Windows PowerShell模块使你能够创建一个远程Windows PowerShell会话，用于连接到 Skype for Business Online 和 Microsoft Teams。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)下载。
