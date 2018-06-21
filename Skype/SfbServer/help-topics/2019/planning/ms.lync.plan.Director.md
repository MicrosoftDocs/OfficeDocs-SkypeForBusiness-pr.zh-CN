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
description: 控制器是运行 Business Server 通信软件可以进行身份验证的用户请求，但不承载任何用户帐户的 Skype 的服务器。
ms.openlocfilehash: a1920d11ed354cab3409a9f2a1fd39280ce2d29d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975986"
---
# <a name="director-planning-tool"></a>控制器 （规划工具）
 
控制器是运行 Business Server 通信软件可以进行身份验证的用户请求，但不承载任何用户帐户的 Skype 的服务器。 
  
此角色是可选的您应当选择以下两种方案中部署控制器：
  
- 如果您启用通过部署边缘服务器的外部用户访问，您还应部署控制器。 在此方案中，控制器验证外部用户，然后将传递到内部服务器其通信。 当控制器用于验证外部用户时，它减少了对前端池服务器执行这些用户的身份验证的开销。 它还有助于阻止恶意流量，如拒绝服务攻击的内部前端池。 如果网络状态不淹没无效的外部流量，在此类攻击中，此通信结束控制器。
    
- 如果您部署在中央站点的多个前端池，通过将控制器添加到该网站可以简化身份验证请求和提高性能。 在此方案中，所有请求都都第一个到 Director，然后将其路由至正确的前端池。
    

