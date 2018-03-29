---
title: 添加持久聊天合规性备份 SQL Server 存储
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 您配置的备份法规遵从性存储 SQL Server 将为永久的聊天服务器提供备份数据库或 SQL Server 存储持久聊天服务器法规遵从性。
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>添加持久聊天合规性备份 SQL Server 存储
 
您配置的备份法规遵从性存储 SQL Server 将为永久的聊天服务器提供备份数据库或 SQL Server 存储持久聊天服务器法规遵从性。
  
 **SQL Server 存储**： 为持久聊天中选择现有的 SQL Server 和实例 （可选）。
  
单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天的备份法规遵从性数据的新实例。
  
选择**启用 SQL Server 存储镜像**复选框来配置 SQL Server 数据库和可选将提供持久聊天备份法规遵从性数据镜像的数据库的实例。
  
从**镜像 SQL Server 存储**列表中选择要用作 SQL Server 镜像持久聊天备份法规遵从性 SQL Server 的 SQL Server 和可选的实例。
  
单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天 SQL Server 镜像的新实例。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或主机的数据持久聊天服务器，但可以确保将镜像配置中只有一个 SQL Server 在任何时间进行活动的 SQL Server。
  
单击**新建**以定义新的 SQL Server 见证 （可选） 持续聊天备份法规遵从性 SQL Server 镜像见证的实例。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池的备份 SQL Server 存储配置并继续持久聊天服务器池定义的选项之后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 的持久聊天服务器业务服务器 2015年计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在 Skype 为业务服务器 2015年配置持久聊天服务器的法规遵从性服务](../../manage/persistent-chat/configure-compliance.md)
  
[为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

