---
title: 定义持久聊天池的属性和选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 通过定义以下属性，可以配置持久聊天服务器或持久聊天服务器池的选项：
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218543"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定义持久聊天池的属性和选项
 
通过定义以下属性，可以配置持久聊天服务器或持久聊天服务器池的选项：
  
 **持久聊天池的显示名称**：一个必需属性，用于定义将为此持久聊天服务器或持久聊天服务器池显示的用户友好名称。
  
 **Persistent 聊天端口**：一个必需属性，它将定义此持久聊天服务器或持久聊天服务器池将侦听的端口号。
  
 **启用符合性**：如果您计划部署和实现可选的持久聊天合规性功能和数据库，请选中此复选框。
  
 **使用 BACKUP SQL Server 存储来启用灾难恢复**：如果计划从另一 SQL Server 上配置的存储备份集部署和实现持久聊天 SQL server 存储的灾难恢复，请选中此复选框。 有关详细信息，请参阅 [在 Skype for Business server 2015 中为持久聊天服务器配置高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此选项仅适用于具有多台服务器的池。 
  
 将**此池用作 \<site that this server or pool is being configured in\> 网站的默认值**：如果这将是该网站的默认持久聊天服务器或持久聊天服务器池，请选中此复选框。 每个站点必须有一个默认的持久聊天服务器或池。
  
> [!NOTE]
> 如果拓扑包括多个站点，则还会显示“使用此池作为所有站点的默认池”**** 复选框。
  
单击“上一步”**** 以回到上一个池定义对话框。
  
完成输入此池的选项后，单击 " **下一步** " 以继续使用持久聊天服务器池定义。
  
单击“取消”**** 以放弃所有更改并退出“定义新的持久聊天池”**** 向导。
  
单击“帮助”**** 以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
