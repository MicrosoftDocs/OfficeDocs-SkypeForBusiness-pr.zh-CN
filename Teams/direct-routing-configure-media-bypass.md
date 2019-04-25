---
title: 使用直接路由配置媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题可了解如何配置媒体绕过与电话系统直接路由。
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232689"
---
# <a name="configure-media-bypass-with-direct-routing"></a>使用直接路由配置媒体旁路

配置媒体绕过直接路由之前，请确保您已阅读[规划媒体绕过直接路由](direct-routing-plan-media-bypass.md)。

若要启用媒体绕过，必须满足以下条件：

1.  请确保您选择的会话边界控制器 (SBC) 供应商支持媒体绕过功能，并提供有关如何配置说明上 SBC 绕过。 请参阅证书页上，若要了解有关 SBCs，哪些与支持媒体绕过，以及有关说明。

2.  您需要使用以下命令中继上的媒体绕过打开：**集 CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。

3.  请确保，打开所需的端口。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>从非绕过中继迁移到启用绕过功能的中继

您可以同时切换所有用户，也可以实现分阶段接近 （推荐）。

- **同时切换所有用户。** 如果满足所有条件，您可以打开绕过模式。 但是，将同时切换所有生产用户。 因为最初配置中继和端口时，可能会遇到的一些问题，可能会影响您的生产用户体验。 

- **分阶段方法。（推荐）**。  创建新的中继 （具有不同的端口） 相同的 SBC、 测试，并更改为指向新的中继的用户的联机语音路由策略。 

  这是建议的方法，因为它允许更平稳转换和不间断的用户体验。 此方法需要配置的 SBC、 新的 FQDN 名称和防火墙的配置。 请注意，您将需要确保您的证书支持两个中继。 在 SAN，您需要有两个名称 （**sbc1.contoso.com**和**sbc2.contoso.com**） 或拥有通配符证书。

![从非绕过中继迁移到启用绕过功能的中继）](media/direct-routing-media-bypass-8.png)

有关如何配置中继和执行迁移的说明，请参阅从您的 SBC 供应商的文档：

- AudioCodes
- 功能区
- TE 系统 (AnyNode)    

认证可用于直接路由的会话边界控制器 (Sbc) 的列表，请参阅[会话 Broder 控制器的列表认证可用于直接路由](direct-routing-border-controllers.md)。



## <a name="see-also"></a>另请参阅

[规划媒体绕过直接路由](direct-routing-plan-media-bypass.md)



