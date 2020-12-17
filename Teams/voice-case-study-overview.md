---
title: Teams 语音 Contoso 案例研究
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
description: 针对多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701220"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams 语音迁移概述

本文介绍一个案例研究，该案例研究介绍了虚构的多语言公司 Contoso 如何为组织实现 Teams 语音解决方案。

Contoso 已部署 Microsoft 365 企业版，并解决了以下主要设计决策和实施详细信息：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从 Skype for Business 升级到 Teams、电话系统和音频会议。  

本文重点介绍 Contoso 如何将其本地用户迁移到 Teams，实现统一的通信、协作和语音。 有关 Contoso 如何使用 Microsoft 云服务加速数字化转型的背景信息，请参阅从 [Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)案例研究概述开始的所有核心文章。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

在核心文章中，可找到以下信息：  

- Contoso 的 IT 基础结构需求
- 网络
- Identity 
- Windows 10 企业版
- Office 365 专业增强版
- 移动设备管理
- 信息保护
- Microsoft 365 企业版安全性摘要
- 顶级机密项目的团队
- 用于高度机密的数字资产的 SharePoint Online 网站

有关规划升级的信息，首先需要开始使用 [Microsoft Teams 升级](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Teams 的 Contoso 业务目标

为了将其本地用户迁移到 Teams，实现统一的通信、协作和语音，Contoso 决定以下业务目标：

- Teams 启用 

  Contoso 的统一通信和协作团队为 Teams 启用了正确的策略，以治理和启用安全的内部和外部协作。 

- Skype for Business 到 Teams 的升级 

  Skype for Business 已广泛部署在 Contoso 中。 由于需要离开旧系统，Contoso 决定将其 Skype for Business 用户升级到 Teams。 有关详细信息，请参阅 [Contoso 案例研究：Teams 升级计划](voice-case-study-migration-plan.md)。

- 电话系统  

  具有企业语音的 Skype for Business 已广泛部署在 Contoso 中。 由于需要离开作为中介服务器的下一跃点的旧系统，Contoso 将其 Skype for Business 企业语音用户迁移到了电话系统。 Contoso 网站使用 Microsoft 呼叫计划、电话系统直接路由或两者的组合。 有关详细信息，请参阅 [Contoso 案例研究：电话系统](voice-case-study-phone-system.md)。

- 基于位置的路由 

  由于办公地点位于电话监管的国家/地区，Contoso 需要重新创建 Skype for Business Location-Based电话系统部署中的网络路由。 有关详细信息，请参阅 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。

- 紧急呼叫 

  实施直接路由时，Contoso 通过批准的第三方设置紧急呼叫。 有关详细信息，请参阅 [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)。

- 音频会议 

  Contoso 将托管在 SIP 中继上的音频会议服务号码设置为 PSTN 提供商。 有关详细信息，请参阅 [Contoso 案例研究：音频会议](voice-case-study-audio-conferencing.md)。 

- 本地媒体优化 

  Contoso 在具有一个直接路由中继到远程站点利用的 Microsoft Phone 系统的位置利用本地媒体优化。 有关详细信息，请参阅["本地媒体优化计划"和](direct-routing-media-optimization.md)"[配置本地媒体优化"。](direct-routing-media-optimization-configure.md)

- 自动助理和呼叫队列

  由于 Covid-19，Contoso 想要在员工远程工作的同时提供接待员支持。 Contoso 使用自动助理和呼叫队列来管理其接待员电话号码的传入呼叫。 有关详细信息，请参阅 [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。  


