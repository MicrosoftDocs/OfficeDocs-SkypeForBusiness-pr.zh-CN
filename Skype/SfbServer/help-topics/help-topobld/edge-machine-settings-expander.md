---
title: Edge 机器设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要编辑边缘服务器池中的服务器的属性，请执行以下操作：
ms.openlocfilehash: 3d24eba1a24cf54da26b00b7b84b5b1b9fe52b61
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203149"
---
# <a name="edge-machine-settings-expander"></a>Edge 机器设置扩展器
 
若要编辑边缘服务器池中的服务器的属性，请执行以下操作：
  
通过编辑的完全限定的域名 (FQDN)，可以更改的**内部名称或 FQDN** 。 域名系统 (DNS) 主机 (A) 记录，并分配给服务器的内部边缘的网络接口的证书的使用者名称必须匹配的 FQDN。 **内部 IP 地址**的值定义分配定义为相对于外围网络设计内部网络的网络接口的 IP 地址。
  
对话框中的下一步三个部分定义此边缘服务器的外部配置的 IP 地址。 若要更改的 IP 地址的能力受设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**在边缘服务器的属性设置在池级别。
  
## <a name="sip-access"></a>SIP 访问

编辑分配给会话初始协议 (SIP) 访问的网络接口的外部 IP 地址。 此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。
  
> [!NOTE]
> 如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**池上设置页上启用，则仅 SIP 访问的 IP 地址将可供编辑。
  
## <a name="web-conferencing"></a>Web 会议

编辑分配给 web 会议的网络接口的外部 IP 地址。 此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。
  
## <a name="audiovideo"></a>音频/视频

编辑分配给音频/视频的网络接口的外部 IP 地址 (A / V)。 此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。
  
**启用公共 IP 地址使用 NAT**的设置是公共地址的外部接口用于任一 A / V 通常网络接口或边缘服务器。 如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**已启用，此公用 IP 地址用于所有三个外部接口。
  

