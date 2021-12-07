---
title: 远程位置的紧急地址
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解 Microsoft 如何支持可调度的位置信息来支持紧急呼叫。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7d241cee858d3ac19747be56b5a53e157b563f64
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2021
ms.locfileid: "61322995"
---
# <a name="emergency-addresses-for-remote-locations"></a>远程位置的紧急地址

本文介绍 Microsoft 在美国支持 911 紧急呼叫位置信息。 此支持可确保尽可能为拨打紧急电话的用户Teams最精确的可调度位置信息。 无论呼叫方位于哪个位置（在现场或在家工作）发送到公共安全应答点 (PSAP) 呼叫者的位置信息都必须准确。

本文包含有关 Microsoft 遵守 RAY BAUM 的适用于多行电话系统法案和 MLTS (的信息) 。 RAY BAUM 的法案扩展了 Kari 的法律要求，该要求于 2021 年初生效。 有关 RAY BAUM 法案和 Kari 法律的信息，请参阅 [911](https://www.fcc.gov/911-dispatchable-location) 呼叫和多线电话系统的可调度位置 - Kari 法律以及 RAY BAUM 的 [911](https://www.fcc.gov/mlts-911-requirements)直接拨号、通知和可调度位置要求。 

在家工作的用户可以设置自己的紧急地址（如果适用）。 本文介绍如何配置用户策略，以便最终用户可以设置其紧急地址。

尽管此信息适用于美国的紧急 911 呼叫，但用户输入的位置也将传达给加拿大的筛选中心。

本文包含以下部分：

- [支持紧急呼叫位置信息](#support-for-emergency-calling-location-information)
- [位置优先级](#location-precedence)
- [紧急地址分类和路由](#emergency-address-classification-and-routing)
- [使最终用户能够配置其紧急地址](#enable-end-users-to-configure-their-emergency-address)
- [说明和限制](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>支持紧急呼叫位置信息

为了支持这些要求，Teams使用相应操作系统提供的位置服务来建议地址（如果管理员或用户授予了权限）。 最终用户可以确认建议地址的位置、对其进行编辑或手动输入新地址。 然后，确认、编辑或手动输入的地址保存在 Teams 客户端上，以便客户端连接到该网络时自动使用用户确认的地址。 用户保存的地址会在客户端Teams自动清除。


## <a name="location-precedence"></a>位置优先级

紧急地址Teams按不同类型分类。 以下列表显示拨打紧急号码时使用的位置优先级：

1. 位置信息服务中的租户管理员定义的动态获取的地址。

2. 最终用户确认、编辑或手动输入的地址，该地址与客户端Teams本地网络相关联。

3. 操作系统自动建议的地址。

4. 管理员静态分配给用户的地址。


## <a name="emergency-address-classification-and-routing"></a>紧急地址分类和路由

下表显示了每种类型的紧急地址类型和关联的路由方法：呼叫是自动路由到服务 PSAP，还是在传输到服务 PSAP 之前进行准确性筛选。 美国支持所有呼叫计划用户、运营商连接和直接路由认证的紧急呼叫服务提供商的此路由行为。


| 紧急地址的类型 | 紧急路由方法 |
| :------------| :-------|
| 由管理员定义的动态获取的紧急地址。 | 直接到 PSAP。 |
| 从操作系统获取的紧急地址 **，用户未确认** 其准确性。 | 已屏蔽并传输到 PSAP。 |
| 从操作系统获取的紧急地址 **，用户确认** 其准确性。| 直接到 PSAP。 |
| 从操作系统获取的、由用户编辑和确认的紧急地址。 | 已屏蔽并传输到 PSAP。 |
| 用户输入并确认的紧急地址。 | 已屏蔽并传输到 PSAP。 |
| 静态分配给用户/号码的紧急地址。 | 已屏蔽并传输到 PSAP。 |
| Null | 已屏蔽并传输到 PSAP。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>使最终用户能够配置其紧急地址

若要为最终用户启用此功能，请使用 New-CsTeamsEmergencyCallingPolicy PowerShell cmdlet，将 ExternalLocationLookupMode 参数设置为 Enabled。 请参阅以下示例： 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

为最终用户启用此功能后，用户可以从"呼叫"选项卡添加、编辑或确认紧急地址，并设置后显示地址。 

在Windows，可以通过使用组策略或 MDM (移动设备管理来管理 Windows 位置服务，以及应用程序[是否有权访问) 。 ](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

有关位置服务Windows，请参阅Windows[服务和隐私。](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)



## <a name="notes-and-restrictions"></a>说明和限制

注意以下几项：

- 所述的在家工作体验适用于在 Teams 和 Mac Windows桌面。

- Teams手机不支持在家工作的体验。

- Teams移动版支持自动位置检测，但不包括所述的用户输入体验。

- 隐私设置可能会与自动位置检测冲突 - 可以使用移动设备管理系统。


## <a name="related-topics"></a>相关主题

[管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)

