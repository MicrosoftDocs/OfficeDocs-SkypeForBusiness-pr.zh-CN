---
title: 分支站点 SIP 中继Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 了解站点中的分支站点中的 SIP Skype for Business Server 企业语音。
ms.openlocfilehash: 9fd9bb742b61516ca450082c187fb460bacdf11d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765290"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>分支站点 SIP 中继Skype for Business Server
 
了解站点中的分支站点中的 SIP Skype for Business Server 企业语音。
  
在某些情况下，您可能需要在选定的分支站点实施分布式 SIP 中继。 要确定分支站点是否需要 SIP 中继，以及有关在分支站点中部署 SIP 中继支持的拓扑选项的详细信息，请参阅 sip [trunking in Skype for Business Server](sip-trunking.md)。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>示例分支站点 SIP 中继要求分析

当您决定部署分支站点 SIP 中继时，您需要执行特定于站点的成本分析。 例如，具有位于华盛顿州雷德蒙德的中央站点和纽约分支站点的企业应进行分析，以确定是否实施从纽约站点到本地服务提供商的 SIP 中继。
  
为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。 可以在中央站点对分支站点进行 DID 终止。 例如，Redmond 中央站点可以承载纽约分支站点的 DID 号码。 如果实现分布式 SIP 中继的成本低于这些呼叫的成本，请考虑在纽约分支站点实施 SIP 中继。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。 如果部署分支站点 SIP 中继，则还需要确定恢复能力和带宽要求。 如果分支站点和中央站点之间的链接具有弹性且具有足够的带宽，您可以部署 SIP 中继或网关。 无需在分支站点部署 Survivable Branch Appliance。 如果分支站点和中央站点之间的链接无法恢复，请部署 Survivable Branch Appliance，或在分支站点部署具有网关或 SIP 中继的 Survivable Branch Server。 
  

