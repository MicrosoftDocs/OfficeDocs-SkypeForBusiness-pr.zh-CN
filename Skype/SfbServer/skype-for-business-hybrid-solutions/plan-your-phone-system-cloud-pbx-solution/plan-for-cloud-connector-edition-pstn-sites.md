---
title: 云连接器版本 PSTN 站点规划
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 阅读本主题，了解如何规划你的云连接器版本 PSTN 网站，以确保有效且经济高效的呼叫路由。
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358798"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>云连接器版本 PSTN 站点规划

> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。
 
阅读本主题，了解如何规划你的云连接器版本 PSTN 网站，以确保有效且经济高效的呼叫路由。
  
本主题介绍了你需要了解的云连接器版本和呼叫路由，以便你可以规划你的云连接器 PSTN 站点。 PSTN 站点是云连接器设备的组合，在同一位置部署，并与通用 PSTN 网关连接。 本主题重点介绍如何设置你的云连接器网站拓扑，以确保云连接器网站能够以尽可能经济高效且有效的方式为分配到网站的所有用户处理入站和出站路由。 若要详细了解云连接器和 PSTN 站点的优势，请务必阅读 Plan for [Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)。 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>云连接器 PSTN 站点和呼叫路由

云连接器 PSTN 站点是为阻止不必要的远距离和国家间关税而创建的拓扑结构，用于确保出站紧急呼叫路由到相应的中继。 为确保经济高效且高效地路由呼叫（包括紧急服务呼叫），必须仔细规划 PSTN 站点以及如何向每个站点分配用户。 
  
作为云连接器规划的一部分，请务必咨询你的运营商，了解你的办公室和用户所在的位置，以及 PSTN 中继从运营商处终止的位置。 您需要与运营商合作，以确定如何路由紧急呼叫，然后使用该信息来定义云连接器 PSTN 站点并将用户分配给相应的站点。 例如，应确保在将 PSTN 站点扩展到的数据中心处终止的中继配置为为分配给该站点中用户的所有号码处理入站和出站路由。 
  
每个云连接器设备都可以连接到多个 IP 网关、IP Pbx 或会话边界控制器 (SBCs) 。 由于网关和 Pbx 连接到电讯中继 (PRI 或 SIP 中继) ，云连接器设备在逻辑上连接到 PSTN 中继以进行入站和出站呼叫。 通过云连接器和本地 PSTN 连接，你可以从你的本地运营商获取中继和关联的电话号码。 如果你的企业是大型企业，则可能会有多个运营商，尤其是当你的公司跨越多个城市、省市/自治区或国家/地区时。 由于你的运营商拥有电话号码，因此运营商负责处理紧急呼叫。
  
Skype for Business Online 在一个站点中同等地处理所有云连接器设备，并将以循环方式将出站呼叫路由到同一站点中的云连接器设备。 站点中的每个云连接器都与同一组 PSTN 中继进行交叉连接 (完全网状) 。 由于每个用户都与云连接器 PSTN 站点相关联，因此来自该用户的任何出站呼叫 (正常或紧急) 都将分配给与该用户关联的 PSTN 站点中的某个云连接器设备。 
  
云连接器执行静态呼叫路由到其连接的 IP 网关、IP-Pbx、SBCs 或直接 PSTN 中继。 云连接器还不能基于目标 (为最低开销路由) 或基于源 (静态或动态紧急呼叫) 的中继进行动态路由。 因为呼叫只能来自与号码关联的中继，所以入站呼叫不是问题。 但是，出站呼叫可以转到站点中的任何云连接器设备 (和扩展连接到该云连接器设备的 PSTN 中继，) 这可能会导致不需要的长途电话呼叫。 此外，如果在具有不同区号或运营商的数据中心跨云连接器 PSTN 站点进行扩展，紧急呼叫将不会经历。
  
## <a name="an-example"></a>示例

下面的示例展示了如何将中继分组到 PSTN 站点，以及如何将用户分配到站点。 对于 Contoso 公司，假定以下内容：
  
- 有四个用户： 
    
  - 美国华盛顿州 Redmond (中的用户 A) 
    
  - 贝尔维尤 WA 中的用户 B (美国) 
    
  - 桑塔利亚 WA 中的用户 C (美国) 
    
  - 美国上海或 (的用户 D) 
    
- 运营商 A 在以下内容中提供电话号码和中继：
    
  - Redmond (区号 425) 
    
  - 贝尔维尤 (区号 425) 
    
  - 桑塔利亚 (区号 360) 
    
- 运营商 B 在以下内容中提供电话号码和中继：
    
  -  上海 (区号 503) 
    
由于 (Redmond 中的用户 A) 和贝尔维尤中的用户 B (数据中心 B) 在 suburbs 中彼此相邻，并且在相同的区号 (425) 中，因此，电信公司 A 应能够在贝尔维尤中的中继上的用户 A 处进行紧急呼叫。 
  
因此，用户 A 和 B 以及贝尔维尤和 Redmond 的云连接器中继可能位于相同的云连接器 PSTN 站点中，如下图中所示。 来自一个办公室中用户的紧急呼叫可以路由到另一个办公室中的中继。 不过，您应与运营商核实，这样做将正常运行。
  
![如何设置 PSTN 站点](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
同时考虑以下示例：
  
- 桑塔利亚中的用户 C （其号码由运营商 A 提供）是两个小时的驱动器，在不同区号 (360) ，从其他运营商的贝尔维尤和 Redmond 425 区域代码中的用户。 
    
    因此，即使呼叫来自运营商 A，桑塔利亚区号360中的电信公司的呼叫路由软件也可能会拒绝来自贝尔维尤区域代码425中的用户 B 的传入紧急呼叫。 在这种情况下，运营商确认桑塔利亚 PSTN 站点中的云连接器及其关联的中继可以处理跨远距离和区号的呼叫，这一点非常重要。
    
- 中的用户 D 使用由运营商 B 提供的号码和中继，因此，运营商 B 对运营商 B 所拥有的电话号码的紧急呼叫的可能性极小。因此，中继中的用户 D 和云连接器设备以及关联的必须位于不同的 PSTN 站点中。
    

