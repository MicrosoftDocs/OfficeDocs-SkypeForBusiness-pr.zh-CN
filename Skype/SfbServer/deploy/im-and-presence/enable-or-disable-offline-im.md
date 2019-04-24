---
title: 启用或禁用业务服务器脱机即时消息 (IM) 中 Skype
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何启用或禁用业务服务器脱机即时消息 (IM) Skype 中。
ms.openlocfilehash: 29342f3903e58f90ab4d2a939be6cd20d3f8e31b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217661"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="89663-103">启用或禁用业务服务器脱机即时消息 (IM) 中 Skype</span><span class="sxs-lookup"><span data-stu-id="89663-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="89663-104">了解如何启用或禁用业务服务器脱机即时消息 (IM) Skype 中。</span><span class="sxs-lookup"><span data-stu-id="89663-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="89663-105">启用业务服务器脱机即时消息 (IM) 中 Skype</span><span class="sxs-lookup"><span data-stu-id="89663-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="89663-106">脱机 IM 是内置 Skype 业务客户端的客户端侧功能 (2016 C2R 构建 16.0.6701.1000 或更高版本) 的利用 Exchange Web Services (EWS) 将消息从业务客户端 Skype 发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="89663-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="89663-107">脱机 IM 使用 Exchange Web Services (EWS) 从业务客户端 Skype 的脱机消息发送到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="89663-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="89663-108">EWS 必须可供用于脱机发送的消息的业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="89663-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="89663-109">若要了解更多有关规划即时消息和状态，请参阅[规划即时消息和 Skype 业务服务器中的状态](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="89663-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="89663-110">业务客户端 （2016 C2R 生成 16.0.6920.1000） Skype 如果用户的邮箱位于中 Exchange 内部部署，则需要</span><span class="sxs-lookup"><span data-stu-id="89663-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="89663-111">若要启用或禁用业务服务器脱机 Skype 中的 IM</span><span class="sxs-lookup"><span data-stu-id="89663-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="89663-112">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="89663-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="89663-113">运行以下命令以启用离线 IM。</span><span class="sxs-lookup"><span data-stu-id="89663-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="89663-114">在业务服务器 2015 CU3 的 Skype，默认情况下 EnableOfflineIM 选项设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="89663-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="89663-115">要禁用，请将此值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="89663-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="89663-116">运行以下命令以确认设置存储脱机 IM 的能力。</span><span class="sxs-lookup"><span data-stu-id="89663-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="89663-117">离线 IM 与 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="89663-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="89663-p103">如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。</span><span class="sxs-lookup"><span data-stu-id="89663-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="89663-120">脱机发送的邮件同一组织中将作为电子邮件与 IM 的邮件类接收它们。Note.MissedConversation 和将包括在 Outlook**错过的对话**文件夹以及其中的选取新列表/对话历史记录的选项卡中 Skype 业务客户端的对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="89663-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="89663-121">从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。</span><span class="sxs-lookup"><span data-stu-id="89663-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="89663-122">疑难解答</span><span class="sxs-lookup"><span data-stu-id="89663-122">Troubleshooting</span></span>

<span data-ttu-id="89663-123">没有从时脱机消息它具有选取和处理时发送到两个分钟计时器。</span><span class="sxs-lookup"><span data-stu-id="89663-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="89663-124">如果无法处理脱机消息它们将显示在以下目录：</span><span class="sxs-lookup"><span data-stu-id="89663-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="89663-125">业务 ETL 日志主 Skype 将包含有关脱机消息处理的信息，调查/故障排除您最佳源。</span><span class="sxs-lookup"><span data-stu-id="89663-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89663-p105">我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。 </span><span class="sxs-lookup"><span data-stu-id="89663-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
