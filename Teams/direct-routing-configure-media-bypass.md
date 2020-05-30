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
description: 了解如何使用电话系统直接路由为 Microsoft 团队配置媒体旁路，方法是同时切换所有用户或实施分阶段接近（推荐）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416892"
---
# <a name="configure-media-bypass-with-direct-routing"></a>使用直接路由配置媒体旁路

在使用直接路由配置媒体旁路之前，请确保具有[直接路由的媒体旁路计划](direct-routing-plan-media-bypass.md)。

若要打开媒体绕过，必须满足以下条件：

1.    确保你的会话边框控制器（SBC）供应商选择支持媒体旁路，并提供有关如何在 SBC 上配置旁路的说明。 请参阅证书页面，了解有关 SBCs、支持媒体旁路的信息以及相关说明。

2.    您需要使用以下命令打开 trunk 上的媒体旁路： **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。

3.    请确保打开所需的端口。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>从非绕过中继迁移到绕过启用中继

您可以一次切换所有用户，也可以实现分阶段的接近（推荐）。

- **一次切换所有用户。** 如果满足所有条件，则可以打开 "绕过" 模式。 但是，你的所有生产用户将同时进行切换。 由于最初配置中继和端口时可能会遇到某些问题，因此你的生产用户体验可能会受到影响。 

- **分阶段方法。（推荐）**。  为同一 SBC （具有不同端口）创建新的主干，对其进行测试，并更改用户的联机语音路由策略，以指向新的主干。 

  这是推荐的方法，因为它允许更平稳的切换和无中断的用户体验。 此方法需要使用 SBC、新的 FQDN 名称和防火墙的配置。 注意你需要确保你的证书支持这两个中继。 在 SAN 中，你需要具有两个名称（**sbc1.contoso.com**和**sbc2.contoso.com**）或具有通配符证书。

![从非绕过的中继迁移到绕过启用的中继）](media/direct-routing-media-bypass-8.png)

有关如何配置中继和执行迁移的说明，请参阅来自 SBC 供应商的文档：

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系统（anynode）部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

有关直接路由认证的会话边框控制器（SBCs）的列表，请参阅为[直接路由认证的会话 Broder 控制器列表](direct-routing-border-controllers.md)。



## <a name="related-topics"></a>相关主题

[使用直接路由规划媒体旁路](direct-routing-plan-media-bypass.md)



