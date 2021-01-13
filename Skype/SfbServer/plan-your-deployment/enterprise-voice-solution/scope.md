---
title: 在 Skype for Business Server 中定义 E9-1-1 部署的范围
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 在 Skype for Business Server 部署中规划 E9-1-1 部署企业语音。
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813422"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>在 Skype for Business Server 中定义 E9-1-1 部署的范围

在 Skype for Business Server 部署中规划 E9-1-1 部署企业语音。

为 E9-1-1 配置 Skype for Business 之前，需要规划 E9-1-1 部署。 要考虑的一些问题包括：

 **贵组织关于 E9-1-1 的策略和法律要求是什么？**

 E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。 你应该咨询法律团队，以了解可能适用于你在相关地理位置部署 Skype for Business 的义务。

 **需要在企业内部的哪些区域启用 E9-1-1？**

 可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。

 **如何为分支站点部署 E9-1-1？**

 语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。 如果您具有集中式 E-9-1-1 SIP 中继并且发生 WAN 中断，则登录的客户端可能无法从位置信息服务获取位置或无法连接到紧急服务服务提供商。 Skype for Business 提供了几种用于处理分支机构中的语音恢复的策略，包括：拥有可恢复的数据网络、在每个分支部署 SIP 中继或在中断期间将紧急呼叫推送到本地网关。 有关详细信息，请参阅[Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。

 **是否为在网络外部工作的用户启用 E9-1-1？**

 自动位置获取仅适用于位于组织网络内部的客户端，因此组织需要决定是否支持在外部时从 Skype for Business 客户端拨打的 E9-1-1 呼叫。 例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？ 如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。 但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。

> [!NOTE]
> 使用 VPN 连接到组织网络的用户的 Skype for Business 客户端可以获取内部 IP 地址信息，但由于这些地址不能用于标识用户的实际位置，因此从位置信息服务中排除 VPN 子网至关重要。

 **是否向美国之外的站点提供紧急呼叫路由？**

 您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。


