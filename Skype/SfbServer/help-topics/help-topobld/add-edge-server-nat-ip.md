---
title: 添加 Edge Server NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公共 IP 地址是网络地址转换（NAT）使用的 IP 地址。 IP 地址必须是公共可路由的。 这是必需的，因为你选择了此向导的 "选择功能" 页面上的 NAT "通过 NAT 转换此边缘池的外部 IP 地址" 选项。
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698397"
---
# <a name="add-edge-server-nat-ip"></a>添加 Edge Server NAT IP

公共 IP 地址是网络地址转换（NAT）使用的 IP 地址。 IP 地址必须是公共可路由的。 这是必需的，因为你选择了此向导的 "**选择功能**" 页面上的**NAT "通过 NAT 转换此边缘池的外部 IP 地址"** 选项。

> [!NOTE]
> 网络地址转换（NAT）允许专用网络上的客户端或服务器（如192.168.0.0 范围）通过公共 Internet 网络与远程网络上的系统通信。 NAT 的工作原理是使用外部接口上的单个公共 IP 地址，并将内部 IP 地址与一个公共 IP 地址相关联。 NAT 映射将内部地址映射到外部公共 IP 地址。 远程系统仅看到源的公共地址。 远程系统响应源，源指向 NAT 映射以确定应返回响应的内部 IP 地址。

可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。


