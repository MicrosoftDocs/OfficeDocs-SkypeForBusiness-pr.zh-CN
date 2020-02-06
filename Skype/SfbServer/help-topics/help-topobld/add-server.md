---
title: 添加服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 若要将新服务器添加到现有服务器池，其中池是以下项之一：
ms.openlocfilehash: d4f4afc0d4a7cb6fafe47de95c648aa1769027e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820644"
---
# <a name="add-server"></a>添加服务器
 
若要将新服务器添加到现有服务器池，其中池是以下项之一：
  
- 企业版前端服务器
    
- 控制器服务器
    
- 中介服务器
    
- 音频/视频会议服务器
    
- 受信任的应用程序服务器
    
每个新的池服务器都有不同的要求。 在以下部分中，找到要添加到现有池中的服务器的类型，并提供所需的信息，这些信息是为每个服务器类型定义的。 你提供所需的信息来定义新的池服务器。
  
 **企业版前端服务器**
  
- 新服务器的完全限定的域名（FQDN），该域名在域名系统（DNS）中定义。
    
- 选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。 或者，你可以选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定地址。 输入的 IP 地址是唯一将响应托管服务的 IP 地址。
    
- 当中介服务器在前端服务器上 collocated 时，请定义**PSTN IP 地址**。
    
- 选择 "**启用 ipv6** " 以为此服务器启用 ipv6。
    
  **控制器服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择 "**使用所有配置的 IP 地址**"，这意味着将使用计算机上定义的任何 ip 地址。 或者，选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定的 ip 地址。 输入的 IP 地址是唯一将响应托管服务的 IP 地址。
    
  **中介服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。 或者，选择 "**将服务使用限制为选定的 IP 地址**"，然后在新服务器上输入特定的 ip 地址作为主 IP 地址，并输入公共交换电话网络（PSTN） ip 地址的 ip 地址。 输入的 IP 地址是唯一将响应指定服务的 IP 地址。
    
    > [!NOTE]
    > 对于中介服务器，默认情况下，为主 IP 地址和 PSTN IP 地址输入的 IP 地址是相同的。 如果在同一网络接口上使用专用网络接口或单独的 IP 地址，则可以单独定义 IP 地址。 如果你有两个网络接口，一个用于本地网络连接，另一个用于 PSTN 连接，则必须分配不同的 IP 地址。 
  
  **音频/视频会议服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。 或者，你可以选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定地址。 输入的 IP 地址是唯一将响应托管服务的 IP 地址。
    
  **受信任的应用程序服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    

