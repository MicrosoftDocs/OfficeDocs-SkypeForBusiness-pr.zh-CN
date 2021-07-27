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
description: 详细了解如何Teams PSTN (连接) 选项以及您将为组织做出的决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57327c408331acb3deb4d2269d87a2a30de13a75
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486252"
---
# <a name="pstn-connectivity-options"></a>PSTN 连接选项

Microsoft 通过 EXCHANGE (为) 提供完整的专用分支和 PBX 电话系统。 但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。

本文重点介绍 PSTN 连接选项。 有关 Microsoft 语音解决方案的详细信息，请参阅规划语音电话系统的详细信息，Teams[解决方案](cloud-voice-landing-page.md)。

若要电话系统 PSTN，可以从以下选项中进行选择：

- [**调用计划**](#phone-system-with-calling-plan)。 以 Microsoft 作为 PSTN 运营商的全云解决方案。

- [**运算符连接，**](#phone-system-with-operator-connect)目前仅在公共预览 **版中提供。**  使用运营商连接，如果你的现有运营商是 Microsoft 运营商 连接 计划的参与者，他们可以管理 PSTN 呼叫和会话边界控制器 (SDC) 。 

- [**直接路由**](#phone-system-with-direct-routing)，通过连接会话边界控制器和 SBC (，)  (使用自己的 PSTN) 电话系统。


还可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移。

请注意，选择的选项会影响某些电话系统的配置方式。 有关详细信息，请参阅 [本文稍后的配置](#configuration-considerations) 注意事项。


## <a name="phone-system-with-calling-plan"></a>电话系统套餐 

电话系统套餐"是 Microsoft 为用户提供的所有云中语音Teams解决方案。 这是将客户端连接到 PSTN 电话系统最简单的选项。 使用此选项，Microsoft 将充当 PSTN 运营商，如下图所示：

![图 1 电话系统套餐](media/voice-solutions-simple.png)

如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：

- 呼叫计划在你的地区可用。
- 无需保留当前 PSTN 运营商。
- 您希望使用 Microsoft 托管的 PSTN 访问权限。

使用此选项： 

- 你可以Microsoft 电话系统添加国内或国际呼叫计划，这些套餐支持拨打世界各地的电话 (具体取决于获得许可的服务) 。

- 不需要部署或维护本地部署，因为调用计划 &mdash; 在Microsoft 365。

- 注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。

此选项需要不间断地连接到 Microsoft 365。

有关呼叫计划详细信息，请参阅以下文章：

- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [如何购买通话套餐](calling-plans-for-office-365.md)
- [通话套餐的国家和地区可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [设置呼叫计划](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>电话系统运算符连接

使用运营商连接（目前为公共预览版）时，如果你的现有运营商是 Microsoft 运营商 连接 计划的参与者，他们可以管理将 PSTN 呼叫引入 Teams。 运营商管理 PSTN 呼叫服务和会话边界控制器 (SDC) ，从而节省硬件购买和管理费用。

如果连接，操作员管理可能是适合组织的解决方案：

- Microsoft 呼叫计划在你的地理位置不可用。
- 首选运营商是 Microsoft 运营商运营连接参与者。
- 您希望查找新的运营商以在 Teams。

有关运营商运营商权益和要求连接，有关参与此计划的运营商列表，请参阅计划运营商[连接。](operator-connect-plan.md) 若要了解如何配置运算符连接，请参阅[配置运算符连接。](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>电话系统直接路由

此选项使用电话系统路由将线路连接到电话网络，如下图所示： 

![图 5 显示电话系统直接路由的路由](media/voice-solution-with-direct-routing.png)

如果对以下问题回答"是"，电话系统直接路由是适合的解决方案：

- 想要将 Teams 与 电话系统。
- 你需要保留当前的 PSTN 运营商。
- 您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。
- 需要和第三方 PBX 和/或设备（例如我们的开销寻呼机、模拟设备等）互操作。

使用此选项：

- 将自己的受支持会话边界控制器 (SBC) 连接到 电话系统，而无需其他本地软件。

- 你几乎可以使用任何电话运营商和电话系统。

- 您可以选择配置和管理此选项，也可以由运营商或合作伙伴组织配置和管理 (询问运营商或合作伙伴是否提供此选项) 。

- 可以在电话设备（例如第三方 PBX）与模拟设备和模拟设备之间配置 &mdash; &mdash; 电话系统。

此选项需要以下各项：

- 不间断地连接到 Microsoft 365。

- 部署和维护支持的 SBC。

- 与第三方运营商的合同。
   (除非部署为为使用呼叫计划.电话系统的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) 

有关直接路由详细信息，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)
- [配置直接路由](direct-routing-configure.md)
- [管理用于直接路由的语音路由策略](manage-voice-routing-policies.md)
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [经认证可用于直接路由的会话边界控制器列表](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>配置注意事项

无论电话系统 PSTN 连接选项，大多数服务功能都是相同的。 例如，呼叫未回声和转接设置、呼叫转接、保留的自定义音乐、呼叫公园、共享线路和语音应用都可用。 有关这些功能的完整电话系统列表，请参阅此处是使用[电话系统。](here-s-what-you-get-with-phone-system.md)

但是，功能存在一些差异，这会影响你配置某些电话系统方式。 例如，直接路由需要额外的步骤来配置呼叫路由。 另举一例，直接路由提供基于位置的路由 (LBR) ，以便你可以限制某些不允许的地理位置的收费绕过。 

下表突出显示了主要配置差异。 下表中的各节提供了更多信息和详细信息的链接。

| 选项 | 说明 | 电话数字管理 | 呼叫路由 | 紧急呼叫可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通话套餐 | -Microsoft 充当 PSTN 运营商。<br>-无需购买或管理 SDC。| 通过 Microsoft 获取。| -由 Microsoft 管理。 <br> -Admin 为号码转换配置用户拨号计划。 | -由 Microsoft 启用。 <br> -Admin 注册地址。 <br> -支持动态调用。 |
| 运算符连接 | -Carrier 管理 PSTN 连接和 SDC。 <br> -无需购买或管理 SDC。 | -通过运营商获取。 <br> - 与运营商管理的紧急地址关联的号码。  | -由运营商管理。 <br>-Admin 为号码转换配置用户拨号计划。 | -由运营商启用。 <br> -Admin 注册地址。 <br> -支持动态调用。 |
| 直接路由 | -需要从第三方供应商处购买的经过认证的 SBC。<br>-连接 SBC 电话系统。<br> -使用现有的 PSTN 运营商。 | 通过运营商获取。 | -需要管理员的额外配置。<br>-Admin 为号码转换配置中继拨号计划。 <br>-LBR 可用于限制收费绕过。 | -需要管理员的额外配置。 <br>-注册的地址不受支持。 <br>-支持动态调用，但需要其他配置。 |
|||||


### <a name="phone-number-management"></a>电话数字管理

Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。 服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。

需要确定：

- 哪些用户位置需要 Microsoft 提供的新电话号码？
- 需要哪种类型的 (或) 电话号码？
- 如何将现有电话号码移植到Teams？

根据 PSTN 连接选项，你获取和管理电话号码的不同。

- 有关管理呼叫计划的电话号码的信息，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 有关使用接线员管理电话号码连接，[请参阅使用](operator-connect-configure.md#set-up-phone-numbers)接线员连接。

- 有关管理直接路由的电话号码的信息，请参阅配置 [电话号码并启用企业语音和语音邮件](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。


### <a name="call-routing-and-dial-plans"></a>呼叫路由和拨号计划

您的呼叫路由配置方式因 PSTN 连接选项的不同而不同。  

- 对于呼叫计划，大多数呼叫路由由 Microsoft 呼叫计划基础结构处理。 为呼叫授权和呼叫路由配置用户拨号计划，以便进行号码转换。 有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)

- 对于运营商连接，大多数呼叫路由由运营商管理。  为呼叫授权和呼叫路由配置用户拨号计划，以便进行号码转换。 有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)

- 对于直接路由，必须通过指定语音路由并将语音路由策略分配给用户来配置呼叫路由。 可以在中继级别为号码转换配置拨号计划，以确保与会话边界控制器 (SDC) 。 有关详细信息，请参阅配置直接 [路由的语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [转换电话号码](direct-routing-translate-numbers.md)。 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在某些国家和地区，绕过 PSTN 运营商降低长途呼叫费用非法。 Location-Based直接 (LBR) ，可基于用户的地理位置限制Teams用户免收费。 若要详细了解如何计划和配置 LBR，请参阅以下文章：

- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  介绍虚拟的多语言公司 Contoso 如何为Location-Based实现路由。


### <a name="emergency-calling"></a>紧急呼叫

根据 PSTN 连接选项，紧急呼叫配置方式有所不同。

- 对于"呼叫计划"，每个用户会自动启用紧急呼叫，并且需要具有与其分配的电话号码相关联的已注册紧急地址。 支持 (客户端服务位置Teams动态) 紧急呼叫。  

- 对于接线连接，会自动为每个用户启用紧急呼叫，并且要求具有与其分配的电话号码相关联的已注册紧急地址，但只能由运营商合作伙伴设置。 支持 (客户端服务位置Teams动态) 紧急呼叫。

- 对于直接路由，必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 来定义紧急号码及其关联的路由目标，为用户定义紧急呼叫策略。 直接路由用户不支持已注册的紧急位置。 对于动态紧急呼叫，需要其他配置才能路由紧急呼叫，并可能需要进行合作伙伴连接。

有关紧急呼叫的概念和术语以及如何配置紧急呼叫和动态紧急呼叫的详细信息，请参阅以下文章：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)<br>
  介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。


### <a name="network-topology-for-voice-features"></a>语音功能的网络拓扑

如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。 若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：

- [云语音功能网络设置Microsoft Teams - 概念和术语](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑Microsoft Teams](manage-your-network-topology.md)



