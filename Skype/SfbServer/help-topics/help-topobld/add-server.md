---
title: 添加服务器
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
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 向现有服务器池添加新的服务器，其中池为以下几项之一：
ms.openlocfilehash: c439f97da983451943692de59031a4fe98bd3e85
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384590"
---
# <a name="add-server"></a>添加服务器
 
向现有服务器池添加新的服务器，其中池为以下几项之一：
  
- Enterprise Edition 前端服务器
    
- 控制器服务器
    
- 中介服务器
    
- 音频/视频会议服务器
    
- 受信任应用程序服务器
    
每个新池服务器都有不同的要求。在以下各节中，查找要添加到现有池的服务器类型，并根据为每种服务器类型定义的要求提供所请求的信息。提供请求的信息以定义新的池服务器。
  
 **Enterprise Edition 前端服务器**
  
- 域名系统 (DNS) 中定义的新服务器的完全限定域名 (FQDN)。
    
- 选择 **“使用所有配置 IP 地址”**，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择 **“服务仅供选定 IP 地址使用”**，然后在新服务器上输入特定的地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。
    
- 如果在前端服务器上并置中介服务器，则定义“PSTN IP 地址”。
    
- 选择“启用 IPv6”为此服务器启用 IPv6。
    
  **控制器服务器**
  
- DNS 中定义的新服务器的 FQDN。
    
- 选择“使用所有已配置的 IP 地址”，这意味着将使用计算机上定义的任何 IP 地址。此外，还可以选择“将服务用途限制为所选 IP 地址”，然后在新服务器上输入特定的 IP 地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。
    
  **中介服务器**
  
- DNS 中定义的新服务器的 FQDN。
    
- 选择 **“使用所有配置 IP 地址”**，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择 **“服务仅供选定 IP 地址使用”**，然后在新服务器上输入特定的 IP 地址作为主 IP 地址，并输入公用电话交换网 (PSTN) IP 地址的 IP 地址。输入的 IP 地址是唯一响应指定服务的 IP 地址。
    
    > [!NOTE]
    > 对于中介服务器，默认情况下，为主 IP 地址和 PSTN IP 地址输入的 IP 地址是相同的。如果使用专用的网络接口或同一网络接口上单独的 IP 地址，则可以单独定义这些 IP 地址。如果具有两个网络接口，其中一个用于本地网络连接，另一个用于 PSTN 连接，则必须分配不同的 IP 地址。 
  
  **音频/视频会议服务器**
  
- DNS 中定义的新服务器的 FQDN。
    
- 选择“使用所有已配置的 IP 地址”，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择“将服务用途限制为所选 IP 地址”，然后在新服务器上输入特定的地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。
    
  **受信任应用程序服务器**
  
- DNS 中定义的新服务器的 FQDN。
    

