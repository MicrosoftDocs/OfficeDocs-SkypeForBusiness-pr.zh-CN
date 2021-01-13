---
title: 添加持久聊天合规性 SQL Server 存储
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
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 配置将为持久SQL Server持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性存储。
ms.openlocfilehash: 1f931df0135e857b53a8067b114e3f9f438c614c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818692"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>添加持久聊天合规性 SQL Server 存储
 
配置将为持久SQL Server持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性存储。
  
 **SQL Server存储**：选择现有SQL Server和可选的持久聊天实例。
  
单击 **"** 新建"可定义SQL Server持久聊天合规性数据的新实例（可选）。
  
选中 **"启用SQL Server存储镜像** "复选框，以配置将为持久SQL Server合规性数据提供镜像数据库的 SQL Server 数据库和可选实例。
  
从列表 **镜像** SQL Server存储SQL Server和可选实例，以充当持久SQL Server合规性策略的镜像SQL Server。
  
单击 **"** 新建"可定义SQL Server持久聊天记录镜像的新实例和SQL Server实例。
  
从“使用 SQL Server 镜像见证启用自动故障转移”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。 见证服务器不镜像或承载持久聊天服务器的数据，但确保镜像配置SQL Server只有一个服务器是SQL Server活动服务器。
  
单击 **"** 新建"以定义一SQL Server见证持久聊天合规性实例（可选）SQL Server镜像见证。
  
单击“上一步”以回到上一个池定义对话框。
  
完成 **为此** 池的备份池存储配置输入SQL Server单击"下一步"，然后继续执行持久聊天服务器池定义。
  
单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。
  
单击“帮助”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在 Skype for Business Server 2015 中为持久聊天服务器配置合规性服务](../../manage/persistent-chat/configure-compliance.md)
