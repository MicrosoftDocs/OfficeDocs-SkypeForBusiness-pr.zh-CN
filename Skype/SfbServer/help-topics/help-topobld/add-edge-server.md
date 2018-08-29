---
title: 添加边缘服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 发布拓扑，其中包括边缘服务器或边缘服务器池和安装 Business Server Skype 之前, 您应已完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的外围网络中安装的服务器的准备。
ms.openlocfilehash: b39161e64d4679e20c0c960811da1eb7ed705643
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244214"
---
# <a name="add-edge-server"></a>添加边缘服务器

要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 发布拓扑，其中包括边缘服务器或边缘服务器池和安装 Business Server Skype 之前, 您应已完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的[Preparing for Installation of Servers 外围网络中](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)。

> [!IMPORTANT]
> 指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。拓扑生成器使用 FQDN，而不是短名称。必须在要部署为未加入域的边缘服务器或边缘服务器池的计算机名称上配置域名系统 (DNS) 后缀。

> [!TIP]
> 如果计划将来实施边缘服务器池，请选择“**多计算机池**”。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单计算机的池并为该单计算机创建池 FQDN。 当您准备好以后向池中添加更多计算机时，您必须拓扑生成器再次以定义新的池成员和发布新拓扑，然后设置 Skype 通过新的边缘服务器池成员的业务 Server 部署向导。 还必须向该池的相应负载平衡器（DNS 负载平衡或硬件负载平衡器）添加新的池成员。 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。 请确保将新成员服务器添加到相应的负载平衡器。

可以在部署初始拓扑时或在部署初始拓扑后添加对外部用户访问的支持。 有关添加边缘服务器或边缘服务器池的现有拓扑的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) 。


