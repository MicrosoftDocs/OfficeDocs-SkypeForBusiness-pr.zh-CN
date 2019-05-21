---
title: 添加持久聊天 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。
ms.openlocfilehash: 3d6e5464cf435440cc7e7b1b29aa5a22ae2cbb0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302278"
---
# <a name="add-persistent-chat-sql-server-store"></a>添加持久聊天 SQL Server 存储
 
配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。
  
 **SQL server 应用商店**: 选择现有的 SQL server 和 (可选) 持久聊天的实例。
  
单击 "**新建**" 以定义新的 SQL Server 和持久聊天数据的新实例 (可选)。
  
选中 "**启用 Sql server 应用商店镜像**" 复选框, 以配置 sql server 数据库和可为持久聊天数据提供镜像数据库的可选实例。
  
从列表中选择 "**镜像 sql** server" 将 sql server 和可选实例用作持久聊天 sql SERVER 的 sql server 镜像。
  
单击 "**新建**" 以定义新的 SQL Server 和持久聊天 SQL server 镜像的新实例 (可选)。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不会镜像或承载持久聊天服务器的数据, 但可确保镜像配置中的每个 SQL Server 在任何时候都是活动 SQL 服务器。
  
单击 "**新建**" 以定义新的 SQL server 见证 (可选择一个持久聊天 sql server 镜像见证的实例)。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池的 SQL Server 应用商店配置的选项后, 单击 "**下一步**", 然后继续使用持久聊天服务器池定义。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
