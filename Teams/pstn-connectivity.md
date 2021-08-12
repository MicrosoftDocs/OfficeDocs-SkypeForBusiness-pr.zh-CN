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
description: 详细了解如何Teams PSTN (PSTN) 选项以及您将为组织做出的决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285933"
---
# <a name="pstn-connectivity-options"></a>PSTN 连接选项

Microsoft 通过 Exchange (为) 提供了完整的专用交换机 PBX 电话系统。 但是，若要使用户能够在组织外部进行呼叫，您需要将 电话系统 连接到公用电话交换网 (PSTN) 。

本文重点介绍 PSTN 连接选项。 有关 Microsoft 语音解决方案的详细信息，请参阅规划电话系统功能的详细信息，Teams[语音解决方案](cloud-voice-landing-page.md)。

若要电话系统 PSTN，可以从以下选项中进行选择：

- [**通话套餐**](#phone-system-with-calling-plan)。 使用 Microsoft 作为 PSTN 运营商的全云解决方案。

- [**运算符连接，**](#phone-system-with-operator-connect)当前仅适用于公共 **预览版。**  使用接线员连接，如果你的现有运营商是 Microsoft Operator 连接 计划的参与者，他们可以通过 SDC 管理 PSTN 呼叫和会话边界 (控制器) 。 

- [**直接路由**](#phone-system-with-direct-routing)，使您可以使用自己的 PSTN 运营商，通过将会话边界控制器 (SBC)  (连接到) 电话系统。


您还可以选择一组选项，这些选项使您能够为复杂环境设计解决方案或管理多步骤迁移。

请注意，你选择的选项会影响某些电话系统配置方式。 有关详细信息，请参阅 [本文稍后介绍](#configuration-considerations) 的配置注意事项。


## <a name="phone-system-with-calling-plan"></a>包含通话套餐的电话系统 

电话系统通话套餐是 Microsoft 为用户提供的所有云语音Teams解决方案。 这是将客户端连接到 PSTN 电话系统最简单的选项。 使用此选项，Microsoft 将充当 PSTN 运营商，如下图所示：

![图 1 电话系统通话套餐](media/voice-solutions-simple.png)

如果你对以下内容回答"是"，电话系统通话套餐"是适合你的解决方案：

- 通话套餐在你的地区可用。
- 无需保留当前的 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

使用此选项，您可以实现以下功能： 

- 可获得包含附加国内或国际通话套餐的 Microsoft 电话系统，从而实现全球呼叫（根据授权的服务等级）。

- 无需部署或维护本地部署，因为通话套餐在 &mdash; Microsoft 365。

- 注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作。

此选项需要不间断地连接到 Microsoft 365。

有关通话套餐详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家/地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [设置通话套餐](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>电话系统运算符连接

使用 operator 连接，当前处于公共预览状态，如果现有运营商是 Microsoft Operator 连接 计划的参与者，他们可以管理将 PSTN 呼叫引入 Teams。 你的运营商管理 SDC (PSTN 呼叫服务和会话边界) ，从而节省硬件购买和管理费用。

如果连接运算符，则可能是适合贵组织的解决方案：

- Microsoft 通话套餐在你的地理位置不可用。
- 首选运营商是 Microsoft 运营商计划的参与者连接者。
- 你想要查找新的运营商，以在 Teams。

有关运营商计划的好处和要求连接以及参与该计划的运营商列表，请参阅 Plan [Operator 连接](operator-connect-plan.md)。 若要了解如何配置接线员连接，请参阅 Configure [Operator 连接](operator-connect-configure.md)。


## <a name="phone-system-with-direct-routing"></a>电话系统直接路由

此选项使用电话系统路由将呼叫连接到电话网络，如下图所示： 

![图 5 电话系统直接路由](media/voice-solution-with-direct-routing.png)

如果下列问题的答案为是，包含直接路由的电话系统是正确的解决方案：

- 想要搭配电话系统使用 Teams。
- 需要保留当前的 PSTN 运营商。
- 你想混合路由，部分呼叫通过通话套餐，部分通过运营商。
- 您需要与第三方 PBX 和/或设备（例如开销寻呼机、模拟设备等）进行互操作。

使用此选项，您可以实现以下功能：

- 将自己支持的会话边界控制器 (SBC) 连接到电话系统，而无需其他本地软件。

- 几乎可以将任何电话运营商与 电话系统。

- 可以选择配置和管理此选项，或者选择由运营商或合作伙伴配置和管理（询问运营商或合作伙伴是否提供此选项）。

- 可以在电话设备（如第三方 PBX）和模拟设备和模拟设备之间配置 &mdash; &mdash; 电话系统。

此选项要求如下：

- 不间断地连接到 Microsoft 365。

- 部署和维护支持的 SBC。

- 与第三方运营商签订合同。(除非部署为选项，可供采用包含通话套餐的电话系统的用户连接到第三方 PBX、模拟设备或其他电话服务设备。)

有关直接路由详细信息，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理语音路由策略以用于直接路由](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>配置注意事项

无论电话系统 PSTN 连接选项如何，大多数服务功能都是相同的。 例如，呼叫未呼叫和转接设置、呼叫转移、自定义保持音乐、呼叫等待、共享线路和语音应用都可用。 有关这些功能的完整电话系统，请参阅以下是使用 电话系统 获取[电话系统。](here-s-what-you-get-with-phone-system.md)

但是，在功能上存在一些差异，这会影响你配置某些电话系统方式。 例如，直接路由需要其他步骤来配置呼叫路由。 另一个示例是，直接路由提供基于位置的路由 (LBR) ，以便你可以限制某些不允许收费的地理位置中的收费绕路。 

下表重点介绍主要配置差异。 下表中的各节提供了指向更多信息和详细信息的链接。

| 选项 | 说明 | 电话号码管理 | 呼叫路由 | 紧急呼叫可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通话套餐 | -Microsoft 充当 PSTN 运营商。<br>-无需购买或管理 SDC。| 通过 Microsoft 获取。| -由 Microsoft 管理。 <br> -Admin 为号码转换配置用户拨号计划。 | -由 Microsoft 启用。 <br> -管理员注册地址。 <br> -支持动态呼叫。 |
| 运营商连接 | -运营商管理 PSTN 连接和 SDC。 <br> -无需购买或管理 SDC。 | -通过运营商获取。 <br> - 与运营商管理的紧急地址相关联的号码。  | -由运营商管理。 <br>-Admin 为号码转换配置用户拨号计划。 | -由运营商启用。 <br> -管理员注册地址。 <br> -支持动态呼叫。 |
| 直接路由 | -需要从第三方供应商处购买的经认证的 SBC。<br>-连接 SBC 电话系统。<br> -使用现有的 PSTN 运营商。 | 通过运营商获取。 | -需要管理员进行额外配置。<br>-Admin 配置用于号码转换的中继拨号计划。 <br>-LBR 可用于限制收费绕路。 | -需要管理员进行额外配置。 <br>-不支持已注册的地址。 <br>-支持动态呼叫，但需要其他配置。 |
|||||


### <a name="phone-number-management"></a>电话号码管理

Microsoft 有两种类型的可用电话号码：订阅者 (用户) 号码（可分配给贵组织的用户）和服务号码（作为收费和免费服务号码）。 服务号码的并发呼叫容量高于订阅者号码，可以分配给音频会议、自动助理或呼叫队列等服务。

你将需要决定：

- 哪些用户位置需要来自 Microsoft 的新电话号码？
- 我所需要的订阅 (服务) 电话号码类型？
- 如何将现有电话号码移植到Teams？

获取和管理电话号码方式因 PSTN 连接选项不同而不同。

- 有关管理通话套餐的电话号码的信息，请参阅 [管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 有关使用 Operator 连接 管理电话号码的信息，请参阅使用 Operator 连接[设置电话号码](operator-connect-configure.md#set-up-phone-numbers)。

- 有关管理直接路由的电话号码的信息，请参阅配置 [电话号码并启用企业语音和语音邮件](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。


### <a name="call-routing-and-dial-plans"></a>呼叫路由和拨号计划

配置呼叫路由方式因 PSTN 连接选项不同而不同。  

- 对于通话套餐，大部分呼叫路由由 Microsoft 通话套餐基础结构处理。 配置用户拨号计划以用于呼叫授权和呼叫路由的号码转换。 有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)

- 对于接线连接，大部分呼叫路由由运营商管理。  配置用户拨号计划以用于呼叫授权和呼叫路由的号码转换。 有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)

- 对于直接路由，必须通过指定语音路由并将语音路由策略分配给用户来配置呼叫路由。 您可以在中继级别为号码转换配置拨号计划，以确保与 SDC 或 SDC 之间的会话边界控制器 (互操作性) 。 有关详细信息，请参阅为直接路由配置 [语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [转换电话号码](direct-routing-translate-numbers.md)。 


### <a name="location-based-routing-for-direct-routing"></a>适用于直接路由的基于位置的路由

在一些国家和地区，绕过 PSTN 运营商来降低长途呼叫成本非法。 Location-Based路由 (LBR) 直接路由功能使你可以根据用户的地理位置Teams用户限制收费绕路。 若要详细了解如何计划和配置 LBR，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  描述虚构的跨国公司 Contoso 如何为Location-Based实现路由。


### <a name="emergency-calling"></a>紧急呼叫

配置紧急呼叫方式因 PSTN 连接选项不同而不同。

- 对于"呼叫计划"，每个用户都将自动启用紧急呼叫，并且需要拥有与其分配的电话号码相关联的已注册紧急地址。 支持 (客户端呼叫Teams动态) 呼叫。  

- 对于接线员连接，每个用户都将自动启用紧急呼叫，并且需要拥有与其分配的电话号码相关联的已注册紧急地址，但只能由运营商合作伙伴设置。 支持 (客户端呼叫Teams动态) 呼叫。

- 对于直接路由，必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 定义紧急号码及其关联的路由目标，为用户定义紧急呼叫策略。 直接路由用户不支持已注册的紧急位置。 对于动态紧急呼叫，路由紧急呼叫可能需要其他配置，并且可能需要进行合作伙伴连接。

有关紧急呼叫概念和术语以及如何配置紧急呼叫和动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)<br>
  描述虚构的跨国公司 Contoso 如何为组织实施紧急呼叫。


### <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。 若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：

- [云中云语音功能的网络Microsoft Teams - 概念和术语](cloud-voice-network-settings.md)
- [管理 Microsoft Teams 中云语音功能的网络拓扑](manage-your-network-topology.md)



