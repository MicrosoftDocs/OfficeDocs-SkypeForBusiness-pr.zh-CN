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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有关将代理服务器与 Microsoft Teams 或 Skype for Business。
ms.openlocfilehash: 559a42c19aa47a9e72a5c0549e80f45de8d50fdf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582156"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或 Skype for Business Online 的代理服务器

本文提供有关将代理服务器与 Teams 或 Skype for Business。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

对于通过代理Teams或Skype for Business流量，Microsoft 建议绕过代理。 代理不会确保Teams或Skype for Business，因为流量已加密。
  
另外，使用代理会产生问题。 环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。 此类问题将导致音频和视频等Teams或Skype for Business场景中的负面体验，实时流至关重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织无法绕过代理来Teams或Skype for Business流量。 如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用外部 DNS 解析
    
- 使用基于直接 UDP 的路由
    
- 允许 UDP 流量
    
- 遵循我们的网络准则中的其他建议：准备组织的网络[以Teams](prepare-network.md)
  
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[为 Teams 准备贵组织的网络](prepare-network.md)