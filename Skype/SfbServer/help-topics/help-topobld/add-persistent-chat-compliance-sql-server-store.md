---
title: 添加持久聊天合规性 SQL Server 存储
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 配置 SQL Server 存储将持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性。
ms.openlocfilehash: 46b8052409bcb65a828bd07ebbec72d3b84c0962
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883072"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>添加持久聊天合规性 SQL Server 存储
 
配置 SQL Server 存储将持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性。
  
 **SQL Server 存储**： 选择现有的 SQL Server 和可选实例的持久聊天。
  
单击**新建**以定义一个新的 SQL Server 和可选的持久聊天合规性数据的新实例。
  
选择**启用 SQL Server 存储镜像**复选框以配置的 SQL Server 数据库和将持久聊天合规性数据提供镜像的数据库的可选实例。
  
从**镜像 SQL Server 存储**列表中选择一个 SQL Server 和可选实例以用作持久聊天合规性 SQL Server 的 SQL Server 镜像。
  
单击**新建**以定义一个新的 SQL Server 和可选的持久聊天 SQL Server 镜像的新实例。
  
从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或主机的数据的持久聊天服务器，但可确保只有一个 SQL Server 镜像配置中随时都是活动的 SQL Server。
  
单击**新建**以定义一个新的 SQL Server 见证和可选持久聊天合规性 SQL Server 镜像见证实例。
  
单击“**上一步**”以回到上一个池定义对话框。
  
完成输入为该池的备份 SQL Server 存储配置并继续进行持久聊天服务器池定义的选项后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[为 Skype for Business Server 2015 中的持久聊天服务器配置合规性服务](../../manage/persistent-chat/configure-compliance.md)
