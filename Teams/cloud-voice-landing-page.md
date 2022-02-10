---
title: 在语音服务中规划Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 详细了解云Microsoft Teams功能和为组织做出部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f6d857e11545df9c338dd2c75b089d8bef0247e
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518794"
---
# <a name="plan-your-teams-voice-solution"></a>规划Teams语音解决方案

本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。 确定后，本文提供内容路线图，实现所选解决方案。

你可能希望使用调用计划&mdash;电话系统最简单的解决方案。 此选项是 Microsoft 的全云解决方案，可提供专用分支 Exchange (PBX) 功能以及拨打公用电话交换网 (PSTN) ，如下图所示。 借助此解决方案，Microsoft 是你的 PSTN 运营商。

![图 1 电话系统呼叫计划。](media/voice-solutions-simple.png)

如果你对以下内容回答"是"，电话系统"呼叫计划"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

但是，情况可能更复杂。 例如，你可能在呼叫计划不可用的位置设有办公室。 或者，可能需要一个支持复杂、跨区域部署、对不同地理位置有不同的要求的组合解决方案。 Microsoft 支持解决方案的组合：

- 电话系统套餐
- 电话系统运营商与自己的 PSTN 运营商连接
- 电话系统直接路由与自己的 PSTN 运营商联系
- 结合使用解决方案，将 电话系统 与呼叫电话系统、电话系统运算符连接和/或电话系统直接路由结合使用

>[!NOTE]
>如果你是一家中小型企业， (300) ，Microsoft 现在电话系统国内呼叫计划。 有关详细信息，请参阅[电话系统](/microsoftteams/business-voice/whats-business-voice)中型企业的指南，帮助你规划、设置和管理语音解决方案。

## <a name="what-do-you-need-to-read"></a>需要阅读哪些信息？

**全部必需。** 本文中的某些部分适用于所有组织。 例如，每个人都应该阅读有关电话系统并了解用于连接到 PSTN 公用电话交换网 (的选项) 。


| 全部必需 | 说明 |
| :------------|:-------|
| [**电话系统**](#phone-system) | Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术Microsoft 365云Microsoft Teams。 |
| [**PSTN 公用电话交换 (PSTN) 连接选项**](#public-switched-telephone-network-connectivity-options) | 选择 Microsoft 作为电话运营商，或者使用接线员或直接Microsoft Teams将你自己的电话运营商连接电话运营商。 PSTN 连接电话系统结合使用，使用户能够拨打全球电话。|

**根据你的要求。** 本文和相关文章中的一些部分与现有的部署和要求相关。 例如，Location-Based不允许绕过收费站的地理位置中的直接路由客户需要直接路由。

请考虑可能需要以下哪些其他配置：

![图 2 显示了其他语音组件，电话 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| 根据要求 | 说明 |
| :------------|:-------|
| [**电话数字管理**](pstn-connectivity.md#phone-number-management) | 如何获取和管理电话号码因 PSTN 连接选项不同而不同。 如果需要获取电话号码、转移现有号码、获取服务号码等，请阅读本部分。 |
| [**呼叫路由和拨号计划**](pstn-connectivity.md#call-routing-and-dial-plans) | 如何配置和管理将拨入电话号码转换为备用格式的拨号计划 (通常使用 E.164) 进行呼叫授权和呼叫路由。 如果需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读本部分。|
| [**紧急呼叫**](pstn-connectivity.md#emergency-calling) | 如何管理和配置紧急呼叫因 PSTN 连接选项的不同而不同。 如果需要了解如何为组织管理紧急呼叫，请阅读本部分。 |
| [**用于直接路由的基于位置的路由**](pstn-connectivity.md#location-based-routing-for-direct-routing) |如何使用 LBR Location-Based路由 (，) 基于用户的地理位置Microsoft Teams免收费。 如果组织在不允许绕过收费站的位置使用直接路由，请阅读本部分。
| [**云语音功能的网络拓扑**](pstn-connectivity.md#network-topology-for-voice-features) | 如果组织为直接Location-Based或动态紧急呼叫Location-Based LBR (路由或 LBR) ，则必须在 Microsoft Teams 中配置这些功能的网络设置。 如果为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。 |
| [**迁移现有语音解决方案**](#migrate-your-existing-voice-solution-to-teams) | 将语音解决方案迁移到云时需考虑Teams。  如果要从现有语音解决方案迁移到 Teams。 

> [!Important]
> 本文重点介绍语音解决方案与 Microsoft Teams。 由于 Skype for Business Online 于 2021 年 7 月 31 日停用，因此不再支持本地环境之间的 PSTN&mdash; 连接（通过 Skype for Business Server 或 Cloud Connector Edition&mdash; 和 Skype for Business Online）。 本文介绍Teams语音解决方案，以及如何在必要时使用接线员或直接路由Teams本地连接网络。


## <a name="phone-system"></a>电话系统

电话系统是 Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术，Microsoft 365云Microsoft Teams。

电话系统适用于Teams客户端和认证的设备。 电话系统将现有 PBX 系统替换为一组直接从 Microsoft 365。 

组织中用户之间的呼叫（无论地理区域如何）在内部电话系统。 这些内部呼叫永远不会转到 PSTN (电话交换) ，因此贵公司可避免产生长途费用。

本文介绍以下电话系统特性和功能，以及需要考虑的部署决策：

- [自动助理和呼叫队列](#auto-attendants-and-call-queues)
- [云语音邮件](#cloud-voicemail)
- [调用标识](#calling-identity)

![图 3 电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识。](media/phone-system-contains.png)

有关所有电话系统功能以及如何设置电话系统，请参阅以下文章：

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)
- [在组织中设置电话系统](setting-up-your-phone-system.md)<br>
  介绍如何购买和分配电话系统、管理电话号码以及设置免费号码的通信信用额度。 

有关管理受支持设备的信息，请参阅[在](devices/device-management.md) Microsoft Teams 和 Teams [中管理设备](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。


### <a name="auto-attendants-and-call-queues"></a>自动助理和呼叫队列

自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。 呼叫队列正在等待呼叫者的区域。 自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。

有关自动助理和呼叫队列的信息，请参阅以下文章：

- [规划Teams自动助理和呼叫队列](plan-auto-attendant-call-queue.md)
- [设置自动助理](create-a-phone-system-auto-attendant.md)
- [创建呼叫队列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)<br>
  介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。

### <a name="cloud-voicemail"></a>云语音邮件

云语音邮件 Azure 语音邮件服务支持将语音邮件Exchange邮箱。 它不支持第三方电子邮件系统。 

云语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。

云语音邮件自动为用户设置Teams预配。  

有关云语音邮件及其配置的信息，请参阅以下文章：

- [设置云语音邮件](set-up-phone-system-voicemail.md)
- [在组织中设置语音邮件策略](manage-voicemail-policies.md)


### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫使用分配的电话号码作为呼叫 (呼叫方 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 有关配置来电显示或更改或阻止来电显示的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用电话交换网络连接选项

电话系统为组织提供完整的 PBX 功能。 但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。 若要电话系统 PSTN，可以选择以下选项之一：

- [**电话系统套餐。**](pstn-connectivity.md#phone-system-with-calling-plan) 以 Microsoft 作为 PSTN 运营商的全云解决方案。

- [**电话系统运营商与自己的 PSTN 运营商**](operator-connect-plan.md)连接。 使用接线连接，如果现有运营商是参与 Microsoft 接线员连接计划，他们可以管理将 PSTN 呼叫引入 Teams。 有关操作员服务权益和要求的信息，连接[计划操作员连接](operator-connect-plan.md)。

- [**电话系统直接**](pstn-connectivity.md#phone-system-with-direct-routing)路由将本地环境连接到本地环境，与自己的 PSTN 运营商Teams。

可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移。 稍后将阅读有关迁移的更多信息。

无论电话系统 PSTN 连接选项，大多数服务功能都是相同的。 但是，在功能上存在一些差异，这会影响你配置某些电话系统，例如呼叫路由和紧急呼叫。 有关 PSTN 连接选项和配置注意事项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。


## <a name="migrate-your-existing-voice-solution-to-teams"></a>将现有语音解决方案迁移到Teams

> [!NOTE]
> 有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 总体计划的一部分的指导，请参阅从 Skype for Business 本地升级到 [Teams Skype for Business 的 PSTN 注意事项](upgrade-to-teams-on-prem-pstn-considerations.md)。

对于要升级到 Teams，最终目标是将所有用户移动到 TeamsOnly 模式。 仅在电话系统 TeamsOnly 模式时，才支持使用 电话系统。 如果需要有关升级到 Teams 的基本信息，请从此处开始：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [关于升级框架](upgrade-framework.md)
- [适用于 IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md)

迁移语音解决方案时，迁移到 TeamsOnly 模式时，有四种可能的呼叫方案：

- [**具有 Microsoft 呼叫Skype for Business Online 中的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 呼叫计划。

- **[使用 Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 的用户，通过本地或云连接器Skype for Business本地语音功能。 用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。

- **[在本地使用 Skype for Business 的用户企业语音](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，该用户将移动到联机并保留本地 PSTN 连接**。 将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。 

- **[在本地使用 Skype for Business 的用户企业语音](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，该用户将移动到联机状态，使用 Microsoft 呼叫计划**。  将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动与 A) 将该用户的电话号码的端口移动到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码。

若要详细了解如何针对每种方案实现语音迁移，请参阅以下文章：

- [升级到网络时 PSTN Teams IT 管理员的注意事项](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 语音迁移案例研究](voice-case-study-overview.md)<br>
  案例研究介绍虚构的多语言公司 Contoso 如何为Teams实现语音解决方案。 它包含以下文章：

  - [Teams升级计划](voice-case-study-migration-plan.md)
  - [电话系统 PSTN 连接选项](voice-case-study-phone-system.md)
  - [基于位置的路由实现](voice-case-study-location-based-routing.md)
  - [紧急呼叫](voice-case-study-emergency-calling.md)
  - [自动助理和呼叫队列](voice-case-study-call-queues.md)
  - [音频会议](voice-case-study-audio-conferencing.md)
