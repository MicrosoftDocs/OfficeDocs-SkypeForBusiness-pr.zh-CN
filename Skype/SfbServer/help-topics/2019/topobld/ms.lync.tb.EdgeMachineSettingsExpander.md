---
title: 边缘计算机设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 要编辑边缘服务器池中的服务器的属性，请执行以下操作：
ms.openlocfilehash: d297de5e4e503932387c1ba207959261cd19024c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579186"
---
# <a name="edge-machine-settings-expander"></a>边缘计算机设置扩展器
 
要编辑边缘服务器池中的服务器的属性，请执行以下操作：
  
通过编辑完全限定域名 (FQDN)，可更改“内部名称或 FQDN”。FQDN 必须与域名系统 (DNS) 主机 (A) 记录以及分配给服务器的内部边缘网络接口的证书使用者名称相匹配。“内部 IP 地址”的值定义分配给定义为内部网络（与外围网络设计相对）的网络接口的 IP 地址。
  
对话框的以下三部分定义此边缘服务器的外部配置的 IP 地址。更改 IP 地址的功能受边缘服务器池级别“属性”设置上的“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置的影响。
  
## <a name="sip-access"></a>SIP 访问

编辑分配给会话初始协议 (SIP) 访问的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。
  
> [!NOTE]
> 如果已启用池设置页上的“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置，则只能编辑 SIP 访问的 IP 地址。
  
## <a name="web-conferencing"></a>Web 会议

编辑分配给 Web 会议的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。
  
## <a name="audiovideo"></a>音频/视频

编辑分配给音频/视频 (A/V) 的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。
  
一般情况下，“已使用的启用了 NAT 的公用 IP 地址”的设置是供 A/V 网络接口或边缘服务器的外部接口使用的公用地址。如果启用“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置，则此公用 IP 地址将用于所有三个外部接口。
  

