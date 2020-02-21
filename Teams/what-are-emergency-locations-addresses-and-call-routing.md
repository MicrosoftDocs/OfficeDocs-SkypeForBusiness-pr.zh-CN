---
title: 计划紧急呼叫、紧急地址、紧急呼叫路由、动态紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
description: 了解紧急电话，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: 85a09880c1eec83851208197c008c8aaafac88f6
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161685"
---
# <a name="manage-emergency-calling"></a>管理紧急电话

本文介绍了管理紧急呼叫的概念，其中包括有关紧急地址、动态紧急地址和紧急呼叫路由的信息。 本文使用以下术语：

- **紧急地址**-市政地址-您的组织的办公地点的物理地址或街道地址。

  例如，地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构，并帮助查找紧急呼叫方。

- **置入**-通常为楼层、建筑物、翼形或办公室号码。 "地点" 与紧急地址相关联，以便在大楼内提供更准确的位置。 您可以拥有与紧急地址相关联的无限位数。 例如，如果您的组织有多个建筑物，您可能希望在每个建筑物内包括每个建筑物和每个楼层的位置信息。  

- **紧急地点**-一个位置是市政地址-有一个可选位置。 如果您的企业有多个物理位置，则可能需要多个紧急位置。 

  创建紧急地址时，系统会自动为此地址创建一个唯一的位置 ID。  如果您向某一 "紧急地址" 添加一个位置，例如，向建筑物地址添加一个楼层时，将为 "紧急地址" 和 "地点" 的组合创建一个位置 ID。  在此示例中，将有两个位置 Id：一个用于市政地址;一个用于加入的市政地址和关联位置。

  将紧急位置分配给用户或网站时，它是与用户或网站相关联的唯一位置 ID。

- **已注册地址**-分配给每个呼叫计划用户的紧急地址;它有时被称为静态紧急地址或记录地址。  （注册的地址不适用于直接路由用户。）

使用团队管理中心为呼叫计划用户创建紧急地址。  

>[!Note]
>根据您使用的是电话系统呼叫计划还是适用于 PSTN 连接的电话系统直接路由，您管理紧急呼叫的方式有一些差异。 本文中介绍了这些注意事项。

## <a name="emergency-address-validation"></a>紧急地址验证

若要为用户或网络标识符分配紧急地址，必须确保紧急地址标记为 "已验证"。  地址验证可确保地址是合法的，并且在分配后不能被修改。 

如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则地址会自动标记为 "已验证"。 您不能修改已验证的紧急地址。 因此，如果地址的格式或表示形式发生更改，则必须使用已更新的格式创建新地址。


## <a name="emergency-address-geo-codes"></a>紧急地址地域代码

每个紧急地址都可以具有与其关联的地域代码（纬度和经度）。 这些地理代码用于某些国家/地区，用动态位置帮助您路由紧急电话。 

如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则 geo 代码将自动与紧急地址相关联。 如果使用 PowerShell 定义地址，还可以将地域代码与地址相关联。 但是，Microsoft 建议使用团队管理中心中的 "映射搜索" 功能为通话计划创建紧急地址，这将确保地址已设置格式、验证，并具有相应的 geo 代码。  

>[!Important]
>要将紧急位置分配给网络标识符以进行动态紧急呼叫，紧急地址必须包含相应的 geo 代码。


## <a name="considerations-for-calling-plans"></a>通话计划的注意事项

要了解您所在区域是否有通话计划，请参阅[电话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。


### <a name="emergency-call-enablement"></a>紧急电话支持

每个通话计划用户将自动启用紧急呼叫，并且必须有一个注册的紧急地址与其分配的电话号码相关联。 

当位置必须与电话号码相关联时，取决于国家/地区：

- 例如，在美国和加拿大，如果向用户分配了一个号码，则需要紧急位置。

- 对于其他国家/地区（如欧洲、中东和非洲（EMEA）），当您从 Office 365 获取电话号码或从其他服务提供商或运营商处转移时，需要紧急位置。

### <a name="dynamic-emergency-calling"></a>动态紧急电话

Microsoft 通话计划的动态紧急呼叫提供根据团队客户端的当前位置配置和路由紧急呼叫的功能。 自动路由到相应的公共安全应答点（PSAP）或通知安全桌面人员的能力会有所不同，具体取决于团队用户使用的国家/地区。  

目前，只有美国的通话计划用户可以利用动态位置来路由紧急呼叫，如下所示：

- 如果美国呼叫计划的团队客户在美国动态获取紧急地址，则该地址将用于紧急路由，而不是注册地址，并且呼叫将自动路由到 PSAP 中的地址的服务区域。

- 如果美国通话计划的团队客户端不会动态获取美国内的紧急地址，则注册的紧急地址将用于帮助屏幕和路由呼叫。 但是，在将呼叫者连接到相应的 PSAP 之前，将对呼叫进行筛选以确定是否需要更新的地址。

在美国，您必须配置作为分配给网络标识符的紧急位置的一部分的市政地址，并包括相关联的地域代码。 有关详细信息，请参阅[规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。


### <a name="emergency-call-routing"></a>紧急呼叫路由

当团队通话计划用户拨打紧急号码时，呼叫如何路由到 PSAP 取决于以下情况：

- 紧急地址是否由团队客户端动态确定。

- 紧急地址是否是与用户的电话号码相关联的注册地址。

- 该国家/地区的紧急电话网络。

  **美国：**

  - 如果团队客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫将自动路由到该地理位置的 PSAP 服务。 

  - 如果团队客户端不在租户定义的动态紧急位置，则来自该客户端的紧急呼叫由全国呼叫中心进行筛选，以便在将呼叫转移到该地理位置的 PSAP 服务之前确定呼叫者的位置。

  - 如果紧急呼叫方无法将其紧急位置更新到 "筛选中心"，则该呼叫将转到服务于呼叫者的注册地址的 PSAP。

  **在加拿大、爱尔兰和**英国，紧急电话先进行筛选，以便在将呼叫连接到相应的派遣中心之前确定用户的当前位置。 

  **在法国、德国和西班牙**，紧急呼叫直接路由到 PSAP 与号码关联的紧急地址的服务，无论呼叫者的位置如何。

  **在荷兰**，无论呼叫者的位置如何，都可以将紧急呼叫直接路由到号码的本地区号 PSAP。

  **在澳大利亚**，由运营商合作伙伴配置和路由紧急地址。

  **在日本**，不支持紧急通话。


有关详细信息，请参阅：

- [通话套餐](calling-plan-landing-page.md)

- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>直接路由的注意事项

如果您所在区域没有通话计划，或者您想要保留现有运营商，请考虑[直接路由](direct-routing-landing-page.md)。 有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)和[管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。

### <a name="emergency-call-enablement-and-configuration"></a>紧急电话支持和配置

你必须通过使用 TeamsEmergencyCallRoutingPolicy 定义用于直接路由用户的紧急呼叫策略，以定义紧急号码及其关联的路由目标。 （请注意，直接路由用户不支持注册的紧急位置。）

你可以将 TeamsEmergencyCallRoutingPolicy 分配给团队直接路由用户帐户和/或网络网站。 当团队客户端启动或更改网络连接时，团队将执行客户端所在的网络站点的查找，如下所示：

- 如果 TeamsEmergencyCallRoutingPolicy 与网站关联，则使用网站策略配置紧急呼叫。

- 如果没有与该网站相关联的 TeamsEmergencyCallRoutingPolicy，或者如果客户在未定义的站点上连接，则将使用与该用户帐户关联的 TeamsEmergencyCallRoutingPolicy 配置紧急呼叫。 

- 如果团队客户不能获得 TeamsEmergencyCallRoutingPolicy，则不会为紧急呼叫启用用户。

### <a name="dynamic-emergency-calling"></a>动态紧急电话

直接路由用户的团队客户可以获取动态紧急地址，该地址可用于根据呼叫者的位置动态路由呼叫。 有关详细信息，请参阅[配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing"></a>紧急呼叫路由

TeamsEmergencyCallRoutingPolicy 引用了一个联机 PSTN 使用，它必须具有适当直接路由配置才能将紧急呼叫正确路由到相应的 PSTN 网关。 特别是，必须确保紧急拨号字符串有 OnlineVoiceRoute。 有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。 

（注意：团队客户在紧急号码之前预置 "+" 登录，其方式与 Skype for Business 客户端的功能类似，即 + 911。 将在未来的几个月内修改此行为，这样，进行紧急通话的团队将不再发送号码前面的 "+";即911。）

为直接路由用户动态路由紧急电话的功能会有所不同，具体取决于给定国家内的紧急呼叫网络。 提供两种解决方案：

- 紧急路由服务提供商（仅限美国） 
- 紧急位置标识号码（ELIN）网关应用程序

#### <a name="emergency-routing-service-providers"></a>紧急路由服务提供商

在美国，有许多认证的紧急路线服务提供商（ERSPs）可以根据呼叫方的位置自动路由紧急电话。

- 如果将紧急路线服务提供商集成到直接路由部署中，则会将带有动态获取位置的紧急呼叫自动路由到服务该位置的公共安全应答点（PSAP）。

-  在将呼叫连接到基于更新的位置之前，没有动态获取的位置的紧急电话将首先进行筛选以确定用户的当前位置。

有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-elin-applications"></a>紧急位置标识号码（ELIN）应用程序

会话边框控制器（SBCs）可以包含紧急位置标识号（ELIN）应用程序。 如果将 SBC ELIN 应用程序集成到直接路由部署，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上载到各自 PSTN 中的紧急调用数据库.  使用 ELIN 标识符的团队紧急位置必须匹配 ELIN 应用程序中的位置。

当带有动态获取位置的紧急呼叫被路由到相应的 SBC 时，ELIN 应用程序：

- 分析呼叫方的紧急位置。
- 将位置与 ELIN 记录相匹配。
- 用 ELIN 电话号码替代紧急呼叫方的号码。
- 将呼叫路由到该位置的 PSAP 服务，然后调度程序从上载的 ELIN 记录中获取位置。

在回拨紧急号码后，ELIN 应用程序将对原始紧急呼叫方执行反向拨叫的号码替换。 

有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>安全桌面通知

Microsoft 通话计划和电话系统直接路由都提供了安全桌面通知。

你可以使用 TeamsEmergencyCallingPolicy 配置应在紧急呼叫期间通知的人员，以及通知方式：仅聊天、conferenced 或已静音，但具有取消静音的功能。  你还可以指定用户或组的外部 PSTN 号码呼叫并加入紧急呼叫。 

可以向团队用户帐户授予 TeamsEmergencyCallingPolicy，或将其分配给网络网站，或同时授予这两种帐户。  当团队客户端启动或更改网络连接时，团队会执行客户端所在的网络站点的查找：

- 如果 TeamsEmergencyCallingPolicy 与网络网站相关联，则使用网站策略配置 security 桌面通知。

- 如果没有与该网站相关联的 TeamsEmergencyCallingPolicy，或者客户端连接到了未定义的站点，则将使用与该用户帐户关联的 TeamsEmergencyCallingPolicy 来配置 security 桌面通知。  

- 如果团队客户端无法获取 TeamsEmergencyCallingPolicy，则不会为安全桌面通知启用用户。

在紧急通话期间，安全桌面将 conferenced 到通话中，而安全桌面用户的体验将根据 TeamsEmergencyCallingPolicy 进行控制。 群组聊天已开始于每个 security 书桌成员，紧急呼叫者的位置通过重要消息通知进行共享。  如果将会议选项配置为 "策略" 的一部分，则每个安全桌面用户还会作为会议的一部分进行调用。

    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
