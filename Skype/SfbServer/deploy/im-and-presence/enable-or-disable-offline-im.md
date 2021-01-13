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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息
 
了解如何在 Skype for Business Server 中启用 (IM) 或禁用脱机即时消息。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>在 Skype for Business Server 中 (即时消息) IM 服务

脱机 IM 是内置于 Skype for Business 客户端 (2016 C2R 内部版本 16.0.6701.1000 或更高版本) 的客户端功能，利用 Exchange Web 服务 (EWS) 将邮件从 Skype for Business 客户端发送到用户的 Exchange 邮箱。 脱机 IM 使用 Exchange Web 服务 (EWS) 将脱机邮件从 Skype for Business 客户端发送到收件人的邮箱。 EWS 必须可用于 Skype for Business 客户端，以发送脱机消息。 若要了解有关规划即时消息和状态的信息，请参阅 Plan [for instant messaging and presence in Skype for Business Server。](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> 如果用户邮箱托管在本地 Exchange 中，则 Skype for Business 客户端 (2016 C2R 版本 16.0.6920.1000) 是必需的 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>在 Skype for Business Server 中启用或禁用脱机 IM

1. 打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下命令以启用脱机 IM。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在 Skype for Business Server 2015 CU3 中，EnableOfflineIM 选项默认设置为$True启用。 若要禁用，请将其设置为 $False。 
  
3. 运行以下命令以确认已设置存储脱机 IM 的能力。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>脱机 IM 与 Exchange 集成

如果发件人的客户端策略禁止将脱机消息自动保存至对话历史记录文件夹 (EnableIMAutoArchiving = $false) ，则发件人将不能使用脱机 IM。 没有机制来检查收件人能否接收脱机邮件。
  
对于在同一组织内发送的脱机邮件，这些邮件将作为包含 IM.Note.MissedConversation 邮件类别的电子邮件接收，并且将包含在 Outlook **错过** 的对话文件夹中，以及对话历史记录（将在 Skype for Business 客户端的最近列表/对话历史记录选项卡中选取）。
  
对于从联盟组织发送的脱机消息，这些邮件将作为不带 IM.Note.MisssedConversation 的电子邮件接收，并且不会在错过的对话或对话历史记录文件夹中选取。 
  
## <a name="troubleshooting"></a>疑难解答

从一个两分钟的计时器，从离线消息发送到何时选取和处理它。 如果无法处理脱机消息，它们将显示在以下目录中： 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

主 Skype for Business ETL 日志将包含有关脱机邮件处理的信息，并且是调查/疑难解答的最佳来源。 
  
> [!NOTE]
> 已报告脱机邮件发送失败以及"草稿"文件夹已填充邮件的问题。 这发生在 Exchange 本地邮箱中。 截至 2016 年 6 月 14 日，所有 C2R 频道中已解决该问题。  
