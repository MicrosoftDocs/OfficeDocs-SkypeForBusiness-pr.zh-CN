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
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="8640b-105">定义持久聊天 FQDN</span><span class="sxs-lookup"><span data-stu-id="8640b-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="8640b-106">您创建一个新的持久聊天服务器或使用**定义新的持久聊天池**向导的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="8640b-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="8640b-107">选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="8640b-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="8640b-108">如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。</span><span class="sxs-lookup"><span data-stu-id="8640b-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="8640b-109">您还必须持久聊天服务器或持久聊天服务器池定义**池 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="8640b-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="8640b-110">单计算机池的池完全限定域名 (FQDN) 必须与组成单服务器池的计算机的 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="8640b-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="8640b-111">对于多计算机池，FQDN 必须为您选择表示此多计算机池的名称，并且在 DNS 中由主机 A（如果使用 IPv6，则为 AAAA）记录定义。</span><span class="sxs-lookup"><span data-stu-id="8640b-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8640b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8640b-112">See also</span></span>

#### 

[<span data-ttu-id="8640b-113">规划持久聊天服务器 Skype 中的业务 Server 2015</span><span class="sxs-lookup"><span data-stu-id="8640b-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="8640b-114">向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="8640b-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

