---
title: 边缘服务器 FQDN 设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: 若要编辑或指定边缘服务器的外部设置，首先必须确定是否对会话初始协议 (SIP) 访问、Web 会议边缘服务和音频/视频边缘服务使用单独的 IP 地址。
ms.openlocfilehash: 7bca4f934e321edbf3c32d9d075b4a1cccd2bbf6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807082"
---
# <a name="edge-server-fqdns-settings-expander"></a>边缘服务器 FQDN 设置扩展器

若要编辑或指定边缘服务器的外部设置，首先必须确定是否将单独的 IP 地址用于会话初始协议 (SIP) 访问、Web 会议边缘服务和音频/视频边缘服务。

如果它们都要使用单独的 IP 地址，请选中 **“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”** 复选框。每个服务必须具有为其创建的对应域名系统 (DNS) 主机 (A) 记录。

对于每个面向外部的服务，指定完全限定的域名 (FQDN) 和关联端口。例如，对于“SIP 访问”，可以使用 sip.contoso.com 和关联端口 5061。

> [!IMPORTANT]
> 如果为每个面向外部的服务选择单独的 FQDN，则每个服务必须具有与其关联的唯一端口值。默认情况下，SIP 使用端口 5061/TLS，Web 会议边缘服务使用端口 444/TLS，A/V 会议边缘服务使用端口 443/TLS。如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。

如果确定组织要为面向外部的服务使用单个 FQDN 和 IP 地址，请清除“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。然后，可以编辑“SIP 访问”池 FQDN 和端口值（如有必要）。

> [!IMPORTANT]
> 如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。

有关定义和配置边缘服务设置的详细信息，请参阅["定义边缘拓扑"。](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)


