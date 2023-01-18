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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 通话套餐和电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814354"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>规划和配置动态紧急呼叫 

Microsoft 通话套餐、运营商连接、Teams 电话移动和直接路由的动态紧急呼叫提供配置和路由紧急呼叫的功能，并根据 Teams 客户端的当前位置通知安全人员。  

根据网络拓扑 (与租户管理员定义的紧急地址关联的网络元素) ，Teams 客户端在向位置信息服务 (LIS) 的请求中提供网络连接信息。 如果有匹配项，则 LIS 会向客户端返回位置。

Teams 客户端将位置数据作为紧急呼叫的一部分包含在内。 然后，紧急服务提供商使用此数据来确定适当的公共安全应答点 (PSAP) ，并将呼叫路由到该 PSAP，从而使 PSAP 调度程序能够获取呼叫方的位置。  

对于动态紧急呼叫，必须发生以下情况：

1. 网络管理员配置网络设置和 LIS 以创建网络/紧急位置映射。

2. 在启动期间和之后定期，或者当网络连接发生更改时，Teams 客户端会向网络设置和 LIS 发送包含其网络连接信息的位置请求。

   - 如果存在网络设置站点匹配 - 紧急呼叫策略将从该站点返回到 Teams 客户端。  (有关策略的详细信息，请参阅 [配置紧急策略](#configure-emergency-policies)) 。

   - 如果有 LIS 匹配项 - Teams 客户端连接到的网络元素中的紧急位置将返回到 Teams 客户端。 匹配按以下顺序执行，并返回第一个匹配结果：
       - Wap
       - 以太网交换机/端口
       - 以太网交换机
       - 子网

3. 当 Teams 客户端发出紧急呼叫时，紧急位置将传达给 PSTN 网络。

自动路由到适当的公共安全应答点 (PSAP) 的功能因 Teams 用户的使用国家/地区而异。

Microsoft 通话套餐、运营商连接合作伙伴和 Teams 电话移动合作伙伴为美国和加拿大的用户提供动态紧急路由服务。

但是，对于直接路由，路由紧急呼叫和合作伙伴连接可能需要其他配置。 管理员必须确保路由紧急呼叫的 PSTN 网关已配置为将位置信息添加到传出 INVITE (，方法是在联机 PSTN 网关对象上将 PidfloSupported 参数设置为 True。 此外，管理员必须配置与紧急路由服务 (ERS) 提供程序 (美国和加拿大的连接) **或** 配置会话边界控制器 (SBC)  (ELIN) 应用程序。 有关 ERS 提供程序的信息，请参阅 [通过直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。

本文包含以下部分。

- [分配紧急地址](#assign-emergency-addresses)
- [配置网络设置](#configure-network-settings)
- [配置位置信息服务](#configure-location-information-service)
- [配置紧急策略](#configure-emergency-policies)
- [启用用户和站点](#enable-users-and-sites)
- [测试紧急呼叫](#test-emergency-calling)

有关紧急呼叫的详细信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息以及有关网络设置和网络拓扑的信息，请参阅以下内容：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)

有关政府云中可用的功能的详细信息，请参阅本文末尾的 [政府支持](#government-support) 。


## <a name="supported-clients"></a>支持的客户端

当前支持以下客户端。  请经常回来查看此列表的更新。

- 适用于 Microsoft Windows 的 Teams 桌面客户端
- 适用于 Apple macOS 的 Teams 桌面客户端
- 适用于 Apple iOS 客户端版本 1.0.92.2019121004 和App Store版本 1.0.92 及更高版本的 Teams 移动客户端
- 适用于 Android 客户端和 Google Play 应用商店版本 1416/1.0.0.2019121201 及更高版本的 Teams 移动客户端
- Teams 手机版本 1449/1.0.94.2019110802 及更高版本
- Teams 会议室版本 4.4.25.0 及更高版本

> [!NOTE]
> 所有支持的 Teams 客户端都支持基于子网和 WiFi 的位置。 <br><br>
> 在上支持以太网/交换机 (LLDP) ：
> - 此时的 Windows 版本 10.0 及更高版本。<br>
> - Mac OS，需要 [LLDP 启用软件](https://www.microsoft.com/download/details.aspx?id=103383)。<br>
> - Teams 手机与 Teams 应用版本 1449/1.0.94.2021110101 及更高版本。

> [!NOTE]
> Teams Web 客户端不支持动态紧急呼叫（包括安全台通知）。 若要防止用户使用 Teams Web 客户端呼叫 PSTN 号码，可以设置 Teams 呼叫策略并关闭 **“允许 Web PSTN 呼叫** ”设置。 若要了解详细信息，请参阅 [Teams 中的呼叫策略](teams-calling-policy.md) 和 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 

> [!NOTE]
> 3PIP 电话不支持动态紧急呼叫。 



## <a name="assign-emergency-addresses"></a>分配紧急地址

可按如下所示分配紧急地址：

- 到通话套餐用户。

- 运营商 Connect 和 Teams Phone Mobile 用户&mdash;，具体取决于运营商将号码上传到客户库存时分配给号码的功能。

- 动态获取位置所需的网络标识符。 

若要支持美国内紧急呼叫的自动路由，必须确保分配给网络标识符的紧急位置包括关联的地理代码。  (没有地理代码的紧急地址无法分配给动态位置所需的网络标识符。) 

Azure Maps用于基于位置的服务。 使用 Microsoft Teams 管理中心输入紧急地址时，Teams 会检查Azure Maps地址：

- 如果找到匹配项，则会自动包含地理代码。

- 如果未找到匹配项，则有机会手动创建紧急地址。 可以使用 PIN 删除功能执行此操作。 

> [!NOTE]
> 无法将超过两年的紧急地址分配给网络标识符。 需要重新创建较旧的地址。

可以在 Microsoft Teams 管理中心或使用 PowerShell 添加和分配紧急地址。 有关详细信息，请参阅[为组织添加紧急位置和](add-change-remove-emergency-location-organization.md)[为用户分配紧急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>配置网络设置

网络设置用于确定 Teams 客户端的位置，以及动态获取紧急呼叫策略和紧急位置。 可以根据组织希望紧急呼叫的工作方式配置网络设置。

网络设置包括包含子网集合的站点，这些站点专门用于向用户分配动态策略。 例如，紧急呼叫策略和紧急呼叫路由策略可能会分配给“Redmond 站点”，以便从家庭或其他 Microsoft 位置漫游的任何用户都配置特定于 Redmond 的紧急号码、路由和安全台。  

受信任的 IP 地址包含企业网络的 Internet 外部 IP 地址的集合，用于确定用户的终结点是否在企业网络内。 仅当用户的外部 IP 地址与受信任 IP 地址中的 IP 地址匹配时，才会尝试获取动态策略或位置。

有关 IP 地址、网络区域、站点和子网地址的详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

可以在 Microsoft Teams 管理中心或使用 PowerShell 配置网络设置。 若要了解详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。

请注意，可能需要一些时间 (长达几个小时) 才能对网络设置 (（例如新地址、网络标识符等）进行某些更改，) 传播并可供 Teams 客户端使用。  

> [!Note]
> 子网还可以在 LIS 中定义，并且可以与紧急位置相关联。  LIS 子网必须由与分配给客户端的子网 IP 范围匹配的网络 ID 定义。 例如，客户端 IP/掩码 10.10.10.150/25 的网络 ID 为 10.10.10.128。 有关详细信息，请参阅 [了解 TCP/IP 寻址和子网化基础知识](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

> [!Important]
> 修改来自 Teams 客户端的源 IP 地址的云代理服务部署不支持网络配置设置查找。



**对于通话套餐、运营商连接和 Teams 电话移动用户：**

- 如果需要动态配置安全台通知，则必须同时配置受信任的 IP 地址和网络站点。

- 如果只需要动态位置，则必须仅配置受信任的 IP 地址;不需要配置网络设置。

- 如果两者都不是必需的，则不需要配置网络设置。 

**对于直接路由用户：**

- 如果需要动态启用紧急呼叫或动态配置安全台通知，则必须配置受信任的 IP 地址和网络站点。

- 如果只需要动态位置，则必须仅配置受信任的 IP 地址;不需要配置网络设置。

- 如果两者都不是必需的，则不需要配置网络设置。


## <a name="configure-location-information-service"></a>配置位置信息服务

Teams 客户端从与不同网络标识符关联的位置获取紧急地址。 

若要使客户端获取位置，必须使用网络标识符 (子网、WAP、交换机、端口) 和紧急位置填充 LIS。 可以在 Microsoft Teams 管理中心或使用 PowerShell 执行此操作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到 **“位置** > **网络&位置**”。
2. 单击表示要添加的网络标识符的选项卡。 例如，单击“ **子网**”、“ **Wi-Fi 接入点**”、“ **交换机**”或“ **端口**”。 然后单击“ **添加**”。
3. 填写字段，添加紧急位置，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

使用以下 cmdlet 将端口、交换机、子网和 WAP 添加到 LIS。

- [获取](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [获取](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [获取](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [获取](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义子网才能呈现动态位置。

## <a name="configure-emergency-policies"></a>配置紧急策略

使用以下策略配置紧急呼叫。 可以在 Microsoft Teams 管理中心或使用 PowerShell 管理这些策略。

- **紧急呼叫路由策略 - 仅适用于直接路由**。 此策略配置紧急号码、每个号码的掩码（如果需要）以及每个号码的 PSTN 路由。 可以将此策略分配给用户和/或网络站点。 若要了解详细信息，请参阅 [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。  

    (通话套餐、运营商连接和 Teams 电话移动版用户将根据其 Microsoft 365 或Office 365使用情况位置自动启用紧急呼叫，以便使用来自国家/地区的紧急号码进行紧急呼叫。) 

- **紧急呼叫策略 - 适用于通话套餐、运营商连接、Teams 电话移动和直接路由。** 此策略在发出紧急呼叫时配置安全服务台通知体验。 可以设置通知谁以及通知他们的方式。 例如，自动通知组织的安全服务台，并让他们侦听紧急呼叫。  此策略可以分配给用户或网络站点，也可以同时分配给这两者。 若要了解详细信息，请参阅 [在 Teams 中管理紧急呼叫策略](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>启用用户和站点

可以将紧急呼叫路由策略和紧急呼叫策略分配给用户和站点。 请记住，紧急呼叫路由策略仅适用于直接路由。  (尽管可以将此策略分配给通话套餐、运营商连接或 Teams 电话移动用户，但该策略将不起作用。) 

可以在 Microsoft Teams 管理中心或使用 PowerShell 分配策略。 若要了解详细信息，请参阅：

- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [在 Teams 中管理紧急呼叫策略](manage-emergency-calling-policies.md)

下面是 PowerShell 示例：

若要为特定用户启用安全服务台通知，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要将名为“Contoso 紧急呼叫策略 1”的策略分配给站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要为特定直接路由用户启用紧急呼叫，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要将名为“Contoso New York 紧急呼叫路由”的策略分配到站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果向网络站点和用户分配了紧急呼叫策略，并且该用户位于该网络站点，则分配给该网络站点的策略将覆盖分配给该用户的策略。

## <a name="test-emergency-calling"></a>测试紧急呼叫

美国中的某些紧急路由服务提供商 (ERSP) 提供紧急呼叫测试机器人。

- **美国或加拿大的通话套餐、运营商连接和 Teams 电话移动用户** 可以使用预定义的测试紧急号码 933 来验证其紧急呼叫配置。 此号码将路由到机器人，机器人随后会回显呼叫者的电话号码 (呼叫线路 ID) 、紧急地址或位置，以及呼叫是自动路由到 PSAP 还是先屏蔽。

- **美国中的直接路由客户** 应与其 ERSP 协调测试服务。

## <a name="government-support"></a>政府支持

下表显示了政府云中对动态紧急呼叫的支持：

| 云 | 可用性 |
| :------------|:-------|
| 全球多租户 | 在所有 Teams 客户端上可用 |
| Gcc | 在所有 Teams 客户端上可用 |
| GCCH | -在 Teams 桌面上可用 <br> -在 Teams 移动客户端上可用 <br> -适用于 Teams 手机，应用版本：1449/1.0.94.2022061702 |
| 国防部 | -在 Teams 桌面上可用 <br>-在 Teams 移动客户端上可用 <br>-在 Teams 手机上挂起 |

 ## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)
