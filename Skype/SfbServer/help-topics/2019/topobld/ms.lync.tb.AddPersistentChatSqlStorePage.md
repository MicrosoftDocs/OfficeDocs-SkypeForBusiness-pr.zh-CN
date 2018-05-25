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
description: 配置持久聊天服务器或持久聊天服务器池将提供数据库的 SQL Server 存储。
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-sql-server-store"></a>添加持久聊天 SQL Server 存储
 
配置持久聊天服务器或持久聊天服务器池将提供数据库的 SQL Server 存储。
  
 **SQL Server 存储**： 选择现有的 SQL Server 和可选实例的持久聊天。
  
单击**新建**以定义一个新的 SQL Server 和可选的持久聊天数据的新实例。
  
选择**启用 SQL Server 存储镜像**复选框以配置的 SQL Server 数据库和将持久聊天数据提供镜像的数据库的可选实例。
  
从**镜像 SQL Server 存储**列表中选择一个 SQL Server 和可选实例以用作持久聊天 SQL Server 的 SQL Server 镜像。
  
单击**新建**以定义一个新的 SQL Server 和可选的持久聊天 SQL Server 镜像的新实例。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或主机的数据的持久聊天服务器，但可确保只有一个 SQL Server 镜像配置中随时都是活动的 SQL Server。
  
单击**新建**以定义持久聊天 SQL server 镜像见证的一个新的 SQL Server 见证和可选实例。
  
单击“**上一步**”以回到上一个池定义对话框。
  
完成输入为该池的 SQL Server 存储配置并继续进行持久聊天服务器池定义的选项后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

#### 

[规划持久聊天服务器 Skype 中的业务 Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[拓扑的业务服务器 2015 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

