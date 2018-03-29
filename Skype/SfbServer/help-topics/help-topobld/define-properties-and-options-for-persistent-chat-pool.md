---
title: 定义持久聊天池的属性和选项
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 您可以通过定义下列属性配置选项持久聊天服务器或持久聊天服务器池：
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定义持久聊天池的属性和选项
 
您可以通过定义下列属性配置选项持久聊天服务器或持久聊天服务器池：
  
 **持续聊天池显示名称**： 必需的属性，定义将显示为此持续聊天服务器或持久聊天服务器池的用户友好名称。
  
 **持续聊天端口**： 所需的属性将定义端口号持久聊天服务器或持久聊天服务器池将侦听。
  
 **实现法规遵从性**： 如果您打算部署和实现的可选持久聊天的法规遵从性功能和数据库中选择复选框。
  
 **使用备份 SQL Server 存储以实现灾难恢复**： 选中此复选框，如果您打算部署和实现灾难恢复的持续讨论 SQL Server 存储从另一个 SQL Server 上的存储配置的备份集。 有关详细信息，请参阅[配置高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此选项仅适用于具有多台服务器的池。 
  
 **该池的默认值用于该网站\<在中配置此服务器或池的网站\>**： 如果这将是默认持久性聊天服务器或站点的持久聊天服务器池，请选中此复选框。 每个站点必须有一个默认的持久性聊天服务器或 pol。
  
> [!NOTE]
> 如果拓扑包括多个站点，则还会显示“**使用此池作为所有站点的默认池**”复选框。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池继续进行持续聊天服务器池定义的选项之后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 的持久聊天服务器业务服务器 2015年计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

