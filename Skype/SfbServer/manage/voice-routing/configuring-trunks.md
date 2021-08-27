---
title: 在 Skype for Business Server
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
description: 作为 企业语音 部署的一部分，您可以在中介服务器与一个或多个对等方之间配置中继，为贵组织的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接。
ms.openlocfilehash: 5f7ce6bac163c481d01e71b3efb4ee13347a49e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598796"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>在 Skype for Business Server

作为 企业语音 部署的一部分，您可以在中介服务器与以下一个或多个对等方之间配置中继，为贵组织的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接：

- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
- PSTN 网关
- 专用交换机 (PBX)

有关详细信息，请参阅 Plan [for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> 开始中继配置之前，请确认已创建拓扑，并且中介服务器及其对等方已配置并相互关联。 有关详细信息，请参阅在拓扑生成器[中](../../deploy/deploy-enterprise-voice/define-a-gateway.md)定义Skype for Business Server。

> [!NOTE]
> 作为中继配置的一部分，您可以启用 Skype for Business Server媒体旁路功能，该功能使媒体可以绕过中介服务器。 配置中继时可以启用媒体旁路，也可以不启用媒体旁路，但我们强烈建议您启用该功能。 有关详细信息，请参阅规划[媒体旁路Skype for Business。](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
