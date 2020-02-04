---
title: Edge 机器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要在边缘服务器池中编辑服务器的属性，请执行下列操作：
ms.openlocfilehash: aeb9c48968b7b5223ac33fc3419d630229724a09
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697477"
---
# <a name="edge-machine-settings-expander"></a>Edge 机器设置扩展器
 
若要在边缘服务器池中编辑服务器的属性，请执行下列操作：
  
通过编辑完全限定的域名（FQDN），可以更改**内部名称或 FQDN** 。 FQDN 必须与域名系统（DNS）主机（A）记录和分配给服务器内部 Edge 网络接口的证书的使用者名称相匹配。 "**内部 IP 地址**" 的值定义了分配网络接口的 IP 地址，该地址是定义为内部网络的网络接口（相对于外围网络设计）。
  
对话框的接下来三个部分定义了此边缘服务器的外部配置的 IP 地址。 更改 IP 地址的功能受此设置的影响在边缘服务器池级别的属性设置上**为 web 会议和 A/V 启用单独的 FQDN 和 IP 地址**。
  
## <a name="sip-access"></a>SIP 访问

编辑分配给用于会话初始协议（SIP）访问的网络接口的外部 IP 地址。 此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。
  
> [!NOTE]
> 如果在启用了 "池设置" 页面上的 "**为 web 会议和 A/V 单独的 FQDN 和 IP 地址**" 设置，则只有 SIP 访问的 IP 地址才可供编辑。
  
## <a name="web-conferencing"></a>Web 会议

编辑分配给 web 会议网络接口的外部 IP 地址。 此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。
  
## <a name="audiovideo"></a>音频/视频

编辑分配给音频/视频的网络接口的外部 IP 地址（A/V）。 此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。
  
**使用支持 NAT 的公共 IP 地址**的设置是由 A/V 网络接口或边缘服务器使用的外部接口的公共地址。 如果设置为**web 会议和 A/V 启用了单独的 FQDN 和 IP 地址**，则此公共 IP 地址将用于所有三个外部接口。
  

