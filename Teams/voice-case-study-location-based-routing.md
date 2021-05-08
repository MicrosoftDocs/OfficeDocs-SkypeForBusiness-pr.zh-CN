---
title: Teams Contoso 案例研究
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
description: Teams多语言公司语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785952"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 案例研究：Location-Based路由

Location-Based LBR (路由) 是一项功能，它基于发出或接收呼叫时的策略和用户的物理位置限制通行费绕过。  

## <a name="overview"></a>概述

Contoso 在一个国家/地区有两个办公室，其中绕过公共电话交换网 (PSTN 提供商) 降低远程呼叫成本非法。 主办公室具有由主办公室和第二个办公室使用的 Internet 连接。 每个办公室都有自己的会话边界控制器 (SBC) PSTN 运营商。  
 
在此国家/地区，Contoso 已针对其用户部署Skype for Business LBR。 若要确定如何为直接路由配置 LBR Teams，Contoso 请阅读规划Location-Based[直接路由的路由](location-based-routing-plan.md)。 Contoso 确定 Teams 和 Skype for Business 在何时可以拨打呼叫、何时可以接收呼叫、PSTN 呼叫何时可以转接到 Teams 用户以及何时可以将另一个 Teams 用户转接到 PSTN 呼叫上遵循相同的方案。  

对于Skype for Business，LBR 配置了会话边界控制器 (SBC) 连接到 PSTN 运营商的 SIP 中继。 对于此 SBC，Contoso 查看[](direct-routing-border-controllers.md)了经过认证的 SBC 列表，确定部署的 SBC 已通过直接路由认证，但没有通过媒体旁路认证。 若要支持 LBR，需要将直接路由配置为本地 SBC，需要有本地 Internet 出口，并且需要为媒体旁路配置 SBC。 Contoso 根据此信息决定以下事项：

- 若要延迟启用 Teams LBR，直到现有 SBC 通过媒体旁路认证。   

- Contoso 决定使用主站点 SBC 作为直接路由来Office 365。  主站点 SBC 将是远程站点的代理 SBC。  

- Contoso 使用一位印度的第三方顾问协助国内电话公司进行 LBR 配置认证。  

- 为了支持从办公室外工作以拨打 PSTN 呼叫的用户，公司向员工提供了公司颁发的移动电话。 

下图显示了在部署之前和之后，对于有电话法规要求使用路由Location-Based国家/地区：

**原始部署**

![显示状态前的图表](media/voice-case-study-5.png)

**使用直接路由进行部署**

![显示状态前的图表](media/voice-case-study-6.png)


## <a name="configuration"></a>配置： 

为了在云中配置网络Teams，Contoso 按照管理云语音功能的网络拓扑[中的说明进行操作](manage-your-network-topology.md)。 Contoso 已完成以下步骤来配置Location-Based路由： 

- 定义网络区域 - 定义了一个网络区域。 

- 定义网络站点 - 定义了两个网络站点。 该区域中每个办公室位置都有一个网站。

- 定义网络子网 - 办公室位置内的每个楼层都有自己的有线和无线网络子网。 此配置导致 Contoso 有 20 个子网。 

- 定义受信任的 IP 地址 - SBC 面向外部的 IP 地址已添加到受信任的 IP 地址。  

