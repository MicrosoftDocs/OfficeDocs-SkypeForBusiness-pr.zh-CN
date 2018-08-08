---
title: Skype 业务服务器中的分支站点 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 了解有关在 Skype 中的分支站点 SIP 中继的业务 Server 企业语音。
ms.openlocfilehash: e14d6ba3101c1981b719ea0f030d2e92fbd4ab7b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966269"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Skype 业务服务器中的分支站点 SIP 中继
 
了解有关在 Skype 中的分支站点 SIP 中继的业务 Server 企业语音。
  
在某些情况下，您可能需要实现选定的分支站点上的分布式的 SIP 中继。 若要确定是否对 SIP 中继所需的分支站点，以及有关支持的拓扑选项用于部署中的分支站点 SIP 中继的详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>示例分支站点 SIP 中继要求分析

如果您决定部署分支站点 SIP 中继，您需要执行的特定于站点的成本分析。 例如，企业已在华盛顿州雷德蒙德，中央站点和分支站点纽约，应执行分析，以确定是否实现从纽约站点 SIP 中继到本地服务提供程序。
  
为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。 您可以为分支站点的 DID 终止在中央站点。 例如，Redmond 中央站点还可以承载纽约分支站点的 DID 号码。 如果实施分布式的 SIP 中继的成本小于这些呼叫的成本，请考虑实现纽约分支站点 SIP 中继。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。 如果您部署分支站点 SIP 中继，您还需要确定您的恢复能力和带宽要求。 如果您的分支站点和中央站点之间的链接弹性并且具有足够带宽，则可以部署 SIP 中继或网关。 不需要部署 Survivable Branch Appliance 分支站点。 如果您的分支站点和中央站点之间的链接不可恢复，部署 Survivable Branch Appliance，或部署 Survivable Branch Server 与网关或 SIP 中继，在分支站点。 
  

