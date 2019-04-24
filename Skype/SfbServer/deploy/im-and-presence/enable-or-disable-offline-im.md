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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>启用或禁用业务服务器脱机即时消息 (IM) 中 Skype
 
了解如何启用或禁用业务服务器脱机即时消息 (IM) Skype 中。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>启用业务服务器脱机即时消息 (IM) 中 Skype

脱机 IM 是内置 Skype 业务客户端的客户端侧功能 (2016 C2R 构建 16.0.6701.1000 或更高版本) 的利用 Exchange Web Services (EWS) 将消息从业务客户端 Skype 发送到用户的 Exchange 邮箱。 脱机 IM 使用 Exchange Web Services (EWS) 从业务客户端 Skype 的脱机消息发送到收件人的邮箱。 EWS 必须可供用于脱机发送的消息的业务客户端 Skype。 若要了解更多有关规划即时消息和状态，请参阅[规划即时消息和 Skype 业务服务器中的状态](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> 业务客户端 （2016 C2R 生成 16.0.6920.1000） Skype 如果用户的邮箱位于中 Exchange 内部部署，则需要 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>若要启用或禁用业务服务器脱机 Skype 中的 IM

1. 打开 Skype 业务 Server 命令行管理程序。
    
2. 运行以下命令以启用离线 IM。
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在业务服务器 2015 CU3 的 Skype，默认情况下 EnableOfflineIM 选项设置为 $True。 要禁用，请将此值设置为 $False。 
  
3. 运行以下命令以确认设置存储脱机 IM 的能力。
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>离线 IM 与 Exchange 集成

如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。
  
脱机发送的邮件同一组织中将作为电子邮件与 IM 的邮件类接收它们。Note.MissedConversation 和将包括在 Outlook**错过的对话**文件夹以及其中的选取新列表/对话历史记录的选项卡中 Skype 业务客户端的对话历史记录。
  
从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。 
  
## <a name="troubleshooting"></a>疑难解答

没有从时脱机消息它具有选取和处理时发送到两个分钟计时器。 如果无法处理脱机消息它们将显示在以下目录： 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

业务 ETL 日志主 Skype 将包含有关脱机消息处理的信息，调查/故障排除您最佳源。 
  
> [!NOTE]
> 我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。   
