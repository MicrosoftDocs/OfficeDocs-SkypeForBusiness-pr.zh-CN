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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 使用 "定义新的持久聊天池" 向导创建新的持久聊天服务器或持久聊天服务器池。 选择 "多计算机池" 或 "单个计算机池"。 如果选择单个计算机池，并且后来需要多个计算机池，则需要删除该单个计算机池，然后再定义多台计算机池。
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217544"
---
# <a name="define-persistent-chat-fqdn"></a>定义持久聊天 FQDN
 
使用 " **定义新的持久聊天池** " 向导创建新的持久聊天服务器或持久聊天服务器池。 选择 " **多计算机池** " 或 " **单个计算机池**"。 如果选择单个计算机池，并且后来需要多个计算机池，则需要删除该单个计算机池，然后再定义多台计算机池。
  
此外，还必须为持久聊天服务器或持久聊天服务器池定义 **池 FQDN** 。 单个计算机池 (FQDN) 的池完全限定域名必须与组成单个服务器池的计算机的 FQDN 相同。 对于多计算机池，FQDN 必须是您选择用来表示此多计算机池的名称，并且由主机 A (和 AAAA 在 DNS 中定义，前提是) 记录使用 IPv6。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
