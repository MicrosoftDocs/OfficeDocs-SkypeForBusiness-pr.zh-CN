---
title: Skype for Business 服务器中的中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for business 服务器通过 intertrunk 路由支持提供基本的会话管理。 '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274966"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business 服务器中的中继间路由

Skype for business 服务器通过 intertrunk 路由支持提供基本的会话管理。 此功能使 Skype for business 服务器能够向下游电话系统提供呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样, Skype for Business 服务器可以互连两个或更多的 IP PBX 系统, 以便可以在不同的 IP PBX 系统中的 PBX 电话之间放置和接收呼叫。 


下图介绍了在 PSTN 网关和 IP PBX 之间提供 interconnectivity 的 Skype for business 服务器。

![PSTN 网关和 IP PBX 之间的 Interconnectivity](../../media/pstn-gateway-ip-pbx.jpg)

下图显示了连接两个 IP PBX 系统的 Skype for business 服务器。

![连接两个 IP-PGX 系统的 Skype for Business 服务器](../../media/two-ip-pbx-systems.jpg)

