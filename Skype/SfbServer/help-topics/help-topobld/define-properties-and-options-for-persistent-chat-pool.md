---
title: 定义持久聊天池的属性和选项
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 通过定义以下属性配置持久聊天服务器或持久聊天服务器池的选项：
ms.openlocfilehash: 242490ebe6be0f68e8c25e0c01b77088c15836d8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622434"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定义持久聊天池的属性和选项
 
通过定义以下属性配置持久聊天服务器或持久聊天服务器池的选项：
  
 **持久聊天池** 的显示名称：定义将为此持久聊天服务器或持久聊天服务器池显示的用户友好名称的必需属性。
  
 **持久聊天端口**：定义此持久聊天服务器或持久聊天服务器池将侦听的端口号的必需属性。
  
 **启用合规性**：如果计划部署和实施可选的持久聊天合规性功能及数据库，请选中此复选框。
  
 使用SQL Server存储启用灾难恢复：如果计划从另一个存储上配置的备份存储集部署和实施持久聊天 SQL Server 存储的灾难恢复，请选中此SQL Server。 有关详细信息，请参阅 Configure [high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此选项仅适用于具有多台服务器的池。 
  
 **使用此池作为站点的默认 \<site that this server or pool is being configured in\>** 池：如果此池将是站点的默认持久聊天服务器或持久聊天服务器池，则选中此复选框。 每个站点必须具有一个默认的持久聊天服务器或 pol。
  
> [!NOTE]
> 如果拓扑包括多个站点，则还会显示“使用此池作为所有站点的默认池”复选框。
  
单击“上一步”以回到上一个池定义对话框。
  
完成 **为此** 池输入选项后，单击"下一步"以继续持久聊天服务器池定义。
  
单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。
  
单击“帮助”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
