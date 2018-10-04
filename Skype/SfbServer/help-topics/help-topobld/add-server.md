---
title: 添加服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 若要将新服务器添加到现有池的服务器，其中池是以下项之一：
ms.openlocfilehash: 6e45048eba1758f6944ea822113622c03703d315
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372963"
---
# <a name="add-server"></a>添加服务器
 
若要将新服务器添加到现有池的服务器，其中池是以下项之一：
  
- Enterprise Edition 前端服务器
    
- 控制器服务器
    
- 中介服务器
    
- 音频/视频会议服务器
    
- 受信任应用程序服务器
    
每个新池服务器具有不同的要求。 以下各节，查找要添加到的现有池的服务器的类型和要求，它定义每种服务器类型提供相关信息。 提供定义的新池服务器请求的信息。
  
 **Enterprise Edition 前端服务器**
  
- 定义在域名系统 (DNS) 的完全限定域名 (FQDN) 的新服务器。
    
- 选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。 此外，您可以选择**将服务使用率限制为所选的 IP 地址**，并输入新的服务器上的特定地址。 输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。
    
- 前端服务器上并置中介服务器，请定义**PSTN IP 地址**。
    
- 选择**启用 IPv6**为此服务器启用 IPv6。
    
  **控制器服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择**使用所有已配置的 IP 地址**，这意味着将使用的计算机上定义任意 IP 地址。 此外，您选择**将服务使用率限制为所选的 IP 地址**，并输入新服务器上的特定的 IP 地址。 输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。
    
  **中介服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。 或者，您选择**服务使用率限制为所选的 IP 地址**和主 IP 地址，在新服务器上输入特定的 IP 地址和 enter 公用电话交换网 (pstn) 的 IP 地址的 IP 地址。 输入的 IP 地址是唯一的 IP 地址，这将指定服务的响应。
    
    > [!NOTE]
    > 为中介服务器中，输入的主要 IP 地址和 PSTN IP 地址的 IP 地址是默认情况下相同。 如果您使用专用的网络接口或单独的 IP 地址相同的网络接口上，可以单独定义的 IP 地址。 如果您有两个网络接口，一个用于本地网络连接，一个用于 PSTN 连接，则必须分配不同的 IP 地址。 
  
  **音频/视频会议服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    
- 选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。 此外，您可以选择**将服务使用率限制为所选的 IP 地址**，并输入新的服务器上的特定地址。 输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。
    
  **受信任应用程序服务器**
  
- 在 DNS 中定义的新服务器的 FQDN。
    

