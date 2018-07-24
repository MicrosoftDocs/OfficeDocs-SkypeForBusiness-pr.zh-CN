---
title: 控制器 （规划工具）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: 控制器是运行 Business Server 通信软件可以进行身份验证的用户请求，但不承载任何用户帐户的 Skype 的服务器。
ms.openlocfilehash: e6210c6c4c6b4f92b99eb9287f82e6268db5df12
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21058270"
---
# <a name="director-planning-tool"></a><span data-ttu-id="6dba3-103">控制器 （规划工具）</span><span class="sxs-lookup"><span data-stu-id="6dba3-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="6dba3-104">控制器是运行 Business Server 通信软件可以进行身份验证的用户请求，但不承载任何用户帐户的 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="6dba3-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="6dba3-105">此角色是可选的您应当选择以下两种方案中部署控制器：</span><span class="sxs-lookup"><span data-stu-id="6dba3-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="6dba3-106">如果您启用通过部署边缘服务器的外部用户访问，您还应部署控制器。</span><span class="sxs-lookup"><span data-stu-id="6dba3-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="6dba3-107">在此方案中，控制器验证外部用户，然后将传递到内部服务器其通信。</span><span class="sxs-lookup"><span data-stu-id="6dba3-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="6dba3-108">当控制器用于验证外部用户时，它减少了对前端池服务器执行这些用户的身份验证的开销。</span><span class="sxs-lookup"><span data-stu-id="6dba3-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="6dba3-109">它还有助于阻止恶意流量，如拒绝服务攻击的内部前端池。</span><span class="sxs-lookup"><span data-stu-id="6dba3-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="6dba3-110">如果网络状态不淹没无效的外部流量，在此类攻击中，此通信结束控制器。</span><span class="sxs-lookup"><span data-stu-id="6dba3-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="6dba3-111">如果您部署在中央站点的多个前端池，通过将控制器添加到该网站可以简化身份验证请求和提高性能。</span><span class="sxs-lookup"><span data-stu-id="6dba3-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="6dba3-112">在此方案中，所有请求都都第一个到 Director，然后将其路由至正确的前端池。</span><span class="sxs-lookup"><span data-stu-id="6dba3-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

