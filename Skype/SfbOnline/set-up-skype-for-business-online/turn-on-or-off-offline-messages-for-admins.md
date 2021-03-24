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
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103818"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="9bebf-103">打开或关闭脱机消息（面向管理员）</span><span class="sxs-lookup"><span data-stu-id="9bebf-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="9bebf-104">你可以向联系人发送 Skype for Business VM，即使他们未登录。</span><span class="sxs-lookup"><span data-stu-id="9bebf-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="9bebf-105">此功能可让你的联系人知道你已尝试联系他们。</span><span class="sxs-lookup"><span data-stu-id="9bebf-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="9bebf-106">你不必等待直到有人在线才发送消息给他们。</span><span class="sxs-lookup"><span data-stu-id="9bebf-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="9bebf-107">对于脱机消息，请务必了解：</span><span class="sxs-lookup"><span data-stu-id="9bebf-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="9bebf-108">脱机消息不会在用户的邮箱中存档。</span><span class="sxs-lookup"><span data-stu-id="9bebf-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="9bebf-109">脱机消息将发送到用户的邮箱，当用户登录到 Skype for Business 时，他们将收到通知。</span><span class="sxs-lookup"><span data-stu-id="9bebf-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="9bebf-110">如果邮件收件人的状态设置为"请勿打扰"或"正在展示"，他们将收到从收件人的 Skype for Business 客户端发送的错过的消息。 </span><span class="sxs-lookup"><span data-stu-id="9bebf-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="9bebf-111">有关详细信息，请参阅在 [Skype for Business 中使用脱机消息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="9bebf-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="9bebf-112">开始使用</span><span class="sxs-lookup"><span data-stu-id="9bebf-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="9bebf-113">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="9bebf-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="9bebf-114">如果你使用的是最新的 Teams PowerShell 公共版本，则不需要安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="9bebf-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="9bebf-115">安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="9bebf-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="9bebf-116">打开 Windows PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9bebf-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="9bebf-117">若要详细了解如何启动 Windows PowerShell，请参阅在单个 Windows PowerShell 窗口中连接到所有[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9bebf-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="9bebf-118">打开或关闭脱机即时消息</span><span class="sxs-lookup"><span data-stu-id="9bebf-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="9bebf-119">脱机消息仅在最新版即点即用 Skype for Business 客户端中可用，在使用旧版即点即用 Skype for Business 或 \*.msi 文件安装 Skype for Business 客户端时不可用。</span><span class="sxs-lookup"><span data-stu-id="9bebf-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="9bebf-120">若要为组织中用户启用或禁用脱机消息发送脱机消息，请将  _EnableIMAutoArchiving 设置为_ `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="9bebf-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="9bebf-121">默认情况下，这设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="9bebf-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="9bebf-122">要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：</span><span class="sxs-lookup"><span data-stu-id="9bebf-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="9bebf-123">若要为用户启用或禁用脱机消息发送脱机消息，请将  _EnableIMAutoArchiving 设置为_ `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="9bebf-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="9bebf-124">默认情况下设置为  `True`。</span><span class="sxs-lookup"><span data-stu-id="9bebf-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="9bebf-125">可以使用现有策略，也可以创建一个，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9bebf-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9bebf-126">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="9bebf-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9bebf-127">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="9bebf-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9bebf-128">使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="9bebf-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9bebf-129">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9bebf-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9bebf-130">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="9bebf-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9bebf-131">你可能希望使用 Office 365 Windows PowerShell Office 365 的六大原因</span><span class="sxs-lookup"><span data-stu-id="9bebf-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="9bebf-132">Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。</span><span class="sxs-lookup"><span data-stu-id="9bebf-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9bebf-133">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="9bebf-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="9bebf-134">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9bebf-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="9bebf-135">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9bebf-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9bebf-136">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="9bebf-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="9bebf-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="9bebf-137">Related topics</span></span>
[<span data-ttu-id="9bebf-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9bebf-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9bebf-139">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="9bebf-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)