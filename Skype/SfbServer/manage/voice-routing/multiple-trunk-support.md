---
title: 多个中继支持Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (，即中继) 。
ms.openlocfilehash: 0e4bc7d0248fa9116651a1384a17a7a8347b2d8f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729041"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>多个中继支持Skype for Business Server

Skype for Business Server支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (，即中继) 。

- 若要在拓扑中分配Skype for Business Server，必须先在拓扑生成器中定义中继。 中继包含以下关联：中介服务器完全限定域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。
- 若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。 这为 pbX 基础结构企业语音复原能力，在专用交换机和 PBX (互操作) 特别有用。 

定义中继，必须将其与路由关联。 若要将中继与路由关联，您可以在拓扑生成器中为中继定义一个简单名称。 此简单名称在控制面板中用作中继Skype for Business Server，其中中继可以与路由关联。 简单中继名称用作命令行管理程序中的Skype for Business Server名称。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理员必须选择与中介服务器关联的默认中继。 在拓扑生成器中，右键单击关联的中介服务器，然后单击"属性 **"。** 指定中介服务器的默认网关。 

下图说明了为每个中介服务器和网关定义的多个中继。 

![多个中继分配。](../../media/multiple-trunk-assignments.jpg)
