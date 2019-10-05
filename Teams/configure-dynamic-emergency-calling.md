---
title: 配置动态紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 配置动态紧急呼叫
appliesto:
- Microsoft Teams
ms.openlocfilehash: 006f131183fe75b8246f0d2fa2d0ae28575e9e1d
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396466"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>规划和配置通话计划的动态紧急呼叫
Microsoft 通话计划的动态紧急呼叫提供根据团队客户端的当前位置配置和路由紧急呼叫的功能。  自动路由到相应的公共安全应答点（PSAP）或通知安全桌面人员的能力会有所不同，具体取决于团队用户使用的国家/地区。  

> [!Note] 
> 动态紧急呼叫目前仅在美国可用。 但是，安全桌面通知在国家边界内受支持。

在**美国**，您可以配置动态紧急呼叫路由，如下所示：
  
- 如果团队客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫将自动路由到该地理位置的 PSAP 服务。  

- 如果团队客户端不在租户定义的动态紧急位置，则来自该客户端的紧急呼叫由全国呼叫中心进行筛选，以便在将呼叫转移到该地理位置的 PSAP 服务之前确定呼叫者的位置。

您可以配置安全桌面通知，如下所示：

- 如果团队客户端位于租户定义的网络网站上，则为该网站配置的安全组成员将收到通知。

- 如果团队客户端不在租户定义的网络网站上，将通知为该用户配置的安全组成员。

**在美国以外**，紧急电话将被路由到映射到分配给用户的电话号码的 PSAP。  某些国家/地区（如英国和加拿大）在将呼叫者转移到相应的 PSAP 之前调用国内长途，而其他国家或地区直接路由到 PSAP，无论用户当前位于何处。 

请注意，您可以为所有呼叫计划用户配置动态安全桌面通知。


## <a name="supported-clients"></a>支持的客户端

目前支持下列客户端。  经常回来查看此列表的更新。

- 适用于 Windows 的团队桌面客户端
- 适用于 Mac 的团队桌面客户端

## <a name="configure-dynamic-emergency-calling"></a>配置动态紧急呼叫

要配置动态紧急呼叫，您需要执行以下任务：

- [配置紧急地址](#configure-emergency-addresses)
- [配置网络设置](#configure-network-settings)
- [配置位置信息服务](#configure-location-information-service)
- [配置紧急策略](#configure-emergency-policies)
- [启用用户和网站](#enable-users-and-sites)
- [测试紧急电话](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>配置紧急地址

若要支持美国的自动路由，必须完全配置分配给网络标识符的紧急位置部分的市政地址，并包括相关联的地域代码。 （不能将没有地理代码的紧急地址分配给动态位置所需的网络标识符。）

- 如果通过 Microsoft 团队管理中心输入紧急地址，则如果找到匹配项，将自动包含 geo 代码。

- 如果未自动找到匹配项，您将有机会手动创建紧急地址。  

这意味着，如果为紧急呼叫配置了现有的紧急地址，则需要重新创建相同的地址以包括 geo 代码。  若要区分这两个地址，应包含不同的说明。 新的紧急地址可以分配给具有旧地址的用户。 完全迁移时，可以删除旧地址。 

有关配置紧急地址的详细信息，请参阅[什么是紧急位置、位置和呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)。

### <a name="configure-network-settings"></a>配置网络设置

你需要配置网络设置以动态获取用于路由紧急呼叫的紧急位置，还可以选择提供安全桌面通知的动态配置。 所需的紧急呼叫体验将规定需要配置的网络设置。 

请记住以下定义：

- 受信任的 IP 包含企业网络的 Internet 外部 Ip 的集合，用于确定用户的终结点是否位于企业网络内。 仅当用户的外部 IP 与受信任的 IP 集合中的 IP 匹配时，才会启用动态位置。  可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。

- 网络区域包含网络站点的集合。 

- 网络站点表示您的组织具有物理价值（如办公室、一组建筑物或校园）的位置。 这些网站定义为 IP 子网的集合。

- 网络子网必须与特定的网络站点相关联。 根据网络子网和关联的网络站点确定客户端的位置。  


对于呼叫计划用户：

- 如果需要对 security 办公桌通知进行动态配置，则必须同时配置受信任的 IP 地址和网络站点。

- 如果仅需要动态位置，则必须仅配置受信任的 IP 地址。 

- 如果两者都不是必需的，则不需要配置网络设置。 

有关详细信息，请参阅[配置基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)，它介绍了如何配置网络设置。 （本文中的信息既适用于通话计划，也适用于直接路由。）


### <a name="configure-location-information-service"></a>配置位置信息服务

团队客户端从与不同网络标识符关联的紧急位置获取紧急地址。  子网和无线访问点均受支持。 （对以太网交换机/端口的支持已挂起。）

要使用网络标识符和紧急位置配置位置信息服务（.LIS），请使用以下 cmdlet：

- 获取、设置、删除 CsOnlineLisPort
- 获取、设置、删除 CsOnlineLisSwitch
- 获取、设置、删除 CsOnlineLisSubnet
- 获取、设置、删除 CsOnlineLisWirelessAccessPoint 

> [!Important] 
> 如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义它们以呈现动态位置。


### <a name="configure-emergency-policies"></a>配置紧急策略

紧急策略确定当组织中的用户进行紧急呼叫时发生的情况。  你可以设置通知人以及当用户呼叫紧急服务时如何通知他们。 例如，您可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急电话上侦听。

你可以使用新的、Set 和 Grant CsTeamsEmergencyCalling 策略 cmdlet 管理紧急策略。  有关详细信息，请参阅[管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)。


### <a name="enable-users-and-sites"></a>启用用户和网站

当通话计划用户自动启用紧急呼叫时，您必须通过配置紧急呼叫策略来为用户启用安全桌面通知，如下例所示：


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

您也可以将紧急呼叫策略分配给网络站点，如以下示例所示，它将名为 "Contoso 紧急呼叫策略 1" 的策略分配给站点1：

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

如果你为网络网站和用户分配了紧急呼叫策略，并且如果该用户位于该网络站点，则分配给网络网站的策略将覆盖分配给该用户的策略。


### <a name="test-emergency-calling"></a>测试紧急电话

要测试美国的紧急电话，请使用预定义的测试紧急号码933。  此号码将路由到 bot，然后回显呼叫者电话号码（呼叫线路 ID）、紧急地址或位置，以及是否首先将呼叫自动路由到 PSAP 或筛选。  