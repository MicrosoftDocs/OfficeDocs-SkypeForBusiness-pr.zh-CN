---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785952"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 个案研究：基于位置的路由

基于位置的路由（LBR）是一种功能，可在发出或接收呼叫时限制基于策略和用户的物理位置的收费旁路。  

## <a name="overview"></a>概述

Contoso 在一个国家/地区有两个办事处，在这种情况下，不能绕过公共交换电话网络（PSTN）提供程序来减少长途通话成本。 主 office 具有由主办公室和第二个 office 使用的 Internet 连接。 每个 office 都有自己的会话边界控制器（SBC）连接到 PSTN 运营商。  
 
在此国家/地区，Contoso 已针对其 Skype for Business 部署配置了 LBR。 若要确定如何为团队配置 LBR，请按 Contoso 读取[计划位置直接路由选择](location-based-routing-plan.md)。 Contoso 确定团队和 Skype for business 在可以进行呼叫时，如果可以接收到当 PSTN 呼叫可以转到团队用户，并且可以将其他团队用户转移到 PSTN 呼叫时，请遵循相同的方案。  

对于 Skype for Business，LBR 已配置有会话边界控制器（SBC） SIP Trunk 连接到 PSTN 运营商。 对于此 SBC，Contoso 检查了已[认证的 SBCs 列表](direct-routing-border-controllers.md)，并确定 SBC 部署的 SBC 已验证为直接路由，但未针对媒体旁路进行验证。 为了支持 LBR，直接路由需要配置到 SBC 现场，需要有本地 Internet 出口，并且需要为媒体旁路配置 SBC。 根据此信息，Contoso 确定以下事项：

- 若要延迟团队 LBR 的启用，直到现有 SBC 验证了媒体绕过。   

- Contoso 决定使用主站点 SBC 直接前往 Office 365。  主站点 SBC 将是远程站点的代理 SBC。  

- Contoso 使用基于印度的第三方顾问来协助 LBR 配置与国家/地区的电话公司的认证。  

- 为了支持从办公室外部工作以进行 PSTN 呼叫，公司颁发的移动电话已提供给其员工。 

下图显示了具有需要基于位置路由的电话服务的国家/地区的部署之前和之后的情况：

**原始部署**

![状态之前显示的图表](media/voice-case-study-5.png)

**直接路由的部署**

![状态之前显示的图表](media/voice-case-study-6.png)


## <a name="configuration"></a>配置 

若要配置团队中的网络组件，Contoso 按照[管理云语音功能的网络拓扑](manage-your-network-topology.md)中的说明进行操作。 Contoso 已完成以下步骤来配置基于位置的路由： 

- 定义网络区域-已定义一个网络区域。 

- 定义网络站点-定义了两个网络站点。 区域中每个办公位置的一个网站。

- 定义网络子网-办公室位置内的每个楼层都有其自己的用于有线和无线网络的子网。 此配置为 Contoso 产生了20个子网。 

- 定义受信任的 IP 地址-将 SBC 的面向外部的 IP 地址添加到受信任的 IP 地址。  

