---
title: 添加控制器池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: 若要定义控制器池 FQDN，请选择将由负载平衡的池中的两个或多个控制器（或单个计算机池）组成的多台计算机池。 还必须键入将用于连接到控制器池或单个控制器的 FQDN 的完全限定的域名（FQDN）。 对于 Director 计算机池，这将是用于硬件负载平衡器的虚拟 IP 或用于 DNS 负载平衡的共享 DNS 条目的域名系统（DNS）条目。
ms.openlocfilehash: 150975cedf09c19acac1afffab25f5becf053fe3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698557"
---
# <a name="add-director-pool"></a>添加控制器池
 
若要**定义控制器池 FQDN**，请选择将由负载平衡的池中的两个或多个控制器（或**单个计算机池**）组成的**多台计算机池**。 还必须键入将用于连接到控制器池或单个控制器的 FQDN 的完全限定的域名（FQDN）。 对于 Director 计算机池，这将是用于硬件负载平衡器的虚拟 IP 或用于 DNS 负载平衡的共享 DNS 条目的域名系统（DNS）条目。
  
> [!TIP]
> 如果你计划在将来实现控制器池，请选择 "**多台计算机池**"。 即使池被定义为两台或多台具有负载平衡的计算机，你也可以创建一个单独的计算机池并为该单台计算机创建一个池 FQDN。 准备好将更多计算机添加到池中后，必须再次运行拓扑生成器来定义新的池成员、发布新拓扑，然后通过 Skype for Business 服务器部署向导设置新的控制器池成员。 还必须将新的池成员添加到池的相应负载平衡器、域名系统（DNS）负载平衡或硬件负载平衡器。 在许多情况下，系统会同时使用负载平衡系统。 请确保将新的成员服务器添加到两者中。 
  

