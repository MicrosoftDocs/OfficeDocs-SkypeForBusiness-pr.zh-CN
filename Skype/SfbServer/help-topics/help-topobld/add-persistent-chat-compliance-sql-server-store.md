---
title: 添加持久聊天合规性 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 配置将为持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性 SQL Server 存储。
ms.openlocfilehash: fd51b3d582c915d02799f2f633869e84f3659c4f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820684"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>添加持久聊天合规性 SQL Server 存储
 
配置将为持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性 SQL Server 存储。
  
 **SQL server 应用商店**：选择现有的 SQL server 和（可选）持久聊天的实例。
  
单击 "**新建**" 以定义新的 SQL Server，还可以选择新的持久聊天合规性数据实例。
  
选中 "**启用 Sql server 应用商店镜像**" 复选框以配置 sql server 数据库和可选实例，该实例将为持久聊天合规性数据提供镜像数据库。
  
从列表中选择 "**镜像 sql** server" 将 sql server 和可选实例用作持久的聊天合规性 sql SERVER 的 sql server 镜像。
  
单击 "**新建**" 以定义新的 SQL Server 和持久聊天 SQL server 镜像的新实例（可选）。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不会镜像或承载持久聊天服务器的数据，但可确保镜像配置中的每个 SQL Server 在任何时候都是活动 SQL 服务器。
  
单击 "**新建**" 以定义一个新的 SQL server 见证，此实例针对持久聊天兼容性 SQL server 镜像见证。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池的备份 SQL Server 应用商店配置的选项后，单击 "**下一步**"，然后继续使用持久聊天服务器池定义。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[为 Skype for Business Server 2015 中的持久聊天服务器配置合规性服务](../../manage/persistent-chat/configure-compliance.md)
