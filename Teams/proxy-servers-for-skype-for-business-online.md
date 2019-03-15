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
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文提供了有关与团队或 Skype 的代理服务器使用的业务信息。
ms.openlocfilehash: a09a1bf53fe4d1a38742856c051a80e5928f36ef
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640895"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或 Skype for Business Online 的代理服务器

本文提供有关使用代理服务器团队或 Skype for Business 的指导。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

当谈到团队或 Skype 的业务流量通过代理时，Microsoft 建议绕过代理服务器。 代理不使团队或 for Business 的 Skype 更加安全因为已加密流量。
  
另外，使用代理会产生问题。 环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。 例如，这些问题将导致这样的团队或 Skype 业务方案音频和视频，为负体验实时流至关重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织具有用于工作组或 Skype 的业务通信不使用代理服务器的选项。 如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 关注我们网络指南中的其他建议：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 