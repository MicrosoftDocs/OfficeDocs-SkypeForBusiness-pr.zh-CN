---
title: 定义持久聊天 FQDN
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 您创建一个新的持久聊天服务器或使用定义新的持久聊天池向导的持久聊天服务器池。 选择多计算机池或单计算机池。 如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。
ms.openlocfilehash: b4fbeb54c926573e908b361e7556fab9d87da848
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="define-persistent-chat-fqdn"></a>定义持久聊天 FQDN
 
您创建一个新的持久聊天服务器或使用**定义新的持久聊天池**向导的持久聊天服务器池。 选择“**多计算机池**”或“**单计算机池**”。 如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。
  
您还必须持久聊天服务器或持久聊天服务器池定义**池 FQDN** 。 单计算机池的池完全限定域名 (FQDN) 必须与组成单服务器池的计算机的 FQDN 相同。 对于多计算机池，FQDN 必须为您选择表示此多计算机池的名称，并且在 DNS 中由主机 A（如果使用 IPv6，则为 AAAA）记录定义。
  
## <a name="see-also"></a>另请参阅

#### 

[规划持久聊天服务器 Skype 中的业务 Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

