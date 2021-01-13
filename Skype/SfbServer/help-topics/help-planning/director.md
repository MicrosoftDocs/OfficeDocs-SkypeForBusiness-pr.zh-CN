---
title: '控制器 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 控制器是运行 Skype for Business Server 2015 通信软件的服务器，可以对用户请求进行身份验证，但不提供任何用户帐户。
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810542"
---
# <a name="director-planning-tool"></a><span data-ttu-id="aff19-103">控制器 (规划工具) </span><span class="sxs-lookup"><span data-stu-id="aff19-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="aff19-104">控制器是运行 Skype for Business Server 2015 通信软件的服务器，可以对用户请求进行身份验证，但不提供任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aff19-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="aff19-105">此角色是可选的，您可以选择在下列两种方案中部署控制器：</span><span class="sxs-lookup"><span data-stu-id="aff19-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="aff19-106">如果通过部署边缘服务器启用外部用户访问，则还应部署控制器。</span><span class="sxs-lookup"><span data-stu-id="aff19-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="aff19-107">在此方案中，控制器对外部用户进行身份验证，然后将他们的流量传递给内部服务器。</span><span class="sxs-lookup"><span data-stu-id="aff19-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="aff19-108">当控制器用于对外部用户进行身份验证时，它可减轻前端池服务器执行这些用户的身份验证的开销。</span><span class="sxs-lookup"><span data-stu-id="aff19-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="aff19-109">它还有助于使内部前端池免受恶意流量（如拒绝服务攻击）的攻击。</span><span class="sxs-lookup"><span data-stu-id="aff19-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="aff19-110">如果网络受到此类攻击中无效外部流量的攻击，则这些流量将终止于控制器。</span><span class="sxs-lookup"><span data-stu-id="aff19-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="aff19-111">如果在中央站点部署多个前端池，则通过向该站点添加控制器，可以简化身份验证请求并提高性能。</span><span class="sxs-lookup"><span data-stu-id="aff19-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="aff19-112">在此方案中，所有请求首先转到控制器，然后控制器将其路由到正确的前端池。</span><span class="sxs-lookup"><span data-stu-id="aff19-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

