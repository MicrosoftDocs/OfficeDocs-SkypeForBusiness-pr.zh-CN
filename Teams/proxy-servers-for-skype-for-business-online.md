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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436678"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>适用于 Teams 和 Skype for Business Online 的代理服务器

本文提供有关将代理服务器与 Teams 或Skype for Business配合使用的指导。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建议不使用代理服务器

当涉及到 Teams 或通过代理Skype for Business流量时，Microsoft建议绕过代理。 代理不会使 Teams 或Skype for Business更安全，因为流量已加密。
  
另外，使用代理会产生问题。 通过尝试通过代理服务器路由 Teams 流量，可能会因延迟和数据包丢失而引入环境与性能相关的问题。 此类问题将导致在此类 Teams 或Skype for Business场景中出现负面体验，例如音频和视频，其中实时流至关重要。

建议 Teams 流量绕过代理服务器基础结构。 你可能希望通过将 Teams 电话和会议室设备置于其自己的 VLAN 上并为其提供 Internet 访问权限来实现此目的。

## <a name="windows-based-teams-devices"></a>Windows-Based Teams 设备

基于 Windows 的 Teams 会议室和 Surface Hub 支持某些代理服务器，但不支持需要身份验证的代理服务器。

我们建议这些设备绕过代理基础结构，并通过防火墙访问 Microsoft 365 服务。

## <a name="android-based-teams-devices"></a>Android-Based Teams 设备

基于 Android 的 Teams 设备（包括 Teams 电话、面板、显示器和板）不支持代理服务器。

由于这些设备上运行的某些组件访问 Internet 的方式，无法通过代理路由所有流量。 必须确保这些设备与 Microsoft 365 服务之间的流量通过防火墙允许。

## <a name="if-you-need-to-use-a-proxy-server"></a>如果需要使用代理服务器

某些组织无法绕过 Teams 代理或Skype for Business流量。 如果你是这种情况，需要留意上面提到的问题。

> [!Note]
> 如果在代理基础结构上使用专用签名的证书，则需要在 Teams 会议室设备上安装专用签名的证书和证书链，以允许设备信任证书。 不支持在 Teams 电话和其他基于 Android 的 Teams 设备上安装专用签名的证书。
  
Microsoft 还强烈建议：
  
- 使用本地外部 DNS 解析 (某些基于云的代理解决方案可能会导致 DNS 解析在另一个位置) 发生。

- 确保 Teams 设备与我们的服务之间的路径尽可能短且直接
    
- 使用基于 UDP 的直接路由，而不是依赖于基于 TCP 的媒体路由
    
- 允许 Teams Media (3478-3481 的 UDP 流量通过防火墙) 

- 允许所有必需的 URL 和 IP，包括 Azure、Office 365、Intune 和 Teams Room Pro (，) 通过防火墙使用
    
- 遵循网络指南中的其他建议： [为 Teams 准备组织的网络](prepare-network.md)
  
    
遵循本指南应尽可能减少潜在问题。
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[为 Teams 准备贵组织的网络](prepare-network.md)
