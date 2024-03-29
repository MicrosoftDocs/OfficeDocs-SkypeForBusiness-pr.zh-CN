---
title: Skype for Business Server控制器规划工具
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: 控制器是运行 Skype for Business Server 2015 通信软件的服务器，它可以对用户请求进行身份验证，但不提供任何用户帐户。
---

# <a name="skype-for-business-server-director-planning-tool"></a>Skype for Business Server控制器规划工具
 
控制器是运行 Skype for Business Server 2015 通信软件的服务器，它可以对用户请求进行身份验证，但不提供任何用户帐户。 
  
此角色是可选的，您可以选择在下列两种方案中部署控制器：
  
- 如果通过部署边缘服务器启用来宾用户访问，则还应部署控制器。 在此方案中，控制器对来宾进行身份验证，然后将其流量传递给内部服务器。 当控制器用于对来宾进行身份验证时，将减少前端池服务器对这些用户进行身份验证的开销。 它还有助于使内部前端池免受恶意流量（如拒绝服务攻击）的感染。 如果网络受到此类攻击中无效外部流量的攻击，则这些流量将终止于控制器。
    
- 如果在中央站点部署多个前端池，则通过将控制器添加到该站点，可以简化身份验证请求并提高性能。 在此方案中，所有请求首先转到控制器，控制器随后将它们路由到正确的前端池。
    

