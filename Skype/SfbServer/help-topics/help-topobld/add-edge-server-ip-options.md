---
title: 添加边缘服务器 IP 选项
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 可以使用 Microsoft Lync Server 2013 边缘服务器和边缘池配置每个接口的 IPv4 和 IPv6 地址。 来做到这一点，请执行以下操作：
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a>添加边缘服务器 IP 选项
 
可以使用 Microsoft Lync Server 2013 边缘服务器和边缘池配置每个接口的 IPv4 和 IPv6 地址。 来做到这一点，请执行以下操作：
  
- **在内部接口上启用 IPv4**： 如果您想要应用于边缘服务器或边缘池内部接口的 IPv4 地址，请选择复选框
    
- **在内部接口上启用 IPv6**： 如果您想要应用于边缘服务器或边缘池内部接口的 IPv6 地址，请选择复选框
    
- **在外部接口上启用 IPv4**： 如果您想要应用于边缘服务器或边缘池外部接口的 IPv4 地址，请选择复选框
    
- **在外部接口上启用 IPv6**： 如果您想要应用于边缘服务器或边缘池外部接口的 IPv6 地址，请选择复选框
    
您还可以配置要用于外部 IP 地址的网络地址翻译地址的边缘服务器或边缘池。 通过选择**通过 NAT 转换此边缘池的外部 IP 地址**复选框执行此操作。
  
NAT 的支持。 网络地址转换 (NAT) 不支持使用硬件负载平衡，因此不选择 NAT 选项，如果您正在部署边缘服务器池使用硬件负载平衡时。
  

