---
title: 部署团队使用 Intune 显示的电话和团队
ms.author: v-lanac
author: lanachin
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
description: 本文提供 Microsoft 团队显示所支持的和功能的概述。
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787607"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>部署团队使用 Intune 显示的电话和团队

本文简要介绍了如何使用 Intune 部署团队电话和团队。

## <a name="conditional-access"></a>条件访问

条件访问是 Azure Active Directory (Azure AD) 功能，可帮助你确保访问 Office 365 资源的设备正确管理且安全。  如果你将条件访问策略应用到团队服务，Android 设备 (包括团队电话和团队显示访问团队需要注册到 Intune 的) ，其设置需要符合你的策略。  如果设备未注册到 Intune，或者它已注册，但其设置不符合你的策略，则条件访问将阻止用户登录或使用设备上的 "团队" 应用。

通常，在 Intune 中定义的合规性策略将分配给用户组。  这意味着，如果你将 Android 合规性策略分配给 user@contoso.com，该策略将同等地应用于其 Android 智能手机和 user@contoso.com 登录的任何基于 Android 的团队设备。

如果使用条件访问（需要强制执行 Intune 注册），则需要设置以下几项才能允许成功完成 Intune 注册：

- **Intune 许可证** 登录到团队设备的用户必须获得 Intune 许可。  只要团队设备登录到具有有效 Intune 许可证的用户帐户，该设备将在登录过程中自动注册到 Microsoft Intune 中。
- **配置 Intune** 你必须为 Android 设备管理员注册设置正确配置的 Intune 租户。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>将 Intune 配置为基于 Android 的设备注册团队

基于 Android 的团队设备通过 Android 设备管理员 (DA) 管理在 Intune 中管理。 在设备可以注册到 Intune 之前，需要执行一些基本步骤。  如果你现在已使用 Intune 管理设备，你可能已经完成了所有这些操作。  如果不是，请执行以下操作：

1. 将 Intune MDM (移动设备管理) 机构。  如果你以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅 [设置移动设备管理机构](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。  这是在创建新的 Intune 租户时必须执行的一次性步骤。
2. 启用 Android 设备管理员注册。 基于 Android 的团队设备通过 Intune 作为设备管理员设备进行管理。  默认情况下，对于新创建的租户，设备管理员注册处于关闭状态。  有关详细信息，请参阅 [Android 设备管理员注册](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. 为用户分配许可证。 必须为要注册到 Intune 的团队设备用户分配一个有效的 Intune 许可证。 有关详细信息，请参阅 [为用户分配许可证，以便他们可以在 Intune 中注册设备](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。
4. 分配设备管理员合规性策略。  创建一个 Android 设备管理员合规性策略，并将其分配给 Azure Active Directory 组，其中包含将登录到团队设备的用户。 有关详细信息，请参阅 [使用合规性策略为使用 Intune 管理的设备设置规则](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另请参阅

[Teams 电话](phones-for-teams.md)

[适用于 Microsoft 团队的 IP 手机认证](teams-ip-phones.md)

[团队显示](teams-displays.md)

[在 Teams 中管理设备](device-management.md)

[团队市场](https://office.com/teamsdevices)
