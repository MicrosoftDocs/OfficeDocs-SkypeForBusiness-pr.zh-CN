---
title: 添加持久聊天合规性备份 SQL Server 存储
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 配置将为持久SQL Server持久聊天服务器或持久聊天服务器合规性存储提供备份数据库的备份SQL Server数据库。
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818712"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>添加持久聊天合规性备份 SQL Server 存储
 
配置将为持久SQL Server持久聊天服务器或持久聊天服务器合规性存储提供备份数据库的备份SQL Server数据库。
  
 **SQL Server存储**：选择现有SQL Server和可选的持久聊天实例。
  
单击 **"** 新建"可定义SQL Server持久聊天备份合规性数据的新实例（可选）。
  
选中 **"启用SQL Server存储镜像** "复选框以配置一个SQL Server数据库和一个可选实例，这些实例将为持久聊天备份合规性数据提供镜像数据库。
  
从 **列表镜像SQL Server** 存储SQL Server和可选实例，以充当持久SQL Server备份合规性策略的镜像SQL Server。
  
单击 **"** 新建"可定义SQL Server持久聊天记录镜像的新实例和SQL Server实例。
  
从“使用 SQL Server 镜像见证启用自动故障转移”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或承载持久聊天服务器的数据，但确保镜像配置SQL Server只有一个服务器是SQL Server活动服务器。
  
单击 **"** 新建"可定义一SQL Server见证镜像见证中的持久聊天备份合规性SQL Server实例。
  
单击“上一步”以回到上一个池定义对话框。
  
完成 **为此** 池的备份池存储配置输入SQL Server单击"下一步"，然后继续执行持久聊天服务器池定义。
  
单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。
  
单击“帮助”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在 Skype for Business Server 2015 中为持久聊天服务器配置合规性服务](../../manage/persistent-chat/configure-compliance.md)
  
[在 Skype for Business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
