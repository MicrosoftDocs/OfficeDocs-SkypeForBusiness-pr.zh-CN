---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定要创建的前端池的完全限定的域名 (FQDN)。 发布包含前端池的拓扑之后，无法更改池的 FQDN。 如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 与新池。
ms.openlocfilehash: 4d09e70e6c75c2e1013b0a801d343865c9d112eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877152"
---
# <a name="add-front-end-pool-fqdn"></a>添加前端池 FQDN
 
指定要创建的前端池的完全限定的域名 (FQDN)。 发布包含前端池的拓扑之后，无法更改池的 FQDN。 如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 与新池。
  
> [!TIP]
> 如果您计划将来实现前端池，选择**多计算机池**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当您准备好以后向池中添加更多计算机时，您必须运行拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置 Skype 通过新的前端池成员的业务 Server 部署向导。 您还必须将新池成员添加到适当的负载平衡器的池、 域名系统 (DNS) 负载平衡或硬件负载平衡器。 在许多情况下，您必须同时负载平衡就地系统。 确保到这两个中添加新的成员服务器。 
  

