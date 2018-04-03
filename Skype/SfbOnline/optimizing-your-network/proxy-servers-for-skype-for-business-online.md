---
title: Skype for Business Online 的代理服务器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。
ms.openlocfilehash: 0f4d0b82eeaedd4b81ea84a8d8d3a67993d7be96
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online 的代理服务器

本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。代理并不会使 Skype for Business 更加安全，因为 Skype for Business 的流量已经过加密。
  
另外，使用代理会产生问题。环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。此类问题会对音频和视频等 Skype for Business 场景中的体验带来负面影响，因为在这些场景中，实时流至关重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 请遵循我们的网络指南中提供的其他建议：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>具有内置 Skype for Business 支持或配置选项的代理供应商

本部分包含提供的产品或服务已证明可以成功用于 Skype for Business 流量的代理供应商的信息。
  
对于使用 **Bluecoat 代理解决方案** 的组织，新固件已发布，可以解决关于以下方面的若干个问题：
    
  - SSL 拦截
    
  - OCSP/SRL 检查
    
  - 基于 TLS 的 SIP
    
  - 对 TURN 的支持
    
Bluecoat 对 Skype for Business 的本地支持很容易启用，以便识别相关流量并相应地加以管理。这样可确保实现最佳的身份验证、信号传输和媒体流量流，以提供非凡的用户体验，且不会产生安全问题。
    
请参考下面的链接，如果 Bluecoat 代理为您的网络拓扑的一部分：https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 