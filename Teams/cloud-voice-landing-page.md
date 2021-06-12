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
description: 详细了解云Microsoft Teams功能和将为组织做出部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 391b8e2f30aa5e64fcb4b9e418af49341c2b9042
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901929"
---
# <a name="plan-your-teams-voice-solution"></a>规划Teams语音解决方案 

本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。 确定后，本文提供内容路线图，实现所选解决方案。

> [!NOTE]
> 有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 的总体计划的一部分的指导，请参阅从 Skype for Business 本地升级到 Teams 的[PSTN 注意事项](upgrade-to-teams-on-prem-pstn-considerations.md)。

你可能希望使用呼叫计划 &mdash; 电话系统最简单的解决方案。 这是 Microsoft 的全云解决方案，可提供专用分支 Exchange (PBX) 功能，并呼叫公用电话交换网 (PSTN) ，如下图所示。 借助此解决方案，Microsoft 是你的 PSTN 运营商。

![图 1 电话系统套餐](media/voice-solutions-simple.png)

如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

但是，情况可能更复杂。 例如，你可能在呼叫计划不可用的位置设有办公室。 或者，可能需要一个支持复杂、跨区域部署、对不同地理位置有不同的要求的组合解决方案。 Microsoft 支持解决方案的组合： 

- 电话系统套餐
- 电话系统您的 PSTN 运营商运营商连接 (目前仅在公共 **预览版中提供)**
- 电话系统直接路由与自己的 PSTN 运营商联系
- 结合使用解决方案，将 电话系统 与呼叫计划结合使用电话系统接线员连接和/或电话系统直接路由


## <a name="what-do-you-need-to-read"></a>需要阅读哪些信息？

**全部必需。** 本文中的某些部分适用于所有组织。 例如，每个人都应该阅读有关电话系统并了解用于连接到 PSTN 公用电话交换网 (的选项) 。 


| 全部必需 | 说明 |
| :------------|:-------|
| [**电话系统**](#phone-system) | Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术Microsoft 365云Microsoft Teams。 |
| [**PSTN 公用电话交换 (PSTN) 连接选项**](#public-switched-telephone-network-connectivity-options) | 可以选择使用 Microsoft 作为电话运营商，还是使用直接路由或接线员Microsoft Teams将你自己的电话运营商连接。 PSTN 连接电话系统结合使用，使用户能够拨打全球电话。|

**根据你的要求。** 本文中的某些部分与现有的部署和要求相关。 例如，Location-Based直接路由客户在不允许收费绕过的地理位置进行直接路由。

请考虑可能需要以下附加配置中的哪一种：

![图 2 显示了其他语音组件，电话 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| 根据要求 | 说明 |
| :------------|:-------|
| [**电话 Microsoft 提供的电话号码**](#phone-numbers-from-microsoft) | 如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。 如果需要获取 Microsoft 呼叫计划的电话号码、转移现有号码、获取服务号码等，请阅读此内容。 |
| [**拨号计划和呼叫路由**](#dial-plans-and-call-routing) | 如何配置和管理将拨号电话号码转换为备用格式的拨号计划 (通常为 E.164 格式) 进行呼叫授权和呼叫路由。 如果需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读此说明。|
| [**紧急呼叫**](#emergency-calling) | 如何管理和配置紧急呼叫 &mdash; ，具体取决于 PSTN 连接选项。 如果使用 Microsoft 呼叫计划或直接路由，并且需要了解如何为组织管理紧急呼叫，请阅读本部分。 |
| [**用于直接路由的基于位置的路由**](#location-based-routing-for-direct-routing) |如何使用 LBR Location-Based路由 (，) 基于用户的地理位置Microsoft Teams免收费。 如果组织在不允许绕过收费站的位置使用直接路由，请阅读本部分。
| [**云语音功能的网络拓扑**](#network-topology-for-voice-features) | 如果组织为直接路由Location-Based LBR (部署) 路由或动态紧急呼叫，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。 如果要为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。 |
| [**迁移现有语音解决方案**](#migrate-your-existing-voice-solution-to-teams) | 将语音解决方案迁移到云时需考虑Teams。  如果要从现有语音解决方案迁移到现有语音解决方案，请阅读此Teams。 



> [!Important]
> 本文重点介绍语音解决方案与Microsoft Teams。 虽然 Skype for Business Online 解决方案 ([Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)电话解决方案) 中所述，但必须了解 Skype for Business Online 将于 2021 年 7 月 31 日停用。  该日期之后，Skype for Business不再可访问联机服务。 此外，将不再支持本地环境之间的 PSTN 连接 &mdash; Skype for Business Server云连接器版本和 Skype for Business Online &mdash; 连接。 本文介绍Teams语音解决方案，以及如何在必要时使用直接路由或接线员Teams连接本地电话连接。


## <a name="phone-system"></a>电话系统

电话系统是 Microsoft 在 Microsoft 365 或 Office 365 云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术，Microsoft Teams。

电话系统适用于Teams或Skype for Business客户端和认证设备。 电话系统将现有 PBX 系统替换为一组直接从 Microsoft 365 或 Office 365。 

您的组织中的用户之间的呼叫在内部处理电话系统，永远不会转到 PSTN (电话) 。 这适用于组织中位于不同地理区域的用户之间的呼叫，消除了这些内部呼叫的远程成本。

本文介绍以下电话系统特性和功能，以及需要考虑的部署决策：

- [自动助理和呼叫队列](#auto-attendants-and-call-queues)
- [云语音邮件](#cloud-voicemail)
- [调用标识](#calling-identity)

![图 3 电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

有关所有电话系统功能以及如何设置电话系统，请参阅以下文章：

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)
- [在组织中设置电话系统](setting-up-your-phone-system.md)<br>
  介绍如何购买和分配电话系统、管理电话号码以及设置免费号码的通信信用额度。 

有关管理受支持设备的信息，请参阅[在](devices/device-management.md)Microsoft Teams 和 Teams[中管理设备](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。


### <a name="auto-attendants-and-call-queues"></a>自动助理和呼叫队列

自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。 呼叫队列正在等待呼叫者的区域。 自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。

有关自动助理和呼叫队列的信息，请参阅以下文章：

- [规划Teams助理和呼叫队列](plan-auto-attendant-call-queue.md)
- [设置自动助理](create-a-phone-system-auto-attendant.md)
- [创建呼叫队列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)<br>
  介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。

### <a name="cloud-voicemail"></a>云语音邮件

云语音邮件由 Azure 语音邮件服务支持将语音邮件Exchange邮箱。 它不支持第三方电子邮件系统。 

云语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。

对于仅联机用户云语音邮件，系统会自动为用户设置和预配用户许可证电话系统许可证。 对于电话系统邮箱Exchange，需要执行额外的配置步骤。 

有关应用程序及其云语音邮件，请参阅以下文章：

- [设置云语音邮件](set-up-phone-system-voicemail.md)
- [在组织中设置语音邮件策略](manage-voicemail-policies.md)


### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 有关配置来电显示或更改或阻止来电显示的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用电话交换网络连接选项

电话系统为组织提供完整的 PBX 功能。 但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。 若要电话系统 PSTN，可以选择以下选项之一：

- [**电话系统套餐 。**](#phone-system-with-calling-plan) 以 Microsoft 作为 PSTN 运营商的全云解决方案。

- [**电话系统直接**](#phone-system-with-own-pstn-carrier-with-direct-routing)路由将本地环境连接到本地环境，与自己的 PSTN 运营商Teams。

- 电话系统运营商或运营商与自己的 [**PSTN 运营商连接，**](operator-connect-plan.md)目前仅在公共预览 **版中提供。**  使用接线连接，如果现有运营商是 Microsoft 接线员连接参与者，他们可管理将 PSTN 呼叫引入 Teams。 有关操作员服务权益和要求连接，有关参与此计划的操作员的列表，请参阅计划操作员[连接。](operator-connect-plan.md)

还可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移 (以后迁移) 。

### <a name="phone-system-with-calling-plan"></a>电话系统套餐 

如本文前面所述，电话系统套餐是 Microsoft 为用户提供的所有云语音Teams解决方案。 这是将 Microsoft 电话 系统连接到公用电话交换网 (PSTN) 以启用对世界各地的座机和移动电话的呼叫的最简单选项。 使用此选项，Microsoft 为组织Exchange (PBX) 专用分支，并充当 PSTN 运营商，如下图所示：

![图 4 电话系统自动助理、呼叫队列、呼叫者 ID 等，以及 Microsoft 作为 PSTN 运营商](media/voice-solution-microsoft-complete.png)

如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

使用此选项： 

- 你可以Microsoft 电话系统添加国内或国际呼叫计划，这些套餐支持拨打世界各地的电话 (具体取决于获得许可的服务) 。

- 不需要部署或维护本地部署，因为呼叫计划在 Microsoft 365 &mdash; 或 Office 365。

- 注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。

此选项需要不间断地连接到 Microsoft 365 或 Office 365。

有关呼叫计划详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家和地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [设置呼叫计划](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>电话系统具有直接路由的 PSTN 运营商

此选项使用Microsoft 电话路由将系统连接到电话网络，如下图所示： 

![图 5 显示电话系统直接路由的路由](media/voice-solution-with-direct-routing.png)

如果对以下问题回答"是"，电话系统直接路由是适合的解决方案：

- 想要将 Teams 与 电话系统。
- 你需要保留当前的 PSTN 运营商。
- 您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。
- 需要和第三方 PBX 和/或设备（例如我们的开销寻呼机、模拟设备等）互操作。

使用此选项：

- 将自己支持的 SBC 连接到 Microsoft 电话 System，而无需其他本地软件。

- 几乎可以将任何电话运营商与 Microsoft 电话系统一起使用。

- 您可以选择配置和管理此选项，也可以由运营商或合作伙伴组织配置和管理 (询问运营商或合作伙伴是否提供此选项) 。

- 可以在电话设备（例如第三方 PBX 和模拟设备）与 Microsoft 电话 &mdash; &mdash; 系统之间配置互操作性。


此选项需要以下各项：

- 不间断地连接到 Microsoft 365 或 Office 365。

- 部署和维护支持的 SBC。

- 与第三方运营商的合同。
   (除非部署为为使用呼叫计划.电话系统的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) 

有关直接路由详细信息，请参阅以下文章：

- [电话系统直接路由](direct-routing-landing-page.md)
- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理用于直接路由的语音路由策略](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>电话 Microsoft 提供的电话号码

Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。 服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。

需要确定：

- 哪些用户位置需要 Microsoft 提供的新电话号码？
- 需要哪种类型的 (或) 电话号码？ 
- 如何将现有电话号码移植到Teams？

有关管理组织中电话号码（包括获取新号码或转移退出号码）的信息，请参阅以下文章：

- [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [用于呼叫计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [为用户获取电话号码](getting-phone-numbers-for-your-users.md)
- [将电话号码转移到Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>拨号计划和呼叫路由

拨号计划是一组规范化规则，将拨入的电话号码转换为备用格式 (通常为 E.164 格式) 进行呼叫授权和呼叫路由。

需要确定以下事项： 

- 我的组织是否需要自定义拨号计划？
- 哪些用户需要自定义拨号计划？
- 应该向每个用户分配哪个租户拨号计划？

有关详细信息，请参阅以下文章： 

- [什么是拨号计划？](what-are-dial-plans.md)
- [规划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [创建并管理拨号计划](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>紧急呼叫

如何配置紧急呼叫取决于 PSTN 连接选项：Microsoft 呼叫计划或直接路由。 Microsoft 呼叫计划和直接路由电话系统动态紧急呼叫提供配置和路由紧急呼叫以及根据客户端的当前位置通知安全Teams的功能。 有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)<br>
  介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。

## <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在某些国家和地区，绕过 PSTN 公用电话交换网 (PSTN) 降低远程呼叫成本非法。 Location-Based直接路由的路由允许根据用户Microsoft Teams限制免收费。 若要详细了解如何计划和配置 Location-Based LBR (路由) ，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  介绍虚拟的多语言公司 Contoso 如何为Location-Based实现路由。

## <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。 若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：

- [云语音功能网络设置Microsoft Teams - 概念和术语](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>将现有语音解决方案迁移到Teams

对于要升级到 Teams，最终目标是将所有用户移动到 TeamsOnly 模式。 仅在电话系统 TeamsOnly Teams，才支持将 Teams 与应用一起使用。 如果需要有关升级到 Teams 的基本信息，请从此处开始：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [关于升级框架](upgrade-framework.md)
- [适用于 IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md)

迁移语音解决方案时，迁移到 TeamsOnly 模式时，有四种可能的呼叫方案：

- [**具有 Microsoft 呼叫Skype for Business的 Skype for Business Online 中的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 呼叫计划。

- **[Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的用户，通过本地或云连接器Skype for Business本地语音功能。 用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。

- **[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)该用户将移动到联机并保持本地 PSTN 连接**。 将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。 

- **[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)该用户将移动到联机，使用 Microsoft 呼叫计划**。  将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。

若要详细了解如何针对每种方案实现语音迁移，包括有关何时需要设置混合连接以及如何将具有本地语音功能的用户迁移到直接路由的信息， &mdash; &mdash; 请参阅以下文章：

- [升级到网络时 PSTN Teams注意事项 - 适用于 IT 管理员](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 语音迁移案例研究](voice-case-study-overview.md)<br>
  案例研究介绍了虚构的多语言公司 Contoso 如何为Teams实现语音解决方案。 它包含以下文章：

  - [Teams升级计划](voice-case-study-migration-plan.md)
  - [电话系统和 PSTN 连接选项](voice-case-study-phone-system.md)
  - [基于位置的路由实现](voice-case-study-location-based-routing.md)
  - [紧急呼叫](voice-case-study-emergency-calling.md)
  - [自动助理和呼叫队列](voice-case-study-call-queues.md)
  - [音频会议](voice-case-study-audio-conferencing.md)
