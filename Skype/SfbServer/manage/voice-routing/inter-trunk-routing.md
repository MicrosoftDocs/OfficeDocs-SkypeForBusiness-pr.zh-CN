---
title: Skype for Business Server：中继间路由
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server通过支持内部路由提供基本会话管理。 '
ms.openlocfilehash: dd63f5f03c46e03f313f9cac42a2432499c216b6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390994"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server：中继间路由

Skype for Business Server通过支持内部路由提供基本会话管理。 此功能使Skype for Business Server为下游电话系统提供呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Skype for Business Server可以相互连接两个或多个 IP-PBX 系统，以便可以在不同 IP-PBX 系统的 PBX 电话之间拨打和接听呼叫。 


下图说明了如何Skype for Business Server PSTN 网关和 IP-PBX 之间的互连性。

![PSTN 网关和 IP-PBX 之间的互连性。](../../media/pstn-gateway-ip-pbx.jpg)

下图说明了如何Skype for Business Server两个 IP-PBX 系统。

![Skype for Business Server两个 IP-PGX 系统。](../../media/two-ip-pbx-systems.jpg)

