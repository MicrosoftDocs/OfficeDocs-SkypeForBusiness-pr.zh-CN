---
title: 团队或 Skype for business Online 的代理服务器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与 Skype for Business 配合使用的信息。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863744"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for business Online 的代理服务器

本文提供有关将代理服务器与 Skype for Business 配合使用的指南。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

当需要通过代理的 Skype for business 通信时，Microsoft 建议绕过代理。由于流量已加密，因此代理不会使 Skype for business 更安全。
  
并且拥有代理可能会导致问题。与性能相关的问题可通过延迟和数据包丢失引入环境。此类问题将在此类团队或 Skype for Business 方案中产生消极的体验，因为实时流非常重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 按照我们的网络指南中的其他建议操作：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)
    
  - [为 Skype for Business Online 优化网络](optimizing-your-network.md)
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](optimizing-your-network.md)
 