---
title: Skype for Business Online 的代理服务器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850010"
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
  
## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 