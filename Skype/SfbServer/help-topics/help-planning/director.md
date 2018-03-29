---
title: 主任 （规划工具）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 导演是业务服务器 2015年通信软件，可以进行身份验证的用户请求，但不承载任何用户帐户运行 Skype 的服务器。
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a><span data-ttu-id="ea877-103">主任 （规划工具）</span><span class="sxs-lookup"><span data-stu-id="ea877-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="ea877-104">导演是业务服务器 2015年通信软件，可以进行身份验证的用户请求，但不承载任何用户帐户运行 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="ea877-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="ea877-105">此角色是可选的可以选择要部署在下列两个方案主管：</span><span class="sxs-lookup"><span data-stu-id="ea877-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="ea877-106">如果通过部署边缘服务器启用的外部用户访问，您还应该部署导演。</span><span class="sxs-lookup"><span data-stu-id="ea877-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="ea877-107">在此方案中，控制器对外部用户进行身份验证，然后将传递到内部服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="ea877-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="ea877-108">当导演使用外部用户进行身份验证时，它还前端池中服务器执行身份验证这些用户的开销。</span><span class="sxs-lookup"><span data-stu-id="ea877-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="ea877-109">它还有助于隔离从例如拒绝服务攻击的恶意通信量的内部前端池。</span><span class="sxs-lookup"><span data-stu-id="ea877-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="ea877-110">如果网络被淹没在此类攻击中无效的外部通信，此通信结束处主任。</span><span class="sxs-lookup"><span data-stu-id="ea877-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="ea877-111">如果您部署多个前端池在中心站点，通过向该站点添加导演您可以优化身份验证请求并提高性能。</span><span class="sxs-lookup"><span data-stu-id="ea877-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="ea877-112">在此方案中，所有请求都都第一个到的控制器，然后将它们路由到正确的前端池。</span><span class="sxs-lookup"><span data-stu-id="ea877-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

