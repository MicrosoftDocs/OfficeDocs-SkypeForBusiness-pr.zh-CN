---
title: 添加边缘服务器 NAT IP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: 公共 IP 地址是由网络地址转换 (NAT) 的 IP 地址。 IP 地址必须公共可路由。 这是必需的因为您选择此边缘池转换 NAT 选项在此向导的选择功能页上的外部 IP 地址。
ms.openlocfilehash: ee4a2d12d44e17c3219395174451f00db7674e76
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059288"
---
# <a name="add-edge-server-nat-ip"></a>添加边缘服务器 NAT IP
 
公共 IP 地址是由网络地址转换 (NAT) 的 IP 地址。 IP 地址必须公共可路由。 这是必需的因为您选择**此边缘池的外部 IP 地址由 NAT 转换**此向导的**选择功能**页上的选项。
  
> [!NOTE]
> 网络地址转换 (NAT) 启用客户端或服务器上的专用网络 (如 192.168.0.0 范围) 通过公共 Internet 网络与远程网络上的系统进行通信。 NAT 工作方式是在外部接口上使用单个公用 IP 地址并将与一个公用 IP 地址的内部 IP 地址。 NAT 映射将内部地址映射到外部公共 IP 地址。 远程系统看到只有源的公共地址。 远程系统响应源，和 NAT 映射以确定哪些内部 IP 地址响应应返回到源引用。 
  
可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。 有关将边缘服务器添加到现有拓扑的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) 。
  

