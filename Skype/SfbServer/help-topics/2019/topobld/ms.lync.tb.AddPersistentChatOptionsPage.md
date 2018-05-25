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
description: 通过定义以下属性配置持久聊天服务器或持久聊天服务器池的选项：
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定义持久聊天池的属性和选项
 
通过定义以下属性配置持久聊天服务器或持久聊天服务器池的选项：
  
 **持久聊天池的显示名称**： 必需的属性，定义将显示此持久聊天服务器或持久聊天服务器池的用户友好名称。
  
 **持久聊天端口**： 必需的属性，将定义的端口号此持久聊天服务器或 Persistent Chat Server pool 将侦听。
  
 **启用合规性**： 如果您打算部署和实施可选持久聊天合规性功能和数据库，请选择复选框。
  
 **使用备份 SQL Server 存储启用灾难恢复**： 选中此复选框，如果您计划部署和实施灾难恢复的持久聊天 SQL Server 存储从另一个 SQL Server 上的存储配置的备份集。 有关详细信息，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此选项仅适用于具有多台服务器的池。 
  
 **使用此池作为默认网站\<中，为其配置此服务器或池的站点\>**： 选中此复选框，如果将该站点的持久聊天服务器池的默认持久聊天服务器。 每个站点，您必须具有一个默认持久聊天服务器或 pol。
  
> [!NOTE]
> 如果拓扑包括多个站点，则还会显示“**使用此池作为所有站点的默认池**”复选框。
  
单击“**上一步**”以回到上一个池定义对话框。
  
完成为该池，然后继续进行持久聊天服务器池定义输入选项后，请单击**下一步**。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

#### 

[规划持久聊天服务器 Skype 中的业务 Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

