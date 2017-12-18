---
title: "Skype for Business Online 的代理服务器"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。"
---

# Skype for Business Online 的代理服务器

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。
  
## 建议不使用代理服务器

考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。代理并不会使 Skype for Business 更加安全，因为 Skype for Business 的流量已经过加密。
  
另外，使用代理会产生问题。环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。此类问题会对音频和视频等 Skype for Business 场景中的体验带来负面影响，因为在这些场景中，实时流至关重要。
  
## 如果需要使用代理服务器

某些组织都有没有可用于绕过代理 for Skype Business 通信选项。如果这是您的情况，上述问题需要注意。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量 
    
- 请遵循我们的网络指南中提供的其他建议：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
遵循本指南应尽可能减少潜在问题。
  
## 具有内置 Skype for Business 支持或配置选项的代理供应商

本部分包含提供的产品或服务已证明可以成功用于 Skype for Business 流量的代理供应商的信息。
  
- 对于使用 **Bluecoat 代理解决方案** 的组织，新固件已发布，可以解决关于以下方面的若干个问题：
    
  - SSL 拦截
    
  - OCSP/SRL 检查
    
  - 基于 TLS 的 SIP
    
  - 对 TURN 的支持
    
    Bluecoat 对 Skype for Business 的本地支持很容易启用，以便识别相关流量并相应地加以管理。这样可确保实现最佳的身份验证、信号传输和媒体流量流，以提供非凡的用户体验，且不会产生安全问题。
    
    请如果 Bluecoat 代理是您的网络拓扑的一部分，参阅以下链接
    
- https://support.symantec.com/en_US/article.DOC9757.html
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

