---
title: 持久聊天常规设置扩展器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 通过配置或定义以下属性编辑持久聊天服务器或持久聊天服务器池的常规设置：
ms.openlocfilehash: e93af8c8924117159434691b550f2ed9fcbb6e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417685"
---
# <a name="persistent-chat-general-settings-expander"></a>持久聊天常规设置扩展器
 
通过配置 **或** 定义以下属性编辑持久聊天服务器或持久聊天服务器池的常规设置：
  
 **常规**
  
- **FQDN**：编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定域名
    
- **持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。 通过此设置，用户能够更轻松地关联基于 显示名称 的给定持久聊天服务器或持久聊天服务器池，而不是更难以理解的完全限定域名。
    
- **持久聊天端口**：指定要用于持久聊天的端口。
    
通过配置 **或** 定义以下属性编辑持久聊天服务器或持久聊天服务器池的关联设置：
  
 **关联**
  
- **SQL Server存储**：从SQL Server选择命名存储和可选命名实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要 **为主SQL Server** 启用镜像，请选中"启用存储镜像SQL Server复选框。
    
    如果选择启用存储SQL Server，请从"镜像和存储"列表中选择SQL Server **实例**。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望 **主SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移SQL Server复选框。
    
    如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要 **启用SQL Server** 灾难恢复，请选中"使用备份存储启用灾难恢复SQL Server复选框
    
    如果选择启用灾难恢复，则从“备份 SQL Server 存储”列表选择一个存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要 **为SQL Server** 镜像存储启用镜像，请选中"启用SQL Server镜像"复选框。
    
    如果选择启用备份和SQL Server镜像，请从"备份和存储镜像"列表中选择SQL Server **和实例**。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望 **备份SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移SQL Server复选框。
    
    如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要允许使用合规性数据库，则选中“启用合规性”复选框
    
    如果选择启用合规性，则从“合规性 SQL Server 存储”列表中选择一个存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要 **为合规性SQL Server** 启用镜像，请选中"启用SQL Server镜像"复选框。
    
    如果选择启用合规性和SQL Server镜像，请从"合规性存储镜像"列表中选择SQL Server **实例**。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望 **合规性SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移SQL Server复选框。
    
    如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果选择启用合规性，则从“备份合规性 SQL Server 存储”列表中选择一个存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果要 **为合规性SQL Server** 启用镜像，请选中"启用SQL Server镜像"复选框。
    
    如果选择启用合规性数据库SQL Server镜像，请从"备份合规性和存储镜像"列表中选择SQL Server **和实例**。
    
    单击“新建”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望 **备份合规性SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移SQL Server复选框。
    
    如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。
    
    单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- **文件存储** 从列表中选择文件存储位置，或单击 **"新建** "以创建新的文件存储。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[在 2015 年 10 月为持久聊天服务器Skype for Business Server灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
