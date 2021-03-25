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
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有关将代理服务器与 Microsoft Teams 或 Skype for Business 一起使用的信息。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117720"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或 Skype for Business Online 的代理服务器

本文提供有关将代理服务器与 Teams 或 Skype for Business 一同使用的指导。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

对于通过代理的 Teams 或 Skype for Business 流量，Microsoft 建议绕过代理。 代理不会使 Teams 或 Skype for Business 更安全，因为流量已加密。
  
另外，使用代理会产生问题。 环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。 此类问题会导致在音频和视频等 Teams 或 Skype for Business 方案中遇到负面体验，实时流至关重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织无法绕过 Teams 或 Skype for Business 流量的代理。 如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 遵循网络指南中的其他建议： [为 Teams 准备组织的网络](prepare-network.md)
  
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[为 Teams 准备贵组织的网络](prepare-network.md)