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
description: 通过配置或定义以下属性编辑持久聊天服务器或持久聊天服务器池的常规设置：
ms.openlocfilehash: 912cacaa050962b85d8e3f70bec78f01306909d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374957"
---
# <a name="persistent-chat-general-settings-expander"></a>持久聊天常规设置扩展器
 
通过配置或定义以下属性编辑持久聊天服务器或持久聊天服务器池的**常规**设置：
  
 **常规**
  
- **FQDN**： 编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定的域名
    
- **持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。 此设置将使您将给定的持久聊天服务器或基于而不是更加难以理解完全限定的域名的显示名称的持久聊天服务器池相关联的用户可以更轻松。
    
- **持久聊天端口**：指定要用于持久聊天的端口。
    
通过配置或定义以下属性编辑持久聊天服务器或持久聊天服务器池的**关联**设置：
  
 **关联**
  
- **SQL Server 存储**：从列表中选择 SQL Server 存储和可选的命名实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用主 SQL Server 存储镜像，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果选择启用 SQL Server 存储镜像，则从**镜像 SQL Server 存储**列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果希望主 SQL Server 存储的自动故障转移，请选择**使用 SQL Server 镜像见证启用自动故障转移**复选框。
    
    如果选择启用 SQL Server 存储镜像见证启用自动故障转移，则从列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果您想要启用使用 SQL Server 灾难恢复，请选择**使用备份 SQL Server 存储启用灾难恢复**复选框
    
    如果选择启用灾难恢复，则从“**备份 SQL Server 存储**”列表选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用备份 SQL server 镜像存储镜像，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果选择启用备份 SQL Server 存储镜像，则从**备份 SQL Server 存储镜像**列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果需要备份 SQL Server 存储的自动故障转移，请选择**使用 SQL Server 镜像见证启用自动故障转移**复选框。
    
    如果选择启用 SQL Server 存储镜像见证启用自动故障转移，则从列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果要允许使用合规性数据库，则选中“**启用合规性**”复选框
    
    如果选择启用合规性，则从“**合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用的合规性 SQL Server 存储镜像，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果选择启用合规性 SQL Server 存储镜像，则从**合规性 SQL Server 存储镜像**列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果希望合规性 SQL Server 存储的自动故障转移，请选择**使用 SQL Server 镜像见证启用自动故障转移**复选框。
    
    如果选择启用 SQL Server 存储镜像见证启用自动故障转移，则从列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- 如果选择启用合规性，则从“**备份合规性 SQL Server 存储**”列表中选择一个存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果您想要启用的合规性 SQL Server 存储镜像，请选择**启用 SQL Server 存储镜像**复选框。
    
    如果选择启用合规性 SQL Server 存储镜像，则从**备份合规性 SQL Server 存储镜像**列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。
    
- 如果需要备份合规性 SQL Server 存储的自动故障转移，请选择**使用 SQL Server 镜像见证启用自动故障转移**复选框。
    
    如果选择启用 SQL Server 存储镜像见证启用自动故障转移，则从列表选择存储和实例。
    
    单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。
    
- **文件存储**从列表中，选择一个文件存储位置，或单击**新建**创建新文件存储。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)