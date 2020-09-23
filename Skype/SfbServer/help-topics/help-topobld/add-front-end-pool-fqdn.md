---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218853"
---
# <a name="add-front-end-pool-fqdn"></a>添加前端池 FQDN
 
指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。
  
> [!TIP]
> 如果计划将来实施前端池，请选择 **“多个计算机池”**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单个计算机的池并为该单个计算机创建池 FQDN。 当您准备好将更多计算机添加到池时，您必须再次运行拓扑生成器以定义新的池成员、发布新的拓扑，然后通过 Skype for Business Server 部署向导设置新的前端池成员。 还必须向该池的相应负载平衡器（域名系统 (DNS) 负载平衡或硬件负载平衡器）添加新的池成员。 多数情况下，会同时部署这两种负载平衡系统。 请确保向这两者均添加新的成员服务器。 
  

