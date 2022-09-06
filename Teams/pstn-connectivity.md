---
title: PSTN 连接选项
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: 详细了解 Teams 调用 (PSTN 连接) 选项以及你将为组织做出的决定。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d30bc6b35f7f5e145e48b9dbf2793d5caa5d12c
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606581"
---
# <a name="pstn-connectivity-options"></a>PSTN 连接选项

Microsoft 通过电话系统为组织提供完整的专用分支交换 (PBX) 功能。 但是，若要使用户能够在组织外部拨打电话，需要将电话系统连接到公共交换电话网络 (PSTN) 。

本文重点介绍 PSTN 连接选项。 有关 Microsoft 语音解决方案的详细信息，包括有关电话系统功能的详细信息，请参 [阅规划 Teams 语音解决方案](cloud-voice-landing-page.md)。

若要将电话系统连接到 PSTN，可以从以下选项中进行选择：

- [**调用计划**](#phone-system-with-calling-plan)。 以 Microsoft 为 PSTN 运营商的全云解决方案。

- [**运算符连接**](#phone-system-with-operator-connect)。 借助 Operator Connect，如果现有运营商参与 Microsoft Operator Connect 计划，他们可以管理 PSTN 调用和会话边界控制器 (SBC) 。

- [**运营商连接移动**](#phone-system-with-operator-connect-mobile)。 使用运营商连接移动，用户启用 SIM 的电话号码也是其 Teams 电话号码。 如果现有运营商参与 Microsoft 运营商连接移动 计划，他们可以管理将 PSTN 调用引入 Teams 的服务。  **运营商连接移动是公共预览版。**

- [**直接路由**](#phone-system-with-direct-routing)，通过将会话边界控制器 (的)  (SBC) 连接到电话系统，可以使用自己的 PSTN 运营商。

还可以选择选项的组合，以便为复杂环境设计解决方案，或管理多步骤迁移。

选择的选项或选项会影响某些电话系统功能的配置方式。 有关详细信息，请参阅本文后面 [的配置注意事项](#configuration-considerations) 。

## <a name="phone-system-with-calling-plan"></a>具有通话套餐的电话系统

包含通话套餐的电话系统是 Microsoft 面向 Teams 用户的全云语音解决方案。 此解决方案是将电话系统连接到 PSTN 的最简单选项。 使用此选项，Microsoft 充当 PSTN 运营商，如下图所示：

![图 1 显示了具有通话套餐的电话系统。](media/voice-solutions-simple.png)

如果对以下内容回答“是”，则电话系统和通话套餐是适合你的解决方案：

- 呼叫计划在你所在的区域中可用。
- 无需保留当前的 PSTN 运营商。
- 你希望使用 Microsoft 管理的 PSTN 访问权限。

使用此选项：

- 你得到的电话系统与添加的国内或国际通话计划，启用电话在世界各地 (取决于服务水平获得许可) 。

- 不需要部署或维护本地部署&mdash;，因为通话套餐在 Microsoft 365 中运行。

- 注意：可以通过直接路由连接受支持的会话边界控制器 (SBC) ，以实现与 SBC 支持的第三方 PBX、模拟设备和其他电话设备的互操作性。

此选项需要与 Microsoft 365 的不间断连接。

有关通话套餐的详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家和地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [设置呼叫计划](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>包含运算符连接的电话系统

借助 Operator Connect，如果现有运营商参与 Microsoft Operator Connect 计划，他们可以管理将 PSTN 调用引入 Teams 的服务。 运营商管理 PSTN 呼叫服务和会话边框控制器 (SBC) ，从而节省硬件购买和管理费用。

如果以下情况，则操作员连接可能是组织的正确解决方案：

- Microsoft 通话套餐在地理位置不可用。
- 首选运营商是 Microsoft 运算符连接计划的参与者。
- 你希望找到一个新的运营商，以在 Teams 中启用呼叫。

有关运算符连接的优势和要求的信息，以及参与此计划的运营商列表，请参阅 [Plan Operator Connect](operator-connect-plan.md)。 有关如何配置运算符连接的信息，请参阅 [配置运算符连接](operator-connect-configure.md)。

## <a name="phone-system-with-operator-connect-mobile"></a>具有运营商连接移动的电话系统

**运营商连接移动是公共预览版。**

如果现有运营商参与 Microsoft 运营商连接移动 计划，他们可以管理将 PSTN 调用引入 Teams 的服务。 使用运营商连接移动，用户启用 SIM 的电话号码也是其 Teams 电话号码。  用户可以在 Microsoft Teams 中的移动服务和桌面线路上使用单个电话号码。  

可以考虑将服务组合在一起。 例如，你可以为需要移动支持的销售和现场组织选择运营商连接移动，但对于依赖于桌面电话的现场呼叫中心组织，则选择另一种解决方案。 

运营商连接移动可能是组织在以下情况下的正确解决方案：

- 你希望将 Teams Phone 的主要公司拥有且启用了 SIM 的移动号码用作单个号码解决方案。
- 首选运算符是 Microsoft 运营商连接移动 计划的参与者。
- 你希望找到一个新的运算符，以在 Teams 中启用呼叫。

有关运营商连接移动的好处和要求以及参与此计划的运营商的链接的信息，请参阅[计划运营商连接移动](operator-connect-mobile-plan.md)。 有关如何配置运营商连接移动的信息，请参阅[配置运营商连接移动](operator-connect-mobile-configure.md)。

## <a name="phone-system-with-direct-routing"></a>具有直接路由的电话系统

此选项使用直接路由将电话系统连接到电话网络，如下图所示： 

![图 5 显示了具有直接路由的电话系统。](media/voice-solution-with-direct-routing.png)

如果对以下问题回答“是”，则具有直接路由的电话系统是适合你的解决方案：

- 你希望将 Teams 与电话系统配合使用。
- 需要保留当前的 PSTN 运营商。
- 你想要混合路由，一些调用通过呼叫计划，有些通过你的运营商。
- 需要与第三方 PBX 和/或设备（如开销寻呼机、模拟设备等）进行互操作。

使用此选项：

- 无需其他本地软件，即可将自己的受支持的会话边界控制器 (SBC) 连接到电话系统。

- 你几乎可以将任何电话运营商与电话系统配合使用。

- 可以配置和管理此选项，也可以由运营商或合作伙伴配置和管理此选项 (询问运营商或合作伙伴是否) 提供此选项。

- 可以配置电话设备（例如第三方 PBX 和模拟设备&mdash;&mdash;）与电话系统之间的互操作性。

此选项需要以下各项：

- 与 Microsoft 365 的不间断连接。

- 部署和维护受支持的 SBC。

- 与第三方运营商签订的合同。
   (除非作为选项进行部署，以便为使用通话套餐的电话系统用户提供与第三方 PBX、模拟设备或其他电话设备的连接。) 

有关直接路由的详细信息，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理用于直接路由的语音路由策略](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>配置注意事项

无论选择哪种 PSTN 连接选项，大多数电话系统功能都是相同的。 例如，呼叫未应答和转发设置、呼叫传输、保留自定义音乐、呼叫寄存、共享线路和语音应用均可用。 有关电话系统功能的完整列表，请参阅 [下面的手机系统](here-s-what-you-get-with-phone-system.md)功能。

但是，功能存在一些差异，这会影响配置某些电话系统功能的方式。 例如，直接路由需要其他步骤来配置呼叫路由。 另一个例子是，直接路由提供基于位置的路由 (LBR) 。 LBR 允许在不允许收费的特定地理位置限制通行费旁路。 

下表突出显示了主要配置差异。 表后面的部分提供了指向更多信息和详细信息的链接。

| 选项 | 说明 | 电话号码管理 | 呼叫路由 | 紧急呼叫可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通话套餐 | -Microsoft 充当 PSTN 运营商。<br>-无需购买或管理 SBC。| 通过 Microsoft 获取。| -由 Microsoft 管理。 <br> -管理员为号码转换配置用户拨号计划。 | -由 Microsoft 启用。 <br> -管理员注册地址。 <br> -支持动态调用。 |
| 运算符连接 | -Carrier 管理 PSTN 连接和 SBC。 <br> -无需购买或管理 SBC。 | -通过运营商获取。 <br> - 与运营商管理的紧急地址相关联的数字。 | -由运营商管理。 <br>-管理员为号码转换配置用户拨号计划。 | -由运营商启用。 <br> -管理员注册地址。 <br> -支持动态调用。 |
| 运营商连接移动 | -Carrier 管理SIM-Enabled移动号码、PSTN 连接和 SBC。 <br> -无需购买或管理 SBC。 | -通过运营商获取。 <br> -与运营商管理的紧急地址相关联的数字。 | -由运营商管理。 <br> 管理员为号码转换配置用户拨号计划。 |- 由运营商启用。 <br> - 管理员注册地址。 <br> - 支持动态调用。 <br> - 运营商支持本机拨号器紧急呼叫。 |
| 直接路由 | -需要从第三方供应商处购买的经过认证的 SBC。<br>-将 SBC 连接到电话系统。<br> -使用现有的 PSTN 运营商。 | 通过运营商获取。 | -需要管理员进行额外配置。<br>-管理员为号码转换配置中继拨号计划。 <br>-LBR 可用于限制通行费旁路。 | -需要管理员进行额外配置。 <br>-未支持的已注册地址。 <br>-支持动态调用，但需要其他配置。 |


### <a name="phone-number-management"></a>电话号码管理

Microsoft 有两种可用电话号码类型：订阅者 (用户) 号码（可分配给组织中的用户）和服务号码（可用作收费和免费服务号码）。 服务号码的并发呼叫容量高于订阅者号码，可以分配给音频会议、自动助理或呼叫队列等服务。

需要决定：

- 哪些用户位置需要 Microsoft 提供新的电话号码？
- 我需要哪种类型的电话号码 (订阅者或服务) ？
- 如何实现将现有电话号码移植到 Teams？

获取和管理电话号码方式因 PSTN 连接选项而异。

- 有关管理通话套餐的电话号码的信息，请参阅 [管理通话套餐的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 有关使用 Operator Connect 管理电话号码的信息，请参阅 [使用 Operator Connect 设置电话号码](operator-connect-configure.md#set-up-phone-numbers)。

- 有关使用运营商连接移动管理电话号码的信息，请参阅[使用运营商连接移动设置电话号码](operator-connect-mobile-configure.md#set-up-phone-numbers)。

- 有关管理直接路由的电话号码的信息，请参阅 [配置电话号码并启用企业语音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。

### <a name="call-routing-and-dial-plans"></a>呼叫路由和拨号计划

如何配置呼叫路由因 PSTN 连接选项而异。  

- 对于呼叫计划，大部分呼叫路由由 Microsoft 呼叫计划基础结构处理。 为呼叫授权和呼叫路由配置用于号码转换的用户拨号计划。 有关详细信息，请参阅[什么是拨号计划？](what-are-dial-plans.md)

- 对于运算符连接和运营商连接移动，大部分呼叫路由由运营商管理。 为呼叫授权和呼叫路由配置用于号码转换的用户拨号计划。 有关详细信息，请参阅[什么是拨号计划？](what-are-dial-plans.md)

- 对于直接路由，必须通过指定语音路由并向用户分配语音路由策略来配置呼叫路由。 可以在中继级别配置号码转换的拨号计划，以确保与会话边框控制器 (SBC) 互操作性。 有关详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [翻译电话号码](direct-routing-translate-numbers.md)。 

### <a name="location-based-routing-for-direct-routing"></a>直接路由Location-Based路由

在一些国家和地区，绕过 PSTN 运营商降低长途通话成本是非法的。 Location-Based路由 (直接路由的 LBR) ，可以根据 Teams 用户的地理位置限制通行费旁路。 有关如何规划和配置 LBR 的详细信息，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  介绍虚构的跨国公司 Contoso 如何为其组织实现Location-Based路由。

### <a name="emergency-calling"></a>紧急呼叫

配置紧急呼叫方式因 PSTN 连接选项而异。

- 对于呼叫计划，将自动为每个用户启用紧急呼叫。 用户必须拥有与其分配的电话号码关联的已注册紧急地址。 支持基于 Teams 客户端) 位置的动态紧急呼叫 (。 有关详细信息，请参阅 [通话套餐的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

- 对于 Operator Connect，将自动为每个用户启用紧急呼叫。 用户必须具有与其分配的电话号码关联的已注册紧急地址。 支持基于 Teams 客户端) 位置的动态紧急呼叫 (。 有关详细信息，请参阅 [操作员连接的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect)。 

- 对于运营商连接移动，将自动为每个用户启用紧急呼叫。 对于给定号码，紧急呼叫会自动路由到运营商连接移动运营商。 支持基于 Teams 客户端) 位置的动态紧急呼叫 (。 有关详细信息，请参阅[运营商连接移动的注意](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect-mobile)事项。 

- 对于直接路由，必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 为用户定义紧急呼叫策略。 该策略将定义紧急号码及其关联的路由目标。 直接路由用户不支持注册的紧急位置。 对于动态紧急呼叫，需要其他配置来路由紧急呼叫，并且可能用于合作伙伴连接。 有关详细信息，请参阅 [直接路由的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。

#### <a name="for-more-information"></a>有关详细信息

有关紧急呼叫概念和术语以及如何配置紧急呼叫和动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)<br>
  介绍虚构的多国公司 Contoso 如何对其组织实施紧急呼叫。

### <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须在 Microsoft Teams 中为这些功能配置网络设置。 若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：

- [Microsoft Teams 中云语音功能的网络设置 - 概念和术语](cloud-voice-network-settings.md)
- [在 Microsoft Teams 中管理云语音功能的网络拓扑](manage-your-network-topology.md)
