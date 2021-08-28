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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 阅读本主题，了解如何规划云连接器版本 PSTN 站点以确保有效且经济高效的呼叫路由。
ms.openlocfilehash: 54f8ec9f89c6a3ef88b5ac8e70e9eebfd2968d2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616328"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>云连接器版本 PSTN 站点规划

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)
 
阅读本主题，了解如何规划云连接器版本 PSTN 站点以确保有效且经济高效的呼叫路由。
  
本主题介绍你需要了解的关于云连接器版本和呼叫路由的内容，以便你可以规划云连接器 PSTN 站点。 PSTN 站点是云连接器设备的组合，部署在同一位置，并连接了常见的 PSTN 网关。 本主题重点介绍如何设置云连接器站点拓扑，以确保云连接器站点可以尽可能经济高效的方式为分配到站点的所有用户处理入站和出站路由。 有关云连接器和 PSTN 站点优势的信息，请务必阅读 Plan for [Skype for Business 云连接器版本](plan-skype-for-business-cloud-connector-edition.md)。 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>云连接器 PSTN 站点和呼叫路由

云连接器 PSTN 站点是一种拓扑结构，用于防止不必要的长途和国家/地区间通信，并确保出站紧急呼叫路由到相应的中继。 为了确保呼叫（包括紧急服务的呼叫）的成本高效路由，您必须仔细规划 PSTN 站点以及如何将用户分配给每个站点。 
  
作为规划云连接器的一部分，有必要与运营商就办公室和用户所在的位置以及 PSTN 中继从运营商处终止的位置交谈。 你需要与运营商合作以确定如何路由紧急呼叫，然后使用该信息定义云连接器 PSTN 站点并将用户分配给相应的站点。 例如，应确保终止于 PSTN 站点拉伸的数据中心的中继配置为处理分配给该站点上用户的所有号码的入站和出站路由。 
  
每台云连接器设备都可以连接到 SDC 或 SDC (多个 IP 网关、IP PBX 或) 。 由于网关和 PBX 连接到 telco 中继 (PRI 或 SIP 中继) ，因此云连接器设备在逻辑上连接到 PSTN 中继进行入站和出站呼叫。 通过云连接器和本地 PSTN 连接，你可以从本地运营商获取中继和相关电话号码。 如果你的企业是一家大型企业，你可能拥有多个运营商，尤其是在你的企业跨越多个城市、州或国家/地区时。 由于运营商拥有电话号码，因此运营商负责处理紧急呼叫。
  
Skype for BusinessOnline 同等对待站点内的所有云连接器设备，并旋转将出站呼叫路由到同一站点中的云连接器设备。 站点中的每个云连接器都交叉连接到同一组 PSTN 中继 (完全网格化) 。 由于每个用户都与云连接器 PSTN 站点关联，因此来自该用户 (正常或紧急) 的任何出站呼叫都将分配给与该用户关联的 PSTN 站点中的一个云连接器设备。 
  
云连接器将静态呼叫路由到其连接的 IP 网关、IP-PBX、SDC 或直接 PSTN 中继。 云连接器尚不能够基于目标 (或基于源静态或动态紧急呼叫) 目标 (路由到中继) 。 入站呼叫不是问题，因为呼叫只能来自与号码关联的中继。 但是，出站呼叫可以转到站点 (并且通过扩展连接到该云连接器设备的 PSTN 中继) 这可能会导致不需要的长途呼叫。 此外，如果云连接器 PSTN 站点扩展到具有不同区号或运营商的数据中心，紧急呼叫将不会通过。
  
## <a name="an-example"></a>示例

以下示例演示如何将中继分组到 PSTN 站点以及如何向这些站点分配用户。 对于 Contoso 公司，假定以下内容：
  
- 有四个用户： 
    
  - 美国雷德蒙德州 (A) 
    
  - 美国雷德维尤州 (B) 
    
  - 华盛顿州中部的用户 C (USA) 
    
  - 波特兰或美国波特兰 (D) 
    
- 运营商 A 在：
    
  - 雷德蒙德 (区号 425) 
    
  - Bellevue (区号 425) 
    
  - Centralia (区号 360) 
    
- 运营商 B 在：
    
  -  波特兰 (区号 503) 
    
由于雷德蒙德 (数据中心 A 的用户 A) 和 Bellevue (数据中心 B) 中的用户 B 彼此并位于同一区号 (425) 中，运营商 A 应该能够在 Bellevue 的中继上接受来自 Redmond 用户 A 的紧急呼叫。 
  
因此，用户 A 和 B 以及 Bellevue 和 Redmond 的云连接器中继可能在同一云连接器 PSTN 站点中，如下图所示。 可以将来自一个办公室用户的紧急呼叫路由到另一个办公室的中继。 但是，你应该与运营商核实这是否正常工作。
  
![如何设置 PSTN 站点](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
还请考虑以下示例：
  
- Centralia 的用户 C（其号码由运营商 A 提供）需要两个小时的时间，并且位于其他运营商 A 用户（位于 Bellevue 和 Redmond 425 区号中）的 360) 区号不同的区号 (360) 中。 
    
    因此，即使呼叫来自运营商 A，Centralia 区号 360 中的运营商的呼叫路由软件也可能拒绝来自 Bellevue 区号 425 中的用户 B 的传入紧急呼叫。 在这种情况下，运营商确认 Centralia PSTN 站点中的云连接器及其关联中继可以处理跨距离和区号的呼叫至关重要。
    
- 波特兰的用户 D 使用运营商 B 提供的号码和中继，因此运营商 B 从运营商 A 拥有的电话号码接听紧急呼叫的可能性很小。因此，波特兰的用户 D 和云连接器设备以及关联的中继必须位于不同的 PSTN 站点中。
