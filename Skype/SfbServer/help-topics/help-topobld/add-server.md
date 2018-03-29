---
title: 添加服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 将新服务器添加到现有池中的服务器，其中池是下列情况之一：
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a>添加服务器
 
将新服务器添加到现有池中的服务器，其中池是下列情况之一：
  
- 企业版前端服务器
    
- Director 服务器
    
- 中介服务器
    
- 音频/视频会议服务器
    
- 受信任的应用程序服务器
    
每个新的库服务器有不同的要求。 在以下部分中，找到要添加到的现有池的服务器的类型和要求规定为每个服务器类型提供相关信息。 提供请求的信息，以定义新的库服务器。
  
 **企业版前端服务器**
  
- 完全限定的新服务器的域名称 (FQDN)，按其定义在域名系统 (DNS)。
    
- 选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。 或者，您可以选择**限制到选定的 IP 地址的服务使用情况**并输入新的服务器上的特定地址。 输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。
    
- 中介服务器在前端服务器上搭配时，请定义**PSTN IP 地址**。
    
- 选择要为此服务器启用 IPv6**启用 IPv6** 。
    
 **Director 服务器**
  
- 它与新服务器的 FQDN，则在 DNS 中定义。
    
- 选择**使用已配置的所有 IP 地址**，这意味着将使用在计算机上定义的任何 IP 地址。 或者，选择**限制服务使用所选的 IP 地址**，并输入新的服务器上的特定的 IP 地址。 输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。
    
 **中介服务器**
  
- 它与新服务器的 FQDN，则在 DNS 中定义。
    
- 选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。 或者，您可以选择**限制到选定的 IP 地址的服务使用情况**和新的主 IP 地址，服务器上特定的 IP 地址输入和输入公用交换的电话网络 (PSTN) IP 地址的 IP 地址。 输入的 IP 地址是唯一的 IP 地址，这将指定服务的响应。
    
    > [!NOTE]
    > 中介服务器中，输入主 IP 地址和 PSTN IP 地址的 IP 地址是相同的默认情况。 如果在同一个网络接口上使用的专用的网络接口或单独的 IP 地址，可以单独定义的 IP 地址。 如果您有两个网络接口，另一个用于本地网络连接的 PSTN 连接，您必须分配不同的 IP 地址。 
  
 **音频/视频会议服务器**
  
- 它与新服务器的 FQDN，则在 DNS 中定义。
    
- 选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。 或者，您可以选择**限制到选定的 IP 地址的服务使用情况**并输入新的服务器上的特定地址。 输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。
    
 **受信任的应用程序服务器**
  
- 它与新服务器的 FQDN，则在 DNS 中定义。
    

