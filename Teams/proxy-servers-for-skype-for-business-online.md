---
title: Teams 或 Skype for Business Online 的代理服务器
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与团队或 Skype for Business 配合使用的信息。
ms.openlocfilehash: b06e7aa43dcbcf5aeab9011af72d94460f69cc63
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573202"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或 Skype for Business Online 的代理服务器

本文提供有关将代理服务器与团队或 Skype for Business 配合使用的指南。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

当来自代理的团队或 Skype for business 通信流时，Microsoft 建议绕过代理。代理不会使团队或 Skype for business 更加安全，因为通信已加密。
  
并且拥有代理可能会导致问题。与性能相关的问题可通过延迟和数据包丢失引入环境。此类问题将在此类团队或 Skype for Business 方案中产生消极的体验，因为实时流非常重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织没有为团队或 Skype for business 流量绕过代理的选项。如果这是你所说的情况，上述问题需要牢记。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 按照我们的网络指南中的其他建议操作：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 