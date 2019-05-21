---
title: 定义新中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: '通过提供以下信息来定义新的会话初始协议 (SIP) 中继:'
ms.openlocfilehash: c66d5999d6aa5bad0e9c16f8d466d82b941a630b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305919"
---
# <a name="define-a-new-trunk"></a>定义新中继

通过提供以下信息来定义新的会话初始协议 (SIP) 中继:

- **主干名称**: 拓扑中将标识此主干的唯一名称

- **关联的 PSTN 网关**: 从列表中选择部署中已部署的和配置的 PSTN 网关

- **Ip/PSTN 网关的侦听端口**: ip PBX 或 PSTN 网关将侦听的端口。 在部署中配置的所有其他中继侦听端口必须是唯一的

- **SIP 传输协议**: 从列表中选择 "TCP" 或 "TLS"

- **关联的中介服务器**: 从列表中选择在部署中部署和配置的中介服务器

- **关联的中介服务器端口**: 将 port 值设置为等于此 SIP 主干将使用的中介服务器的 TCP 或 TLS 端口值

## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 中的 M:N 中继](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何实现 SIP 中继？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
