---
title: 在 Skype for Business 服务器中配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 作为企业语音部署的一部分, 你可以在中介服务器和一个或多个对等方之间配置主干, 以便为组织中的企业语音客户端和设备提供公共交换电话网络 (PSTN) 连接。
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275001"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置中继

作为企业语音部署的一部分, 您可以在中介服务器和一个或多个以下对等方之间配置主干, 以便为企业语音客户端和组织中的设备提供公共交换电话网络 (PSTN) 连接:

- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
- PSTN 网关
- 专用交换机 (PBX)

有关详细信息, 请参阅[在 Skype For Business 服务器中规划 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> 在开始中继配置之前, 验证已创建拓扑, 并且中介服务器及其对等已配置并与另一个关联。 有关详细信息, 请参阅[在 Skype For Business 服务器的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。

> [!NOTE]
> 作为中继配置的一部分, 您可以启用 Skype for business 服务器媒体旁路功能, 这使媒体能够绕过中介服务器。 中继可以使用或不启用媒体旁路进行配置, 但我们强烈建议你启用它。 有关详细信息, 请参阅[在 Skype For business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
