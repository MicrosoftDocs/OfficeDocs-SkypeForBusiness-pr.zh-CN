---
title: 使用直接路由配置媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题, 了解如何使用 "电话系统直接路由" 配置 "绕过媒体"。
ms.openlocfilehash: ab7fbb7549793f7c557d11629f9aab4ef922e516
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394568"
---
# <a name="configure-media-bypass-with-direct-routing"></a>使用直接路由配置媒体旁路

在使用直接路由配置媒体旁路之前, 请确保具有[直接路由的媒体旁路计划](direct-routing-plan-media-bypass.md)。

若要打开媒体绕过, 必须满足以下条件:

1.  确保你的会话边框控制器 (SBC) 供应商选择支持媒体旁路, 并提供有关如何在 SBC 上配置旁路的说明。 请参阅证书页面, 了解有关 SBCs、支持媒体旁路的信息以及相关说明。

2.  您需要使用以下命令打开 trunk 上的媒体旁路: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。

3.  请确保打开所需的端口。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>从非绕过中继迁移到绕过启用中继

您可以一次切换所有用户, 也可以实现分阶段的接近 (推荐)。

- **一次切换所有用户。** 如果满足所有条件, 则可以打开 "绕过" 模式。 但是, 你的所有生产用户将同时进行切换。 由于最初配置中继和端口时可能会遇到某些问题, 因此你的生产用户体验可能会受到影响。 

- **分阶段方法。(推荐)**。  为同一 SBC (具有不同端口) 创建新的主干, 对其进行测试, 并更改用户的联机语音路由策略, 以指向新的主干。 

  这是推荐的方法, 因为它允许更平稳的切换和无中断的用户体验。 此方法需要使用 SBC、新的 FQDN 名称和防火墙的配置。 注意你需要确保你的证书支持这两个中继。 在 SAN 中, 你需要具有两个名称 (**sbc1.contoso.com**和**sbc2.contoso.com**) 或具有通配符证书。

![从非绕过的中继迁移到绕过启用的中继)](media/direct-routing-media-bypass-8.png)

有关如何配置中继和执行迁移的说明, 请参阅来自 SBC 供应商的文档:

- AudioCodes
- 带
- TE-系统 (AnyNode)    

有关直接路由认证的会话边框控制器 (SBCs) 的列表, 请参阅为[直接路由认证的会话 Broder 控制器列表](direct-routing-border-controllers.md)。



## <a name="see-also"></a>另请参阅

[使用直接路由规划媒体旁路](direct-routing-plan-media-bypass.md)



