---
title: 定义持久聊天 FQDN
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
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 使用"定义新的持久聊天池"向导创建新的持久聊天服务器或持久聊天服务器池。 选择"多计算机池"或"单计算机池"。 如果选择单计算机池，但后来需要多计算机池，则需要删除单计算机池，然后定义多计算机池。
ms.openlocfilehash: 2136d740a451670fe01d3123c48c63f3d7de0cc1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622454"
---
# <a name="define-persistent-chat-fqdn"></a>定义持久聊天 FQDN
 
使用"定义新的持久聊天池"向导创建新的持久聊天服务器或 **持久聊天服务器** 池。 选择"多 **计算机池"或**"**单计算机池"。** 如果选择单计算机池，但后来需要多计算机池，则需要删除单计算机池，然后定义多计算机池。
  
还必须为持久聊天服务器或持久聊天服务器池定义池 **FQDN。** 单个计算机池的池 (FQDN) FQDN 必须与单个服务器池的计算机的 FQDN 相同。 对于多计算机池，FQDN 必须是您选择用于表示此多计算机池的名称，并且由主机 A (和 AAAA 在 DNS 中定义（如果使用 IPv6) 记录）。
  
## <a name="see-also"></a>另请参阅

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
