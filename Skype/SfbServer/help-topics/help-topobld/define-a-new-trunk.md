---
title: 定义新的 Trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 通过提供以下信息定义一个新的会话初始协议 (SIP) Trunk：
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218553"
---
# <a name="define-a-new-trunk"></a>定义新的 Trunk

通过提供以下信息定义一个新的会话初始协议 (SIP) Trunk：

- **Trunk 名称**：标识此 Trunk 的拓扑中的唯一名称

- **关联的 PSTN 网关**：从列表选择部署中的一个已部署且已配置的 PSTN 网关

- **IP/PSTN 网关的侦听端口**：IP-PBX 或 PSTN 网关将侦听的端口。必须是唯一的，不同于部署中配置的所有其他 Trunk 侦听端口

- **SIP 传输协议**：从列表中选择 TCP 或 TLS

- **关联的中介服务器**：从列表中选择在部署中部署和配置的中介服务器

- **关联的中介服务器端口**：将端口值设置为等于此 SIP 中继将使用的中介服务器的 TCP 或 TLS 端口值

## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 中的 M:N 中继](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何实现 SIP 中继？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
