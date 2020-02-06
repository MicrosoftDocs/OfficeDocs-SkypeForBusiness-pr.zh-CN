---
title: Skype for Business 服务器中的多个中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。 这些关联通过定义主干（这是中介服务器池和公共交换电话网络（PSTN）网关、会话边界控制器（SBC）或 ip-pbx）之间的逻辑关联来进行。 使用拓扑生成器将网关与中介服务器相关联（即中继）。
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816942"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype for Business 服务器中的多个中继支持

Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。 这些关联通过定义主干（这是中介服务器池和公共交换电话网络（PSTN）网关、会话边界控制器（SBC）或 ip-pbx）之间的逻辑关联来进行。 使用拓扑生成器将网关与中介服务器相关联（即中继）。

- 若要在 Skype for Business 服务器中分配或删除主干，必须首先在拓扑生成器中定义一个主干。 主干包含以下关联：中介服务器完全限定的域名（FQDN）、中介服务器侦听端口、网关 FQDN 和网关侦听端口。
- 若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。 这将为企业语音基础结构提供额外的复原，这在专用分支 exchange （PBX） interoperational 方案中尤其有用。 

定义中继，必须将其与路由关联。 若要将主干关联到路由，请为拓扑生成器中的主干定义一个简单名称。 此简单名称用作 Skype for Business Server 控制面板中的主干名称，其中中继可以与路线相关联。 简单主干名称用作 Skype for Business Server Management Shell 中的网关名称。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理员必须选择与中介服务器关联的默认中继。 从拓扑生成器中，右键单击关联的中介服务器，然后单击 "**属性**"。 指定中介服务器的默认网关。 

下图显示了为每个中介服务器和网关定义的多个中继。 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)
