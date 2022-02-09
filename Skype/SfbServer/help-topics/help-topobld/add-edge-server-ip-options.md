---
title: 添加边缘服务器 IP 选项
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
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 允许您为边缘服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此，请执行以下操作：
ms.openlocfilehash: b0a7483b7d9f8c19b045611ebcbc6c9b2d6e8237
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401246"
---
# <a name="add-edge-server-ip-options"></a>添加边缘服务器 IP 选项
 
Microsoft Lync Server 2013 允许您为边缘服务器和边缘池的每个接口配置 IPv4 和 IPv6 地址。 为此，请执行以下操作：
  
- 在内部接口上启用 **IPv4**：如果要将 IPv4 地址应用于边缘服务器或边缘池内部接口，请选中此复选框
    
- **在内部接口上启用 IPv6**：如果要将 IPv6 地址应用于边缘服务器或边缘池内部接口，请选中此复选框
    
- 在外部接口上启用 **IPv4**：如果要将 IPv4 地址应用于边缘服务器或边缘池外部接口，请选中此复选框
    
- **在外部接口上启用 IPv6**：如果要将 IPv6 地址应用于边缘服务器或边缘池外部接口，请选中此复选框
    
还可以将边缘服务器或边缘池配置为对外部 IP 地址使用网络地址转换地址。 通过选中“此边缘池的外部 IP 地址是由 NAT 转换的”复选框来执行该操作。
  
NAT 支持。使用硬件负载平衡时不支持网络地址转换 (NAT)，因此如果要部署具有硬件负载平衡的边缘服务器池，请不要选择 NAT 选项。
  

