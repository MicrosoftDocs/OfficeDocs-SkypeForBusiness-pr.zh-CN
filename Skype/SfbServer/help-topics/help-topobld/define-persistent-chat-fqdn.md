---
title: 定义持久聊天 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 使用 "定义新的持久聊天池" 向导创建新的持久聊天服务器或持久聊天服务器池。 选择“多计算机池”或“单计算机池”。 如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305868"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="f24d0-105">定义持久聊天 FQDN</span><span class="sxs-lookup"><span data-stu-id="f24d0-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="f24d0-106">使用 "**定义新的持久聊天池**" 向导创建新的持久聊天服务器或持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="f24d0-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="f24d0-107">选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="f24d0-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="f24d0-108">如果选择单计算机池，但后来需要多计算机池，则需要先删除单计算机池，然后再定义多计算机池。</span><span class="sxs-lookup"><span data-stu-id="f24d0-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="f24d0-109">你还必须为持久聊天服务器或持久聊天服务器池定义**池 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="f24d0-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="f24d0-110">单计算机池的池完全限定域名 (FQDN) 必须与组成单服务器池的计算机的 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="f24d0-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="f24d0-111">对于多计算机池，FQDN 必须为您选择表示此多计算机池的名称，并且在 DNS 中由主机 A（如果使用 IPv6，则为 AAAA）记录定义。</span><span class="sxs-lookup"><span data-stu-id="f24d0-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f24d0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f24d0-112">See also</span></span>

[<span data-ttu-id="f24d0-113">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="f24d0-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="f24d0-114">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="f24d0-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
