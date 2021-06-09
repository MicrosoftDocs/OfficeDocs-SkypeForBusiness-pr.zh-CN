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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 呼叫计划并电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46e9e206e82fdc535f115ab276e9cb67ba58d959
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796786"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>规划和配置动态紧急呼叫 

Microsoft 呼叫计划和直接路由电话系统动态紧急呼叫提供配置和路由紧急呼叫的功能，并基于客户端的当前位置通知Teams人员。  

根据租户管理员定义的网络拓扑，Teams 客户端在向位置信息服务请求中提供网络连接信息 (LIS) 。 如果存在匹配项，LIS 会向客户端返回一个位置。 此位置数据将传输回客户端。  

客户端Teams紧急呼叫中包含位置数据。 然后，紧急服务提供机构会使用这些数据来确定适当的公共安全应答点 (PSAP) ，然后将呼叫路由到该 PSAP，以便 PSAP 调度程序获取调用方的位置。  

对于动态紧急呼叫，必须发生以下情况：

1. 网络管理员配置网络设置和 LIS 以创建网络/紧急位置地图。

   对于直接路由，路由紧急呼叫可能需要其他配置，并且合作伙伴连接可能需要其他配置。 管理员必须配置与紧急路由服务 (ERS) 提供商 (美国) **的连接，或者** 为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。

2. 在启动期间和之后定期，或者当网络连接发生更改时，Teams客户端会向网络设置和 LIS 发送包含其网络连接信息的位置请求。

   - 如果存在网络设置站点匹配 ，则紧急呼叫策略将返回到Teams客户端。  (有关策略详细信息，请参阅配置 [紧急](#configure-emergency-policies)) 。

   - 如果存在 LIS 匹配 ，则客户端连接到的网络元素中的Teams位置将返回到Teams客户端。 按以下顺序执行匹配，并返回第一个匹配的结果：
       - WAP
       - 以太网交换机/端口
       - 以太网交换机
       - 子网

3. 当Teams进行紧急呼叫时，紧急位置将传达给 PSTN 网络。

   对于直接路由，管理员必须将 SBC 配置为向 ERS 提供程序发送紧急呼叫，或配置 SBC ELIN 应用程序。

本文包含以下部分。

- [配置紧急地址](#assign-emergency-addresses)
- [配置网络设置](#configure-network-settings)
- [配置位置信息服务](#configure-location-information-service)
- [配置紧急策略](#configure-emergency-policies)
- [启用用户和网站](#enable-users-and-sites)
- [测试紧急呼叫](#test-emergency-calling)

执行自动路由到相应的公共安全应答点 (PSAP) 取决于用户使用Teams国家/地区。

有关紧急呼叫的信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息，以及有关网络设置和网络拓扑的信息，请参阅以下内容：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)

有关政府云中可用的功能详细信息 [，请参阅本文](#government-support) 末尾的"政府支持"。


## <a name="supported-clients"></a>支持的客户端

目前支持以下客户端。  请经常返回查看此列表的更新。

- Teams Microsoft 桌面客户端Windows
- Teams Apple macOS 的桌面客户端
- Teams Apple iOS 客户端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更高的移动客户端
- Teams Android 客户端和 Google Play 商店版本 1416/1.0.0.2019121201 及更大版本的移动客户端
- Teams 1449/1.0.94.2019110802 及更大版本
- Teams 会议室 4.4.25.0 及更大版本

> [!NOTE]
> Web 客户端不支持动态紧急呼叫，包括安全Teams通知。 若要防止用户使用 Teams Web 客户端呼叫 PSTN 号码，你可以设置Teams策略并关闭"允许 **Web PSTN** 呼叫"设置。 有关详细信息，[请参阅在](teams-calling-policy.md)Teams[和 Set-CsTeamsCallingPolicy 中调用策略](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 支持子网和 WiFi AP。 此时，Windows 8.1和更高版本支持以太网交换机/端口。 

## <a name="assign-emergency-addresses"></a>分配紧急地址

可以将紧急地址分配给呼叫计划用户以及动态获取位置所需的网络标识符。  (子网和 WiFi AP。 此时，Windows 8.1和更高版本支持以太网交换机/) 。

若要支持美国境内紧急呼叫的自动路由，必须确保分配给网络标识符的紧急位置包含关联的地理代码。  (没有地理代码的紧急地址不能分配给动态位置.) 

Azure 地图用于基于位置的服务。  使用管理中心输入紧急Microsoft Teams时，Teams Azure 地图检查地址：

- 如果找到匹配项，则会自动包含地理代码。

- 如果未找到匹配项，你将有机会手动创建紧急地址。 可以使用 PIN 拖放功能来这样做。 

这意味着，如果为分配给呼叫计划用户而创建的现有紧急位置适用于动态位置，需要重新创建相同的地址以包含地理代码。 若要区分这两个位置，应包含不同的说明。 可以将新的紧急位置分配给具有旧位置的用户。 完全迁移后，可以删除旧位置。

在管理中心或 PowerShell Microsoft Teams和分配紧急地址。 有关详细信息，请参阅 [为组织添加紧急](add-change-remove-emergency-location-organization.md) 位置和 [为用户分配紧急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>配置网络设置

网络设置用于确定紧急Teams的位置，以及动态获取紧急呼叫策略和紧急位置。 你可以根据组织希望紧急呼叫如何工作来配置网络设置。

网络设置包括包含子网集合的站点，这些子网专门用于向用户动态分配策略。 例如，紧急呼叫策略和紧急呼叫路由策略可能分配给"雷德蒙德站点"，以便从家里或其他 Microsoft 位置漫游的任何用户都配置了特定于雷德蒙德的紧急号码、路由和安全服务台。  

>[!Note]
>子网还可以在 LIS 中定义，并可以与紧急位置相关联。  LIS 子网必须由与分配给客户端的子网 IP 范围匹配的网络 ID 定义。 例如，10.10.10.150/25 的客户端 IP/掩码的网络 ID 为 **10.10.10.128。** 有关详细信息，请参阅了解 [TCP/IP 寻址和子网基础知识](https://docs.microsoft.com/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

请记住以下定义。 有关详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

- 受信任的 IP 地址包含企业网络的 Internet 外部 IP 地址的集合，用于确定用户的终结点是否位于企业网络中。 只有在用户的外部 IP 地址与受信任的 IP 地址中的 IP 地址匹配时，才尝试获取动态策略或位置。 可以针对 IPv4 或 IPv6 IP 地址进行匹配，并且取决于发送到网络设置的 IP 数据包的格式。   (如果公共 IP 地址同时具有 IPv4 和 IPv6，则需要将两者添加为受信任的 IP 地址.) 

- 网络区域包含网络站点的集合。 

- 网络网站表示组织具有物理值的位置，例如办公室、一组建筑物或校园。 这些站点定义为 IP 子网的集合。

- 网络子网必须与特定网络站点相关联。 根据网络子网和关联的网络站点确定客户端的位置。  

在管理中心或Microsoft Teams PowerShell 配置网络设置。 有关详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。

请注意，可能需要一些时间 () 才能对网络设置进行一些更改 (例如新地址、网络标识符等) 才能传播并可供 Teams 客户端使用。  

**对于调用计划用户：**

- 如果需要动态配置安全服务台通知，则必须同时配置受信任的 IP 地址和网络站点。

- 如果只需要动态位置，则必须仅配置受信任的 IP 地址。

- 如果两者都不需要，则不需要配置网络设置。 

**对于直接路由用户：**

- 如果需要动态启用紧急呼叫或安全服务台通知的动态配置，则必须同时配置受信任的 IP 地址和网络站点。

- 如果只需要动态位置，则必须仅配置受信任的 IP 地址。

- 如果两者都不需要，则不需要配置网络设置。


## <a name="configure-location-information-service"></a>配置位置信息服务

客户端Teams从与不同网络标识符关联的位置获取紧急地址。 支持子网和无线接入点 () WAN。 此时，Windows 8.1和更高版本支持以太网交换机/端口。

若要让客户端获取位置，必须使用子网、 (、交换机、端口和紧急位置的网络标识符) LIS。 可以在管理中心或Microsoft Teams PowerShell 中执行此操作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到 **"位置**  >  **""网络&位置"。**
2. 单击表示要添加的网络标识符的选项卡。 例如，单击 **"子网****、Wi-Fi 接入点**、交换机"或"**端口"。** 然后单击"**添加"。**
3. 填写字段，添加紧急位置，然后单击"应用 **"。**

### <a name="using-powershell"></a>使用 PowerShell

使用以下 cmdlet 将端口、交换机、子网和 WAP 添加到 LIS。

- [获取](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [获取](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [获取](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [获取](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>如果将子网用作网络网站的一部分，则必须在位置信息服务中重新定义子网，以呈现动态位置。

## <a name="configure-emergency-policies"></a>配置紧急策略

使用以下策略配置紧急呼叫。 可以在管理中心内或Microsoft Teams PowerShell 管理这些策略。

- **紧急呼叫路由策略** - 仅适用于直接路由。 此策略配置紧急号码、每个号码的掩码（如果需要）和每个号码的 PSTN 路由。  可以将此策略分配给用户、网络站点或两者。  (呼叫计划 Teams 客户端根据其 Microsoft 365 或 Office 365 使用位置自动启用紧急呼叫。) 若要了解有关详细信息，请参阅管理直接路由的紧急呼叫路由[策略](manage-emergency-call-routing-policies.md)。

- **紧急呼叫策略** - 适用于呼叫计划和直接路由。 此策略配置进行紧急呼叫时的安全服务台通知体验。 可以设置要通知谁以及如何通知他们。 例如，自动通知组织的安全服务台，让他们接听紧急呼叫。  可以将此策略分配给用户或网络站点，也可以同时分配给这两者。 若要了解有关详细信息，请参阅[在 Teams 中管理紧急Teams。](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>启用用户和网站

可以将紧急呼叫路由策略和紧急呼叫策略分配给用户和站点。 请记住，紧急呼叫路由策略仅适用于直接路由。  (尽管可以将此策略分配给呼叫计划用户，但该策略将不起作用。) 

在管理中心Microsoft Teams PowerShell 分配策略。 若要了解详细信息，请参阅：

- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [管理紧急呼叫策略Teams](manage-emergency-calling-policies.md)

下面是一些 PowerShell 示例。

若要为安全服务台通知启用特定用户，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要将名为"Contoso 紧急呼叫策略 1"的策略分配到站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要为特定的直接路由用户启用紧急呼叫，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要将名为"Contoso New York 紧急呼叫路由"的策略分配到站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果将紧急呼叫策略分配给网络站点和用户，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。

## <a name="test-emergency-calling"></a>测试紧急呼叫

美国某些紧急路由 (ERSP) 提供紧急呼叫测试机器人。

- **美国呼叫计划用户可以使用** 预定义的测试紧急号码 933 来验证其紧急呼叫配置。 此号码将路由到机器人，机器人随后回显呼叫方电话号码 (呼叫线路 ID) 、紧急地址或位置，以及呼叫是自动路由到 PSAP 还是先进行筛选。

- **美国直接路由客户应** 协调其 ERSP 以测试服务。

## <a name="government-support"></a>政府支持

下表显示了对政府云中的动态紧急呼叫的支持：

| 云 | 可用性 |
| :------------|:-------|
| 万维多租户 | 在所有客户端Teams可用 |
| GCC | 在所有客户端Teams可用 |
| GCCH | 在桌面Teams可用 |
| DoD | Pending |

 ## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)
