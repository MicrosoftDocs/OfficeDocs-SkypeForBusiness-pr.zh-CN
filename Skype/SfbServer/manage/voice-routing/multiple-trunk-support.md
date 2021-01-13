---
title: Skype for Business Server 中的多个中继支持
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 功能支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (即中继) 。
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826222"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype for Business Server 中的多个中继支持

Skype for Business Server 功能支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (即中继) 。

- 若要在 Skype for Business Server 中分配或删除中继，必须先在拓扑生成器中定义中继。 中继包含以下关联：中介服务器完全限定域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。
- 若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。 这为网络基础结构企业语音复原能力，在专用交换机和 PBX (互操作) 尤其有用。 

定义中继，必须将其与路由关联。 若要将中继与路由关联，请为拓扑生成器中的中继定义一个简单的名称。 此简单名称用作 Skype for Business Server 控制面板中的中继名称，其中中继可以与路由关联。 简单中继名称用作 Skype for Business Server 命令行管理程序 中的网关名称。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理员必须选择与中介服务器关联的默认中继。 在拓扑生成器中，右键单击关联的中介服务器，然后单击"**属性"。** 指定中介服务器的默认网关。 

下图演示了为每个中介服务器和网关定义的多个中继。 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)
