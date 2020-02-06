---
title: 在 Skype for Business 服务器中启用或禁用脱机即时消息（IM）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何在 Skype for Business 服务器中启用或禁用脱机即时消息（IM）。
ms.openlocfilehash: d96c7fc0de51cbdcfb6ba3acde3bf854c874f05b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795323"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="2ee1a-103">在 Skype for Business 服务器中启用或禁用脱机即时消息（IM）</span><span class="sxs-lookup"><span data-stu-id="2ee1a-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="2ee1a-104">了解如何在 Skype for Business 服务器中启用或禁用脱机即时消息（IM）。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="2ee1a-105">在 Skype for Business 服务器中启用脱机即时消息（IM）</span><span class="sxs-lookup"><span data-stu-id="2ee1a-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="2ee1a-106">脱机 IM 是内置于 Skype for Business 客户端（2016 C2R build 16.0.6701.1000 或更高版本）的客户端功能，它利用 Exchange Web 服务（EWS）将消息从 Skype for business 客户端发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="2ee1a-107">脱机 IM 使用 Exchange Web 服务（EWS）将脱机消息从 Skype for Business 客户端发送到收件人邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="2ee1a-108">EWS 必须适用于要发送的脱机消息的 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="2ee1a-109">若要了解有关如何规划即时消息和状态的详细信息，请参阅[在 Skype For Business 服务器中规划即时消息和状态](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ee1a-110">如果用户的邮箱托管在本地 Exchange 中，则需要 Skype for business 客户端（2016 C2R build 16.0.6920.1000）</span><span class="sxs-lookup"><span data-stu-id="2ee1a-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="2ee1a-111">在 Skype for Business 服务器中启用或禁用脱机即时消息</span><span class="sxs-lookup"><span data-stu-id="2ee1a-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="2ee1a-112">打开 Skype for Business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="2ee1a-113">运行以下命令以启用离线 IM。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="2ee1a-114">在 Skype for Business Server 2015 CU3 中，EnableOfflineIM 选项默认设置为 "$True"。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="2ee1a-115">要禁用，请将此值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="2ee1a-116">运行以下命令以确认是否设置了存储脱机 IM 的功能。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="2ee1a-117">离线 IM 与 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="2ee1a-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="2ee1a-p103">如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="2ee1a-120">对于在同一组织内发送的脱机消息，他们将收到一封带有 IM 邮件类的电子邮件。注意： MissedConversation 和将包含在 Outlook "**错过的对话**" 文件夹中，以及将在 Skype for business 客户端的 "最近的列表/对话历史记录" 选项卡中选取的对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="2ee1a-121">从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="2ee1a-122">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2ee1a-122">Troubleshooting</span></span>

<span data-ttu-id="2ee1a-123">当收到和处理脱机消息时，将出现两分钟计时器。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="2ee1a-124">如果脱机消息无法处理，它们将显示在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="2ee1a-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="2ee1a-125">主要的 Skype for Business ETL 日志将包含有关脱机消息处理的信息，并且是用于调查/疑难解答的最佳来源。</span><span class="sxs-lookup"><span data-stu-id="2ee1a-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2ee1a-p105">我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。 </span><span class="sxs-lookup"><span data-stu-id="2ee1a-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
