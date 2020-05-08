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
ms.openlocfilehash: 4af24f66aa82bbd0f0099e062981157b08c639db
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164091"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>打开或关闭脱机消息（面向管理员）

您可以将 Skype for business 即时消息发送给您的联系人，即使他们未登录也是如此。此功能可让你的联系人知道你已尝试访问它们。您无需等到某人联机才能发送邮件。

对于脱机消息，请务必了解：

- 脱机消息不会在用户的邮箱中存档。

- 脱机消息将发送到用户的邮箱，当用户登录到 Skype for Business 时，将收到通知。

- 如果邮件收件人的状态设置为 "请勿**打扰**" 或 "正在**演示**"，他们将收到从收件人的 Skype for business 客户端发送的错过的消息。

有关详细信息，请参阅[在 Skype For business 中使用脱机消息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。

## <a name="to-get-you-started"></a>开始使用

## #

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**

1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.

2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。 出现提示时，请重启计算机。

4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。

如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。

## #

 **启动 Windows PowerShell 会话**

1. From the **Start Menu** > **Windows PowerShell**.

2. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：

    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。

## <a name="turning-on-or-off-offline-im"></a>打开或关闭脱机即时消息

> [!NOTE]
> 脱机消息**仅**在最新版本的 "即点即用 skype for business 客户端" 中可用，在使用较旧的即点即用 skype for business 时不可用，或者使用 * .msi 文件安装 Skype for business 客户端时不可用。

若要启用或禁用脱机消息，请为组织中的用户发送脱机消息， `True`将`False` _EnableIMAutoArchiving_设置为或。 默认情况下，"" 设置`True`为 ""。

要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要启用或禁用脱机消息，请为用户发送脱机消息_EnableIMAutoArchiving_ ，将`True` EnableIMAutoArchiving `False`设置为或。 默认情况下设置为  `True`。 可以使用现有策略，也可以创建类似于下面的示例的策略。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [可能希望使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六个原因](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：

  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)


