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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中启用或禁用脱机即时消息 (IM)
 
了解如何启用或禁用脱机即时消息 (IM) 在 Skype 业务服务器 2015年个。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>启用脱机即时消息 (IM) 在 Skype 业务服务器 2015

脱机即时消息是一种客户端侧功能，内置 Skype 业务客户端 (2016 C2R 生成 16.0.6701.1000 或更高版本)，利用 Exchange Web 服务 (EWS) 将消息从 Skype 业务客户端发送到用户的 Exchange 邮箱。 脱机即时消息使用 Exchange Web 服务 (EWS) 将脱机消息从 Skype 业务客户端发送到收件人的邮箱。 EWS 必须可供业务客户端脱机邮件发送 Skype。 要了解更多有关规划的即时消息和状态，请参阅[计划即时消息和 Skype 的业务服务器 2015年遍布](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> 业务客户端 （2016 C2R 生成 16.0.6920.1000） 的 Skype 用户的邮箱位于中交换内部，如果是必需的 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a>若要启用或禁用脱机即时消息在 Skype 的 CU3 具有的业务服务器 2015

1. 企业服务器管理外壳程序打开 Skype。
    
2. 运行以下命令以启用离线 IM。
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在 Skype 的业务服务器 2015 CU3，EnableOfflineIM 选项是默认设置为 $True。 要禁用，请将此值设置为 $False。 
  
3. 运行以下命令以确定设置存储脱机即时消息的能力。
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>离线 IM 与 Exchange 集成

如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。
  
脱机消息在同一组织内发送将电子邮件和即时消息的邮件类作为接收他们。Note.MissedConversation，将包括在**错过对话**的 Outlook 文件夹中，以及将选取在 Skype 的最新列表/对话历史记录选项卡中为业务客户端会话历史记录。
  
从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。 
  
## <a name="troubleshooting"></a>疑难解答

还有两分钟计时器从在脱机消息发送到已接听并处理。 如果不能处理脱机消息它们将显示在下面的目录： 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

主要 Skype 业务 ETL 日志将包含有关脱机消息处理的信息，是您最佳的诊断调查/来源。 
  
> [!NOTE]
> 我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。  
  

