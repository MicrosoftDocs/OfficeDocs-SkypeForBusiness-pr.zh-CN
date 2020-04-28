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
description: 本文提供有关将代理服务器用于 Microsoft 团队或 Skype for Business 的信息。
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905674"
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
    
- 按照我们的网络指南中的其他建议操作：[为团队准备组织的网络](prepare-network.md)
  
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[Office 365 网络连接原则](https://aka.ms/pnc)

[为 Teams 准备贵组织的网络](prepare-network.md)
