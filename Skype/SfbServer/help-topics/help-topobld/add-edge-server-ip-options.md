---
title: 添加 Edge Server IP 选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 允许你为 Edge 服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此, 请执行以下操作:'
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293971"
---
# <a name="add-edge-server-ip-options"></a>添加 Edge Server IP 选项
 
Microsoft Lync Server 2013 允许你为 Edge 服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此, 请执行以下操作:
  
- **在内部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框
    
- **在内部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框
    
- **在外部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框
    
- **在外部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框
    
你还可以将 Edge 服务器或边缘池配置为使用外部 IP 地址的网络地址转换地址。 要执行此操作, 请选中该复选框**此边缘池的外部 IP 地址由 NAT 转换**。
  
NAT 支持。 使用硬件负载平衡时, 不支持网络地址转换 (NAT), 因此, 如果你要部署具有硬件负载平衡的 Edge 服务器池, 请不要选择 NAT 选项。
  

