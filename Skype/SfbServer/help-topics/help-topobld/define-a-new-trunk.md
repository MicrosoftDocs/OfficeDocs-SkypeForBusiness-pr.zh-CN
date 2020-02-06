---
title: 定义新中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 通过提供以下信息来定义新的会话初始协议（SIP）中继：
ms.openlocfilehash: 9b3d42500c57723b13d9c74668b3c4ad7159301b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820214"
---
# <a name="define-a-new-trunk"></a>定义新中继

通过提供以下信息来定义新的会话初始协议（SIP）中继：

- **主干名称**：拓扑中将标识此主干的唯一名称

- **关联的 PSTN 网关**：从列表中选择部署中已部署的和配置的 PSTN 网关

- **Ip/PSTN 网关的侦听端口**： ip PBX 或 PSTN 网关将侦听的端口。 在部署中配置的所有其他中继侦听端口必须是唯一的

- **SIP 传输协议**：从列表中选择 "TCP" 或 "TLS"

- **关联的中介服务器**：从列表中选择在部署中部署和配置的中介服务器

- **关联的中介服务器端口**：将 port 值设置为等于此 SIP 主干将使用的中介服务器的 TCP 或 TLS 端口值

## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 中的 M:N 中继](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何实现 SIP 中继？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
