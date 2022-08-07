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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解 Microsoft 如何支持可调度的位置信息来支持紧急呼叫。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272067"
---
# <a name="emergency-addresses-for-remote-locations"></a>远程位置的紧急地址

本文介绍 Microsoft 对 美国中 911 紧急呼叫位置信息的支持。 此支持可确保为执行紧急呼叫的 Teams 用户提供最精确的可调度位置信息。 无论呼叫者的位置（现场或在家工作），呼叫者发送到公共安全应答点的位置信息 (PSAP) 必须准确。

本文包含有关 Microsoft 遵守 RAY BAUM 的多线电话系统法案 (MLTS) 的信息。 RAY BAUM法案延长了卡里的法律要求，该要求于2021年初生效。 有关 RAY BAUM 法案和 Kari 法律的详细信息，请参阅 [911 呼叫](https://www.fcc.gov/911-dispatchable-location) 和 [多行电话系统的可调度位置 – Kari 的法律和 RAY BAUM 第 911 号直接拨号、通知和可调度位置要求](https://www.fcc.gov/mlts-911-requirements)。 

在家工作的用户现在可以设置自己的紧急地址（如果适用）。 本文介绍如何配置用户策略，以便最终用户可以设置其紧急地址。

虽然此信息适用于美国中的紧急 911 呼叫，但用户输入的位置也将传达给加拿大的筛选中心。

本文包含以下部分：

- [支持紧急呼叫位置信息](#support-for-emergency-calling-location-information)
- [位置优先级](#location-precedence)
- [紧急地址分类和路由](#emergency-address-classification-and-routing)
- [使最终用户能够配置其紧急地址](#enable-end-users-to-configure-their-emergency-address)
- [说明和限制](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>支持紧急呼叫位置信息

为了支持这些要求，Teams 使用相应操作系统提供的位置服务来建议地址（如果管理员或用户授予了权限）。 最终用户可以确认建议地址的位置、编辑该地址或手动输入新地址。 然后，在 Teams 客户端上保存确认、编辑或手动输入的地址，以便在客户端连接到该网络时自动使用用户确认的地址。 当 Teams 客户端注销时，将自动清除用户保存的地址。


## <a name="location-precedence"></a>位置优先级

Teams 的紧急地址可按不同类型分类。 以下列表显示拨打紧急号码时使用的位置优先级：

1. 由租户在位置信息服务中管理的动态获取地址。

2. 最终用户确认、编辑或手动输入的地址，该地址与 Teams 客户端连接到的本地网络相关联。

3. 操作系统自动建议的地址。

4. 管理员静态分配给用户的地址。


## <a name="emergency-address-classification-and-routing"></a>紧急地址分类和路由

下表显示了每种类型的紧急地址和关联路由方法的类型：调用是自动路由到服务 PSAP 还是在传输到服务 PSAP 之前进行准确性筛选。 对于所有呼叫计划用户、运算符连接合作伙伴和直接路由认证的紧急呼叫服务提供商，美国支持此路由行为。


| 紧急地址的类型 | 紧急路由方法 |
| :------------| :-------|
| 管理员定义的动态获取的紧急地址。 | 直接到 PSAP。 |
| 从操作系统获取的紧急地址 **，但未确认用户准确性** 。 | 已筛选并传输到 PSAP。 |
| 从操作系统获取的紧急地址 **，并确认用户准确性** 。| 直接到 PSAP。 |
| 从操作系统获取并由用户编辑和确认的紧急地址。 | 已筛选并传输到 PSAP。 |
| 用户输入并确认的紧急地址。 | 已筛选并传输到 PSAP。 |
| 静态分配给用户/数字的紧急地址。 | 已筛选并传输到 PSAP。 |
| 空 | 已筛选并传输到 PSAP。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>使最终用户能够配置其紧急地址

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **紧急策略**。
2. 选择“**添加**”。
3. 输入紧急调用策略的名称，例如“E911WFH”。
4. 打开 **外部位置查找模式**。
5. 选择 **“应用**”。

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>为用户分配自定义紧急呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>使用 PowerShell

若要为最终用户启用此功能，请使用 New-CsTeamsEmergencyCallingPolicy PowerShell cmdlet，并将 ExternalLocationLookupMode 参数设置为“已启用”。 请参阅以下示例： 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

为最终用户启用此功能后，用户可以从“呼叫”选项卡添加、编辑或确认紧急地址，并在设置该地址后显示该地址。 有关最终用户如何设置位置服务的详细信息，请参阅 [来自家庭紧急 911 的工作：启用位置服务](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)。

在 Windows 上，可以通过使用组策略或使用 [移动设备管理 (MDM) ](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)来管理 Windows 位置服务，以及应用程序是否有权访问该位置。

有关 Windows 位置服务的详细信息，请参阅 [Windows 位置服务和隐私](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。



## <a name="notes-and-restrictions"></a>说明和限制

注意以下几项：

- 介绍的自家工作体验适用于 Windows 和 Mac 上的 Teams 桌面。

- Teams 电话不支持在家工作体验。

- Teams 移动版支持自动位置检测，但不支持用户输入的所述体验。

- 隐私设置可能与自动位置检测冲突 - 可以使用移动设备管理系统。


## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)

- [来自家庭紧急 911 的工作：启用位置服务](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

