---
title: 定义新的中继
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 通过提供以下信息定义新的会话初始协议 (SIP) 中继：
ms.openlocfilehash: 7c9675989b6282e7af5aa117213093cf55ae583b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250827"
---
# <a name="define-a-new-trunk"></a>定义新的中继

通过提供以下信息定义新的会话初始协议 (SIP) 中继：

- **Trunk 名称**： 标识此 trunk 的拓扑中的唯一名称

- **关联的 PSTN 网关**： 选择部署从列表中的部署和配置 PSTN 网关

- **IP/PSTN 网关的侦听端口**： 的 IP PBX 或 PSTN 网关将侦听的端口。 必须是唯一的从所有部署中配置其他中继侦听端口

- **SIP 传输协议**： 从列表中选择 TCP 或 TLS

- **关联的中介服务器**： 从列表中选择一个已部署且您部署中配置中介服务器

- **关联的中介服务器端口**： 将端口值设置为等于该 SIP 中继将使用的中介服务器的 TCP 或 TLS 端口值

## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 中的 M:N 中继](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何实施 SIP 中继？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)