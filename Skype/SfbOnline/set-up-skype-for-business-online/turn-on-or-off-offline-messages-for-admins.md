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
ms.openlocfilehash: 7c579e947383c9165035c7cd6a5baee6f2012a1f5bba063dd433f40b95faa164
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326659"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>打开或关闭脱机消息（面向管理员）

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

即使联系人Skype for Business，也可以向联系人发送这些 VM。 此功能可让你的联系人知道你已尝试联系他们。 你不必等待直到有人在线才发送消息给他们。

对于脱机消息，请务必了解：

- 脱机消息不会在用户的邮箱中存档。

- 脱机邮件将发送到用户的邮箱，当用户登录到用户邮箱时Skype for Business。

- 如果邮件收件人的状态设置为"请勿打扰"或"正在展示"，他们将收到从收件人的客户端发送的Skype for Business邮件。 

有关详细信息，请参阅在 Skype for Business[中使用脱机Skype for Business。](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>开始使用

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
若要详细了解如何启动 Windows PowerShell，请参阅连接窗口中Office 365所有[](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)Windows PowerShell 服务，或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>打开或关闭脱机即时消息

> [!NOTE]
> 脱机消息 **仅在** 最新版本的即点即用 Skype for Business 客户端中可用，在使用旧版即点即用 Skype for Business 或 *.msi 文件安装 Skype for Business 客户端时不可用。

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

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次为许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：

  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
