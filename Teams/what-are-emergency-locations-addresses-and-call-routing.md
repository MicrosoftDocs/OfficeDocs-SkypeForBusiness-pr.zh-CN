---
title: 计划和管理紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 了解紧急呼叫，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: f6c1dd766ae14d855b9f2ffcf21c41ed8a5a1550
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634861"
---
# <a name="manage-emergency-calling"></a>管理紧急呼叫

本文介绍管理紧急呼叫时需要知道的概念，其中包括有关紧急地址、动态紧急地址和紧急 &mdash; 呼叫路由的信息。 本文使用以下术语：

- **紧急地址** - 一个街道地址，用于组织的业务 &mdash; 地点的物理地址或街道地址。

  例如，地址 *12345 North Main Street， Redmond， WA 98052* 用于将紧急呼叫路由到相应的调度机构，以及帮助定位紧急呼叫者。

- **地点** - 通常是楼层、建筑物、楼层或办公室号码。 位置与紧急地址相关联，以在建筑物内提供更精确的位置。 你可以将无限数量的地点与紧急地址相关联。 例如，如果你的组织有多个建筑物，你可能希望包含每个建筑物和每个建筑物内每个楼层的位置信息。  

- **紧急位置** - 位置是具有可选位置 &mdash; 的市政地址。 如果你的企业具有多个物理位置，则你可能需要多个紧急位置。 

  创建紧急地址时，会自动为此地址创建唯一的位置 ID。 例如，如果向紧急地址添加位置，则向建筑物地址添加楼层时，将创建一个位置 ID，用于组合使用紧急地址 &mdash; &mdash; 和位置。  本示例将存在两个位置 ID：一个针对市/区地址;一个地址用于已加入的市政地址和关联位置。

  将紧急位置分配给用户或网站时，这是与用户或网站关联的此唯一位置 ID。

- **注册地址** - 分配给每个用户的紧急地址。 注册的地址有时称为静态紧急地址或记录地址。  (，直接路由目前不支持注册的地址。 请尽快返回查看更新。) 

>[!Note]
>根据 PSTN 连接使用的是 Microsoft 呼叫计划、接线员连接还是直接路由，紧急呼叫管理方式存在一[些差异](pstn-connectivity.md)。 本文中介绍了这些注意事项。

## <a name="emergency-address-validation"></a>紧急地址验证

若要向用户或网络标识符分配紧急地址，必须确保紧急地址标记为"已验证"。 地址验证可确保地址是合法的，并且分配后无法对其进行修改。 

如果使用地址映射搜索功能在 Teams 中心定义紧急地址，该地址会自动标记为已验证。 由于如果地址的格式或表示形式发生更改，则不能修改已验证的紧急地址，因此必须使用更新的格式创建新 &mdash; 地址。


## <a name="emergency-address-geo-codes"></a>紧急地址地理代码

每个紧急地址可以具有与 (和经度) 地理代码。 这些国家/地区使用这些地理代码来帮助通过动态位置路由紧急呼叫。 

如果使用地址映射搜索功能在 Teams 中心定义紧急地址，则地理代码会自动与紧急地址相关联。 如果使用 PowerShell 定义地址，还可以将地理代码与地址关联。 

Microsoft 建议使用 Teams 管理中心中的地图搜索功能创建紧急地址，该功能将确保地址经过格式设置、验证并拥有适当的地理代码。 

>[!Important]
>若要为网络标识符分配紧急位置以用于动态紧急呼叫，紧急地址必须包含相应的地理代码。


## <a name="considerations-for-calling-plans"></a>通话套餐注意事项

以下部分介绍如何管理 Microsoft 呼叫计划用户的紧急呼叫。 若要了解 Microsoft 呼叫计划是否适合你的企业，请参阅 [PSTN 连接选项](pstn-connectivity.md)。


### <a name="emergency-call-enablement-for-calling-plans"></a>为呼叫计划启用紧急呼叫

每个呼叫计划用户会自动启用紧急呼叫，并且需要具有与其分配的电话号码相关联的已注册紧急地址。 

当位置与电话号码关联时，取决于国家/地区：

- 例如，在美国和加拿大，向用户分配号码时需要紧急位置。

- 对于欧洲、中东和非洲 (EMEA) 等其他国家/地区) 当您从 Microsoft 365 获取电话号码或者从另一服务提供商或运营商转移电话号码时，需要紧急位置。 &mdash; &mdash;


### <a name="dynamic-emergency-calling-for-calling-plans"></a>呼叫计划的动态紧急呼叫

呼叫计划的动态紧急呼叫提供基于呼叫客户端的当前位置配置和路由Teams呼叫的功能。 自动路由到相应的公共安全应答点 (PSAP) 或通知安全服务台人员的能力因使用安全Teams国家/地区而异。  

美国支持用于路由紧急呼叫的动态位置，如下所示。 

- 如果美国呼叫Teams用户的客户端动态获取美国内的紧急地址，该地址将用于紧急路由，而不是注册的地址，并且该呼叫将自动路由到地址服务区域中的 PSAP。

- 如果Teams呼叫计划用户的用户客户端未在美国动态获取紧急地址，则注册的紧急地址用于帮助筛选和路由呼叫。 但是，在将呼叫方连接到相应的 PSAP 之前，将筛选呼叫以确定是否要求更新的地址。

加拿大支持将紧急呼叫路由到的动态位置，但美国除外：所有紧急呼叫都将在传输到 PSAP 之前进行国内筛选。

有关详细信息，请参阅 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-calling-plans"></a>呼叫计划的紧急呼叫路由

当Teams呼叫计划用户拨打紧急号码时，呼叫路由到 PSAP 的方式取决于以下条件：

- 紧急地址是否由客户端动态Teams确定。

- 紧急地址是否是与用户电话号码关联的已注册地址。

- 该国家/地区紧急呼叫网络。

例如：

**在美国：**

- 如果Teams客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫会自动路由到提供该地理位置的 PSAP。

- 如果Teams客户端未位于租户定义的动态紧急位置，则国家/地区呼叫中心会筛选来自该客户端的紧急呼叫，以确定呼叫者的位置，然后再将呼叫转接到为该地理位置服务的 PSAP。

- 如果紧急呼叫者无法将其紧急位置更新到筛选中心，呼叫将转接到 PSAP，为呼叫者注册的地址提供。

**加拿大、爱尔兰** 和英国将首先筛选紧急呼叫，以确定用户的当前位置，然后再将呼叫连接到相应的调度中心。

**法国、德国以及** 西班牙的紧急呼叫将直接路由到 PSAP，为与号码关联的紧急地址提供紧急地址，而不考虑呼叫者的位置。

**在荷兰，** 紧急呼叫将直接路由到 PSAP，该号码的本地区号与呼叫者的位置不同。

**在澳大利亚**，紧急地址由运营商合作伙伴配置和路由。

**在日本**，不支持紧急呼叫。


有关详细信息，请参阅：

- [通话套餐](calling-plan-landing-page.md)
- [设置通话套餐](set-up-calling-plans.md)
- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>操作员管理注意事项连接

以下部分介绍如何为接线员和连接呼叫。 若要了解接线员连接是否是适合你的企业的解决方案，请参阅[PSTN 连接选项](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-operator-connect"></a>为接线员启用紧急呼叫连接

每个接线员连接自动启用紧急呼叫。 紧急呼叫将自动路由到运营商连接运营商为给定号码。

租户管理员为接线员 连接 用户设置注册地址的能力取决于运营商将其上传到客户库存时分配给号码的功能。 根据此设置，租户管理员可能（也可能不需要）设置、修改 &mdash; &mdash; 或删除用户的紧急位置。 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>接线员电话的动态紧急连接

对于接线员连接动态紧急呼叫，能够根据客户端的当前位置配置和路由Teams呼叫。 自动路由到相应的公共安全应答点 (PSAP) 或通知安全服务台人员的能力因使用安全Teams国家/地区而异。 

美国支持用于路由紧急呼叫的动态位置，如下所示。 

- 如果美国用户的 Teams 客户端动态获取美国内的紧急地址，该地址将用于紧急路由，而不是注册的地址，呼叫将自动路由到地址服务区域中的 PSAP。

- 如果Teams用户的用户客户端未在美国动态获取紧急地址，则注册的紧急地址用于帮助筛选和路由呼叫。 但是，在将呼叫方连接到相应的 PSAP 之前，将筛选呼叫以确定是否要求更新的地址。

加拿大支持将紧急呼叫路由到的动态位置，但美国除外：所有紧急呼叫都将在传输到 PSAP 之前进行国内筛选。

有关详细信息，请参阅 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-operator-connect"></a>接线员呼叫的紧急呼叫连接

当用户Teams接线员连接紧急号码时，呼叫路由到 PSAP 的方式取决于以下条件：

- 紧急地址是否由客户端动态Teams确定。

- 紧急地址是否是与用户电话号码关联的已注册地址。

- 该国家/地区紧急呼叫网络。

- 在美国和加拿大，动态路由是运营商服务的一部分。 不需要从另一个服务提供商处购买此服务。

在美国和加拿大：

- 如果Teams客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫会自动路由到提供该地理位置的 PSAP。

- 如果Teams客户端未位于租户定义的动态紧急位置，则国家/地区呼叫中心会筛选来自该客户端的紧急呼叫，以确定呼叫者的位置，然后再将呼叫转接到为该地理位置服务的 PSAP。

- 如果紧急呼叫者无法将其紧急位置更新到筛选中心，呼叫将转接到 PSAP，为呼叫者注册的地址提供。


## <a name="considerations-for-direct-routing"></a>直接路由注意事项

以下部分介绍如何管理直接路由用户的紧急呼叫。 若要了解直接路由是否是适合你的企业的解决方案，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-direct-routing"></a>直接路由的紧急呼叫启用

对于直接路由，必须使用紧急呼叫路由策略来定义紧急呼叫Teams紧急呼叫[](manage-emergency-call-routing-policies.md)策略来定义紧急号码及其关联的路由目标。  (，直接路由用户.) 

可以将紧急呼叫路由策略分配给直接路由用户帐户和网络站点，或同时分配两者。 当Teams客户端启动或更改网络连接时，Teams将执行客户端所在的网络站点的查找，如下所示：

- 如果紧急呼叫路由策略与站点关联，则站点策略用于配置紧急呼叫。

- 如果没有与网站关联的紧急呼叫路由策略，如果客户端在未定义的站点连接，或者拨打的号码与与网站关联的紧急呼叫路由策略中定义的任何紧急号码不匹配，则使用与用户帐户关联的紧急呼叫路由策略来配置紧急呼叫。 

- 如果Teams客户端无法获取紧急呼叫路由策略，则用户未启用紧急呼叫。


### <a name="dynamic-emergency-calling-for-direct-routing"></a>直接路由的动态紧急呼叫

直接路由的动态紧急呼叫提供基于客户端当前位置配置和路由紧急Teams的功能。 自动路由到相应的公共安全应答点 (PSAP) 或通知安全服务台人员的能力因使用安全Teams国家/地区而异。

对于直接路由用户，仅美国支持路由紧急呼叫的动态位置，如下所示：

-   如果Teams直接路由用户的客户端动态获取美国内的紧急地址，该地址将用于紧急路由，呼叫将自动路由到地址服务区域中的 PSAP。

-   如果Teams直接路由用户的客户端未在美国动态获取紧急地址，将筛选呼叫以确定在将呼叫方连接到相应的 PSAP 之前，是否要求更新的地址。

加拿大支持将紧急呼叫路由到的动态位置，但美国除外：所有紧急呼叫都将在传输到 PSAP 之前进行国内筛选。

有关详细信息，请参阅 [配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-direct-routing"></a>直接路由的紧急呼叫路由

直接路由的紧急呼叫路由策略引用联机 PSTN 使用情况，该策略必须具有适当的直接路由配置，以正确将紧急呼叫路由到 (PSTN) 。 具体而言，必须确保紧急拨号字符串有 OnlineVoiceRoute。 有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。 

> [!NOTE]
> Teams客户端不再在紧急号码前面加"+"号;即 +911。 因此，Teams紧急呼叫将不再发送 911 号码之前的"+"。 请确保语音路由模式反映此更改。

根据给定国家/地区内的紧急呼叫网络，为直接路由用户动态路由紧急呼叫的能力有所不同。 有两种可用的解决方案：

- [紧急路由服务提供商 (美国) ](#emergency-routing-service-providers)
- [紧急位置标识号应用程序](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>紧急路由服务提供商

在美国，有许多经过认证的紧急路由服务提供商 (ERSP) 根据呼叫者的位置自动路由紧急呼叫。

- 如果紧急路由服务提供商集成到直接路由部署中，具有动态获取位置的紧急呼叫将自动路由到提供该位置的公共安全应答点 (PSAP) 。

-  没有动态获取位置的紧急呼叫首先经过筛选，以确定用户的当前位置，然后根据更新的位置将呼叫连接到相应的调度中心。

有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-applications"></a>紧急位置标识号应用程序

会话边界控制器 (SDC) 包括 ELIN (紧急位置标识) 编号。 如果 SBC ELIN 应用程序集成到直接路由部署中，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上传到相应 PSTN 中的紧急呼叫数据库。 Teams ELIN 标识符的紧急位置必须与 ELIN 应用程序中的位置匹配。

将具有动态获取位置的紧急呼叫路由到相应的 SBC 时，ELIN 应用程序：

- 分析调用方的紧急位置。
- 将位置与 ELIN 记录匹配。
- 将紧急呼叫者的电话号码替换为 ELIN 电话号码。
- 将调用路由到提供该位置的 PSAP，然后调度程序从上传的 ELIN 记录获取位置。

呼叫回紧急号码后，ELIN 应用程序将执行与原始紧急呼叫者相反的呼叫号码替换。 

有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>安全服务台通知

安全服务台通知可用于 Microsoft 呼叫计划、接线员连接和直接路由。

使用 Teams 紧急呼叫策略 (TeamsEmergencyCallingPolicy) 来配置在紧急呼叫期间应通知谁以及如何通知他们：仅聊天、参加会议和静音，或者已进入和静音但能够取消静音。 您还可以指定要呼叫和加入紧急呼叫的用户或组的外部 PSTN 号码。 请注意，不允许 PSTN 群取消静音。

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
