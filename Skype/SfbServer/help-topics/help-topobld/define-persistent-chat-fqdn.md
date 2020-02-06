---
title: 定义持久聊天 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 使用 "定义新的持久聊天池" 向导创建新的持久聊天服务器或持久聊天服务器池。 选择“多计算机池”或“单计算机池”。 如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820194"
---
# <a name="define-persistent-chat-fqdn"></a>定义持久聊天 FQDN
 
使用 "**定义新的持久聊天池**" 向导创建新的持久聊天服务器或持久聊天服务器池。 选择“**多计算机池**”或“**单计算机池**”。 如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。
  
你还必须为持久聊天服务器或持久聊天服务器池定义**池 FQDN** 。 单计算机池的池完全限定域名 (FQDN) 必须与组成单服务器池的计算机的 FQDN 相同。 对于多计算机池，FQDN 必须为您选择表示此多计算机池的名称，并且在 DNS 中由主机 A（如果使用 IPv6，则为 AAAA）记录定义。
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
