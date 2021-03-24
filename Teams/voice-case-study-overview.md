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
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097488"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams 语音迁移概述

本文介绍一个案例研究，该案例研究介绍了虚构的多语言公司 Contoso 如何为组织实现 Teams 语音解决方案。

Contoso 部署了 Microsoft 365 企业版，并针对以下事项解决了主要设计决策和实施细节：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从 Skype for Business 升级到 Teams、电话系统和音频会议。  

本文重点介绍 Contoso 如何将其本地用户迁移到 Teams，实现统一的通信、协作和语音。 有关 Contoso 如何使用 Microsoft 云服务加速数字化转型的背景信息，请参阅从 [Contoso](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)案例研究概述 开始的所有核心文章。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

在核心文章中，可找到以下信息：  

- Contoso 的 IT 基础结构需求
- 网络
- Identity 
- Windows 10 企业版
- Office 365 专业增强版
- 移动设备管理
- 信息保护
- Microsoft 365 企业安全性摘要
- 顶级机密项目的团队
- 用于高度机密数字资产的 SharePoint Online 网站

有关规划升级的信息，需要从 Microsoft Teams 升级入门 [开始](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Teams 的 Contoso 业务目标

为了将其本地用户迁移到 Teams，实现统一的通信、协作和语音，Contoso 决定实现以下业务目标：

- Teams 启用 

  Contoso 的统一通信和协作团队为 Teams 启用了正确的策略，用于治理和实现安全的内部和外部协作。 

- Skype for Business 到 Teams 的升级 

  Skype for Business 已广泛部署在 Contoso 中。 由于需要关闭旧系统，Contoso 决定将其 Skype for Business 用户升级到 Teams。 有关详细信息，请参阅 [Contoso 案例研究：Teams 升级计划](voice-case-study-migration-plan.md)。

- 电话系统  

  具有企业语音的 Skype for Business 已广泛部署在 Contoso 中。 由于需要将旧系统（作为中介服务器的下一跃点）移走，Contoso 将其 Skype for Business 企业语音用户迁移到了电话系统。 Contoso 站点使用 Microsoft 呼叫计划、电话系统直接路由或两者的组合。 有关详细信息，请参阅 [Contoso 案例研究：电话系统](voice-case-study-phone-system.md)。

- 基于位置的路由 

  由于办公地点位于电话管制的国家/地区，Contoso 需要重新创建 Skype for Business Location-Based电话系统部署中的网络路由。 有关详细信息，请参阅 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。

- 紧急呼叫 

  实施直接路由时，Contoso 与批准的第三方建立紧急呼叫。 有关详细信息，请参阅 [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)。

- 音频会议 

  Contoso 设置在 PSTN 提供商的 SIP 中继上托管的音频会议服务号码。 有关详细信息，请参阅 [Contoso 案例研究：音频会议](voice-case-study-audio-conferencing.md)。 

- 本地媒体优化 

  Contoso 在有一个直接路由中继到远程站点利用的 Microsoft Phone System 的位置利用了本地媒体优化。 有关详细信息，请参阅[规划本地媒体优化和](direct-routing-media-optimization.md)[配置本地媒体优化](direct-routing-media-optimization-configure.md)。

- 自动助理和呼叫队列

  由于 Covid-19，Contoso 想要在员工远程工作的同时提供接待员支持。 Contoso 使用自动助理和呼叫队列来管理接收者电话号码的传入呼叫。 有关详细信息，请参阅 [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。