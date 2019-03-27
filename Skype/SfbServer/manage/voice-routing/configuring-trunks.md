---
title: 为业务服务器中 Skype 配置中继
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 作为企业语音部署的一部分，您可以配置您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的中介服务器和一个或多个对等方之间的中继。
ms.openlocfilehash: 5e07f0152aac32c4d57962cf619e56777221c955
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883968"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>为业务服务器中 Skype 配置中继

作为企业语音部署的一部分，您可以配置中介服务器和一个或多个您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的以下的对等方之间中继：

- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
- PSTN 网关
- 专用交换机 (PBX)

有关详细信息，请参阅[规划中的业务服务器 Skype 的 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> 中继配置之前，验证已创建的拓扑和，中介服务器和其对等已配置并与另一个关联。 有关详细信息，请参阅[Define 拓扑生成器中的业务服务器 Skype 的网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。

> [!NOTE]
> 作为中继配置的一部分，您可以启用 Business Server 媒体绕过功能，使媒体绕过中介服务器的 Skype。 可以使用或不启用媒体旁路配置中继，但强烈建议您启用它。 有关详细信息，请参阅[规划媒体绕过 Skype for Business 中](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
