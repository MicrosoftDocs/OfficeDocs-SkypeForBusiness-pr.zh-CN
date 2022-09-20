---
title: Teams 语音 Contoso 案例研究概述
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司 Teams 语音案例研究：语音迁移概述
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808623"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams 语音迁移概述

本文介绍一个案例研究，说明虚构的多国公司 Contoso 如何为其组织实现 Teams 语音解决方案。

Contoso 已部署Microsoft 365 企业版并解决了以下主要设计决策和实施详细信息：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从Skype for Business升级 到 Teams、电话系统和音频会议。  

本文重点介绍 Contoso 如何将其本地用户迁移到 Teams 以实现统一的通信、协作和语音。 有关 Contoso 如何使用 Microsoft 云服务加速其数字化转型的背景信息，请参阅 [从 Contoso 案例研究开始](/microsoft-365/enterprise/contoso-case-study)的所有核心文章概述。

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

在核心文章中，你将找到以下信息：  

- Contoso 的 IT 基础结构需求
- 网络
- Identity 
- Windows 10 企业版
- Office 365 Pro Plus
- 移动设备管理
- 信息保护
- Microsoft 365 企业版安全性摘要
- 一个绝密项目的团队
- 用于高度机密的数字资产的 SharePoint Online 网站

有关计划升级的信息，需要从 [Microsoft Teams 升级入](upgrade-start-here.md)门开始。

## <a name="contoso-business-goals-for-teams"></a>Teams 的 Contoso 业务目标

为了将其本地用户迁移到 Teams 以实现统一的通信、协作和语音，Contoso 决定了以下业务目标：

- Teams 启用 

  Contoso 的统一通信和协作团队为 Teams 启用了正确的策略来治理和启用安全的内部和外部协作。 

- Skype for Business 到 Teams 的升级 

  Skype for Business广泛部署在 Contoso 中。 由于需要离开旧系统，Contoso 决定将其Skype for Business用户升级到 Teams。 有关详细信息，请参阅 [Contoso 案例研究：Teams 升级计划](voice-case-study-migration-plan.md)。

- 电话系统  

  具有企业语音的Skype for Business广泛部署在 Contoso 中。 由于需要从作为中介服务器下一跃点的旧系统移开，Contoso 将其Skype for Business企业语音用户迁移到电话系统。 Contoso 站点使用 Microsoft 呼叫计划、电话系统直接路由或两者的组合。 有关详细信息，请参阅 [Contoso 案例研究：电话系统](voice-case-study-phone-system.md)。

- 基于位置的路由 

  Contoso 在电话管理的国家/地区拥有办公地点，因此需要重新创建其电话系统部署中Skype for Business中存在的Location-Based路由。 有关详细信息，请参阅 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。

- 紧急呼叫 

  在实施直接路由的地方，Contoso 与经批准的第三方建立紧急呼叫。 有关详细信息，请参阅 [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)。

- 音频会议 

  Contoso 将托管在其 SIP 中继上的音频会议服务号码设置为其 PSTN 提供程序。 有关详细信息，请参阅 [Contoso 案例研究：音频会议](voice-case-study-audio-conferencing.md)。 

- 本地媒体优化 

  Contoso 利用本地媒体优化的位置，其中有一个直接路由中继到 Microsoft Phone 系统，由远程站点利用。 有关详细信息，请参阅 [“本地媒体优化计划](direct-routing-media-optimization.md) ”和 [“配置本地媒体优化](direct-routing-media-optimization-configure.md)计划”。

- 自动助理和呼叫队列

  由于 Covid-19，Contoso 希望在员工远程工作时提供接待员支持。 Contoso 使用自动助理和呼叫队列来管理接待员电话号码的传入呼叫。 有关详细信息，请参阅 [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。
