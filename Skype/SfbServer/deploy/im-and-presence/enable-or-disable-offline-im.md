---
title: 启用或禁用脱机即时消息 (即时消息) 即时消息Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何在客户端中启用或禁用 (即时消息) IM Skype for Business Server。
ms.openlocfilehash: 36894fb2a1ed11428b21b572a28e9ac177a4237d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753324"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>启用或禁用脱机即时消息 (即时消息) 即时消息Skype for Business Server
 
了解如何在客户端中启用或禁用 (即时消息) IM Skype for Business Server。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>在客户端中启用 (即时消息) IM Skype for Business Server

脱机 IM 是内置在 Skype for Business 客户端 (2016 C2R 内部版本 16.0.6701.1000 或更高版本) 中的客户端功能，它利用 Exchange Web 服务 (EWS) 将邮件从 Skype for Business 客户端发送到用户的 Exchange 邮箱。 脱机 IM 使用 Exchange Web (EWS) 将脱机消息从 Skype for Business 客户端发送到收件人的邮箱。 EWS 必须可用于 Skype for Business 客户端，以发送脱机消息。 若要了解有关规划即时消息和状态的信息，请参阅规划即时消息[和](../../plan-your-deployment/instant-messaging-and-presence.md)状态Skype for Business Server。
  
> [!NOTE]
> 如果用户邮箱托管在本地 Exchange 中，则 Skype for Business 客户端 (2016 C2R 内部版本 16.0.6920.1000) 是必需的 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>启用或禁用脱机 IM Skype for Business Server

1. 打开"Skype for Business Server命令行管理程序"。
    
2. 运行以下命令以启用脱机 IM。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在 Skype for Business Server 2015 CU3 中，EnableOfflineIM 选项$True默认设置。 若要禁用，将此值设置为 $False。 
  
3. 运行以下命令以确认已设置存储脱机 IM 的能力。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>脱机 IM 与 Exchange

如果发件人具有禁用将脱机消息自动保存到对话历史记录文件夹的客户端策略，则发件人将 (EnableIMAutoArchiving = $false) 。 没有机制可检查收件人能否接收脱机邮件。
  
对于在同一组织内发送的脱机消息，这些消息作为 IM.Note.MissedConversation 邮件类别的电子邮件接收，并且将包含在 Outlook 错过的对话文件夹中，以及对话历史记录（将在 Skype for Business 客户端的最近列表/对话历史记录选项卡中选取）。
  
对于从联盟组织发送的脱机消息，这些消息将作为没有 IM.Note.MisssedConversation 的电子邮件接收，并且不会在错过的对话或对话历史记录文件夹中进行选取。 
  
## <a name="troubleshooting"></a>疑难解答

从发送脱机消息到选取和处理脱机消息的时间，有两分钟计时器。 如果无法处理脱机消息，它们将显示在以下目录中： 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

ETL 日志Skype for Business包含有关脱机邮件处理的信息，是调查/疑难解答的最佳来源。 
  
> [!NOTE]
> 已报告一个问题，其中脱机邮件发送失败，"草稿"文件夹填充了邮件。 这发生在Exchange邮箱中。 截至 2016 年 6 月 14 日，该问题已在所有 C2R 频道中修复。  
