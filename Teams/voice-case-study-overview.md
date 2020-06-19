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
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785955"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：团队语音迁移概述

本文将介绍一个案例研究，介绍如何为其组织实施团队语音解决方案。

Contoso 已部署 Microsoft 365 企业版并解决了主要的设计决策和实现详细信息：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从 Skype for Business 升级到团队、电话系统和音频会议。  

本文重点介绍 Contoso 如何将他们的本地用户迁移到团队进行统一通信、协作和语音。 有关 Contoso 如何使用 Microsoft 的云服务加速其数字转换的背景信息，请参阅从[Contoso 案例研究概述](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)开始的所有核心文章。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

在核心文章中，你将找到有关以下内容的信息：  

- Contoso 的 IT 基础结构需求
- 网络
- Identity 
- Windows 10 企业版
- Office 365 Pro Plus
- 移动设备管理
- 信息保护
- Microsoft 365 企业版安全摘要
- 首要项目的团队
- 高机密数字资产的 SharePoint Online 网站

有关规划升级的详细信息，您将希望从[Microsoft 团队升级](upgrade-start-here.md)入门开始。

## <a name="contoso-business-goals-for-teams"></a>Contoso 企业团队的目标

要将他们的本地用户迁移到团队进行统一通信、协作和语音，Contoso 确定以下业务目标：

- 团队支持 

  Contoso 的统一通信和协作团队使用正确的策略管理和启用安全的内部和外部协作。 

- Skype for Business 到 Teams 的升级 

  Skype for business 已在 Contoso 中广泛部署。 由于需要移出旧式系统，Contoso 决定将其 Skype for Business 用户升级到团队。 有关详细信息，请参阅[Contoso 个案研究：团队升级计划](voice-case-study-migration-plan.md)。

- 电话系统  

  企业语音版 Skype for Business 在 Contoso 中广泛部署。 如果需要将下一跃点的旧系统迁移到其中介服务器的下一跃点，Contoso 将其 Skype for Business 企业语音用户迁移到电话系统。 Contoso 站点使用的是 Microsoft 通话计划、电话系统直接路由或两者的组合。 有关详细信息，请参阅[Contoso 个案研究：电话系统](voice-case-study-phone-system.md)。

- 基于位置的路由 

  在电话管控国家/地区的 office 位置，Contoso 需要在其手机系统部署中重新创建 Skype for Business 中提供的基于位置的路线。 有关详细信息，请参阅[Contoso 个案研究：基于位置的路由](voice-case-study-location-based-routing.md)。

- 紧急呼叫 

  在直接路由实施的位置，Contoso 利用经认可的第三方设置紧急电话。 有关详细信息，请参阅[Contoso 个案研究：紧急电话](voice-case-study-emergency-calling.md)。

- 音频会议 

  Contoso 将其 SIP 主干上托管的音频会议服务号码设置为其 PSTN 提供商。 有关详细信息，请参阅[Contoso 个案研究：音频会议](voice-case-study-audio-conferencing.md)。 

- 本地媒体优化 

  Contoso 利用本地媒体优化功能，这些位置中的位置与远程站点使用的 Microsoft Phone 系统之间有一个直接路由主干。 有关详细信息，请参阅[规划本地媒体优化](direct-routing-media-optimization.md)和[配置本地媒体优化](direct-routing-media-optimization-configure.md)。

- 自动助理和呼叫队列

  由于 Covid-19，Contoso 希望在员工在远程工作的同时提供接待员支持。 Contoso 使用 "自动助理" 和 "呼叫队列" 来管理传入呼叫的接待员电话号码。 有关详细信息，请参阅[Contoso 个案研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。  


