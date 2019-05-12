---
title: Skype 中的业务服务器的多个中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。 通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。 使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。
ms.openlocfilehash: 001045d10cd1169ced6a6bdc2856e2d12e818410
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910338"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype 中的业务服务器的多个中继支持

业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。 通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。 使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。

- 若要分配或删除业务服务器在 Skype 中继，必须首先在拓扑生成器中定义中继。 中继包含的以下关联： 中介服务器的完全限定域名 (FQDN)、 中介服务器侦听端口、 网关 FQDN，和网关侦听端口。
- 若要配置多个中继，可以创建多个同一个网关和中介服务器之间的关联。 这将提供企业语音基础结构，即在专用交换机 (pbx) interoperational 方案中尤其有用的其他恢复能力。 

定义中继，必须将其与路由关联。 若要将路由到中继相关联，请拓扑生成器中定义中继的简单名称。 此简单名称用作中继可以路由相关联的业务 Server Control Panel 中 Skype 的中继名称。 简单 trunk 名称用作业务 Server 命令行管理程序 Skype 的网关名称。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理员必须选择默认中继与中介服务器关联。 从拓扑生成器中，右键单击关联的中介服务器，然后单击**属性**。 为中介服务器指定默认网关。 

下图说明了每个中介服务器和网关定义的多个中继。 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)
