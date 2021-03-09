---
title: 打开或关闭脱机消息（面向管理员）
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568752"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>打开或关闭脱机消息（面向管理员）

你可以向联系人发送 Skype for Business VM，即使他们未登录。 此功能可让你的联系人知道你已尝试联系他们。 你不必等待直到有人在线才发送消息给他们。

对于脱机消息，请务必了解：

- 脱机消息不会在用户的邮箱中存档。

- 脱机消息将发送到用户的邮箱，当用户登录到 Skype for Business 时，用户将收到通知。

- 如果邮件收件人的状态设置为"请勿打扰"或"正在展示"，他们将收到从收件人的 Skype for Business 客户端发送的错过的消息。 

有关详细信息，请参阅"[在 Skype for Business 中使用脱机消息"。](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>开始使用

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
如果希望详细了解如何启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>打开或关闭脱机即时消息

> [!NOTE]
> 脱机消息仅在最新版即点即用 Skype for Business 客户端中可用，在使用旧版即点即用 Skype for Business 或 *.msi 文件安装 Skype for Business 客户端时不可用。

若要为组织中用户启用或禁用脱机消息发送脱机消息，请将  _EnableIMAutoArchiving 设置为_ `True` 或 `False` 。 默认情况下，这设置为 `True` 。

要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要为用户启用或禁用脱机消息发送脱机消息，请将  _EnableIMAutoArchiving 设置为_ `True` 或 `False` 。 默认情况下设置为  `True`。 可以使用现有策略，也可以创建一个，如以下示例所示。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，当你有多个任务需要执行时，可以使用单点管理来管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [你可能想要使用 office 365 Windows PowerShell Office 365 的六大原因](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。 通过以下主题了解这些优势：

  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
