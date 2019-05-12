---
title: 添加控制器池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义控制器池 FQDN，选择将包含两个或多个控制器负载平衡池中的多个计算机池或单计算机池。 您还必须键入的完全限定的域名 (FQDN) 将用于连接到控制器池或单个控制器的 FQDN。 对于控制器计算机的池，这将为硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。
ms.openlocfilehash: e3c99df44d1d95c3d7a448cd03715572218d4b92
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889141"
---
# <a name="add-director-pool"></a>添加控制器池
 
要在**定义控制器池 FQDN**中，选择是将包含两个或多个控制器负载平衡池中的**多个计算机池**或**单计算机池**。 您还必须键入的完全限定的域名 (FQDN) 将用于连接到控制器池或单个控制器的 FQDN。 对于控制器计算机的池，这将为硬件负载平衡器的虚拟 IP 的域名系统 (DNS) 条目或 DNS 负载平衡的共享的 DNS 条目。
  
> [!TIP]
> 如果您计划将来实现控制器池，选择**多计算机池**。 即使池中定义为两个或多台计算机的负载平衡，您可以创建单计算机池，并创建单个计算机池的 FQDN。 当您准备好以后向池中添加更多计算机时，您必须运行拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置业务 Server 部署向导 Skype 通过新的控制器池成员。 您还必须将新的池成员添加到适当的负载平衡器的池的域名系统 (DNS) 负载平衡，或硬件负载平衡器。 在许多情况下，您将具有两个负载平衡就地系统。 确保到这两个中添加新的成员服务器。 
  

