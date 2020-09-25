---
title: 配置动态紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 通话计划和电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 772b439c7d0590cdc917c3e94780761de2da8915
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269646"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>规划和配置动态紧急呼叫 

Microsoft 通话计划和电话系统直接路由的动态紧急呼叫提供了配置和路由紧急呼叫的功能，并根据团队客户的当前位置通知安全人员。  

根据租户管理员定义的网络拓扑，团队客户端在 (.LIS) 位置的位置信息服务请求中提供网络连接信息。 如果存在匹配项，则 IIS 将向客户端返回一个位置。 此位置数据将传回客户端。  

团队客户端包括作为紧急呼叫的一部分的位置数据。 这些数据随后由紧急服务提供商用于确定相应的公共安全应答点 (PSAP) 并将呼叫路由到该 PSAP，从而允许 PSAP dispatcher 获取呼叫者的位置。  

对于动态紧急呼叫，必须执行以下操作：

1. 网络管理员配置网络设置和 .LIS 以创建网络/紧急位置映射。

   对于直接路由，需要进行额外的配置来路由紧急呼叫，并且可能需要进行合作伙伴连接。 管理员必须将连接配置为紧急路由服务 (ERS) 提供商 (美国) **或** 为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。

2. 在启动和以后定期，或者当网络连接更改时，团队客户端会将包含其网络连接信息的位置请求发送到网络设置和 .LIS。

   - 如果存在网络设置网站匹配项，则会将紧急呼叫策略从该网站返回到团队客户端。  (有关策略的详细信息，请参阅 [配置紧急策略](#configure-emergency-policies)) 。

   - 如果存在一个 .LIS 匹配项-来自团队客户端连接到的网络元素的紧急位置将返回到团队客户端。 按以下顺序执行匹配，并返回第一个匹配的结果：
       - WAP
       - 以太网交换机/端口
       - 以太网交换机
       - 子网

3. 当团队客户端进行紧急呼叫时，会将紧急位置传达给 PSTN 网络。

   对于直接路由，管理员必须将 SBC 配置为向 ERS 提供商发送紧急呼叫或配置 SBC ELIN 应用程序。

本文包含以下部分。

- [配置紧急地址](#assign-emergency-addresses)
- [配置网络设置](#configure-network-settings)
- [配置位置信息服务](#configure-location-information-service)
- [配置紧急策略](#configure-emergency-policies)
- [启用用户和网站](#enable-users-and-sites)
- [测试紧急电话](#test-emergency-calling)

自动路由到相应的公共安全应答点的能力 (PSAP) 根据团队用户的使用情况的不同而有所不同。

有关紧急呼叫的详细信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息以及有关网络设置和网络拓扑的信息，请参阅以下内容：

- [管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)

## <a name="supported-clients"></a>支持的客户端

目前支持下列客户端。  经常回来查看此列表的更新。

- 适用于 Microsoft Windows 的团队桌面客户端
- Apple macOS 的团队桌面客户端
- Apple iOS 客户端版本1.0.92.2019121004 和应用商店版本1.0.92 及更高版本的团队移动客户端
- 适用于 Android 客户端和 Google Play 版的团队移动客户端和 Google Play store 版本 1416/1.0.0.2019121201 及更高
- 工作组电话版本 1449/1.0.94.2019110802 及更高版本
- 团队聊天室版本4.4.25.0 及更高版本

> [!NOTE]
> 不支持团队 web 客户端上的动态紧急呼叫（包括安全桌面通知）。 若要防止用户使用团队 web 客户端调用 PSTN 号码，您可以设置团队呼叫策略并关闭 " **允许 WEB PSTN 呼叫** " 设置。 若要了解详细信息，请参阅 [在团队中调用策略](teams-calling-policy.md) 和 [设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。

## <a name="assign-emergency-addresses"></a>分配紧急地址

你可以将紧急地址分配给呼叫计划用户和动态获取位置所需的网络标识符。 支持 (子网和 WiFi AP。 在 Windows 8.1 和更高版本) 上支持以太网交换机/端口。

若要支持在美国的紧急呼叫自动路由，必须确保分配给网络标识符的紧急位置包括关联的地域代码。 不能将没有地域代码的紧急地址分配给动态位置所需的网络标识符。 )  (

Azure 映射用于基于位置的服务。  使用 Microsoft 团队管理中心输入紧急地址时，团队会检查该地址的 Azure 映射：

- 如果找到匹配项，则自动包括 geo 代码。

- 如果找不到匹配项，您将有机会手动创建紧急地址。 你可以使用 "固定放置" 功能执行此操作。 

这意味着，如果为分配给呼叫计划用户而创建的现有紧急位置适用于动态位置，则需要重新创建相同的地址以包括 geo 代码。 若要区分这两个位置，应包含不同的说明。 新的紧急位置可分配给具有旧位置的用户。 完全迁移时，可以删除旧位置。

在 Microsoft 团队管理中心或使用 PowerShell 中添加和分配紧急地址。 有关详细信息，请参阅为 [你的组织添加紧急位置](add-change-remove-emergency-location-organization.md) 和为 [用户分配紧急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>配置网络设置

网络设置用于确定团队客户端的位置，并动态获取紧急呼叫策略和紧急位置。 您可以根据组织希望的紧急呼叫功能来配置网络设置。

网络设置包括包含子网集合的网站，这些网站专门用于向用户分配动态策略。 例如，紧急呼叫策略和紧急呼叫路由策略可能会分配给 "雷德蒙" 网站，以便从家里或其他 Microsoft 位置漫游的任何用户都使用特定于 Redmond 的紧急号码、路线和安全桌面进行配置。  

>[!Note]
>子网也可以在 .LIS 中定义，并且可以与紧急位置相关联。  

请记住以下定义。 有关详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

- "受信任的 IP 地址" 包含企业网络的 internet 外部 IP 地址的集合，用于确定用户的终结点是否位于企业网络内。 仅当用户的外部 IP 地址与受信任的 IP 地址中的 IP 地址匹配时，才会尝试获取动态策略或位置。 可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。   (如果公共 IP 地址同时具有 IPv4 和 IPv6，则需要将两者都添加为受信任的 IP 地址。 ) 

- 网络区域包含网络站点的集合。 

- 网络站点表示您的组织具有物理价值（如办公室、一组建筑物或校园）的位置。 这些网站定义为 IP 子网的集合。

- 网络子网必须与特定的网络站点相关联。 根据网络子网和关联的网络站点确定客户端的位置。  

在 Microsoft 团队管理中心或通过使用 PowerShell 配置网络设置。 若要了解详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。

请注意，可能需要一段时间 (几个小时，) 对网络设置的某些更改 (如新地址、网络标识符等) 传播并供团队客户端使用。  

**对于呼叫计划用户：**

- 如果需要对 security 办公桌通知进行动态配置，则必须同时配置受信任的 IP 地址和网络站点。

- 如果仅需要动态位置，则必须仅配置受信任的 IP 地址。

- 如果两者都不是必需的，则不需要配置网络设置。 

**对于直接路由用户：**

- 如果需要动态启用紧急呼叫或安全桌面通知的动态配置，则必须同时配置受信任的 IP 地址和网络站点。

- 如果仅需要动态位置，则必须仅配置受信任的 IP 地址。

- 如果两者都不是必需的，则不需要配置网络设置。


## <a name="configure-location-information-service"></a>配置位置信息服务

团队客户端从与不同网络标识符关联的位置获取紧急地址。 子网和无线访问点 (WAPs) 均受支持。 目前在 Windows 8.1 和更高版本上支持以太网交换机/端口。

若要获取某个位置的客户端，你必须使用网络标识符（ (子网、WAPs、交换机、端口) 和紧急位置）填充 IIS。 可以在 Microsoft 团队管理中心或使用 PowerShell 执行此操作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到 "**位置**  >  **网络" & 位置**。
2. 单击表示要添加的网络标识符的选项卡。 例如，单击 " **子网**"、" **wi-fi 访问点**"、" **交换机**" 或 " **端口**"。 然后单击 " **添加**"。
3. 填写字段，添加紧急位置，然后单击 " **应用**"。

### <a name="using-powershell"></a>使用 PowerShell

使用以下 cmdlet 将端口、开关、子网和 WAPs 添加到 .LIS。

- [获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) CsOnlineLisSubnet
- [获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) CsOnlineLisPort
- [获取](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) CsOnlineLisWirelessAccessPoint
- [获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) CsOnlineLisSwitch

>[!Important]
>如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义它们以呈现动态位置。

## <a name="configure-emergency-policies"></a>配置紧急策略

使用以下策略配置紧急呼叫。 你可以在 Microsoft 团队管理中心或通过使用 PowerShell 管理这些策略。

- **紧急呼叫路由策略** -仅适用于直接路由。 此政策配置紧急号码、每个号码的掩码（如果需要），以及每个号码的 PSTN 路由。  你可以将此策略分配给用户和/或网络站点。  (通话计划团队客户将使用基于其 Microsoft 365 或 Office 365 使用位置的紧急电话自动启用紧急呼叫。 ) 了解详细信息，请参阅 [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。

- **紧急呼叫政策** -适用于通话计划和直接路由。 此策略配置在进行紧急呼叫时的安全桌面通知体验。 可以设置要通知的人员以及通知的方式。 例如，自动通知组织的安全桌面并让他们在紧急电话上侦听。  此策略既可以分配给用户，也可以同时分配给用户或网络站点。 若要了解详细信息，请参阅 [管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>启用用户和网站

您可以为用户和网站分配紧急呼叫路由策略和紧急呼叫策略。 请记住，紧急呼叫路由策略仅适用于直接路由。  (尽管可以将此策略分配给通话计划用户，但该策略不会有任何影响。 ) 

在 Microsoft 团队管理中心或通过使用 PowerShell 分配策略。 要了解详细信息，请参阅：

- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)

下面是一些 PowerShell 示例。

若要为安全桌面通知启用特定用户，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要将名为 "Contoso 紧急呼叫策略 1" 的策略分配给站点1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要启用特定直接路由用户进行紧急呼叫，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要将名为 "Contoso 纽约紧急呼叫路由" 的策略分配给站点1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果你为网络网站和用户分配了紧急呼叫策略，并且如果该用户位于该网络站点，则分配给网络网站的策略将覆盖分配给该用户的策略。

## <a name="test-emergency-calling"></a>测试紧急电话

某些紧急路线服务提供商 (ERSPs) 在美国提供紧急呼叫测试机器人。

- **美国的通话计划用户** 可以使用预定义的测试紧急号码933验证紧急呼叫配置。 此号码将路由到一个 bot，然后将回显呼叫者电话号码 (呼叫线路 ID) 、紧急地址或位置，以及是否会首先自动将呼叫路由到 PSAP 或筛选。

- **美国直接路由客户** 应与他们的 ERSP 进行测试服务协调。

 ## <a name="related-topics"></a>相关主题

- [管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)
