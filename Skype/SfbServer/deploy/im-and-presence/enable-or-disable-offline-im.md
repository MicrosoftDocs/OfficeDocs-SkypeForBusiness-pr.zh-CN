---
title: 在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息。
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801942"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="9886b-103">在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息</span><span class="sxs-lookup"><span data-stu-id="9886b-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="9886b-104">了解如何在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息。</span><span class="sxs-lookup"><span data-stu-id="9886b-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="9886b-105">在 Skype for Business Server 中 (即时消息) IM 服务</span><span class="sxs-lookup"><span data-stu-id="9886b-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="9886b-106">脱机 IM 是内置于 Skype for Business 客户端 (2016 C2R 内部版本 16.0.6701.1000 或更高版本) 的客户端功能，利用 Exchange Web 服务 (EWS) 将邮件从 Skype for Business 客户端发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="9886b-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="9886b-107">脱机 IM 使用 Exchange Web 服务 (EWS) 将脱机邮件从 Skype for Business 客户端发送到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9886b-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="9886b-108">EWS 必须可用于 Skype for Business 客户端，以发送脱机消息。</span><span class="sxs-lookup"><span data-stu-id="9886b-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="9886b-109">若要了解有关规划即时消息和状态的信息，请参阅 Plan [for instant messaging and presence in Skype for Business Server。](../../plan-your-deployment/instant-messaging-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="9886b-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9886b-110">如果用户邮箱托管在本地 Exchange 中，则 Skype for Business 客户端 (2016 C2R 版本 16.0.6920.1000) 是必需的</span><span class="sxs-lookup"><span data-stu-id="9886b-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="9886b-111">在 Skype for Business Server 中启用或禁用脱机 IM</span><span class="sxs-lookup"><span data-stu-id="9886b-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="9886b-112">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9886b-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="9886b-113">运行以下命令以启用脱机 IM。</span><span class="sxs-lookup"><span data-stu-id="9886b-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="9886b-114">在 Skype for Business Server 2015 CU3 中，EnableOfflineIM 选项默认设置为$True启用。</span><span class="sxs-lookup"><span data-stu-id="9886b-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="9886b-115">若要禁用，请将其设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="9886b-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="9886b-116">运行以下命令以确认已设置存储脱机 IM 的能力。</span><span class="sxs-lookup"><span data-stu-id="9886b-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="9886b-117">脱机 IM 与 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="9886b-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="9886b-118">如果发件人的客户端策略禁止将脱机消息自动保存至对话历史记录文件夹 (EnableIMAutoArchiving = $false) ，则发件人将不能使用脱机 IM。</span><span class="sxs-lookup"><span data-stu-id="9886b-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="9886b-119">没有机制来检查收件人能否接收脱机邮件。</span><span class="sxs-lookup"><span data-stu-id="9886b-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="9886b-120">对于在同一组织内发送的脱机邮件，这些邮件将作为包含 IM.Note.MissedConversation 邮件类别的电子邮件接收，并且将包含在 Outlook **错过** 的对话文件夹中，以及对话历史记录（将在 Skype for Business 客户端的最近列表/对话历史记录选项卡中选取）。</span><span class="sxs-lookup"><span data-stu-id="9886b-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="9886b-121">对于从联盟组织发送的脱机消息，这些邮件将作为不带 IM.Note.MisssedConversation 的电子邮件接收，并且不会在错过的对话或对话历史记录文件夹中选取。</span><span class="sxs-lookup"><span data-stu-id="9886b-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="9886b-122">疑难解答</span><span class="sxs-lookup"><span data-stu-id="9886b-122">Troubleshooting</span></span>

<span data-ttu-id="9886b-123">从一个两分钟的计时器，从离线消息发送到何时选取和处理它。</span><span class="sxs-lookup"><span data-stu-id="9886b-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="9886b-124">如果无法处理脱机消息，它们将显示在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="9886b-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="9886b-125">主 Skype for Business ETL 日志将包含有关脱机邮件处理的信息，并且是调查/疑难解答的最佳来源。</span><span class="sxs-lookup"><span data-stu-id="9886b-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9886b-126">已报告脱机邮件发送失败以及"草稿"文件夹已填充邮件的问题。</span><span class="sxs-lookup"><span data-stu-id="9886b-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="9886b-127">这发生在 Exchange 本地邮箱中。</span><span class="sxs-lookup"><span data-stu-id="9886b-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="9886b-128">截至 2016 年 6 月 14 日，所有 C2R 频道中已解决该问题。</span><span class="sxs-lookup"><span data-stu-id="9886b-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
