---
title: 使用直接路由配置媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何通过一次切换所有用户电话系统 Microsoft Teams或实施分阶段的按建议方法 (媒体旁路) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74cfdb0d0bd92849b062d84df20e4ca1428f4034b2e8864bfc89ff70b77c6c3c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284183"
---
# <a name="configure-media-bypass-with-direct-routing"></a>使用直接路由配置媒体旁路

使用直接路由配置媒体旁路之前，请确保已阅读使用直接路由 [规划媒体旁路](direct-routing-plan-media-bypass.md)。

若要启用媒体旁路，必须满足以下条件：

1.    请确保选择的 SBC (会话) 控制器支持媒体旁路，并说明如何在 SBC 上配置旁路。 请参阅认证页面，了解支持媒体绕过的 SDC，以及说明。

2.    需使用以下命令在中继上打开媒体旁路 **：Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true。**

3.    确保打开所需的端口。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>从未绕过的中继迁移到已启用绕过的中继

可以一次切换所有用户，也可以实施分阶段的 (建议) 。

- **一次切换所有用户。** 如果满足所有条件，可以打开绕过模式。 但是，将同时切换所有生产用户。 由于在配置中继和端口时，最初可能会遇到一些问题，因此生产用户体验可能会受到影响。 

- **分阶段方法。 (建议) 。**  为同一 SBC (使用不同的端口) ，测试它，并更改用户的联机语音路由策略以指向新的中继。 

  这是建议的方法，因为它可实现更流畅的过渡和不间断的用户体验。 此方法需要配置 SBC、新的 FQDN 名称和防火墙配置。 请注意，需要确保证书支持这两个中继。 在 SAN 中，需要具有两个名称 (sbc1.contoso.com **和** **sbc2.contoso.com)** 或具有通配符证书。

![从非绕过的中继迁移到已启用旁路的中继) ](media/direct-routing-media-bypass-8.png)

有关如何配置中继和执行迁移的说明，请参阅 SBC 供应商提供的文档：

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

有关已通过直接路由认证的 (SDC 的会话边界控制器) 列表，请参阅通过直接路由 认证的会话 [Broder](direct-routing-border-controllers.md)控制器列表。



## <a name="related-topics"></a>相关主题

[使用直接路由规划媒体旁路](direct-routing-plan-media-bypass.md)



