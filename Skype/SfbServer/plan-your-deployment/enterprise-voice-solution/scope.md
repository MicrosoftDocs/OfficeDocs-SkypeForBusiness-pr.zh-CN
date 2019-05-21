---
title: 在 Skype for Business 服务器中定义 E9 部署的范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 在 Skype for Business Server Enterprise Voice 中规划 E9 部署所需的决策。
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276459"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>在 Skype for Business 服务器中定义 E9 部署的范围

在 Skype for Business Server Enterprise Voice 中规划 E9 部署所需的决策。

在为 E9 配置 Skype for Business 之前, 你需要规划 E9-1-1 部署。 要考虑的一些问题包括：

 **您的组织的政策和法律义务与 E9-1 有关？**

 E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。 您应咨询您的法律团队, 了解在相关地区的 Skype for business 部署中可能需要遵守的义务。

 **需要在企业内部的哪些区域启用 E9-1-1？**

 可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。

 **如何为分支站点部署 E9-1-1？**

 语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。 如果您有集中式电子 9-1-1 SIP 中继并且发生 WAN 中断, 则登录的客户可能无法从位置信息服务获取位置或连接到紧急服务服务提供商。 Skype for Business 提供了用于处理分支机构中的语音复原的多个策略, 包括: 拥有弹性数据网络、在每个分支机构部署 SIP 主干或在中断期间将紧急呼叫推送到本地网关。 有关详细信息，请参阅 [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。

 **是否为在网络外部工作的用户启用 E9-1-1？**

 自动位置获取仅适用于组织网络内的客户端, 因此你的组织需要确定它是否支持 E9-1-从 Skype for Business 客户端在离外部客户处拨打的电话。 例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？ 如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。 但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。

> [!NOTE]
> 通过使用 VPN 连接到组织网络的用户的 Skype for Business 客户端可以获取内部 IP 地址信息, 但由于这些地址不能用于标识用户的实际位置, 因此必须排除 VPN 子网从位置信息服务。

 **是否向美国之外的站点提供紧急呼叫路由？**

 您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。


