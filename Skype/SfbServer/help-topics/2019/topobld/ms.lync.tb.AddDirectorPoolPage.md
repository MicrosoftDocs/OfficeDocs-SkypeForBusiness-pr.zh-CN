---
title: 添加控制器池
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 要“定义控制器池 FQDN”，请选择“多计算机池”（在负载平衡池中包含两个或更多控制器）或“单计算机池”。 还必须在 FQDN (键入将用于连接到控制器池) 或单个控制器的 FQDN 的完全限定域名。 对于控制器计算机池，该完全限定的域名可以是硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享 DNS 条目。
ms.openlocfilehash: a8fdb37fb5a64c9f228a941c36dda7a56c5013d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590336"
---
# <a name="add-director-pool"></a>添加控制器池
 
要“定义控制器池 FQDN”，请选择“多计算机池”（在负载平衡池中包含两个或更多控制器）或“单计算机池”。 还必须在 FQDN (键入将用于连接到控制器池) 或单个控制器的 FQDN 的完全限定域名。 对于控制器计算机池，该完全限定的域名可以是硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享 DNS 条目。
  
> [!TIP]
> 如果计划将来实施控制器池，请选择“多计算机池”。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 以后准备好向池中添加更多计算机时，必须再次运行拓扑生成器以定义新的池成员，发布新拓扑，然后通过 Skype for Business Server 部署向导设置新的控制器池成员。 还必须向该池的相应负载平衡器（域名系统 (DNS) 负载平衡或硬件负载平衡器）添加新的池成员。 多数情况下，会同时部署这两种负载平衡系统。 请确保向这两者均添加新的成员服务器。 
  

