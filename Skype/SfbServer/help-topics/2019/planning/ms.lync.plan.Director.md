---
title: '控制器 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ROBOTS: NOINDEX, NOFOLLOW
description: 控制器是运行 Skype for Business Server 通信软件的服务器，可以对用户请求进行身份验证，但不管理任何用户帐户。
ms.openlocfilehash: 0c76fb5290715bb394b4c84ffadad3a2e9dd74db
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801092"
---
# <a name="director-planning-tool"></a>控制器 (规划工具) 
 
控制器是运行 Skype for Business Server 通信软件的服务器，可以对用户请求进行身份验证，但不管理任何用户帐户。 
  
此角色是可选的，您可以选择在下列两种方案中部署控制器：
  
- 如果通过部署边缘服务器启用外部用户访问，则还应部署控制器。 在此方案中，控制器对外部用户进行身份验证，然后将他们的流量传递给内部服务器。 当控制器用于对外部用户进行身份验证时，它可减轻前端池服务器执行这些用户的身份验证的开销。 它还有助于使内部前端池免受恶意流量（如拒绝服务攻击）的攻击。 如果网络受到此类攻击中无效外部流量的攻击，则这些流量将终止于控制器。
    
- 如果在中央站点部署多个前端池，则通过向该站点添加控制器，可以简化身份验证请求并提高性能。 在此方案中，所有请求首先转到控制器，然后控制器将其路由到正确的前端池。
    

