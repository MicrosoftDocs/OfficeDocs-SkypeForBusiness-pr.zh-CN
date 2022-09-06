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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 呼叫计划和电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9109f26abc953fd131e96440bd62d147cac8114f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606031"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>规划和配置动态紧急呼叫 

Microsoft 呼叫计划、操作员连接、运营商连接移动 (公共预览版) 和直接路由的动态紧急呼叫可根据 Teams 客户端的当前位置配置和路由紧急呼叫并通知安全人员。  

Teams 客户端基于与租户管理员定义) 的紧急地址关联的网络拓扑 (网络元素，在请求位置信息服务 (LIS) 时提供网络连接信息。 如果存在匹配项，LIS 会向客户端返回一个位置。

Teams 客户端在紧急呼叫中包含位置数据。 然后，紧急服务提供商使用此数据来确定适当的公共安全应答点 (PSAP) ，并将呼叫路由到该 PSAP，从而使 PSAP 调度程序能够获取调用方的位置。  

对于动态紧急呼叫，必须执行以下操作：

1. 网络管理员配置网络设置和 LIS 以创建网络/紧急位置映射。

2. 在启动期间和之后，或者当网络连接发生更改时，Teams 客户端会向网络设置和 LIS 发送包含其网络连接信息的位置请求。

   - 如果有网络设置站点匹配 - 紧急调用策略将从该站点返回到 Teams 客户端。  (有关策略的详细信息，请参阅 [配置紧急](#configure-emergency-policies) 策略) 。

   - 如果存在 LIS 匹配 - Teams 客户端连接到的网络元素中的紧急位置将返回到 Teams 客户端。 按照以下顺序执行匹配，并返回第一个匹配的结果：
       - Wap
       - 以太网交换机/端口
       - 以太网交换机
       - 子网

3. 当 Teams 客户端发出紧急呼叫时，紧急位置将传递给 PSTN 网络。

执行自动路由到适当的公共安全应答点 (PSAP) 的能力因 Teams 用户的使用情况而异。

Microsoft 呼叫计划、运算符连接合作伙伴和运营商连接移动合作伙伴包括适用于美国和加拿大用户的动态紧急路由服务。

但是，对于直接路由，需要其他配置才能路由紧急呼叫，并且可能用于合作伙伴连接。 管理员必须确保已将路由紧急呼叫的 PSTN 网关配置为通过在联机 PSTN 网关对象上将参数 PidfloSupported 设置为 True，将位置信息添加到传出 INVITE (。 此外，管理员必须配置与紧急路由服务 (ERS) 提供程序 (美国的连接，加拿大) **或** 为 ELIN) 应用程序 (紧急位置标识号配置会话边界控制器 (SBC) 。 有关 ERS 提供程序的信息，请参阅 [经过直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。

本文包含以下部分。

- [分配紧急地址](#assign-emergency-addresses)
- [配置网络设置](#configure-network-settings)
- [配置位置信息服务](#configure-location-information-service)
- [配置紧急策略](#configure-emergency-policies)
- [启用用户和网站](#enable-users-and-sites)
- [测试紧急呼叫](#test-emergency-calling)

有关紧急呼叫的详细信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息，以及有关网络设置和网络拓扑的信息，请参阅以下内容：

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)

有关哪些功能在政府云中可用的详细信息，请参阅本文末尾的 [政府支持](#government-support) 。


## <a name="supported-clients"></a>支持的客户端

目前支持以下客户端。  经常返回查看此列表的更新。

- 适用于 Microsoft Windows 的 Teams 桌面客户端
- 适用于 Apple macOS 的 Teams 桌面客户端
- 适用于 Apple iOS 客户端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更高版本的 Teams 移动客户端
- 适用于 Android 客户端和 Google Play 商店版本 1416/1.0.0.2019121201 及更高版本的 Teams 移动客户端
- Teams 手机版本 1449/1.0.94.2019110802 及更高版本
- Teams 会议室版本 4.4.25.0 及更高版本

> [!NOTE]
> 所有受支持的 Teams 客户端都支持基于子网和基于 WiFi 的位置。 <br><br>
> 支持以太网/交换机 (LLDP) ：
> - Windows 版本 10.0 及更高版本。<br>
> - 需要 [LLDP 启用软件的](https://www.microsoft.com/download/details.aspx?id=103383) Mac OS。<br>
> - Teams 手机与 Teams 应用版本 1449/1.0.94.2021110101 及更高版本。

> [!NOTE]
> Teams Web 客户端不支持动态紧急呼叫（包括安全台通知）。 若要防止用户使用 Teams Web 客户端调用 PSTN 号码，可以设置 Teams 呼叫策略并关闭 **“允许 Web PSTN 呼叫** ”设置。 若要了解详细信息，请参阅 Teams 和 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 中的[通话](teams-calling-policy.md)策略。 

> [!NOTE]
> 3PIP 电话不支持动态紧急呼叫。 



## <a name="assign-emergency-addresses"></a>分配紧急地址

可以按如下所示分配紧急地址：

- 调用计划用户。

- To Operator Connect，运营商连接移动用户&mdash;，具体取决于运营商将用户上传到客户清单时分配给数字的功能。

- 到动态获取位置所需的网络标识符。 

若要支持自动路由美国内的紧急呼叫，必须确保分配给网络标识符的紧急位置包括关联的地理代码。  (没有地理代码的紧急地址无法分配给动态位置所需的网络标识符。) 

Azure Maps用于基于位置的服务。 使用 Microsoft Teams 管理中心输入紧急地址时，Teams 会检查Azure Maps地址：

- 如果找到匹配项，则会自动包含地理代码。

- 如果找不到匹配项，你将有机会手动创建紧急地址。 可以使用 PIN 删除功能来执行此操作。 

> [!NOTE]
> 无法将超过两年的紧急地址分配给网络标识符。 需要重新创建较旧的地址。

在 Microsoft Teams 管理中心或使用 PowerShell 添加和分配紧急地址。 有关详细信息，请参阅[为组织添加紧急位置并为](add-change-remove-emergency-location-organization.md)[用户分配紧急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>配置网络设置

网络设置用于确定 Teams 客户端的位置，以及动态获取紧急呼叫策略和紧急位置。 可以根据组织希望紧急呼叫的运作方式配置网络设置。

网络设置包括包含子网集合的站点，这些网站专门用于向用户进行动态策略分配。 例如，可以将紧急呼叫策略和紧急呼叫路由策略分配给“Redmond 站点”，以便使用特定于 Redmond 的紧急号码、路由和安全台配置从家里或其他 Microsoft 位置漫游的任何用户。  

受信任的 IP 地址包含企业网络的 Internet 外部 IP 地址集合，用于确定用户的终结点是否在公司网络内。 仅当用户的外部 IP 地址与受信任 IP 地址中的 IP 地址匹配时，才会尝试获取动态策略或位置。

有关 IP 地址、网络区域、站点和子网地址的详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

在 Microsoft Teams 管理中心或使用 PowerShell 配置网络设置。 若要了解详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。

请注意，) 对网络设置的某些更改（例如新地址、网络标识符等） () 进行一些更改， (最多需要几个小时才能传播并提供给 Teams 客户端。  

> [!Note]
> 子网也可以在 LIS 中定义，并且可以与紧急位置相关联。  LIS 子网必须由与分配给客户端的子网 IP 范围匹配的网络 ID 定义。 例如，客户端 IP/掩码 10.10.10.150/25 的网络 ID 为 10.10.10.128。 有关详细信息，请参阅 [了解 TCP/IP 寻址和子网基础知识](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

> [!Important]
> 修改 Teams 客户端的源 IP 地址的云代理服务部署不支持网络配置设置查找。



**对于呼叫计划、运算符连接和运营商连接移动用户：**

- 如果需要动态配置安全桌面通知，则必须配置受信任的 IP 地址和网络站点。

- 如果仅需要动态位置，则必须仅配置受信任的 IP 地址;不需要配置网络设置。

- 如果两者都不需要，则不需要配置网络设置。 

**对于直接路由用户：**

- 如果需要动态启用紧急呼叫或动态配置安全台通知，则必须配置受信任的 IP 地址和网络站点。

- 如果仅需要动态位置，则必须仅配置受信任的 IP 地址;不需要配置网络设置。

- 如果两者都不需要，则不需要配置网络设置。


## <a name="configure-location-information-service"></a>配置位置信息服务

Teams 客户端从与不同网络标识符关联的位置获取紧急地址。 

若要使客户端获取位置，必须使用网络标识符填充 LIS， (子网、WAP、交换机、端口) 和紧急位置。 可以在 Microsoft Teams 管理中心或 PowerShell 中执行此操作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到 **“位置** > **网络”&位置**。
2. 单击表示要添加的网络标识符的选项卡。 例如，单击 **子网**、 **Wi-Fi 访问点**、 **交换机** 或 **端口**。 然后单击 **“添加**”。
3. 完成字段，添加紧急位置，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

使用以下 cmdlet 将端口、交换机、子网和 WAP 添加到 LIS。

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义子网以呈现动态位置。

## <a name="configure-emergency-policies"></a>配置紧急策略

使用以下策略配置紧急呼叫。 可以在 Microsoft Teams 管理中心或使用 PowerShell 管理这些策略。

- **紧急呼叫路由策略 - 仅适用于直接路由**。 此策略配置紧急号码、每个数字的掩码（如果需要）和每个数字的 PSTN 路由。 可以将此策略分配给用户、网络站点或两者。 若要了解详细信息，请参阅 [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。  

    (呼叫计划、运算符连接和运营商连接移动用户根据其 Microsoft 365 或Office 365使用位置自动启用来自全国的紧急呼叫。) 

- **紧急呼叫策略 - 适用于呼叫计划、运算符连接、运营商连接移动和直接路由。** 此策略在发出紧急呼叫时配置安全台通知体验。 可以设置要通知的人员及其通知方式。 例如，自动通知组织的安全部门，并让他们侦听紧急呼叫。  此策略可以分配给用户或网络站点，也可以同时分配给两者。 若要了解详细信息，请参阅 [Teams 中的管理紧急呼叫策略](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>启用用户和网站

可以向用户和站点分配紧急呼叫路由策略和紧急呼叫策略。 请记住，紧急呼叫路由策略仅适用于直接路由。  (虽然可以将此策略分配给呼叫计划、运算符连接或运营商连接移动用户，但策略将不起作用。) 

在 Microsoft Teams 管理中心或使用 PowerShell 分配策略。 若要了解详细信息，请参阅：

- [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [在 Teams 中管理紧急呼叫策略](manage-emergency-calling-policies.md)

下面是 PowerShell 示例：

若要为安全台通知启用特定用户，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要将名为“Contoso 紧急呼叫策略 1”的策略分配到站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要为紧急呼叫启用特定的直接路由用户，请使用以下命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要将名为“Contoso 纽约紧急呼叫路由”的策略分配到站点 1，请使用以下命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果向网络站点和用户分配了紧急呼叫策略，并且该用户位于该网络站点，则分配给网络站点的策略将替代分配给用户的策略。

## <a name="test-emergency-calling"></a>测试紧急呼叫

美国中的一些紧急路由服务提供商 (ERSP) 提供紧急呼叫测试机器人。

- **美国或加拿大中的呼叫计划、运算符连接和运营商连接移动用户** 可以使用预定义的测试紧急号码 933 来验证其紧急呼叫配置。 此号码将路由到机器人，然后它会回显呼叫者电话号码 (呼叫行 ID) 、紧急地址或位置，以及呼叫是自动路由到 PSAP 还是首先进行筛选。

- **美国中的直接路由客户** 应与其测试服务的 ERSP 协调。

## <a name="government-support"></a>政府支持

下表显示了对政府云中动态紧急呼叫的支持：

| 云 | 可用性 |
| :------------|:-------|
| 万维多租户 | 在所有 Teams 客户端上可用 |
| Gcc | 在所有 Teams 客户端上可用 |
| GCCH | -在 Teams 桌面上可用 <br> -在 Teams 移动客户端上可用 <br> -在 Teams 手机上可用，应用版本：1449/1.0.94.2022061702 |
| 国防部 | Pending |

 ## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理紧急呼叫策略](manage-emergency-calling-policies.md)
- [管理紧急呼叫路由策略 ](manage-emergency-call-routing-policies.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [云语音功能的网络设置](cloud-voice-network-settings.md)
- [管理云语音功能的网络拓扑](manage-your-network-topology.md)
