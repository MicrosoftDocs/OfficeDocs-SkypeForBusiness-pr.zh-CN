---
title: 使用 Intune 部署 Teams 手机和 Teams 显示
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文概述了 Microsoft Teams 显示器支持的功能。
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825412"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>使用 Intune 部署 Teams 手机和 Teams 显示

本文概述了如何使用 Intune 部署 Teams 手机和 Teams 显示。

## <a name="conditional-access"></a>条件访问

条件访问是 Azure AD (Azure Active Directory) 功能，可帮助确保正确管理访问 Office 365 资源的设备并确保其安全。  如果将条件访问策略应用到 Teams 服务，则 Android 设备 (包括 Teams 手机和 Teams) 将显示需要将 Teams 注册到 Intune 中并且其设置需要符合策略的组。  如果设备未注册到 Intune，或者设备已注册，但其设置不符合策略，则条件访问将阻止用户登录或使用该设备上 Teams 应用。

通常，在 Intune 中定义的符合性策略将分配给用户组。  这意味着，如果将 Android 符合性策略分配给 user@contoso.com，该策略将同样适用于其 Android 智能手机以及任何登录user@contoso.com Android 的 Teams 设备。

如果使用需要强制实施 Intune 注册的条件性访问，则需要在组织中设置一些操作，以便成功进行 Intune 注册：

- **Intune 许可证** 登录 Teams 设备的用户必须获得 Intune 许可。  只要 Teams 设备登录到具有有效 Intune 许可证的用户帐户，该设备就会在登录过程中自动注册到 Microsoft Intune 中。
- **配置 Intune** 必须为 Android 设备管理员注册设置正确配置的 Intune 租户。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>配置 Intune 以注册基于 Teams Android 的设备

基于 Teams Android 的设备在 Intune 中通过 Android 设备管理员和 DA () 进行管理。 在将设备注册到 Intune 之前，需要执行几个基本步骤。  如果当前已在使用 Intune 管理设备，则很可能已完成所有这些操作。  如果没有，下面是要执行哪些工作：

1. 将 Intune MDM (移动设备管理) 颁发机构。  如果以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅"[设置移动设备管理机构"。](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  这是一个一次步骤，在创建新的 Intune 租户时必须完成。
2. 启用 Android 设备管理员注册。 使用 Intune 将基于 Android 的 Teams 设备作为设备管理员设备进行管理。  默认情况下，对于新创建的租户，设备管理员注册已关闭。  有关详细信息，请参阅 [Android 设备管理员注册](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. 向用户分配许可证。 必须为注册到 Intune 的 Teams 设备的用户分配有效的 Intune 许可证。 有关详细信息，请参阅["向用户分配许可证，以便他们可以在 Intune 中注册设备"。](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. 分配设备管理员符合性策略。  创建 Android 设备管理员符合性策略，并将其分配给包含将登录 Teams 设备的用户的 Azure Active Directory 组。 有关详细信息，请参阅 ["使用符合性策略"为使用 Intune 管理的设备设置规则](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另请参阅

[Teams 电话](phones-for-teams.md)

[Microsoft Teams 认证的 IP 电话](teams-ip-phones.md)

[Teams 显示](teams-displays.md)

[在 Teams 中管理设备](device-management.md)

[Teams 市场](https://office.com/teamsdevices)
