---
title: Teams 或 Skype for Business Online 的代理服务器
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 本文提供有关将代理服务器与 Microsoft Teams 或 Skype for Business 配合使用的信息。
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176669"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或 Skype for Business Online 的代理服务器

本文提供有关将代理服务器与 Teams 或Skype for Business配合使用的指导。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

当涉及到 Teams 或通过代理Skype for Business流量时，Microsoft建议绕过代理。 代理不会使 Teams 或Skype for Business更安全，因为流量已加密。
  
另外，使用代理会产生问题。 通过尝试通过代理服务器路由 Teams 流量，可能会因延迟和数据包丢失而引入环境与性能相关的问题。 此类问题将导致在此类 Teams 或Skype for Business场景中出现负面体验，例如音频和视频，其中实时流至关重要。

建议 Teams 流量绕过代理服务器基础结构。

## <a name="teams-phones"></a>Teams 电话

Teams 电话不支持代理服务器。

我们的建议是确保 (TCP 443) 和媒体 (UDP 3478-3481) 流量绕过代理服务器基础结构。

## <a name="teams-meeting-rooms-and-panels"></a>Teams 会议室和面板

建议确保 Teams 会议室绕过代理基础结构。

基于 Windows 的 Teams 会议室支持代理服务器，但不支持需要身份验证的代理服务器。 基于 Android 的 Teams 会议室不支持代理服务器。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织无法绕过 Teams 代理或Skype for Business流量。 如果你是这种情况，需要留意上面提到的问题。
  
Microsoft 还强烈建议：
  
- 使用本地外部 DNS 解析 (某些基于云的代理解决方案可能会导致 DNS 解析在另一个位置) 发生。
    
- 使用基于 UDP 的直接路由，而不是依赖于基于 TCP 的媒体路由
    
- 允许 UDP 流量 (3478-3481) 

- 允许所有必需的 URL 和 IP，包括 Azure、Office 365、Intune 和 Teams 会议室 Pro (使用的 URL 和 IP) 
    
- 遵循网络指南中的其他建议： [为 Teams 准备组织的网络](prepare-network.md)
  
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[为 Teams 准备贵组织的网络](prepare-network.md)
