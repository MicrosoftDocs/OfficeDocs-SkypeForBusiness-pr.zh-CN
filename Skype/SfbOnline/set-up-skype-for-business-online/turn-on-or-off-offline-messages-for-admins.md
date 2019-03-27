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
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="8e735-103">打开或关闭脱机消息（面向管理员）</span><span class="sxs-lookup"><span data-stu-id="8e735-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="8e735-104">您可以向您的联系人的业务 Im 的发送 Skype 即使未登录。</span><span class="sxs-lookup"><span data-stu-id="8e735-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="8e735-105">此功能可让你的联系人知道你已尝试联系他们。</span><span class="sxs-lookup"><span data-stu-id="8e735-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="8e735-106">你不必等待直到有人在线才发送消息给他们。</span><span class="sxs-lookup"><span data-stu-id="8e735-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="8e735-107">对于脱机消息，请务必了解：</span><span class="sxs-lookup"><span data-stu-id="8e735-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="8e735-108">脱机消息不会在用户的邮箱中存档。</span><span class="sxs-lookup"><span data-stu-id="8e735-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="8e735-109">脱机消息将发送到用户的邮箱，并登录到 for Business 的 Skype 时将通知用户。</span><span class="sxs-lookup"><span data-stu-id="8e735-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="8e735-110">如果在邮件收件人的状态设置为**请勿打扰**或**演示**，他们将收到错过的消息所发送的收件人的 Skype 业务客户端。</span><span class="sxs-lookup"><span data-stu-id="8e735-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="8e735-111">有关详细信息，请参阅[使用脱机消息 for Business 的 Skype](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="8e735-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="8e735-112">开始使用</span><span class="sxs-lookup"><span data-stu-id="8e735-112">To get you started</span></span>

## #

 <span data-ttu-id="8e735-113">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="8e735-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="8e735-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8e735-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="8e735-115">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="8e735-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="8e735-p102">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="8e735-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="8e735-p103">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="8e735-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="8e735-122">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e735-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="8e735-123">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="8e735-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="8e735-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8e735-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="8e735-125">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="8e735-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="8e735-126">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="8e735-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="8e735-127">如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Windows PowerShell 将计算机设置](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="8e735-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="8e735-128">打开或关闭脱机即时消息</span><span class="sxs-lookup"><span data-stu-id="8e735-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="8e735-129">脱机消息**仅**在单击即点即用 Skype 业务客户端的最新版本中可用和不可用时使用 for Business 旧单击即点即用 Skype 或 \*.msi 文件用于安装业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="8e735-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="8e735-130">启用或禁用脱机邮件发送脱机消息在组织中的用户设置为_EnableIMAutoArchiving_ `True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="8e735-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="8e735-131">默认情况下，这设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="8e735-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="8e735-132">要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：</span><span class="sxs-lookup"><span data-stu-id="8e735-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="8e735-133">要启用或禁用脱机邮件发送脱机邮件的用户，请将_EnableIMAutoArchiving_设置为`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="8e735-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="8e735-134">默认情况下设置为  `True`。</span><span class="sxs-lookup"><span data-stu-id="8e735-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="8e735-135">您可以使用现有的策略或创建一个类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="8e735-135">You can use an existing policy or create one like the example below.</span></span>


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8e735-136">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="8e735-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="8e735-137">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="8e735-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8e735-138">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="8e735-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8e735-139">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="8e735-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="8e735-140">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="8e735-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="8e735-141">为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）</span><span class="sxs-lookup"><span data-stu-id="8e735-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="8e735-p107">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="8e735-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="8e735-144">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="8e735-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="8e735-145">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8e735-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="8e735-146">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="8e735-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="8e735-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="8e735-147">Related topics</span></span>
[<span data-ttu-id="8e735-148">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8e735-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8e735-149">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="8e735-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


