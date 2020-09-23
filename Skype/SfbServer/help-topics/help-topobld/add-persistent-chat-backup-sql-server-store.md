---
title: 添加持久聊天备份 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 您可以配置将为持久聊天服务器或持久聊天服务器池提供备份数据库的备份 SQL Server 存储。
ms.openlocfilehash: 70eec229c567120d0669979f688c152e1b1e3d79
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218703"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>添加持久聊天备份 SQL Server 存储
 
您可以配置将为持久聊天服务器或持久聊天服务器池提供备份数据库的备份 SQL Server 存储。
  
 **SQL server 存储**：选择现有的 SQL Server 和持久聊天的实例（可选）。
  
单击 " **新建** " 以定义一个新的 SQL Server 和持久聊天备份数据的新实例（可选）。
  
选中 " **启用 Sql server 存储镜像** " 复选框，以配置将为持久聊天备份数据提供镜像数据库的 SQL server 数据库和可选实例。
  
从 " **镜像 Sql server 存储** " 列表中选择 "将 sql server 和可选实例用作持久聊天备份 sql SERVER 的 sql server 镜像"。
  
单击 " **新建** " 以定义一个新的 sql server，以及（可选）持久聊天 SQL server 镜像的新实例。
  
从“使用 SQL Server 镜像见证启用自动故障转移”**** 列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不会对持久聊天服务器的数据进行镜像或主机数据，但可确保镜像配置中的每个 SQL Server 在任何时候都是活动的 SQL Server。
  
单击 " **新建** " 以定义一个新的 SQL server 见证，其中一个持久聊天备份 SQL server 镜像见证的实例（可选）。
  
单击“上一步”**** 以回到上一个池定义对话框。
  
完成为此池的备份 SQL Server 存储配置输入选项后，请单击 " **下一步** "，然后继续使用持久聊天服务器池定义。
  
单击“取消”**** 以放弃所有更改并退出“定义新的持久聊天池”**** 向导。
  
单击“帮助”**** 以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在 Skype for business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
