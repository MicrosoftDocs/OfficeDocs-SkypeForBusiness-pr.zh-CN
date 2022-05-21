---
title: 规划和管理紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
ms.openlocfilehash: 2806499e81b524168944e6cca2e9a6acb4d0b6a7
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624126"
---
# <a name="manage-emergency-calling"></a>管理紧急呼叫

本文介绍管理紧急呼叫&mdash;所需的概念，包括有关紧急地址、动态紧急地址和紧急呼叫路由的信息。 本文使用以下术语：

- **紧急地址** - 公民地址&mdash;，为组织提供营业场所的物理或街道地址。

  例如，地址 *12345 北主街，雷德蒙德，WA 98052* 用于将紧急呼叫路由到适当的调度当局，并协助找到紧急呼叫者。

- **位置** - 通常为楼层、建筑物、机翼或办公号码。 Place 与紧急地址相关联，以便在建筑物中提供更精确的位置。 可以有无限数量的与紧急地址关联的地点。 例如，如果你的组织有多个建筑物，你可能希望包含每栋建筑和每栋建筑内每个楼层的位置信息。  

- **紧急位置** - 位置是具有可选地点的公民地址&mdash;。 如果你的企业有多个物理位置，则可能需要多个紧急位置。 

  创建紧急地址时，会自动为此地址创建唯一的位置 ID。 如果将一个位置添加到紧急地址&mdash;，则如果将楼层添加到建筑物地址&mdash;位置 ID，则会为紧急地址和位置的组合创建。  在此示例中，将有两个位置 ID：一个用于公民地址;一个用于联接的公民地址和关联的地方。

  将紧急位置分配给用户或站点时，与用户或站点关联的唯一位置 ID。

- **已注册的地址** - 分配给每个用户的紧急地址。 注册的地址有时称为静态紧急地址或记录地址。  (目前，直接路由不支持注册的地址。 请尽快回来查看 updates.) 

>[!Note]
>管理紧急呼叫的方式存在一些差异，具体取决于是使用 Microsoft 呼叫计划、运营商连接还是直接路由来[实现 PSTN 连接](pstn-connectivity.md)。 本文中介绍了这些注意事项。

## <a name="emergency-address-validation"></a>紧急地址验证

若要向用户或网络标识符分配紧急地址，必须确保紧急地址标记为“已验证”。 地址验证可确保地址合法，并且在分配地址后无法对其进行修改。 

如果在Teams管理中心使用地址映射搜索功能定义紧急地址，则该地址会自动标记为已验证。 由于如果地址的格式或表示形式发生更改，则无法修改已验证的紧急地址&mdash;，因此必须使用更新的格式创建新地址。


## <a name="emergency-address-geo-codes"></a>紧急地址地理代码

每个紧急地址可以具有与之关联的地理代码 (纬度和经度) 。 这些地理代码在某些国家/地区用于帮助通过动态位置路由紧急呼叫。 

如果在Teams管理中心使用地址地图搜索功能定义紧急地址，则地理代码会自动与紧急地址相关联。 如果使用 PowerShell 定义地址，还可以将地理代码与地址相关联。 

Microsoft 建议使用Teams管理中心中的地图搜索功能创建紧急地址，这将确保地址格式化、验证并具有适当的地理代码。 

>[!Important]
>若要将紧急位置分配给网络标识符以进行动态紧急呼叫，紧急地址必须包含适当的地理代码。


## <a name="considerations-for-calling-plans"></a>通话套餐的注意事项

以下部分介绍如何管理 Microsoft 呼叫计划用户的紧急呼叫。 若要了解 Microsoft 通话套餐是否适合你的业务，请参阅 [PSTN 连接选项](pstn-connectivity.md)。


### <a name="emergency-call-enablement-for-calling-plans"></a>呼叫计划的紧急呼叫启用

每个呼叫计划用户自动启用紧急呼叫，并且需要有与其分配的电话号码关联的已注册紧急地址。 

与电话号码关联的位置取决于国家/地区：

- 例如，在美国和加拿大，当向用户分配数字时，需要紧急位置。

- 对于其他国家&mdash;（如欧洲、中东和非洲） (EMEA) &mdash;从Microsoft 365获取电话号码或从其他服务提供商或运营商转移电话号码时，需要紧急位置。


### <a name="dynamic-emergency-calling-for-calling-plans"></a>呼叫计划的动态紧急呼叫

针对呼叫计划的动态紧急呼叫提供根据Teams客户端的当前位置配置和路由紧急呼叫的功能。 自动路由到适当的公共安全应答点 (PSAP) 或通知安全部门人员的能力因Teams用户的使用情况而异。  

美国支持路由紧急呼叫的动态位置，如下所示。 

- 如果美国呼叫计划用户的Teams客户端动态获取美国中的紧急地址，则该地址用于紧急路由而不是已注册的地址，并且呼叫将自动路由到地址服务区域中的 PSAP。

- 如果美国呼叫计划用户的Teams客户端未在美国中动态获取紧急地址，则使用注册的紧急地址帮助筛选和路由呼叫。 但是，在将调用方连接到相应的 PSAP 之前，将筛选调用以确定是否需要更新的地址。

加拿大支持路由紧急呼叫的动态位置，与美国中相同，但以下例外情况是：所有紧急呼叫在转移到 PSAP 之前将在全国范围内进行筛选。

有关详细信息，请参阅 [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-calling-plans"></a>呼叫计划的紧急呼叫路由

当Teams呼叫计划用户拨打紧急号码时，如何将呼叫路由到 PSAP 取决于以下内容：

- 紧急地址是否由Teams客户端动态确定。

- 紧急地址是否是与用户电话号码关联的已注册地址。

- 该国的紧急呼叫网络。

例如：

**在美国中：**

- 如果Teams客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫会自动路由到服务于该地理位置的 PSAP。

- 如果Teams客户端不在租户定义的动态紧急位置，则国家呼叫中心会对来自该客户端的紧急呼叫进行筛选，以确定调用方的位置，然后再将呼叫转移到为该地理位置提供服务的 PSAP。

- 如果紧急呼叫者无法将其紧急位置更新到筛选中心，则呼叫将传输到为呼叫者注册地址提供服务的 PSAP。

**在加拿大、爱尔兰和联合王国**，在将呼叫连接到相应的调度中心之前，首先会对紧急呼叫进行筛选，以确定用户的当前位置。

**在法国、德国和西班牙**，无论呼叫者的位置如何，紧急呼叫都直接路由到 PSAP，提供与号码相关联的紧急地址。

**在荷兰**，无论呼叫者的位置如何，紧急呼叫都直接路由到 PSAP，以获取号码的本地区域代码。

**在澳大利亚**，紧急地址由运营商合作伙伴配置和路由。

**在日本**，不支持紧急呼叫。


有关详细信息，请参阅：

- [通话套餐](calling-plan-landing-page.md)
- [设置通话套餐](set-up-calling-plans.md)
- [用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>运营商连接的注意事项

以下部分介绍如何管理运营商连接用户的紧急呼叫。 若要了解运营商连接是否适合你的业务，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-operator-connect"></a>运营商连接的紧急呼叫启用

每个运营商连接用户都会自动启用紧急呼叫。 对于给定号码，紧急呼叫会自动路由到运营商连接运营商。

租户管理员为运营商连接用户设置注册地址的能力取决于当承运商将其上传到客户清单时分配给数字的功能。 根据此设置，租户管理员可以设置、修改或删除用户的紧急位置，也可能不是必需&mdash;&mdash;的。 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>动态紧急呼叫运营商连接

动态紧急调用运营商连接提供根据Teams客户端的当前位置配置和路由紧急呼叫的功能。 自动路由到适当的公共安全应答点 (PSAP) 或通知安全部门人员的能力因Teams用户的使用情况而异。 

美国支持路由紧急呼叫的动态位置，如下所示。 

- 如果美国用户的Teams客户端动态获取美国中的紧急地址，则该地址用于紧急路由而不是注册地址，并且呼叫将自动路由到地址服务区域中的 PSAP。

- 如果美国用户的Teams客户端未在美国中动态获取紧急地址，则使用注册的紧急地址帮助筛选和路由呼叫。 但是，在将调用方连接到相应的 PSAP 之前，将筛选调用以确定是否需要更新的地址。

加拿大支持用于路由紧急呼叫的动态位置，与美国中一样，存在以下例外情况：所有紧急呼叫在转移到 PSAP 之前将在全国范围内进行筛选。

有关详细信息，请参阅 [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-operator-connect"></a>运营商连接的紧急呼叫路由

当Teams 运营商连接用户拨打紧急号码时，如何将呼叫路由到 PSAP 取决于以下内容：

- 紧急地址是否由Teams客户端动态确定。

- 紧急地址是否是与用户电话号码关联的已注册地址。

- 该国的紧急呼叫网络。

- 在美国和加拿大，动态路由是运营商服务的一部分。 无需从其他服务提供商采购此服务。

- 如果Teams客户端位于租户定义的动态紧急位置：

   - 在美国中，来自该客户端的紧急呼叫会自动路由到服务于该地理位置的 PSAP。
   - 在加拿大，所有紧急呼叫将由国家呼叫中心进行筛选，然后再将呼叫转移到为该地理位置提供服务的 PSAP。

- 如果Teams客户端不在租户定义的动态紧急位置，则国家呼叫中心会对来自该客户端的紧急呼叫进行筛选，以确定调用方的位置，然后再将呼叫转移到为该地理位置提供服务的 PSAP。

- 如果紧急呼叫者无法将其紧急位置更新到筛选中心，则呼叫将传输到为呼叫者注册地址提供服务的 PSAP。


## <a name="considerations-for-direct-routing"></a>直接路由的注意事项

以下部分介绍如何管理直接路由用户的紧急呼叫。 若要了解直接路由是否适合你的业务，请参阅 [PSTN 连接选项](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-direct-routing"></a>直接路由的紧急呼叫启用

对于直接路由，必须使用[Teams紧急呼叫路由策略](manage-emergency-call-routing-policies.md)来定义紧急号码及其关联的路由目标，为用户定义紧急呼叫策略。  (目前，直接路由用户不支持注册的紧急位置。) 

可以将紧急呼叫路由策略分配给直接路由用户帐户、网络站点或两者。 当Teams客户端启动或更改网络连接时，Teams执行客户端所在的网络站点的查找，如下所示：

- 如果紧急呼叫路由策略与站点相关联，则站点策略用于配置紧急呼叫。

- 如果没有与站点关联的紧急呼叫路由策略，如果客户端在未定义的站点连接，或者拨号号码与与站点关联的紧急呼叫路由策略中定义的任何紧急号码不匹配，则使用与用户帐户关联的紧急呼叫路由策略来配置紧急呼叫。 

- 如果Teams客户端无法获取紧急呼叫路由策略，则不会为用户启用紧急呼叫。


### <a name="dynamic-emergency-calling-for-direct-routing"></a>针对直接路由的动态紧急呼叫

针对直接路由的动态紧急调用提供基于 Teams 客户端的当前位置配置和路由紧急呼叫的功能。 自动路由到适当的公共安全应答点 (PSAP) 或通知安全部门人员的能力因Teams用户的使用情况而异。

对于直接路由用户，仅美国支持路由紧急呼叫的动态位置，如下所示：

-   如果美国直接路由用户的Teams客户端动态获取美国中的紧急地址，则该地址用于紧急路由，并且呼叫将自动路由到地址服务区域中的 PSAP。

-   如果美国直接路由用户的Teams客户端未在美国中动态获取紧急地址，则会对呼叫进行筛选，以确定是否需要更新地址，然后再将调用方连接到相应的 PSAP。

加拿大支持路由紧急呼叫的动态位置，与美国中相同，但以下例外情况是：所有紧急呼叫在转移到 PSAP 之前将在全国范围内进行筛选。

有关详细信息，请参阅 [配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-direct-routing"></a>直接路由的紧急呼叫路由

直接路由的紧急呼叫路由策略引用联机 PSTN 使用情况，该使用情况必须具有适当的直接路由配置，才能将紧急呼叫正确路由到适当的 PSTN 网关 () 。 特别是，必须确保紧急拨号字符串有 OnlineVoiceRoute。 有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。 

> [!NOTE]
> Teams客户端不再在紧急号码前面加上“+”登录，即 +911。 因此，Teams紧急呼叫将不再在 911 号码之前发送“+”。 请确保语音路由模式反映此更改。

针对直接路由用户动态路由紧急呼叫的能力因给定国家/地区内的紧急呼叫网络而异。 有两种可用的解决方案：

- [仅在美国 (紧急路由服务提供商) ](#emergency-routing-service-providers)
- [紧急位置标识号应用程序](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>紧急路由服务提供程序

在美国中，有许多经认证的紧急路由服务提供商 (ERSP) ，可以根据调用方的位置自动路由紧急呼叫。

- 如果紧急路由服务提供程序集成到直接路由部署中，则具有动态获取位置的紧急呼叫将自动路由到公共安全应答点 (PSAP) 为该位置提供服务。

-  在根据更新的位置将呼叫连接到相应的调度中心之前，首先会对没有动态获取位置的紧急呼叫进行筛选，以确定用户的当前位置。

有关详细信息，请参阅 [经过直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-applications"></a>紧急位置标识号应用程序

会话边框控制器 (SBC) 可以包括紧急位置标识号 (ELIN) 应用程序。 如果 SBC ELIN 应用程序集成到直接路由部署中，则必须在 ELIN 应用程序中配置紧急地址和相关电话号码，然后将 ELIN 记录上传到相应 PSTN 中的紧急呼叫数据库。 Teams具有 ELIN 标识符的紧急位置必须与 ELIN 应用程序中的紧急位置匹配。

当具有动态获取位置的紧急呼叫路由到相应的 SBC 时，ELIN 应用程序：

- 分析调用方的紧急位置。
- 将位置与 ELIN 记录匹配。
- 将紧急呼叫者的号码替换为 ELIN 电话号码。
- 将调用路由到为该位置提供服务的 PSAP，然后调度程序从上传的 ELIN 记录中获取该位置。

回调紧急号码后，ELIN 应用程序将执行反向调用号码替换为原始紧急调用方。 

有关详细信息，请参阅 [经过直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>安全台通知

Microsoft 呼叫计划、运营商连接和直接路由均提供安全服务台通知。

使用 Teams 紧急呼叫策略 (TeamsEmergencyCallingPolicy) 配置在紧急呼叫期间应通知的人员及其通知方式：仅聊天、会议进入和静音，或会议进入和静音，但能够取消静音。 还可以指定要调用和加入紧急呼叫的用户或组的外部 PSTN 号码。 请注意，不允许 PSTN 方取消静音。

可以将紧急呼叫策略授予Teams用户帐户、分配给网络站点或同时分配给两者。  当Teams客户端启动或更改网络连接时，Teams对客户端所在的网络站点执行查找：

- 如果紧急呼叫策略与网络站点相关联，则站点策略用于配置安全桌面通知。

- 如果没有与站点关联的紧急呼叫策略，或者客户端在未定义的站点上连接，则使用与用户帐户关联的紧急呼叫策略来配置安全桌面通知。  

- 如果Teams客户端无法获取紧急呼叫策略，则不会为用户启用安全服务台通知。

在紧急呼叫期间，安全服务台将加入呼叫，安全台用户的体验根据Teams紧急呼叫策略进行控制。 与每个安全台成员开始群聊，并通过重要消息通知共享紧急呼叫者的位置。  如果将会议选项配置为策略的一部分，则会在会议中另外调用每个安全台用户。

### <a name="custom-emergency-disclaimer"></a>自定义紧急免责声明

管理员能够在租户中为其用户添加自定义横幅以启用 E911。 用户在确认地址时可以关闭横幅，当重新启动Teams时，横幅将重新出现。 若要启用此功能，请在Teams紧急呼叫策略下设置 **紧急服务免责声明**，并输入要显示给用户的字符串消息。 设置自定义策略时，此字段是可选的，字符串字段限制为 250 个字符。

    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)
