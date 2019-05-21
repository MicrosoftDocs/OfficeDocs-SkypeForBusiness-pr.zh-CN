---
title: PSTN 网关设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：
ms.openlocfilehash: d84cede93166a94b353134991143089702a0d2fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289866"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN 网关设置扩展器
 
若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：
  
网关 FQDN 或 IP 地址是必需条目，按照域名系统 (DNS) 主机 (A) 记录、静态 HOSTS 文件条目或 PSTN 网关的 IP 地址的定义，定义 PSTN 网关的“**完全限定域名 (FQDN)**”。
  
SIP 传输协议可以是传输控制协议 (TCP)，也可以是传输层安全性 (TLS)。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。
  
选择是否为网关启用 IPv4 和 IPv6。
  
**备用媒体 IP 地址**是中介服务器的定义, 其中部署的 PSTN 网关的媒体流量与默认配置的 ip 地址 (通常专用于 SIP 流量) 具有不同的 ip 地址。 如果定义此参数，则 PSTN 网关为媒体提供不同的网络接口或路径支持。 如果此地址留空，则 PSTN 网关不支持媒体的备用路径。
  

