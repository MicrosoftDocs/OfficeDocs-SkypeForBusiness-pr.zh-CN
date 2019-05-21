---
title: 持久聊天常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: '通过配置或定义这些属性, 可以编辑持久聊天服务器或持久聊天服务器池的常规设置:'
ms.openlocfilehash: c79ef61e2b7609aa344766c37cf38adaa195f23d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289971"
---
# <a name="persistent-chat-general-settings-expander"></a>持久聊天常规设置扩展器
 
通过配置或定义这些属性, 可以编辑持久聊天服务器或持久聊天服务器池的**常规**设置:
  
 **常规**
  
- **FQDN**: 编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定的域名
    
- **持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。 此设置将使你的用户能够更轻松地基于显示名称关联给定的持久聊天服务器或持久聊天服务器池, 而不是更难理解完全限定的域名。
    
- **持久聊天端口**：指定要用于持久聊天的端口。
    
通过配置或定义这些属性, 可以编辑持久聊天服务器或持久聊天服务器池的**关联**设置:
  
 **关联**
  
- **SQL Server 存储**：从列表中选择 SQL Server 存储和可选的命名实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要为主 SQL Server 应用商店启用镜像, 请选中 "**启用 SQL Server 应用商店镜像**" 复选框。
    
    如果您选择启用 SQL Server 应用商店镜像, 请从列表**镜像 SQL Server 应用商店**中选择应用商店和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果需要主 SQL Server 应用商店的自动故障转移, 请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。
    
    如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移, 请从列表中选择 "应用商店和实例"。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要启用 SQL Server 灾难恢复的使用, 请选中 "**使用备份 SQL Server 存储来启用灾难恢复**" 复选框
    
    如果选择启用灾难恢复，则从“**备份 SQL Server 存储**”列表选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要为备份 SQL Server 镜像存储启用镜像, 请选中 "**启用 SQL server 应用商店镜像**" 复选框。
    
    如果您选择启用 "备份 SQL Server 应用商店镜像", 请从列表中选择 "**备份 Sql server 存储" 镜像**中的应用商店和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果需要自动故障切换备份 SQL Server 应用商店, 请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。
    
    如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移, 请从列表中选择 "应用商店和实例"。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要允许使用合规性数据库，则选中“**启用合规性**”复选框
    
    如果选择启用合规性，则从“**合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要为合规性 SQL Server 应用商店启用镜像, 请选中 "**启用 SQL server 应用商店镜像**" 复选框。
    
    如果你选择启用合规性 SQL Server 应用商店镜像, 请从 "列表**合规性 Sql server 应用商店镜像**" 中选择应用商店和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果需要自动故障转移 SQL Server 应用商店, 请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。
    
    如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移, 请从列表中选择 "应用商店和实例"。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果选择启用合规性，则从“**备份合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要为合规性 SQL Server 应用商店启用镜像, 请选中 "**启用 SQL server 应用商店镜像**" 复选框。
    
    如果你选择启用合规性 SQL Server 应用商店镜像, 请从列表中选择 "**备份合规性 Sql server 应用商店" 镜像**中的应用商店和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果想要自动执行备份合规性 SQL Server 应用商店, 请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。
    
    如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移, 请从列表中选择 "应用商店和实例"。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- **文件存储**从列表中选择文件存储位置, 或单击 "**新建**" 以创建新的文件存储。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
