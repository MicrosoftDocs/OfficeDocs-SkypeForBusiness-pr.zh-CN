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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 可通过定义以下属性来配置持久聊天服务器或持久聊天服务器池的选项：
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697547"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定义持久聊天池的属性和选项
 
可通过定义以下属性来配置持久聊天服务器或持久聊天服务器池的选项：
  
 **持久聊天池的显示名称**：一个必需属性，定义将为此持久聊天服务器或持久聊天服务器池显示的用户友好名称。
  
 **持久聊天端口**：将定义此永久聊天服务器或持久聊天服务器池将侦听的端口号的 "必需" 属性。
  
 **启用合规性**：如果你计划部署和实现可选的持久聊天合规性功能和数据库，请选中该复选框。
  
 **使用备份 SQL Server 存储来启用灾难恢复**：如果你计划从另一个 SQL Server 上配置的存储备份集部署和实现持久聊天 SQL Server 存储的灾难恢复，请选中此复选框。 有关详细信息，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此选项仅适用于具有多台服务器的池。 
  
 **将此池用作在\<\>其中配置此服务器或池的网站网站的默认值**：如果这将是该网站的默认持久聊天服务器或持久聊天服务器池，请选中此复选框。 每个网站必须有一个默认持久聊天服务器或 pol。
  
> [!NOTE]
> 如果拓扑包括多个站点，则还会显示“**使用此池作为所有站点的默认池**”复选框。
  
单击“**上一步**”以回到上一个池定义对话框。
  
输入此池的选项后，单击 "**下一步**" 以继续使用持久聊天服务器池定义。
  
单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。
  
单击“**帮助**”以访问上下文相关帮助，例如此页面。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
