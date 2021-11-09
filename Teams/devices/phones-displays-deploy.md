---
title: 使用 Intune Teams Android Teams手机、Microsoft Teams 会议室和显示器
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.localizationpriority: medium
description: 本文概述了屏幕屏幕支持的功能Microsoft Teams的功能。
ms.openlocfilehash: 96ffaef167fd40b320ff4c1b9b7a6dca0e9c3325
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861959"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>使用 Intune Teams Android Teams手机、Microsoft Teams 会议室和显示器

本文概述了如何使用 Intune 在 Android Teams手机、Teams和Microsoft Teams 会议室设备。

## <a name="conditional-access"></a>条件访问

条件访问是Azure Active Directory (Azure AD) 一项功能，可帮助确保访问资源的设备Office 365管理正确且安全。  如果将条件访问策略应用到 Teams 服务，Android (设备（包括 Teams 手机、Teams 显示器和 Microsoft Teams 会议室）在 Android) 上需要将访问 Teams 的设备注册到 Intune 中，并且其设置需要符合策略。  如果设备未注册到 Intune，或者设备已注册，但其设置不符合策略，则条件访问将阻止用户登录或使用该设备上 Teams 应用。

通常，Intune 中定义的符合性策略将分配给用户组。  这意味着，如果将 Android 符合性策略分配给 user@contoso.com，该策略同样适用于其 Android 智能手机和任何登录Teams Android user@contoso.com 设备。

如果使用条件访问（要求强制使用 Intune 注册）在组织中，需要设置一些操作，以允许成功进行 Intune 注册：

- **Intune 许可证** 登录设备的用户Teams Intune 许可。  只要Teams登录到具有有效 Intune 许可证的用户帐户，该设备就会在 Microsoft Intune 中作为登录过程的一部分自动注册。
- **配置 Intune** 必须为 Android 设备管理员注册设置正确配置的 Intune 租户。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>配置 Intune 以Teams基于 Android 的设备

Teams基于 Android 的设备由 Intune 通过 Android 设备管理员 (DA) 管理。 在将设备注册到 Intune 之前，需要执行几个基本步骤。  如果当前已在使用 Intune 管理设备，可能已完成所有这些操作。  如果没有，下面是要执行哪些工作：

> [!NOTE]
> - 如果租户管理员希望将公用区域电话注册到 Intune 中，则需要将 Intune 许可证添加到帐户，并按照 Intune 注册的步骤操作。
> - 如果用于登录到 Teams设备的用户帐户未获得 Intune 的许可，则需要为帐户禁用 Intune 符合性策略和注册限制。



1. 将 Intune MDM (设置为") 管理"。  

   如果以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅 [设置移动设备管理机构](/intune/fundamentals/mdm-authority-set)。  这是一个一步，在创建新的 Intune 租户时必须完成。
1. 启用 Android 设备管理员注册。
  
   使用 Intune Teams基于 Android 的设备作为设备管理员设备进行管理。  默认情况下，对于新建的租户，设备管理员注册已关闭。 请参阅 [Android 设备管理员注册](/intune/enrollment/android-enroll-device-administrator)。
1. 向用户分配许可证。 
 
   必须Teams注册到 Intune 的设备的用户分配有效的 Intune 许可证。 有关详细信息，请参阅 [向用户分配许可证，以便他们可以在 Intune 中注册设备](/intune/fundamentals/licenses-assign)。
1. 分配设备管理员符合性策略。  

   1. 创建 Android 设备管理员符合性策略。

   1. 将其分配给Azure Active Directory组，该组包含要登录Teams的用户。 请参阅 [使用符合性策略为使用 Intune 管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另请参阅

[Teams 电话](phones-for-teams.md)

[经认证的 IP 电话Microsoft Teams](teams-ip-phones.md)

[Teams显示器](teams-displays.md)

[在 Teams 中管理设备](device-management.md)

[Teams市场](https://office.com/teamsdevices)
