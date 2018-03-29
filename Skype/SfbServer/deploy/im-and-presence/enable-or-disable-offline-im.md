---
title: 在 Skype for Business Server 2015 中启用或禁用脱机即时消息 (IM)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何启用或禁用脱机即时消息 (IM) 在 Skype 业务服务器 2015年个。
ms.openlocfilehash: a9133ad82e4d25fae2aebd266273ecbb37c2a010
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="37d5d-103">在 Skype for Business Server 2015 中启用或禁用脱机即时消息 (IM)</span><span class="sxs-lookup"><span data-stu-id="37d5d-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="37d5d-104">了解如何启用或禁用脱机即时消息 (IM) 在 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="37d5d-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server 2015.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="37d5d-105">启用脱机即时消息 (IM) 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="37d5d-105">Enable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>

<span data-ttu-id="37d5d-106">脱机即时消息是一种客户端侧功能，内置 Skype 业务客户端 (2016 C2R 生成 16.0.6701.1000 或更高版本)，利用 Exchange Web 服务 (EWS) 将消息从 Skype 业务客户端发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="37d5d-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="37d5d-107">脱机即时消息使用 Exchange Web 服务 (EWS) 将脱机消息从 Skype 业务客户端发送到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="37d5d-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="37d5d-108">EWS 必须可供业务客户端脱机邮件发送 Skype。</span><span class="sxs-lookup"><span data-stu-id="37d5d-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="37d5d-109">要了解更多有关规划的即时消息和状态，请参阅[计划即时消息和 Skype 的业务服务器 2015年遍布](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="37d5d-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="37d5d-110">业务客户端 （2016 C2R 生成 16.0.6920.1000） 的 Skype 用户的邮箱位于中交换内部，如果是必需的</span><span class="sxs-lookup"><span data-stu-id="37d5d-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a><span data-ttu-id="37d5d-111">若要启用或禁用脱机即时消息在 Skype 的 CU3 具有的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="37d5d-111">To enable or disable Offline IM in Skype for Business Server 2015 with CU3</span></span>

1. <span data-ttu-id="37d5d-112">企业服务器管理外壳程序打开 Skype。</span><span class="sxs-lookup"><span data-stu-id="37d5d-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="37d5d-113">运行以下命令以启用离线 IM。</span><span class="sxs-lookup"><span data-stu-id="37d5d-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="37d5d-114">在 Skype 的业务服务器 2015 CU3，EnableOfflineIM 选项是默认设置为 $True。</span><span class="sxs-lookup"><span data-stu-id="37d5d-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="37d5d-115">要禁用，请将此值设置为 $False。</span><span class="sxs-lookup"><span data-stu-id="37d5d-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="37d5d-116">运行以下命令以确定设置存储脱机即时消息的能力。</span><span class="sxs-lookup"><span data-stu-id="37d5d-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="37d5d-117">离线 IM 与 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="37d5d-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="37d5d-p103">如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。</span><span class="sxs-lookup"><span data-stu-id="37d5d-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="37d5d-120">脱机消息在同一组织内发送将电子邮件和即时消息的邮件类作为接收他们。Note.MissedConversation，将包括在**错过对话**的 Outlook 文件夹中，以及将选取在 Skype 的最新列表/对话历史记录选项卡中为业务客户端会话历史记录。</span><span class="sxs-lookup"><span data-stu-id="37d5d-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="37d5d-121">从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。</span><span class="sxs-lookup"><span data-stu-id="37d5d-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="37d5d-122">疑难解答</span><span class="sxs-lookup"><span data-stu-id="37d5d-122">Troubleshooting</span></span>

<span data-ttu-id="37d5d-123">还有两分钟计时器从在脱机消息发送到已接听并处理。</span><span class="sxs-lookup"><span data-stu-id="37d5d-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="37d5d-124">如果不能处理脱机消息它们将显示在下面的目录：</span><span class="sxs-lookup"><span data-stu-id="37d5d-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

<span data-ttu-id="37d5d-125">主要 Skype 业务 ETL 日志将包含有关脱机消息处理的信息，是您最佳的诊断调查/来源。</span><span class="sxs-lookup"><span data-stu-id="37d5d-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="37d5d-p105">我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。 </span><span class="sxs-lookup"><span data-stu-id="37d5d-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span> 
  

