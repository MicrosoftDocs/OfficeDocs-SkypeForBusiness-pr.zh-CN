---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Director 是运行 Skype for Business Server 2015 通信软件的服务器，可对用户请求进行身份验证，但不会在家任何用户帐户。
ms.openlocfilehash: 2abb3cac867771ecd46c233be5864779512d39da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821514"
---
# <a name="director-planning-tool"></a><span data-ttu-id="251ff-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="251ff-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="251ff-104">Director 是运行 Skype for Business Server 2015 通信软件的服务器，可对用户请求进行身份验证，但不会在家任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="251ff-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="251ff-105">此角色是可选的，你可以选择在以下两种方案中部署控制器：</span><span class="sxs-lookup"><span data-stu-id="251ff-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="251ff-106">如果通过部署边缘服务器启用外部用户访问，则还应部署 Director。</span><span class="sxs-lookup"><span data-stu-id="251ff-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="251ff-107">在此方案中，控制器对外部用户进行身份验证，然后将其流量传递到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="251ff-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="251ff-108">当使用 Director 对外部用户进行身份验证时，它将从执行这些用户的身份验证的开销中免除前端池服务器。</span><span class="sxs-lookup"><span data-stu-id="251ff-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="251ff-109">它还有助于将内部前端池与恶意流量（如拒绝服务攻击）隔离。</span><span class="sxs-lookup"><span data-stu-id="251ff-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="251ff-110">如果网络被此类攻击中的无效外部通信所淹没，则该流量将在 Director 处结束。</span><span class="sxs-lookup"><span data-stu-id="251ff-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="251ff-111">如果在中心网站上部署多个前端池，则通过向该网站添加 Director，可以简化身份验证请求并提高性能。</span><span class="sxs-lookup"><span data-stu-id="251ff-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="251ff-112">在此方案中，所有请求首先转到 Director，然后将其路由到正确的前端池。</span><span class="sxs-lookup"><span data-stu-id="251ff-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

