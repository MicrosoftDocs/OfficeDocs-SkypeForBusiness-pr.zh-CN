---
title: 在 Skype for Business 服务器中启用或禁用脱机即时消息 (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 了解如何在 Skype for Business 服务器中启用或禁用脱机即时消息 (IM)。
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289705"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用脱机即时消息 (IM)
 
了解如何在 Skype for Business 服务器中启用或禁用脱机即时消息 (IM)。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用脱机即时消息 (IM)

脱机 IM 是内置于 Skype for Business 客户端 (2016 C2R build 16.0.6701.1000 或更高版本) 的客户端功能, 它利用 Exchange Web 服务 (EWS) 将消息从 Skype for business 客户端发送到用户的 Exchange 邮箱。 脱机 IM 使用 Exchange Web 服务 (EWS) 将脱机消息从 Skype for Business 客户端发送到收件人邮箱。 EWS 必须适用于要发送的脱机消息的 Skype for Business 客户端。 若要了解有关如何规划即时消息和状态的详细信息, 请参阅[在 Skype For Business 服务器中规划即时消息和状态](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> 如果用户的邮箱托管在本地 Exchange 中, 则需要 Skype for business 客户端 (2016 C2R build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用脱机即时消息

1. 打开 Skype for Business 服务器命令行管理程序。
    
2. 运行以下命令以启用离线 IM。
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在 Skype for Business Server 2015 CU3 中, EnableOfflineIM 选项默认设置为 "$True"。 要禁用，请将此值设置为 $False。 
  
3. 运行以下命令以确认是否设置了存储脱机 IM 的功能。
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>离线 IM 与 Exchange 集成

如果发件人采用了禁止将离线消息自动保存到对话历史记录文件夹的客户端策略 (EnableIMAutoArchiving = $false)，他们将无法使用离线 IM。没有用于检查收件人是否可以接收离线消息的机制。
  
对于在同一组织内发送的脱机消息, 他们将收到一封带有 IM 邮件类的电子邮件。注意: MissedConversation 和将包含在 Outlook "**错过的对话**" 文件夹中, 以及将在 Skype for business 客户端的 "最近的列表/对话历史记录" 选项卡中选取的对话历史记录。
  
从联盟组织发送的离线消息将作为不带 IM.Note.MisssedConversation 的电子邮件消息接收，并且不能从错过的对话或对话历史记录文件夹中获取。 
  
## <a name="troubleshooting"></a>疑难解答

当收到和处理脱机消息时, 将出现两分钟计时器。 如果脱机消息无法处理, 它们将显示在以下目录中: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

主要的 Skype for Business ETL 日志将包含有关脱机消息处理的信息, 并且是用于调查/疑难解答的最佳来源。 
  
> [!NOTE]
> 我们收到了关于离线消息发送失败并且消息显示在“草稿”文件夹中的问题报告。此问题出现在 Exchange 内部部署邮箱中。此问题已在 2016 年 6 月 14 日之后的所有 C2R 渠道中得以解决。   
