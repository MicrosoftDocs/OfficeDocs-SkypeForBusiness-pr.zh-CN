---
title: 添加前端池 FQDN
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。
ms.openlocfilehash: d77eb93c9fd8c7694b4f044bd879e9a6aed1c223
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396634"
---
# <a name="add-front-end-pool-fqdn"></a>添加前端池 FQDN
 
指定要创建的前端池的完全限定域名 (FQDN)。发布包含前端池的拓扑后，就无法更改该池的 FQDN。如果需要重命名池，必须先删除该池，然后添加具有新 FQDN 的新池。
  
> [!TIP]
> 如果计划将来实施前端池，请选择 **“多个计算机池”**。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单个计算机的池并为该单个计算机创建池 FQDN。 以后准备好向池中添加更多计算机时，必须再次运行拓扑生成器以定义新的池成员，发布新拓扑，然后通过 Skype for Business Server 部署向导设置新的前端池成员。 还必须向该池的相应负载平衡器（域名系统 (DNS) 负载平衡或硬件负载平衡器）添加新的池成员。 多数情况下，会同时部署这两种负载平衡系统。 请确保向这两者均添加新的成员服务器。 
  

