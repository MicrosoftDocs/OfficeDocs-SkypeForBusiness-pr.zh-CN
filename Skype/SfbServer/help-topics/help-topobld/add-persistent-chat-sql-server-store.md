---
title: 添加持久聊天 SQL Server 存储
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 配置将为SQL Server持久聊天服务器或持久聊天服务器池提供数据库的聊天存储。
ms.openlocfilehash: 7d3f9754e402c6049c4d0fd8cec9dd97758b5d32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630836"
---
# <a name="add-persistent-chat-sql-server-store"></a>添加持久聊天 SQL Server 存储
 
配置将为SQL Server持久聊天服务器或持久聊天服务器池提供数据库的聊天存储。
  
 **SQL Server存储**：选择现有SQL Server和可选的持久聊天实例。
  
单击 **"** 新建"定义SQL Server持久聊天数据的新实例（可选）。
  
选中"**启用SQL Server存储镜像**"复选框以配置将为持久聊天数据提供镜像数据库的 SQL Server 数据库和可选实例。
  
从"镜像"列表中 **SQL Server** 存储SQL Server和可选实例以用作持久聊天SQL Server的镜像SQL Server。
  
单击 **"** 新建"以定义SQL Server持久聊天策略镜像的新实例SQL Server实例。
  
从“使用 SQL Server 镜像见证启用自动故障转移”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或承载持久聊天服务器的数据，但确保镜像配置中SQL Server一个服务器是活动SQL Server处于活动状态。
  
单击 **"** 新建"以定义SQL Server持久聊天和镜像见证的SQL Server实例。
  
单击“上一步”以回到上一个池定义对话框。
  
完成 **为此** 池的"存储"SQL Server选项后，单击"下一步"，然后继续进行持久聊天服务器池定义。
  
单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。
  
单击“帮助”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 中的持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[在 2015 年 10 月为持久聊天服务器Skype for Business Server灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
