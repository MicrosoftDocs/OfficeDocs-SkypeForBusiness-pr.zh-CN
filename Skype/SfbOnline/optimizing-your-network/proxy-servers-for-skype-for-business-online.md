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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与 Skype for Business。
ms.openlocfilehash: c6c094bad366cf6a7febb092d471dd0723ce219b90664963a5e58a2ce64d70ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323514"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online 的代理服务器

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文提供有关将代理服务器与 Skype for Business。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。 代理不会使Skype for Business更安全，因为流量已加密。
  
另外，使用代理会产生问题。 环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。 此类问题将导致音频和视频等Teams或Skype for Business场景中的负面体验，实时流至关重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 遵循网络指南中的其他建议：
    
  - [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)
    
  - [为 Skype for Business Online 优化网络](optimizing-your-network.md)
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[为 Skype for Business Online 优化网络](optimizing-your-network.md)
 
