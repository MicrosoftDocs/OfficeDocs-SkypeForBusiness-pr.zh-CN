---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 指定你要创建的前端池的完全限定的域名 (FQDN)。 发布包含前端池的拓扑后, 无法更改池的 FQDN。 如果需要重命名池, 必须删除该池, 然后使用新的 FQDN 添加新池。
ms.openlocfilehash: 00bc6276062412abe55a518a45941fa9c4fbaff8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297749"
---
# <a name="add-front-end-pool-fqdn"></a>添加前端池 FQDN
 
指定你要创建的前端池的完全限定的域名 (FQDN)。 发布包含前端池的拓扑后, 无法更改池的 FQDN。 如果需要重命名池, 必须删除该池, 然后使用新的 FQDN 添加新池。
  
> [!TIP]
> 如果你计划在将来实施前端池, 请选择 "**多台计算机池**"。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 准备好将更多计算机添加到池中后, 必须再次运行拓扑生成器来定义新的池成员、发布新拓扑, 然后通过 Skype for Business 服务器部署向导设置新的前端池成员。 还必须将新的池成员添加到池、域名系统 (DNS) 负载平衡或硬件负载平衡器的相应负载平衡器。 在许多情况下, 你可以同时使用两个负载平衡系统。 请确保将新的成员服务器添加到两者中。 
  

