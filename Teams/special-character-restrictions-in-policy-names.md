---
title: Teams 策略中采用了哪些特殊字数限制？
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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
description: 查看策略名称中有特殊字符以及可以执行哪些操作来修复这些问题。
ms.openlocfilehash: 4116f34c06667a3bd4e75f9a5541b23c8ea79dcb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837922"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 策略中采用了哪些特殊字数限制？

**不能在 Microsoft 团队管理中心的名称中创建或编辑具有特殊字符的策略（对于邮件、会议等）**。 

如果策略名称包含特殊字符，则在 Microsoft 团队管理中心中管理这些策略将受到限制。 **因此，我们强烈建议策略名称不要包含特殊字符**。 

在团队中使用 PowerShell 为会议和消息创建的策略名称可以有特殊字符，如 @、#、$。 但是，如果你想要更改 Microsoft 团队管理中心中的策略，你将无法执行。 

如果你有带有特殊字符的策略，你将需要使用 Windows PowerShell （永久）编辑策略，或在 Microsoft 团队管理中心中使用与旧策略相同的设置创建新策略，并将其分配给同一组用户。

## <a name="to-remove-special-characters"></a>删除特殊字符

**步骤 1-使用 PowerShell 进行远程连接。**
如果尚未[安装 Windows PowerShell，请设置计算机](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**步骤 2-获取旧策略的设置并捕获输出。**

> [!NOTE]
> 此示例适用于[消息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)策略。  对于其他策略类型，步骤是相同的，但你必须使用正确的 cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步骤 3-创建新策略。**

你可以使用 Microsoft 团队管理中心或 PowerShell 创建具有相同设置的新策略。

运行此操作将为你创建新策略，但你需要添加正确的设置，方法是先查看 "[设置-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) "，然后运行它：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步骤 4-分配策略。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
有关此 cmdlet 的详细信息，请参阅、[授权 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。

**步骤 5-删除旧策略。**

这将删除具有特殊字符的旧策略。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
有关此 cmdlet 的详细信息，请参阅[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。

如果此命令成功，您就已完成。 如果上面的命令返回错误，则是因为旧策略已分配给用户，因此你需要运行以从策略中删除所有分配的用户：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell？](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 适用于 Skype for Business Online 的 Windows PowerShell 模块可创建连接到 Skype for business Online 和 Microsoft 团队的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  

