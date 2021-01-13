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
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 使用"定义新的持久聊天池"向导创建新的持久聊天服务器或持久聊天服务器池。 选择多计算机池或单计算机池。 如果选择单个计算机池，但之后需要多计算机池，则需要删除单个计算机池，然后定义一个多计算机池。
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818442"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="5cfb7-105">定义持久聊天 FQDN</span><span class="sxs-lookup"><span data-stu-id="5cfb7-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="5cfb7-106">使用"定义新的持久聊天池"向导创建新的持久聊天服务器或 **持久聊天服务器** 池。</span><span class="sxs-lookup"><span data-stu-id="5cfb7-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="5cfb7-107">选择多 **计算机池或\*\*\*\*单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="5cfb7-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="5cfb7-108">如果选择单个计算机池，但之后需要多计算机池，则需要删除单个计算机池，然后定义一个多计算机池。</span><span class="sxs-lookup"><span data-stu-id="5cfb7-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="5cfb7-109">还必须为持久聊天服务器或持久聊天服务器池定义池 **FQDN。**</span><span class="sxs-lookup"><span data-stu-id="5cfb7-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="5cfb7-110">单个计算机池 (FQDN) 的池完全限定域名必须与单个服务器池的计算机的 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="5cfb7-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="5cfb7-111">对于多计算机池，FQDN 必须是您选择代表此多计算机池的名称，并且由主机 A (和 AAAA 在 DNS 中定义（如果使用 IPv6) 记录）。</span><span class="sxs-lookup"><span data-stu-id="5cfb7-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5cfb7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cfb7-112">See also</span></span>

[<span data-ttu-id="5cfb7-113">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="5cfb7-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5cfb7-114">将持久聊天服务器添加到 Skype for Business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="5cfb7-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
