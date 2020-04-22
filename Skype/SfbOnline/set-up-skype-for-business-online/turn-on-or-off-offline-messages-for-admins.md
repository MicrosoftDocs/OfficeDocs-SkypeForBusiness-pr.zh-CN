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
ms.openlocfilehash: 03e92118fd915582030b5259654664121ca96c50
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777137"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="86aed-103">打开或关闭脱机消息（面向管理员）</span><span class="sxs-lookup"><span data-stu-id="86aed-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="86aed-p101">您可以将 Skype for business 即时消息发送给您的联系人，即使他们未登录也是如此。此功能可让你的联系人知道你已尝试访问它们。您无需等到某人联机才能发送邮件。</span><span class="sxs-lookup"><span data-stu-id="86aed-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="86aed-107">对于脱机消息，请务必了解：</span><span class="sxs-lookup"><span data-stu-id="86aed-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="86aed-108">脱机消息不会在用户的邮箱中存档。</span><span class="sxs-lookup"><span data-stu-id="86aed-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="86aed-109">脱机消息将发送到用户的邮箱，当用户登录到 Skype for Business 时，将收到通知。</span><span class="sxs-lookup"><span data-stu-id="86aed-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="86aed-110">如果邮件收件人的状态设置为 "请勿**打扰**" 或 "正在**演示**"，他们将收到从收件人的 Skype for business 客户端发送的错过的消息。</span><span class="sxs-lookup"><span data-stu-id="86aed-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="86aed-111">有关详细信息，请参阅[在 Skype For business 中使用脱机消息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="86aed-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="86aed-112">开始使用</span><span class="sxs-lookup"><span data-stu-id="86aed-112">To get you started</span></span>

## #

 <span data-ttu-id="86aed-113">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="86aed-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="86aed-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="86aed-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="86aed-115">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="86aed-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="86aed-116">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="86aed-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="86aed-117">请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="86aed-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="86aed-118">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="86aed-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="86aed-p103">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="86aed-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="86aed-122">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="86aed-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="86aed-123">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="86aed-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="86aed-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="86aed-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="86aed-125">在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="86aed-125">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="86aed-126">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="86aed-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="86aed-127">如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="86aed-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="86aed-128">打开或关闭脱机即时消息</span><span class="sxs-lookup"><span data-stu-id="86aed-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="86aed-129">脱机消息**仅**在最新版本的 "即点即用 skype for business 客户端" 中可用，在使用较旧的即点即用 skype for business 时不可用，或者使用 \* .msi 文件安装 Skype for business 客户端时不可用。</span><span class="sxs-lookup"><span data-stu-id="86aed-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="86aed-130">若要启用或禁用脱机消息，请为组织中的用户发送脱机消息， `True`将`False` _EnableIMAutoArchiving_设置为或。</span><span class="sxs-lookup"><span data-stu-id="86aed-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="86aed-131">默认情况下，"" 设置`True`为 ""。</span><span class="sxs-lookup"><span data-stu-id="86aed-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="86aed-132">要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：</span><span class="sxs-lookup"><span data-stu-id="86aed-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="86aed-133">若要启用或禁用脱机消息，请为用户发送脱机消息_EnableIMAutoArchiving_ ，将`True` EnableIMAutoArchiving `False`设置为或。</span><span class="sxs-lookup"><span data-stu-id="86aed-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="86aed-134">默认情况下设置为  `True`。</span><span class="sxs-lookup"><span data-stu-id="86aed-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="86aed-135">可以使用现有策略，也可以创建类似于下面的示例的策略。</span><span class="sxs-lookup"><span data-stu-id="86aed-135">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="86aed-136">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="86aed-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="86aed-137">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="86aed-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="86aed-138">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="86aed-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="86aed-139">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="86aed-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="86aed-140">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="86aed-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="86aed-141">可能希望使用 Windows PowerShell 管理 Office 365 的六个原因</span><span class="sxs-lookup"><span data-stu-id="86aed-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="86aed-142">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="86aed-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="86aed-143">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="86aed-143">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="86aed-144">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="86aed-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="86aed-145">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86aed-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="86aed-146">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="86aed-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="86aed-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="86aed-147">Related topics</span></span>
[<span data-ttu-id="86aed-148">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="86aed-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="86aed-149">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="86aed-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


