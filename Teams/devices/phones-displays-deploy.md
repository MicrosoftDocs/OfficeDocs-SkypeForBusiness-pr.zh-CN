---
title: 使用Intune在Android上部署Teams手机、Teams显示器、Teams面板和Microsoft Teams 会议室
ms.author: serdars
author: SerdarSoysal
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
description: 本文概述了Microsoft Teams Android设备支持的功能。
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674854"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>使用Intune在Android上部署Teams手机、Teams显示器、Teams面板和Microsoft Teams 会议室

本文概述了如何使用Intune部署Teams手机、Teams显示器、Teams面板和Microsoft Teams 会议室Android。

## <a name="conditional-access"></a>条件访问

条件访问是一项Azure Active Directory (Azure AD) 功能，可帮助你确保访问Office 365资源的设备得到正确管理且安全。  如果将条件访问策略应用到Teams服务，Android设备 (包括Teams手机、Teams显示、Teams面板和Microsoft Teams 会议室，Android) 需要将访问Teams注册到Intune及其设置需要符合策略。  如果设备未注册到Intune，或者已注册但其设置不符合策略，条件访问将阻止用户登录或使用设备上的Teams应用。

通常，Intune中定义的符合性策略分配给用户组。  这意味着，如果将Android合规性策略分配给 user@contoso.com，该策略将同样应用于其Android智能手机和任何 user@contoso.com 登录的基于Android的Teams设备。

如果使用条件访问（需要强制执行Intune注册），则需要在组织中设置几项内容才能成功Intune注册：

- **Intune许可证** 登录到Teams设备的用户必须获得Intune许可。  只要Teams设备登录到具有有效Intune许可证的用户帐户，设备就会自动注册Microsoft Intune作为登录过程的一部分。
- **配置Intune** 必须为Android设备管理员注册设置正确配置的Intune租户。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>配置Intune以注册基于Teams Android的设备

基于Teams Android的设备通过Android设备管理员 (DA) 管理Intune进行管理。 在将设备注册到Intune之前，需要执行一些基本步骤。  如果你现在已经在使用Intune管理设备，你可能已经完成了所有这些操作。  如果没有，下面是要执行的操作：

> [!NOTE]
> - 如果租户管理员希望将公共区域电话注册到Intune，则他们需要向帐户添加Intune许可证，并按照步骤Intune注册。
> - 如果用于登录Teams设备的用户帐户未获得Intune许可，则需要为该帐户禁用Intune合规性策略和注册限制。



1. 设置 Intune MDM (移动设备管理) 颁发机构。  

   如果以前从未使用过Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅 [“设置移动设备管理机构](/intune/fundamentals/mdm-authority-set)”。  这是创建新的Intune租户时必须执行的一次性步骤。
1. 启用Android设备管理员注册。
  
   基于Android Teams设备以设备管理员设备的身份进行管理，并具有Intune。  默认情况下，新创建的租户的设备管理员注册处于关闭状态。 请参阅[Android设备管理员注册](/intune/enrollment/android-enroll-device-administrator)。
1. 向用户分配许可证。 
 
   必须为注册到Intune的Teams设备的用户分配有效的Intune许可证。 有关详细信息，请参阅[向用户分配许可证，以便他们可以在Intune中注册设备](/intune/fundamentals/licenses-assign)。
1. 分配设备管理员符合性策略。  

   1. 创建Android设备管理员合规性策略。

   1. 将其分配给包含将登录到Teams设备的用户的Azure Active Directory组。 请参阅[使用符合性策略为使用Intune管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另请参阅

[Teams 电话](phones-for-teams.md)

[已通过Microsoft Teams认证的 IP 电话](teams-ip-phones.md)

[Teams显示](teams-displays.md)

[在 Teams 中管理设备](device-management.md)

[Teams市场](https://office.com/teamsdevices)
