---
title: 添加持久聊天备份 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 配置将为持久SQL Server持久聊天服务器或持久聊天服务器池提供备份数据库的备份数据库。
ms.openlocfilehash: c62cf2114d2a982e70aa6218b90109d7fafcea2f85abf9aff5bfd155a5ddef76
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302556"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>添加持久聊天备份 SQL Server 存储
 
配置将为持久SQL Server持久聊天服务器或持久聊天服务器池提供备份数据库的备份数据库。
  
 **SQL Server存储**：选择现有SQL Server持久聊天的实例（可选）。
  
单击 **"** 新建"以定义SQL Server持久聊天备份数据的新实例（可选）。
  
选中"**启用SQL Server存储镜像**"复选框以配置将为持久聊天备份数据提供镜像数据库的 SQL Server 数据库和可选实例。
  
从列表"**镜像**"SQL Server存储SQL Server和可选实例，以用作持久SQL Server持久聊天备份SQL Server。
  
单击 **"** 新建"以定义SQL Server持久聊天策略镜像的新实例SQL Server实例。
  
从“使用 SQL Server 镜像见证启用自动故障转移”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或承载持久聊天服务器的数据，但确保镜像配置中SQL Server一个服务器是SQL Server活动服务器。
  
单击 **"** 新建"以定义新的SQL Server（可选）用于镜像见证的持久聊天SQL Server实例。
  
单击“上一步”以回到上一个池定义对话框。
  
完成 **为此** 池的备份选项输入存储配置SQL Server单击"下一步"，然后继续进行持久聊天服务器池定义。
  
单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。
  
单击“帮助”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 中的持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在 2015 年 10 月为持久聊天服务器Skype for Business Server灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
