---
title: Microsoft 团队中的语音
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
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 了解有关 Microsoft 团队云语音功能的详细信息以及你将为组织制定的部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 464f3591d86879db5830ca0abbea1bfbff538cec
ms.sourcegitcommit: 4dd8a326a7284872f0d14e0a61bd4fcbe2297c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071763"
---
# <a name="plan-your-teams-voice-solution"></a>规划团队语音解决方案 

本文将帮助你确定哪种 Microsoft 语音解决方案适合你的组织。 确定后，本文将提供内容的路线图，使你能够实现所选的解决方案。 

您可能希望最简单的解决方案 &mdash; 电话系统具有通话计划。 这是 Microsoft 的所有云解决方案，它提供了专用分支 Exchange (PBX) 功能以及对公共交换电话网络 (PSTN) 的调用，如下图所示。 通过此解决方案，Microsoft 是你的 PSTN 运营商。

![图1显示了带有呼叫计划的电话系统](media/msft-voice-solutions-1.png)

如果对以下项回答 "是"，则带有呼叫计划的电话系统是适合你的解决方案：

- 您所在的地区有通话计划。
- 您无需保留当前的 PSTN 运营商。
- 您想要对 PSTN 使用 Microsoft 托管访问。

但是，你的情况可能更复杂。 例如，您可能在不支持通话计划的位置有办事处。 或者，你可能需要支持复杂的多国部署的组合解决方案，但对不同地理位置的要求不同。 Microsoft 支持解决方案组合： 

- 带有呼叫计划的电话系统
- 带有直接路由的您自己的 PSTN 运营商的电话系统
- 结合使用电话系统和直接路由的通话计划和电话系统结合使用的组合解决方案

## <a name="what-do-you-need-to-read"></a>您需要阅读哪些内容？

**必填。** 本文中的部分内容适用于所有组织。 例如，每个人都应阅读有关电话系统的信息，并了解连接到公共交换电话网络 (PSTN) 的选项。 


| 所有必填 | 说明 |
| :------------|:-------|
| [**电话系统**](#phone-system) | Microsoft 365 cloud 中与 Microsoft 团队 (PBX) 功能的 microsoft 的技术，用于启用呼叫控制和专用分支 Exchange。 |
| [**公共交换电话网络 (PSTN) 连接选项**](#public-switched-telephone-network-connectivity-options) | 在使用 Microsoft 作为电话运营商，或使用直接路由将您自己的电话运营商连接到 Microsoft 团队之间的选择。 通过结合使用手机系统，PSTN 连接选项使你的用户可以拨打世界各地的电话。|

**具体取决于你的需求。** 本文中的部分内容取决于您的现有部署和要求。 例如，仅在不允许进行收费跳过的地理位置直接路由客户的情况下，才需要 Location-Based 路由。


| 根据您的要求 | 说明 |
| :------------|:-------|
| [**Microsoft 的电话号码**](#phone-numbers-from-microsoft) | 如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。 如果需要获取 Microsoft 通话计划的电话号码、转移现有号码、获取服务号码等，请阅读此项。 |
| [**拨号计划和呼叫路由**](#dial-plans-and-call-routing) | 如何配置和管理将已拨打的电话号码转换为备用格式的拨号计划 (一般情况下，) 用于呼叫授权和呼叫路由的 E：164格式。 如果需要了解拨号计划以及是否需要为你的组织指定拨号计划，请阅读此内容。|
| [**紧急电话**](#emergency-calling) | 如何根据 PSTN 连接选项管理和配置紧急呼叫 &mdash; 。 如果您使用的是 Microsoft 通话计划或直接路由，并且需要了解如何管理您的组织的紧急呼叫，请阅读本部分。 |
| [**直接路由的基于位置的路由**](#location-based-routing-for-direct-routing) |如何使用 Location-Based 路由 (LBR) 根据地理位置限制 Microsoft 团队用户进行收费跳过。 如果你的组织在不允许使用免收费的位置使用直接路由，请阅读本部分。
| [**云语音功能的网络拓扑**](#network-topology-for-voice-features) | 如果你的组织正在部署 Location-Based 路由 (LBR) 用于直接路由或动态紧急呼叫，则必须在 Microsoft 团队中配置用于这些功能的网络设置。 如果你要为直接路由实现 LBR，或者如果你要通过呼叫计划或直接路由实施动态紧急呼叫，请阅读本部分。 |
| [**迁移现有的语音解决方案**](#migrate-your-existing-voice-solution-to-teams) | 将语音解决方案迁移到团队时需要考虑的内容。  如果要从现有语音解决方案迁移到团队，请阅读本部分。 



> [!Important]
> 本文重点介绍 Microsoft 团队的语音解决方案。 虽然 Skype for business Online 的解决方案仍然可用 (如 [Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)) 所述，但了解 skype For business online 将于2021年7月31日停用，这一点很重要。  在该日期之后，Skype for Business Online 服务将无法再访问。 此外，你的本地环境之间的 PSTN 连接（ &mdash; 无论是通过 skype For Business 服务器还是云连接器版本 &mdash; 和 Skype For business Online）都将不再受支持。 本文介绍团队语音解决方案，以及如何使用直接路由将本地电话网络（如有必要）连接到团队。


## <a name="phone-system"></a>电话系统

电话系统是 Microsoft 在 microsoft 365 或 Office 365 云中与 Microsoft 团队 (PBX) 功能的 Microsoft 技术，用于启用呼叫控制和专用分支 Exchange。

电话系统与团队或 Skype for business 客户端和认证设备配合使用。 电话系统允许你将现有的 PBX 系统替换为从 Microsoft 365 或 Office 365 直接提供的一组功能。 

您的组织内的用户之间的通话在电话系统内部处理，绝不会转到公共交换电话网络 (PSTN) 。 这适用于位于不同地理区域的组织中的用户之间的通话，可删除这些内部呼叫的长途费用。

本文介绍以下电话系统密钥功能和功能，您需要考虑的部署决策：

- [自动助理和呼叫队列](#auto-attendants-and-call-queues)
- [云语音邮件](#cloud-voicemail)
- [通话标识](#calling-identity)

有关所有电话系统功能以及如何设置电话系统的信息，请参阅以下文章：

- [电话系统的功能](here-s-what-you-get-with-phone-system.md)
- [在组织中设置电话系统](setting-up-your-phone-system.md)<br>
  介绍如何购买和分配电话系统许可证、管理电话号码以及为免费号码设置通信信用点数。 

有关管理受支持的设备的信息，请参阅在 Microsoft 团队和[团队市场](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[中管理设备](devices/device-management.md)。


### <a name="auto-attendants-and-call-queues"></a>自动助理和呼叫队列

自动助理允许你设置菜单选项，以根据呼叫方输入路由呼叫。 通话队列是呼叫方的等待区域。 "自动助理" 和 "呼叫队列" 一起使用，可以轻松地将呼叫者路由到组织中的相应人员或部门。

有关自动助理和通话队列的信息，请参阅以下文章：

- [规划团队自动助理和通话队列](plan-auto-attendant-call-queue.md)
- [设置自动助理](create-a-phone-system-auto-attendant.md)
- [创建呼叫队列](create-a-phone-system-call-queue.md) 
- [Contoso 个案研究：自动助理和呼叫队列](voice-case-study-call-queues.md)<br>
  介绍一个虚构的多国企业（Contoso）如何为其语音解决方案实现自动助理和通话队列。

### <a name="cloud-voicemail"></a>云语音邮件

云语音邮件（由 Azure 语音邮件服务提供支持）仅支持向 Exchange 邮箱存款语音邮件。 它不支持第三方电子邮件系统。 

云语音邮件包括语音邮件脚本，默认情况下为组织中的所有用户启用。 您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。

对于仅供联机使用的用户，为用户分配电话系统许可证后，将自动为其设置和设置云语音邮件。 对于具有 Exchange 邮箱的电话系统用户，你将需要执行额外的配置步骤。 

有关云语音邮件及其配置的详细信息，请参阅以下文章：

- [设置云语音邮件](set-up-phone-system-voicemail.md)
- [在组织中设置语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>通话标识

默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫方 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 有关配置来电显示或更改或阻止呼叫方 ID 的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公共交换电话网络连接选项

电话系统为您的组织提供完整的 PBX 功能。 但是，若要使用户可以在组织外部进行呼叫，您需要将电话系统连接到公共交换电话网络 (PSTN) 。 要将电话系统连接到 PSTN，您可以选择以下选项之一：

- [**带有呼叫计划的电话系统**](#phone-system-with-calling-plan)。 Microsoft 作为 PSTN 运营商提供的所有云解决方案。

- [**带有您自己的 PSTN 运营商的电话系统**](#phone-system-with-own-pstn-carrier-with-direct-routing) ，使用直接路由将本地环境连接到团队。

你还可以选择选项组合，以便为复杂的环境设计解决方案，或者管理多步迁移 (有关稍后) 迁移的详细信息。

### <a name="phone-system-with-calling-plan"></a>带有呼叫计划的电话系统 

如本文前面所述，带有呼叫计划的电话系统是适用于团队用户的 Microsoft 的所有云语音解决方案。 这是将 Microsoft Phone 系统连接到公共交换电话网络 (PSTN) 的最简单选项，可拨打世界各地的座机和移动电话。 通过此选项，Microsoft 为你的组织提供专用分支 Exchange (PBX) 功能，并充当 PSTN 运营商，如下图所示：

![图1显示了带有呼叫计划的电话系统](media/msft-voice-solutions-1a.png)

如果对以下项回答 "是"，则带有呼叫计划的电话系统是适合你的解决方案：

- 您所在的地区有通话计划。
- 您无需保留当前的 PSTN 运营商。
- 您想要对 PSTN 使用 Microsoft 托管访问。

通过此选项： 

- 您可以通过添加国内或国际呼叫计划的 Microsoft Phone 系统，让您拨打世界各地的电话 (，具体取决于) 许可的服务级别。

- 你不需要部署或维护本地部署， &mdash; 因为通话计划的运行方式不是 Microsoft 365 或 Office 365。

- 注意：如有必要，你可以选择通过直接路由与 SBC 支持的第三方 Pbx、模拟设备和其他第三方电话设备的互操作性，将受支持的会话边界控制器连接 (SBC) 。

此选项需要与 Microsoft 365 或 Office 365 的无中断连接。

有关通话计划的详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家和地区可用性](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [设置通话计划](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>带有直接路由的 PSTN 运营商的电话系统

此选项通过直接路由将 Microsoft Phone 系统连接到电话网络，如下图所示： 

![图2显示了带有直接路由的电话系统](media/msft-voice-solutions-2.png)

如果对以下问题回答 "是"，则带有直接路由的电话系统是适合你的解决方案：

- 您希望将团队与电话系统配合使用。
- 您需要保留当前的 PSTN 运营商。
- 您想要混合路由，通过通话计划进行一些通话，而有些通过运营商。
- 您需要与第三方的 Pbx 和/或设备互操作，例如，我们的系统开销、模拟设备等。

通过此选项：

- 将您自己支持的 SBC 连接到 Microsoft Phone 系统，而无需额外的本地软件。

- 您可以将任何电话运营商与 Microsoft Phone 系统配合使用。

- 你可以选择配置和管理此选项，或者你的运营商或合作伙伴 (询问你的运营商或合作伙伴是否提供此选项) 。

- 你可以配置电话设备 &mdash; （如第三方 PBX 和模拟设备 &mdash; 和 Microsoft Phone 系统）之间的互操作性。


此选项需要以下内容：

- 不中断连接到 Microsoft 365 或 Office 365。

- 部署和维护受支持的 SBC。

- 与第三方运营商签订的合同。
   (，除非已部署为向使用呼叫计划的电话系统上的用户提供与第三方 PBX、模拟设备或其他电话设备的连接的选项。 ) 

有关直接路由的详细信息，请参阅以下文章：

- [电话系统直接路由](direct-routing-landing-page.md)
- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理用于直接路由的语音路由策略](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)


## <a name="phone-numbers-from-microsoft"></a>Microsoft 的电话号码

Microsoft 有两种类型的电话号码可用： *订户* (用户) 号码（可分配给您组织中的用户）和 *服务* 号码（可用作收费电话和免费服务号码）。 服务号码的并行呼叫容量比订户号码的数量更高，并且可以分配给服务，例如音频会议、自动助理或呼叫队列。

你将需要确定：

- 哪些用户位置需要来自 Microsoft 的新电话号码？
- 我需要 (订阅者或服务) 哪些类型的电话号码？ 
- 如何将现有电话号码移植到团队？

有关管理组织中的电话号码的详细信息，包括获取新号码或转移现有号码，请参阅以下文章：

- [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [用于呼叫计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [为用户获取电话号码](getting-phone-numbers-for-your-users.md)
- [将电话号码转移到 Microsoft 团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>拨号计划和呼叫路由

拨号计划是一组规范化规则，可将拨出的电话号码转换为备用格式 (一般情况下，) 用于呼叫授权和呼叫路由的 E-164 格式的格式。

您需要确定以下事项： 

- 我的组织是否需要自定义拨号计划？
- 哪些用户需要自定义的拨号计划？
- 应将哪些租户拨号计划分配给每个用户？

有关详细信息，请参阅以下文章： 

- [什么是拨号计划？](what-are-dial-plans.md)
- [计划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [创建并管理拨号计划](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>紧急呼叫

配置紧急呼叫的方式会有所不同，具体取决于 PSTN 连接选项： Microsoft 通话计划或直接路由。 Microsoft 通话计划和电话系统直接路由的动态紧急呼叫提供了配置和路由紧急呼叫的功能，并根据团队客户的当前位置通知安全人员。 有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [Contoso 案例研究：紧急电话](voice-case-study-emergency-calling.md)<br>
  介绍一个虚构的多国企业（Contoso）如何为其组织实现紧急呼叫。

## <a name="location-based-routing-for-direct-routing"></a>直接路由的 Location-Based 路由

在某些国家和地区，不能绕过公共交换电话网络 (PSTN) 提供商减少长途通话成本。 通过 "Location-Based 路由选择直接路由"，你可以根据其地理位置限制 Microsoft 团队用户的收费跳过。 有关如何规划和配置 Location-Based 路由 (LBR) 的详细信息，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究： Location-Based 路由](voice-case-study-location-based-routing.md)<br>
  介绍虚构的多国公司（Contoso）如何为其组织实施 Location-Based 路由。

## <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或 Location-Based 路由，则必须在 Microsoft 团队中配置用于这些功能的网络设置。 若要了解如何配置网络区域、网络站点、网络子网和受信任的 IP 地址的网络设置，请参阅以下文章：

- [Microsoft 团队中云语音功能的网络设置-概念和术语](cloud-voice-network-settings.md)
- [在 Microsoft 团队中管理云语音功能的网络拓扑](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>将现有语音解决方案迁移到团队

对于升级到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。 仅当用户处于 TeamsOnly 模式时，才支持将电话系统与团队配合使用。 如果需要有关升级到团队的基本信息，请从此处开始：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [关于升级框架](upgrade-framework.md)
- [从 Skype for Business 升级到团队-面向 IT 管理员](upgrade-to-teams-on-prem-overview.md)

迁移语音解决方案时，在移动到 TeamsOnly 模式时有四种可能的通话方案：

- [**Skype For Business Online 中使用 Microsoft 通话计划的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 通话计划。

- **[Skype For business Online 中的用户，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)通过 skype for Business 本地或云连接器版本使用本地语音功能** 。 用户对团队的升级需要与用户迁移以直接路由，以确保 TeamsOnly 用户具有 PSTN 功能。

- **[使用企业语音的 Skype for business Online 中的用户](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，这些用户将移动到联机状态并保持本地 PSTN 连接** 。 将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。 

- **[使用企业语音的 Skype for business Online 中的用户](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，这些用户将移动到联机并使用 Microsoft 通话计划** 。  将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。

有关如何为每种情况实现您的语音迁移的详细信息 &mdash; ，包括有关何时需要设置混合连接的信息以及如何将具有本地语音功能的用户迁移到直接路由， &mdash; 请参阅以下文章：

- [升级到团队时的 PSTN 注意事项-适用于 IT 管理员](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 语音迁移案例研究](voice-case-study-overview.md)<br>
  案例研究介绍了一个虚构的多国公司（Contoso）如何为其组织实施团队语音解决方案。 其中包含以下文章：

  - [团队升级计划](voice-case-study-migration-plan.md)
  - [电话系统和 PSTN 连接选项](voice-case-study-phone-system.md)
  - [基于位置的路由实现](voice-case-study-location-based-routing.md)
  - [紧急电话](voice-case-study-emergency-calling.md)
  - [自动助理和呼叫队列](voice-case-study-call-queues.md)
  - [音频会议](voice-case-study-audio-conferencing.md)












