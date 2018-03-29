---
title: Skype for Business Server 2015 中的分支站点 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 对于业务服务器企业语音了解分支站点在 Skype 上的 SIP 中继。
ms.openlocfilehash: 92616062c12fce51e3adb816d5ebc299a5dbf3fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的分支站点 SIP 中继
 
对于业务服务器企业语音了解分支站点在 Skype 上的 SIP 中继。
  
在某些情况下，您可能需要实现分布式的 SIP 中继，在选定的分支站点。 确定是否对 SIP 中继和所需的分支网站，有关部署分支站点中的 SIP 中继的受支持的拓扑选项的详细信息，请参阅[SIP 中继业务服务器 2015年的 Skype 中](sip-trunking.md)。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>示例分支站点 SIP 中继要求分析

当您决定部署分支站点 SIP 中继时，您需要执行特定于站点的成本分析。 例如，在华盛顿州雷蒙德市的中心站点和分支站点在纽约，一个企业应该做分析，以确定是否实现 SIP 中继从纽约上给当地服务提供商。
  
为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。 DID 终止时为执行的分支站点可以在中心站点。 例如，雷德蒙中央站点可以承载的纽约分部地点的 DID 号码。 实施分布式的 SIP 中继的成本小于这些调用的开销，如果考虑实现 SIP 中继在纽约分部地点。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。 如果您部署分支站点 SIP 中继，还需要确定您的恢复能力和带宽的需求。 如果中心站点和分支站点之间的链接有弹性，并且具有足够的带宽，您可以部署 SIP 中继或网关。 您不需要部署在分支站点高存活力分支装置。 如果中心站点和分支站点之间的链接不是弹性的部署高存活力的分支装置，或者部署自动恢复的分支服务器与网关或分支地点的 SIP 中继。 
  

