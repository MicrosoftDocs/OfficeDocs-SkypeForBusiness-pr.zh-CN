---
title: 定义业务 Server 中 Skype E9-1-1 部署范围
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 规划业务 Server 企业语音中 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: 01b6b1656826977444928583ff08e8cb23b2982d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886287"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>定义业务 Server 中 Skype E9-1-1 部署范围

规划业务 Server 企业语音中 Skype E9-1-1 部署所需的决策。

为 E9-1-1 配置 Skype for Business 之前，您需要规划 E9-1-1 部署。 要考虑的一些问题包括：

 **贵组织的策略和法律义务 E9-1-1 是什么？**

 E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。 您应咨询法律团队了解可能适用于您相关的地理区域中的业务的 Skype 您部署义务。

 **需要在企业内部的哪些区域启用 E9-1-1？**

 可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。

 **如何为分支站点部署 E9-1-1？**

 语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。 如果您已集中 E-9-1-1 SIP 中继和 WAN 中断时，发生此事件，客户端登录可能不能用于从位置信息服务获取位置，或连接到紧急服务服务提供商。 Skype for Business 提供用于处理，包括为分支机构中的语音恢复能力的多个策略： 具有可恢复的数据网络、 部署在每个分支中，SIP 中继或推送紧急呼叫到本地网关在中断期间。 有关详细信息，请参阅[规划分支站点语音恢复能力](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。

 **是否为在网络外部工作的用户启用 E9-1-1？**

 仅适用于位于组织网络内，所以您的组织需要决定是否将支持业务时关闭内部部署的客户端发出 Skype E9-1-1 呼叫的客户端自动位置获取。 例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？ 如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。 但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。

> [!NOTE]
> 业务客户端的用户使用 VPN 连接到组织的网络的 Skype 可以拿起内部 IP 地址信息，但这些地址不能用于标识用户的实际位置，因为它非常重要的排除 VPN 子网从位置信息服务。

 **是否向美国之外的站点提供紧急呼叫路由？**

 您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。


