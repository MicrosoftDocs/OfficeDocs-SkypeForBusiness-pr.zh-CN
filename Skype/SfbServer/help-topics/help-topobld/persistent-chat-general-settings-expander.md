---
title: 持久聊天常规设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 您可以通过配置或定义这些属性编辑为持久聊天服务器池的持久聊天服务器的常规设置：
ms.openlocfilehash: 84d6600c6ff99d55233ad40c7238fbb2c0480c98
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-general-settings-expander"></a>持久聊天常规设置扩展器
 
您可以通过配置或定义这些属性编辑为持久聊天服务器池的持久聊天服务器的**常规**设置：
  
 **常规**
  
- **FQDN**： 编辑此设置定义持久聊天服务器或持久聊天服务器池的完全限定的域名
    
- **持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。 此设置将使容易对您的用户将给定的持久聊天服务器或基于显示名称而不是更难理解完全合格的域名称的持久聊天服务器池相关联。
    
- **持久聊天端口**：指定要用于持久聊天的端口。
    
您可以通过配置或定义这些属性编辑持久聊天服务器或持久聊天服务器池的**关联**设置：
  
 **关联**
  
- **SQL Server 存储**：从列表中选择 SQL Server 存储和可选的命名实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用镜像的主 SQL Server 存储区，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果您选择启用 SQL Server 存储镜像，商店和实例从列表中选择**镜像 SQL Server 存储**。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果希望主 SQL Server 存储的自动故障切换，请选择**使用 SQL Server 镜像见证启用自动故障切换**复选框。
    
    如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 选择**使用备份 SQL Server 存储以实现灾难恢复**复选框如果您希望能够使用的 SQL Server 灾难恢复
    
    如果选择启用灾难恢复，则从“**备份 SQL Server 存储**”列表选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用镜像的镜像存储备份 SQL Server，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果您选择启用镜像备份 SQL Server 存储，存储和实例从列表中选择**备份 SQL Server 存储镜像**。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望备份的 SQL Server 存储的自动故障切换，请选择**使用 SQL Server 镜像见证启用自动故障切换**复选框。
    
    如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要允许使用合规性数据库，则选中“**启用合规性**”复选框
    
    如果选择启用合规性，则从“**合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用镜像为法规遵从性 SQL Server 存储，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果您选择启用镜像的法规遵从性 SQL Server 存储，存储和实例从列表中选择**法规遵从性 SQL Server 存储镜像**。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果所需的法规遵从性 SQL Server 存储的自动故障转移，请选中**使用 SQL Server 镜像见证启用自动故障切换**复选框。
    
    如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果选择启用合规性，则从“**备份合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用镜像为法规遵从性 SQL Server 存储，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果您选择启用镜像的法规遵从性 SQL Server 存储，存储和实例从列表中选择**备份法规遵从性 SQL Server 存储镜像**。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您希望备份法规遵从性 SQL Server 存储的自动故障转移，请选中**使用 SQL Server 镜像见证启用自动故障切换**复选框。
    
    如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- **文件存储**从列表中选择文件存储位置，或单击**新建**以创建新的文件存储。
    
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 的持久聊天服务器业务服务器 2015年计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

