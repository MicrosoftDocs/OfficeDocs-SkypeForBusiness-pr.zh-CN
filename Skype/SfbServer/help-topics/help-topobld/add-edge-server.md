---
title: 添加边缘服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 在发布包含边缘服务器或边缘服务器池的拓扑并安装Skype for Business Server之前，您应已完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的Preparing for Installation of Servers in the Perimeter Network。
ms.openlocfilehash: 6f905b24a0ca0da499cf94acda57404fabe289bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592657"
---
# <a name="add-edge-server"></a>添加边缘服务器

要在拓扑设计中引入边缘服务器或边缘服务器池，需指定要在其上部署边缘服务器或边缘服务器池的服务器的完全限定的域名 (FQDN)。 在发布包含边缘服务器或边缘服务器池的拓扑并安装Skype for Business Server之前，您应已完成部署外部用户访问的所有先决条件。 有关这些先决条件的详细信息，请参阅部署文档中的[Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network)。

> [!IMPORTANT]
> 指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。拓扑生成器使用 FQDN，而不是短名称。必须在要部署为未加入域的边缘服务器或边缘服务器池的计算机名称上配置域名系统 (DNS) 后缀。

> [!TIP]
> 如果计划将来实施边缘服务器池，请选择“多个计算机池”。 即使将池定义为具有两个或更多负载平衡的计算机，仍然可以创建单个计算机的池并为该单个计算机创建池 FQDN。 以后准备好向池中添加更多计算机时，必须再次使用拓扑生成器定义新的池成员，发布新拓扑，然后通过 Skype for Business Server 部署向导设置新的边缘服务器池成员。 还必须向该池的相应负载平衡器（DNS 负载平衡或硬件负载平衡器）添加新的池成员。 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。 请确保将新成员服务器添加到相应的负载平衡器。

可以在部署初始拓扑时或在部署初始拓扑后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器或边缘服务器池的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。