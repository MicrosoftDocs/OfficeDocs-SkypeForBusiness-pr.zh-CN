---
title: 计划和管理紧急呼叫
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
- m365initiative-voice
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
- seo-marvel-mar2020
description: 了解紧急呼叫，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: e6904139d73b8fe671c8013af7cac5917fe88305d81af5fd33501d92b81e2d61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316578"
---
# <a name="manage-emergency-calling"></a>管理紧急呼叫

本文介绍管理紧急呼叫时需要知道的概念，其中包括有关紧急地址、动态紧急地址和紧急 &mdash; 呼叫路由的信息。 本文使用以下术语：

- **紧急地址** - 一个街道地址，用于组织的业务 &mdash; 地点的物理地址或街道地址。

  例如，地址  *12345 North Main Street， Redmond， WA 98052* 用于将紧急呼叫路由到相应的调度机构，以及帮助定位紧急呼叫者。

- **地点** - 通常是楼层、建筑物、楼层或办公室号码。 位置与紧急地址相关联，以在建筑物内提供更精确的位置。 你可以将无限数量的地点与紧急地址相关联。 例如，如果组织有多个建筑物，可能需要包括每个建筑物和每个建筑物内每个楼层的位置信息。  

- **紧急位置** - 位置是具有可选位置 &mdash; 的市政地址。 如果你的企业具有多个物理位置，则你可能需要多个紧急位置。 

  创建紧急地址时，会自动为此地址创建唯一的位置 ID。  例如，如果向紧急地址添加位置，则向建筑物地址添加楼层时，将创建一个位置 ID，用于组合使用紧急地址 &mdash; &mdash; 和位置。  本示例将存在两个位置 ID：一个针对市/区地址;一个地址用于已加入的市政地址和关联位置。

  向用户或网站分配紧急位置时，这是与用户或网站关联的此唯一位置 ID。

- **已注册** 的地址 - 分配给每个呼叫计划用户的紧急地址;它有时称为静态紧急地址或记录地址。   (注册的地址不适用于直接路由用户.) 

使用管理中心为呼叫计划用户创建Teams地址。  

>[!Note]
>管理紧急呼叫方式存在一些差异，具体取决于你使用的是电话系统呼叫计划电话系统 PSTN 连接直接路由。 本文中介绍了这些注意事项。

## <a name="emergency-address-validation"></a>紧急地址验证

若要向用户或网络标识符分配紧急地址，必须确保紧急地址标记为"已验证"。  地址验证可确保地址是合法的，并且分配后无法对其进行修改。 

如果使用地址管理中心中的地址映射搜索功能Teams紧急地址，该地址会自动标记为已验证。 无法修改已验证的紧急地址。 因此，如果地址的格式或表示形式发生更改，则必须使用更新的格式创建新地址。


## <a name="emergency-address-geo-codes"></a>紧急地址地理代码

每个紧急地址可以具有与 (和经度) 地理代码。 这些国家/地区使用这些地理代码来帮助通过动态位置路由紧急呼叫。 

如果使用紧急管理中心中的地址映射搜索功能定义Teams地址，则地理代码会自动与紧急地址相关联。 如果使用 PowerShell 定义地址，还可以将地理代码与地址关联。 但是，Microsoft 建议使用 Teams 管理中心中的地图搜索功能为呼叫计划创建紧急地址，这将确保地址经过格式设置、验证并拥有适当的地理代码。  

>[!Important]
>若要为网络标识符分配紧急位置以用于动态紧急呼叫，紧急地址必须包含相应的地理代码。


## <a name="considerations-for-calling-plans"></a>通话套餐注意事项

若要了解呼叫计划在你的区域中是否可用，请参阅通话套餐[的"国家/地区"和"区域可用性"。](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>紧急呼叫启用

每个呼叫计划用户都将自动启用紧急呼叫，并且需要具有与其分配的电话号码相关联的已注册紧急地址。 

当位置必须与电话号码关联时，取决于国家/地区：

- 例如，在美国和加拿大，向用户分配号码时需要紧急位置。

- 对于其他国家/地区（例如欧洲、中东和非洲 (EMEA) ）来说，从 Microsoft 365 或 Office 365 获取电话号码或者从另一服务提供商或运营商转移电话号码时，需要紧急位置。

### <a name="dynamic-emergency-calling"></a>动态紧急呼叫

Microsoft 呼叫计划的动态紧急呼叫提供根据客户端的当前位置配置和路由Teams呼叫的功能。 自动路由到相应的公共安全应答点 (PSAP) 或通知安全服务台人员的能力因使用安全Teams国家/地区而异。  

对于呼叫计划用户，仅美国支持用于路由紧急呼叫的动态位置，如下所示。  (有关动态紧急呼叫和直接路由的信息，请参阅 [直接路由注意事项](#considerations-for-direct-routing)。

- 如果美国Teams计划的客户端动态获取美国内的紧急地址，该地址将用于紧急路由，而不是注册的地址，并且该呼叫将自动路由到地址服务区域中的 PSAP。

- 如果Teams呼叫计划用户的用户客户端未在美国动态获取紧急地址，则注册的紧急地址用于帮助筛选和路由呼叫。 但是，在将呼叫方连接到相应的 PSAP 之前，将筛选呼叫以确定是否要求更新的地址。

在美国，必须配置属于分配给网络标识符的紧急位置的一部分的市政地址，并 &mdash; 包含关联的地理代码。 有关详细信息，请参阅 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。


### <a name="emergency-call-routing"></a>紧急呼叫路由

当Teams呼叫计划用户拨打紧急号码时，呼叫路由到 PSAP 的方式取决于以下条件：

- 紧急地址是否由客户端动态Teams确定。

- 紧急地址是否是与用户电话号码关联的已注册地址。

- 该国家/地区紧急呼叫网络。

  **在美国：**

  - 如果Teams位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫会自动路由到该地理位置服务的 PSAP。 

  - 如果Teams客户端未位于租户定义的动态紧急位置，则国家/地区呼叫中心将筛选来自该客户端的紧急呼叫，以确定呼叫者的位置，然后再将呼叫转接到为该地理位置服务的 PSAP。

  - 如果紧急呼叫者无法将其紧急位置更新到筛选中心，呼叫将转接到 PSAP，为呼叫者注册的地址提供。

  **加拿大、爱尔兰** 和英国将首先筛选紧急呼叫，以确定用户的当前位置，然后再将呼叫连接到相应的调度中心。 

  **法国、德国以及** 西班牙的紧急呼叫将直接路由到 PSAP，为与号码关联的紧急地址提供紧急地址，而不考虑呼叫者的位置。

  **在荷兰，** 紧急呼叫直接路由到 PSAP，该号码的本地区号与呼叫者的位置不同。

  **在澳大利亚**，紧急地址由运营商合作伙伴配置和路由。

  **在日本**，不支持紧急呼叫。


有关详细信息，请参阅：

- [通话套餐](calling-plan-landing-page.md)

- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>直接路由注意事项

如果呼叫计划在你的区域中不可用，或者你想要保留你的现有运营商，请考虑直接 [路由](direct-routing-landing-page.md)。 有关详细信息，请参阅配置[直接路由和管理](direct-routing-configure.md)[紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。

### <a name="emergency-call-enablement-and-configuration"></a>紧急呼叫启用和配置

必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 来定义紧急号码及其关联的路由目标，为直接路由用户定义紧急呼叫策略。  (请注意，直接路由用户.) 

可以将紧急呼叫路由策略Teams直接路由用户帐户和网络站点。 当Teams客户端启动或更改网络连接时，Teams将执行客户端所在的网络站点的查找，如下所示：

- 如果紧急呼叫路由策略与站点关联，则站点策略用于配置紧急呼叫。

- 如果没有与站点关联的紧急呼叫路由策略，或者客户端在未定义的站点连接，则使用与用户帐户关联的紧急呼叫路由策略来配置紧急呼叫。 

- 如果Teams客户端无法获取紧急呼叫路由策略，则用户未启用紧急呼叫。

### <a name="dynamic-emergency-calling"></a>动态紧急呼叫

Teams路由的用户客户端可以获取动态紧急地址，该地址可用于根据调用方的位置动态路由调用。 有关详细信息，请参阅 [配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing"></a>紧急呼叫路由

紧急呼叫路由策略引用联机 PSTN 使用情况，该策略必须具有适当的直接路由配置，以正确将紧急呼叫路由到 (PSTN) 。 具体而言，必须确保紧急拨号字符串有 OnlineVoiceRoute。 有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。 

 (：Teams客户端在紧急号码前面加"+"登录，其方式与Skype for Business类似;即 +911。 这将在几个月内修改此行为，Teams紧急呼叫不再发送号码前面的"+";即 911.) 

根据给定国家/地区内的紧急呼叫网络，为直接路由用户动态路由紧急呼叫的能力有所不同。 有两种可用的解决方案：

- 紧急路由服务提供商 (美国)  
- 紧急位置标识号 (ELIN) 网关应用程序

#### <a name="emergency-routing-service-providers"></a>紧急路由服务提供商

在美国，有许多经过认证的紧急路由服务提供商 (ERSP) 根据呼叫者的位置自动路由紧急呼叫。

- 如果将紧急路由服务提供商集成到直接路由部署中，具有动态获取位置的紧急呼叫将自动路由到提供该位置的公共安全应答点 (PSAP) 。

-  没有动态获取位置的紧急呼叫首先经过筛选，以确定用户的当前位置，然后根据更新的位置将呼叫连接到相应的调度中心。

有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-elin-applications"></a>紧急位置标识号 (ELIN) 应用程序

会话边界控制器 (SBC) ELIN 应用程序 (紧急位置标识) 编号。 如果 SBC ELIN 应用程序集成到直接路由部署中，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上传到相应 PSTN 中的紧急呼叫数据库。  Teams ELIN 标识符的紧急位置必须与 ELIN 应用程序中的位置匹配。

将具有动态获取位置的紧急呼叫路由到相应的 SBC 时，ELIN 应用程序：

- 分析调用方的紧急位置。
- 将位置与 ELIN 记录匹配。
- 将紧急呼叫者的电话号码替换为 ELIN 电话号码。
- 将调用路由到提供该位置的 PSAP，然后调度程序从上传的 ELIN 记录获取位置。

呼叫回紧急号码后，ELIN 应用程序将执行与原始紧急呼叫者相反的呼叫号码替换。 

有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>安全服务台通知

安全服务台通知可用于 Microsoft 呼叫计划和 电话系统直接路由。

使用 Teams 紧急呼叫策略 (TeamsEmergencyCallingPolicy) 来配置在紧急呼叫期间应通知哪些人以及如何通知他们：仅聊天、参加会议和静音，或者已进入和静音但能够取消静音。  您还可以指定要呼叫和加入紧急呼叫的用户或组的外部 PSTN 号码。 

紧急呼叫策略可以授予用户Teams或分配给网络站点。  当Teams客户端启动或更改网络连接时，Teams将执行客户端所在的网络站点的查找：

- 如果紧急呼叫策略与网络站点相关联，则站点策略用于配置安全服务台通知。

- 如果没有与站点关联的紧急呼叫策略，或者客户端在未定义的站点连接，则与用户帐户关联的紧急呼叫策略用于配置安全服务台通知。  

- 如果Teams客户端无法获取紧急呼叫策略，则用户未启用安全服务台通知。

在紧急呼叫期间，安全服务台将参加会议，安全服务台用户的体验根据紧急呼叫Teams控制。 与每个安全服务台成员开始群组聊天，紧急呼叫者的位置通过重要消息通知共享。  如果将会议选项配置为策略的一部分，则额外调用每个安全服务台用户作为会议的一部分。

    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
