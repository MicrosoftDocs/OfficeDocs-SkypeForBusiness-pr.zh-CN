---
title: 添加前端池的 FQDN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定要创建的前端池完全限定的域名 (FQDN)。 发布包含前端池拓扑结构之后，您无法更改池的 FQDN。 如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 的新池。
ms.openlocfilehash: 73fce35786cdce2a39ebf2981b59a500991112f0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-pool-fqdn"></a>添加前端池的 FQDN
 
指定要创建的前端池完全限定的域名 (FQDN)。 发布包含前端池拓扑结构之后，您无法更改池的 FQDN。 如果您需要重命名一个池，您必须删除池，然后添加新的 FQDN 的新池。
  
> [!TIP]
> 如果打算在将来实现前端池，可选择**多个计算机池**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当准备好以后向池中添加更多的计算机时，您必须运行拓扑生成器再次以定义新的池成员，发布新的拓扑，然后设置新的前端池成员通过 Skype 业务服务器部署向导。 您还必须将新池成员添加到池、 域名系统 (DNS) 负载平衡，或硬件负载平衡器的适当的负载平衡器。 在许多情况下，会有两种负载平衡系统中的位置。 请确保同时添加新的成员服务器。 
  

