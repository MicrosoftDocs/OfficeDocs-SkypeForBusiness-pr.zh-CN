---
title: 添加边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 在发布包含边缘服务器或边缘服务器池并安装 Skype for Business Server 的拓扑之前，应完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的Preparing for Installation of Servers in the Perimeter Network。
ms.openlocfilehash: 379c181336ecc855feb1344e3328a8ffcd38f447
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216743"
---
# <a name="add-edge-server"></a>添加边缘服务器

要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 在发布包含边缘服务器或边缘服务器池并安装 Skype for Business Server 的拓扑之前，应完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的[Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)。

> [!IMPORTANT]
> 指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。拓扑生成器使用 FQDN，而不是短名称。必须在要部署为未加入域的边缘服务器或边缘服务器池的计算机名称上配置域名系统 (DNS) 后缀。

> [!TIP]
> 如果计划将来实施边缘服务器池，请选择“多个计算机池”****。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单个计算机的池并为该单个计算机创建池 FQDN。 当您准备好将更多计算机添加到池时，您必须再次使用拓扑生成器来定义新的池成员，发布新的拓扑，然后通过 Skype for Business Server 部署向导设置新的边缘服务器池成员。 还必须向该池的相应负载平衡器（DNS 负载平衡或硬件负载平衡器）添加新的池成员。 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。 请确保将新成员服务器添加到相应的负载平衡器。

可以在部署初始拓扑时或在部署初始拓扑后添加对外部用户访问的支持。 有关向现有拓扑中添加边缘服务器或边缘服务器池的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。


