---
title: 边缘机设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要编辑的属性中的边缘服务器池的服务器，执行以下操作：
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a>边缘机设置扩展器
 
若要编辑的属性中的边缘服务器池的服务器，执行以下操作：
  
通过编辑的完全合格的域名称 (FQDN)，可以更改**内部名称或 FQDN** 。 域名系统 (DNS) 主机 (A) 记录，并分配给服务器的内部边缘网络接口的证书的接受方名称必须匹配 FQDN。 **内部 IP 地址**的值定义为分配定义为内部网络，相对于外围网络设计的网络接口的 IP 地址。
  
对话框中的三个部分定义的外部边缘服务器配置的 IP 地址。 更改 IP 地址的能力受设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**属性设置在边缘服务器上池级别。
  
## <a name="sip-access"></a>SIP 访问

编辑分配给网络接口为会话启动协议 (SIP) 访问的外部 IP 地址。 此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。
  
> [!NOTE]
> 如果该设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**池上设置启用页，仅为 SIP 访问的 IP 地址可供编辑。
  
## <a name="web-conferencing"></a>Web 会议

编辑外部 IP 地址分配给网络接口的网络会议。 此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。
  
## <a name="audiovideo"></a>音频/视频

编辑外部 IP 地址分配给网络接口的音频/视频 (A / V)。 此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。
  
**使用的公用 IP 地址启用 NAT**的设置是通过外部接口用于建立的公用地址 / V 一般网络接口或边缘服务器。 如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**已启用，此公用 IP 地址用于所有三个外部接口。
  

