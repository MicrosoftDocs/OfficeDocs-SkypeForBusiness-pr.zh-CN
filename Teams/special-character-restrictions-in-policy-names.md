---
title: 什么是团队策略中的特殊字符限制？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: 请参阅有与特殊字符的策略和解决办法可以执行的操作的名称中哪些问题。
ms.openlocfilehash: 6aabd3c1d7e373c048ea1d1f723f83ad1108dbe0
ms.sourcegitcommit: e5a54e2ead0edd9e450bbed4b6e50b3cfd2e91c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "21645385"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>什么是团队策略中的特殊字符限制？

**您无法创建或编辑 Business Admin Center 中的 Microsoft 团队和 Skype 的名称中具有特殊字符的策略 （对于消息、 会议、 等）。** 

如果某个策略名称包含特殊字符，您将在管理中的 Microsoft 团队和业务管理中心的 Skype 这些策略限制。 **因此，我们强烈建议策略名称不包含特殊字符**。 

使用 PowerShell 的会议和消息团队可以如具有特殊字符已创建的策略名称 @，#、 $。 但是，如果您想对中的 Microsoft 团队和 Skype 业务管理中心的策略进行更改，将看不到。 

如果必须具有特殊字符的策略，您将需要编辑策略使用 Windows PowerShell （始终） 或创建新策略中的 Microsoft 团队和业务管理中心的 Skype 与旧策略相同的设置和将其分配给同一分组p 的用户。

## <a name="to-remove-special-characters"></a>若要删除特殊字符



**步骤 1 – 进行远程 powershell 连接。**
如果尚未尚未[设置您的计算机的 Windows PowerShell](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 。
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**步骤 2-获取旧策略设置和捕获输出。**

> [!NOTE]
> 此示例适用于[消息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)策略。  步骤是其他策略类型相同，但您必须使用正确的 cmdlet。 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步骤 3-创建新的策略。**

您可以使用相同的设置用于业务管理中心或 PowerShell 的 Microsoft 团队和 Skype 创建新策略。

运行此会为您创建新策略，但您需要通过查看[设置 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ，然后运行它添加正确设置：

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步骤 4-将策略分配。**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
请参阅[授予 CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)有关此 cmdlet 的详细信息。

**步骤 5-删除旧的策略。**

这将删除特殊字符的旧策略。
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
请参阅[删除 CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)有关此 cmdlet 的详细信息。

如果此命令成功执行，即已完成。 如果上述命令将返回错误，这是因为旧策略分配给用户，因此您需要运行以从策略中删除所有已分配的用户：

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell？](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype 业务 online 的 Windows PowerShell 模块使您能够创建了业务 Online 和 Microsoft 团队连接到 Skype 远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
### <a name="related-topics"></a>相关主题
