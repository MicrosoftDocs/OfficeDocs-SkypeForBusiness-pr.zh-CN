---
title: 内部中继路由中 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype 业务服务器提供通过支持的中继间路由的基本会话管理。 '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222812"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>内部中继路由中 Skype 业务服务器

Skype 业务服务器提供通过支持的中继间路由的基本会话管理。 此功能允许 Skype 业务服务器提供与下游电话系统的呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Skype 业务服务器可以互连两个或多个 IP-PBX 系统，以便可以发出呼叫，并将其从不同的 IP PBX 系统的 PBX 电话之间收到。 


下图展示了业务服务器提供 PSTN 网关和 IP-PBX 之间的互连性的 Skype。

![PSTN 网关和 IP-PBX 之间的互连性](../../media/pstn-gateway-ip-pbx.jpg)

下图显示连接两个 IP-PBX 系统的业务服务器 Skype。

![Skype 连接两个 IP PGX 系统的业务服务器](../../media/two-ip-pbx-systems.jpg)

