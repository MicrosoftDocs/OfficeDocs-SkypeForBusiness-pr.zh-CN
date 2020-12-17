---
title: 在 Microsoft Teams 中规划语音解决方案
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
description: 了解有关 Microsoft Teams 云语音功能以及你将为组织做出部署决策的信息。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16a2aea0d367c720cf36c8010670a34472ab43a
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701330"
---
# <a name="plan-your-teams-voice-solution"></a>规划 Teams 语音解决方案 

本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。 确定后，本文提供了一个路线图用于实现所选解决方案的内容。

> [!NOTE]
> 有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 总体计划的一部分的指导，请参阅从本地 Skype for Business 升级到 Teams 的 [PSTN 注意事项](upgrade-to-Teams-on-prem-pstn-considerations.md)。

你可能希望使用具有呼叫计划 &mdash; 的最简单解决方案电话系统。 这是 Microsoft 的全云解决方案，可提供 Private Branch Exchange (PBX) 功能，并呼叫公用电话交换网 (PSTN) ，如下图所示。 借助此解决方案，Microsoft 是你的 PSTN 运营商。

![图 1 显示具有通话套餐的电话系统](media/voice-solutions-simple.png)

如果你对以下内容回答"是"，则"电话系统与通话套餐"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

但是，情况可能更复杂。 例如，你可能在呼叫计划不可用的位置设有办公室。 或者，可能需要一个支持复杂、跨区域部署的组合解决方案，对不同的地理位置有不同的要求。 Microsoft 支持组合解决方案： 

- 具有通话套餐的电话系统
- 具有自己的 PSTN 运营商的电话系统与直接路由
- 将电话系统与通话计划结合使用和电话系统与直接路由的组合解决方案

## <a name="what-do-you-need-to-read"></a>需要阅读哪些信息？

**全部必需。** 本文中的某些部分适用于所有组织。 例如，每个人都应阅读有关电话系统的信息，并了解用于连接到 PSTN 公用电话交换 (PSTN) 。 


| 全部必需 | 描述 |
| :------------|:-------|
| [**电话系统**](#phone-system) | Microsoft 的技术，用于通过 Microsoft Teams 在 Microsoft 365 云 (PBX) 实现呼叫控制和专用交换机交换功能。 |
| [**公用电话交换网 (PSTN) 连接选项**](#public-switched-telephone-network-connectivity-options) | 可以选择使用 Microsoft 作为电话运营商，还是使用直接路由将你自己的电话运营商连接到 Microsoft Teams。 PSTN 连接选项与电话系统相结合，可让用户进行全球电话呼叫。|

**取决于你的要求。** 本文中的某些部分与现有的部署和要求相关。 例如，Location-Based不允许通行费绕过的地理位置中的直接路由客户需要直接路由。

请考虑可能需要以下哪些附加配置：

![图 2 显示了其他语音组件，例如来自 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| 根据要求 | 描述 |
| :------------|:-------|
| [**Microsoft 提供的电话号码**](#phone-numbers-from-microsoft) | 如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。 如果需要获取 Microsoft 呼叫计划的电话号码、转移现有号码、获取服务号码等，请阅读此内容。 |
| [**拨号计划和呼叫路由**](#dial-plans-and-call-routing) | 如何配置和管理将拨号电话号码转换为备用格式的拨号计划 (通常为 E.164 格式) 呼叫授权和呼叫路由。 如果你需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读此说明。|
| [**紧急呼叫**](#emergency-calling) | 如何管理和配置紧急呼叫 &mdash; ，具体取决于 PSTN 连接选项。 如果使用 Microsoft 呼叫计划或直接路由，并且需要了解如何为组织管理紧急呼叫，请阅读本部分。 |
| [**用于直接路由的基于位置的路由**](#location-based-routing-for-direct-routing) |如何使用 LBR Location-Based路由 (，) 根据地理位置限制 Microsoft Teams 用户的通行费绕过。 如果组织在不允许通行费绕过的位置使用直接路由，请阅读本部分。
| [**云语音功能的网络拓扑**](#network-topology-for-voice-features) | 如果组织为直接Location-Based或 (呼叫) LBR 路由服务，则必须配置网络设置，以在 Microsoft Teams 中与这些功能一同使用。 如果要为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。 |
| [**迁移现有语音解决方案**](#migrate-your-existing-voice-solution-to-teams) | 将语音解决方案迁移到 Teams 时需考虑的问题。  如果要从现有语音解决方案迁移到 Teams，请阅读本部分。 



> [!Important]
> 本文重点介绍 Microsoft Teams 的语音解决方案。 虽然 Skype for Business Online 解决方案 ([如 Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 电话解决方案) 中所述，但必须了解 Skype for Business Online 将于 2021 年 7 月 31 日停用。  在此日期之后，Skype for Business Online 服务将无法再访问。 此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是 Cloud Connector Edition 和 Skype for Business Online）建立 PSTN &mdash; &mdash; 连接。 本文介绍 Teams 语音解决方案，以及如何在必要时使用直接路由将本地电话网络连接到 Teams。


## <a name="phone-system"></a>电话系统

电话系统是 Microsoft 的技术，用于通过 Microsoft Teams 在 Microsoft 365 或 Office 365 云中启用呼叫控制和专用交换机 (PBX) 功能。

电话系统适用于 Teams 或 Skype for Business 客户端和经过认证的设备。 使用电话系统，可以使用直接从 Microsoft 365 或 Office 365 提供的一组功能替换现有 PBX 系统。 

组织中用户之间的呼叫在电话系统内部处理，永远不会转到 PSTN (公用电话) 。 这适用于组织中位于不同地理区域的用户之间的呼叫，消除了这些内部呼叫的远程成本。

本文介绍以下电话系统关键特性和功能，以及需要考虑的部署决策：

- [自动助理和呼叫队列](#auto-attendants-and-call-queues)
- [云语音邮件](#cloud-voicemail)
- [调用标识](#calling-identity)

![图 3 显示电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

有关所有电话系统功能以及如何设置电话系统的信息，请参阅以下文章：

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)
- [在组织中设置电话系统](setting-up-your-phone-system.md)<br>
  介绍如何购买和分配电话系统许可证、管理电话号码以及设置免费号码的通信信用额度。 

有关管理受支持设备的信息，请参阅"在[Microsoft Teams](devices/device-management.md)和 Teams 市场中管理[设备"。](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>自动助理和呼叫队列

自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。 呼叫队列正在等待呼叫者的区域。 自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。

有关自动助理和呼叫队列的信息，请参阅以下文章：

- [规划 Teams 自动助理和呼叫队列](plan-auto-attendant-call-queue.md)
- [设置自动助理](create-a-phone-system-auto-attendant.md)
- [创建呼叫队列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)<br>
  介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。

### <a name="cloud-voicemail"></a>云语音邮件

云语音邮件（由 Azure 语音邮件服务提供）仅支持将语音邮件置于 Exchange 邮箱。 它不支持第三方电子邮件系统。 

云语音邮件包括语音邮件听录，默认情况下为贵组织的所有用户启用。 你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。

对于仅联机用户，为用户分配电话系统许可证后，会自动设置和预配云语音邮件。 对于具有 Exchange 邮箱的电话系统用户，需要执行额外的配置步骤。 

有关云语音邮件及其配置的信息，请参阅以下文章：

- [设置云语音邮件](set-up-phone-system-voicemail.md)
- [在组织中设置语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫使用分配的电话号码作为呼叫 (呼叫方 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 有关配置呼叫者 ID 或更改或阻止呼叫者 ID 的信息，请参阅"为[用户设置呼叫方 ID"。](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用电话交换网络连接选项

电话系统为组织提供完整的 PBX 功能。 但是，若要让用户在组织外部进行呼叫，你需要将电话系统连接到 PSTN (公用电话) 。 若要将电话系统连接到 PSTN，可以选择以下选项之一：

- [**具有通话套餐的电话系统**](#phone-system-with-calling-plan)。 使用 Microsoft 作为 PSTN 运营商的全云解决方案。

- [**使用直接路由将本地**](#phone-system-with-own-pstn-carrier-with-direct-routing) 环境连接到 Teams，使用自己的 PSTN 运营商的电话系统。

还可以选择选项组合，这样，就可以为复杂环境设计解决方案，或者管理多步骤迁移 (以后进行迁移) 。

### <a name="phone-system-with-calling-plan"></a>具有通话套餐的电话系统 

如本文前面所述，具有通话计划的电话系统是 Microsoft 为 Teams 用户提供的全云语音解决方案。 这是将 Microsoft Phone System 连接到公用电话交换网 (PSTN) 以启用对世界各地的座机和移动电话的呼叫的最简单选项。 通过此选项，Microsoft (PBX) 功能，并充当 PSTN 运营商，如下图所示：

![图 4 显示电话系统与自动助理、呼叫队列、呼叫者 ID 等，以及 Microsoft 作为 PSTN 运营商](media/voice-solution-microsoft-complete.png)

如果你对以下内容回答"是"，则"电话系统与通话套餐"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

使用此选项： 

- 通过添加的国内或国际呼叫计划，你可以获取 Microsoft Phone 系统 (根据获得许可的服务级别拨打世界各地的) 。

- 由于呼叫计划在 &mdash; Microsoft 365 或 Office 365 外运行，因此不需要部署或维护本地部署。

- 注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。

此选项需要不间断地连接到 Microsoft 365 或 Office 365。

有关呼叫计划详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家和地区可用性](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [设置呼叫计划](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>使用直接路由的具有自己的 PSTN 运营商的电话系统

此选项使用直接路由将 Microsoft Phone 系统连接到电话网络，如下图所示： 

![图 5 显示具有直接路由的电话系统](media/voice-solution-with-direct-routing.png)

如果对以下问题回答"是"，则使用直接路由的电话系统是适合你的解决方案：

- 你想要将 Teams 与手机系统一同使用。
- 你需要保留当前的 PSTN 运营商。
- 您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。
- 你需要与第三方 PBX 和/或设备（例如我们的开销分页器、模拟设备等）互操作。

使用此选项：

- 将自己支持的 SBC 连接到 Microsoft Phone System，而无需其他本地软件。

- 几乎可以将任何电话运营商与 Microsoft Phone System 一同使用。

- 你可以选择配置和管理此选项，也可以由运营商或合作伙伴配置和管理 (询问你的运营商或合作伙伴是否提供此选项) 。

- 可以在电话设备（例如第三方 PBX 和模拟设备和 Microsoft Phone 系统）之间配置 &mdash; &mdash; 互操作性。


此选项需要以下各项：

- 不间断连接到 Microsoft 365 或 Office 365。

- 部署和维护支持的 SBC。

- 与第三方运营商签署合同。
   (，除非部署为为使用呼叫计划的电话系统上的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) 

有关直接路由详细信息，请参阅以下文章：

- [电话系统直接路由](direct-routing-landing-page.md)
- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理用于直接路由的语音路由策略](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Microsoft 提供的电话号码

Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。 服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。

需要确定：

- 哪些用户位置需要 Microsoft 提供的新电话号码？
- 我需要哪种类型的 (或) 电话号码？ 
- 如何将现有电话号码移植到 Teams？

有关管理组织中电话号码（包括获取新号码或转移退出号码）的信息，请参阅以下文章：

- [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [用于呼叫计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [为用户获取电话号码](getting-phone-numbers-for-your-users.md)
- [将电话号码转移到 Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>拨号计划和呼叫路由

拨号计划是一组规范化规则，用于将拨打的电话号码转换为备用格式 (通常为 E.164 格式) 呼叫授权和呼叫路由。

需要确定以下事项： 

- 我的组织是否需要自定义拨号计划？
- 哪些用户需要自定义拨号计划？
- 应该将哪个租户拨号计划分配给每个用户？

有关详细信息，请参阅以下文章： 

- [什么是拨号计划？](what-are-dial-plans.md)
- [规划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [创建并管理拨号计划](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>紧急呼叫

你的紧急呼叫配置方式因 PSTN 连接选项（Microsoft 呼叫计划或直接路由）不同。 Microsoft 呼叫计划和电话系统直接路由的动态紧急呼叫提供配置和路由紧急呼叫以及根据 Teams 客户端的当前位置通知安全人员的功能。 有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)<br>
  介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。

## <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在某些国家和地区，绕过公用电话交换网和 PSTN (PSTN) 降低远程呼叫成本非法。 Location-Based路由允许根据 Microsoft Teams 用户的地理位置限制免验证收费。 若要详细了解如何为 LBR Location-Based和配置 (路由) ，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  介绍虚拟的多语言公司 Contoso 如何为Location-Based实现虚拟路由。

## <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以在 Microsoft Teams 中与这些功能一同使用。 若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：

- [Microsoft Teams 中云语音功能的网络设置 - 概念和术语](cloud-voice-network-settings.md)
- [在 Microsoft Teams 中管理云语音功能的网络拓扑](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>将现有语音解决方案迁移到 Teams

对于要升级到 Teams 的组织，最终目标是将所有用户移动到 TeamsOnly 模式。 仅在用户位于 TeamsOnly 模式下时，才支持将电话系统与 Teams 一同使用。 如果需要有关升级到 Teams 的基本信息，请从此处开始：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [关于升级框架](upgrade-framework.md)
- [从 Skype for Business 升级到 Teams - 适用于 IT 管理员](upgrade-to-teams-on-prem-overview.md)

迁移语音解决方案时，在迁移到 TeamsOnly 模式时，有四种可能的通话方案：

- [**Skype for Business Online 中的用户，具有 Microsoft 呼叫计划**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 呼叫计划。

- **[Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的用户，通过本地 Skype for Business 或 Cloud Connector Edition 提供本地语音功能。 用户升级到 Teams 需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。

- **[本地 Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 中具有 企业语音 的用户，该用户将移动到联机并保留本地 PSTN 连接。 将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。 

- **[本地 Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 中具有 企业语音 的用户，该用户将移动到在线，使用 Microsoft 呼叫计划。  将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并将该移动与 A 协调) 将该用户的电话号码的端口转移到 Microsoft 呼叫计划，或者 B) 从可用区域分配新的订阅者号码。

若要详细了解如何针对每种方案实现语音迁移，包括有关何时需要设置混合连接以及如何将具有本地语音功能的用户迁移到直接路由的信息，请参阅 &mdash; &mdash; 以下文章：

- [升级到 Teams 时 PSTN 注意事项 - 适用于 IT 管理员](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 语音迁移案例研究](voice-case-study-overview.md)<br>
  案例研究介绍虚构的多语言公司 Contoso 如何为组织实现 Teams 语音解决方案。 它包含以下文章：

  - [Teams 升级计划](voice-case-study-migration-plan.md)
  - [电话系统和 PSTN 连接选项](voice-case-study-phone-system.md)
  - [基于位置的路由实现](voice-case-study-location-based-routing.md)
  - [紧急呼叫](voice-case-study-emergency-calling.md)
  - [自动助理和呼叫队列](voice-case-study-call-queues.md)
  - [音频会议](voice-case-study-audio-conferencing.md)












