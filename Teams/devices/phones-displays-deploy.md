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
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120774"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>使用 Intune 部署 Teams 手机和 Teams 显示

本文概述了如何使用 Intune 部署 Teams 手机和 Teams 显示。

## <a name="conditional-access"></a>条件访问

条件访问是 Azure AD (Azure Active Directory) 功能，可帮助确保访问 Office 365 资源的设备得到正确管理且安全。  如果将条件访问策略应用到 Teams 服务，则 Android 设备 (包括 Teams 手机和 Teams）将显示需要将访问 Teams 的) 注册到 Intune 中，并且其设置需要符合策略。  如果设备未注册到 Intune，或者该设备已注册，但其设置不符合策略，则条件访问将阻止用户登录或使用该设备上 Teams 应用。

通常，Intune 中定义的符合性策略将分配给用户组。  这意味着，如果将 Android 符合性策略分配给 user@contoso.com，该策略将同样适用于其 Android 智能手机和登录的任何基于 Android 的 Teams user@contoso.com 应用。

如果使用条件访问（要求强制使用 Intune 注册）在组织中，需要设置一些操作，以允许成功进行 Intune 注册：

- **Intune 许可证** 登录 Teams 设备的用户必须获得 Intune 的许可。  只要 Teams 设备登录到具有有效 Intune 许可证的用户帐户，该设备就会在登录过程中自动注册到 Microsoft Intune 中。
- **配置 Intune** 必须为 Android 设备管理员注册设置正确配置的 Intune 租户。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>配置 Intune 以注册基于 Teams Android 的设备

基于 Teams Android 的设备在 Intune 中通过 Android 设备管理员 (DA) 管理。 在将设备注册到 Intune 之前，需要执行几个基本步骤。  如果当前已在使用 Intune 管理设备，可能已完成所有这些操作。  如果没有，下面是要执行哪些工作：

1. 将 Intune MDM (设置为") 管理"。  如果以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅 [设置移动设备管理机构](/intune/fundamentals/mdm-authority-set)。  这是一个一步，在创建新的 Intune 租户时必须完成。
2. 启用 Android 设备管理员注册。 使用 Intune 将基于 Android 的 Teams 设备作为设备管理员设备进行管理。  默认情况下，对于新建的租户，设备管理员注册已关闭。  有关详细信息，请参阅 [Android 设备管理员注册](/intune/enrollment/android-enroll-device-administrator)。
3. 向用户分配许可证。 必须为注册到 Intune 的 Teams 设备的用户分配有效的 Intune 许可证。 有关详细信息，请参阅 [向用户分配许可证，以便他们可以在 Intune 中注册设备](/intune/fundamentals/licenses-assign)。
4. 分配设备管理员符合性策略。  创建 Android 设备管理员符合性策略，并将其分配给包含将登录 Teams 设备的用户的 Azure Active Directory 组。 有关详细信息，请参阅使用 [符合性策略为使用 Intune 管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另请参阅

[Teams 电话](phones-for-teams.md)

[Microsoft Teams 认证的 IP 电话](teams-ip-phones.md)

[Teams 显示](teams-displays.md)

[在 Teams 中管理设备](device-management.md)

[Teams 市场](https://office.com/teamsdevices)