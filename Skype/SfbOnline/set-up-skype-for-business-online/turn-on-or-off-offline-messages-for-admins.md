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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 3992c2b4be9cbaaee5f7e7c9648f90d8034bc6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884889"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>打开或关闭脱机消息（面向管理员）

您可以向您的联系人的业务 Im 的发送 Skype 即使未登录。 此功能可让你的联系人知道你已尝试联系他们。 你不必等待直到有人在线才发送消息给他们。

对于脱机消息，请务必了解：

- 脱机消息不会在用户的邮箱中存档。

- 脱机消息将发送到用户的邮箱，并登录到 for Business 的 Skype 时将通知用户。

- 如果在邮件收件人的状态设置为**请勿打扰**或**演示**，他们将收到错过的消息所发送的收件人的 Skype 业务客户端。

有关详细信息，请参阅[使用脱机消息 for Business 的 Skype](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。

## <a name="to-get-you-started"></a>开始使用

## #

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**

1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.

2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。

4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。

如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。

## #

 **启动 Windows PowerShell 会话**

1. From the **Start Menu** > **Windows PowerShell**.

2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：

    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Windows PowerShell 将计算机设置](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。

## <a name="turning-on-or-off-offline-im"></a>打开或关闭脱机即时消息

> [!NOTE]
> 脱机消息**仅**在单击即点即用 Skype 业务客户端的最新版本中可用和不可用时使用 for Business 旧单击即点即用 Skype 或 *.msi 文件用于安装业务客户端 Skype。

启用或禁用脱机邮件发送脱机消息在组织中的用户设置为_EnableIMAutoArchiving_ `True`或`False`。 默认情况下，这设置为`True`。

要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

要启用或禁用脱机邮件发送脱机邮件的用户，请将_EnableIMAutoArchiving_设置为`True`或`False`。 默认情况下设置为  `True`。 您可以使用现有的策略或创建一个类似于下面的示例。


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)

- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)


