---
title: PSTN 网关设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：
ms.openlocfilehash: 45b3945a811a2e9c9b5d1c0cce805c78368c9a70
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201627"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN 网关设置扩展器
 
若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：
  
网关 FQDN 或 IP 地址是必需条目，按照域名系统 (DNS) 主机 (A) 记录、静态 HOSTS 文件条目或 PSTN 网关的 IP 地址的定义，定义 PSTN 网关的“**完全限定域名 (FQDN)**”。
  
SIP 传输协议可以是传输控制协议 (TCP)，也可以是传输层安全性 (TLS)。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。
  
选择是否为网关启用 IPv4 和 IPv6。
  
**备用媒体 IP 地址**是中介服务器部署的 PSTN 网关有比通常专门用于 SIP 通信的默认配置 IP 地址的媒体流量的不同 IP 地址的定义。 如果定义此参数，则 PSTN 网关为媒体提供不同的网络接口或路径支持。 如果此地址留空，则 PSTN 网关不支持媒体的备用路径。
  

