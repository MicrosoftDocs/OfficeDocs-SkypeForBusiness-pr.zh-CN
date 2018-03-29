---
title: 添加持久聊天 SQL Server 存储
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-sql-server-store"></a>添加持久聊天 SQL Server 存储
 
配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。
  
 **SQL Server 存储**： 为持久聊天中选择现有的 SQL Server 和实例 （可选）。
  
单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天数据的新实例。
  
选择**启用 SQL Server 存储镜像**复选框来配置 SQL Server 数据库和可选将提供持久聊天数据镜像的数据库的实例。
  
从**镜像 SQL Server 存储**列表中选择要作为持久聊天 SQL Server SQL Server 镜像的 SQL Server 和可选的实例。
  
单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天 SQL Server 镜像的新实例。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或主机的数据持久聊天服务器，但可以确保将镜像配置中只有一个 SQL Server 在任何时间进行活动的 SQL Server。
  
单击**新建**定义持久聊天 SQL Server 镜像见证新的 SQL Server 见证服务器实例 （可选）。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池的 SQL Server 存储配置并继续持久聊天服务器池定义的选项之后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 的持久聊天服务器业务服务器 2015年计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype 业务服务器 2015年拓扑结构基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

