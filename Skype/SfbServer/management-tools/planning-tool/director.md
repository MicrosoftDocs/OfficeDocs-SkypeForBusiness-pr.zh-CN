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
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Director 是运行 Skype for Business Server 2015 通信软件的服务器，可对用户请求进行身份验证，但不会在家任何用户帐户。
ms.openlocfilehash: 48b691262dc638faf6f0aa9910a5adac3c1f0e46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684245"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Director 是运行 Skype for Business Server 2015 通信软件的服务器，可对用户请求进行身份验证，但不会在家任何用户帐户。 
  
此角色是可选的，你可以选择在以下两种方案中部署控制器：
  
- 如果通过部署边缘服务器启用外部用户访问，则还应部署 Director。 在此方案中，控制器对外部用户进行身份验证，然后将其流量传递到内部服务器。 当使用 Director 对外部用户进行身份验证时，它将从执行这些用户的身份验证的开销中免除前端池服务器。 它还有助于将内部前端池与恶意流量（如拒绝服务攻击）隔离。 如果网络被此类攻击中的无效外部通信所淹没，则该流量将在 Director 处结束。
    
- 如果在中心网站上部署多个前端池，则通过向该网站添加 Director，可以简化身份验证请求并提高性能。 在此方案中，所有请求首先转到 Director，然后将其路由到正确的前端池。
    

