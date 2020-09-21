---
title: Microsoft Teams 的电话功能
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文介绍针对 microsoft 团队认证的手机的列表，以及 Microsoft 团队的手机认证中支持的功能。
ms.openlocfilehash: cd38586b67f728febb4a43d3f018875b378cffd8
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962843"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 的电话功能

Microsoft 团队为需要传统电话体验的用户支持一套桌面电话。 本文提供了有关团队手机的完整概述，并可帮助你在 Microsoft Phone 系统解决方案中规划、提供和管理 Microsoft 团队的手机。 

为在手机上提供高质量和可靠的 Microsoft 团队体验，我们将与 Yealink、Crestron、联想、Polycom 和 Audiocodes 合作，以开发和认证一系列桌面手机和会议室音频设备。 若要获取有关团队设备的最新信息和最新信息，请转到 [团队市场](https://office.com/teamsdevices)。

要管理电话，您必须是全局管理员、团队服务管理员或团队设备管理员。有关管理员角色的详细信息，请参阅 [使用 Microsoft 团队管理员角色管理团队](../using-admin-roles.md)。

## <a name="features-supported-by-teams-phones"></a>团队手机支持的功能
团队认证的手机具有广泛的功能，可帮助你的用户完成工作，并帮助你管理其使用。 下面是团队认证的手机中可用的功能摘要：

- **身份验证** 手机使用新式身份验证简化登录和提高安全性。 用户可以通过在手机上输入用户名和密码，或通过其他设备（如 PC/智能手机）登录来登录。
- **快速拨号和通话记录** 用户可以快速访问其联系人、通话历史记录和语音邮件。 他们可以轻松地管理联系人，并通过电话快速拨打拨号条目。
- **会议和通话** 用户可以查看其日程安排，并轻松地使用团队的一次触控联接加入会议。
- **呼叫组** 参与呼叫组的电话代理可以轻松管理其可用性并接受或拒绝来自呼叫队列的传入呼叫。
- **用户委派** 行政助理和管理员可管理其执行官的电话-截取来电;代表总经理进行呼叫;接管管理层暂候的通话;并监控执行官是否在通话、保持通话等。
- **热 desking** 用户可以通过登录到手机来获取他们的联系人、会议和其他首选项。 完成后，他们可以注销，并让下一位用户的电话准备就绪。
- **视频** 带有视频支持的手机让用户加入呼叫和视频会议，就像他们在自己的计算机上一样。 用户可以通过使用手机的相机快门和麦克风静音开关（如果可用）来保持隐私。
- **更好地协作** 当连接到运行64位团队桌面客户端的 Windows 电脑时，手机可以以集成方式锁定和解锁。
- **辅助功能** 手机具有多种辅助功能（如高对比度文本），便于任何人使用。
- **动态和增强的 E911 支持** 呼叫911的登录用户将在手机上看到他们的位置。 
    > [!IMPORTANT]
    > 如果某个电话未登录，或者没有 Internet 连接，则无法放置911呼叫。 如果出现这种情况，将在手机上显示通知。

除了上述功能，您还可以根据分配给登录到手机的用户的许可证和电话策略的类型来控制可用的功能。 例如，使用个人帐户登录到手机的用户可以访问各种功能-通话、会议、语音邮件等。 如果帐户分配了登录到手机的通用区域电话许可证，则只能访问有限范围的功能;例如，通话记录和会议计划可能无法保留，例如保护用户的隐私。

## <a name="required-licenses"></a>需要的许可证

Microsoft 团队许可证可以作为其 [microsoft 365 和 Office 365 订阅](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)的一部分进行购买。 若要了解有关在手机上使用 Microsoft 团队所需的许可证的详细信息，请参阅可用的 [电话系统许可证](https://products.office.com/microsoft-teams/voice-calling)。

有关获取团队的详细信息，请查看 [如何获取 Microsoft 团队的访问权限？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>通过 Intune 部署你的手机

### <a name="conditional-access"></a>条件访问

条件访问是一种 Azure Active Directory 功能，可帮助你确保访问 Office 365 资源的设备正确管理且安全。  如果你将条件访问策略应用到团队服务，则 Android 设备 (包括团队电话) 需要将访问团队注册到 Intune 且其设置需要遵守你的策略。  如果设备未注册到 Intune，或者它已注册，但其设置不符合你的策略，则条件访问将阻止用户登录或使用设备上的 "团队" 应用。

通常，在 Intune 中定义的合规性策略将分配给用户组。  这意味着，如果你将 Android 合规性策略分配给 user@contoso.com，该策略将同等地应用于其 Android 智能手机和 user@contoso.com 登录的任何基于 Android 的团队设备。

如果使用条件访问（需要强制执行 Intune 注册），则需要设置以下几项才能允许成功完成 Intune 注册：

- **Intune 许可证** 登录到 Microsoft 团队手机的用户必须获得 Intune 许可。  只要 Microsoft 团队手机登录到具有有效 Intune 许可证的用户帐户，手机将在登录过程中自动注册到 Microsoft Intune 中。
- **配置 Intune** 你必须为 Android 设备管理员注册设置正确配置的 Intune 租户。

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>将 Intune 配置为基于 Android 的设备注册团队

基于 Android 的团队设备通过 Android 设备管理员 (DA) 管理在 Intune 中管理。 在设备可以注册到 Intune 之前，需要执行一些基本步骤。  如果你现在已使用 Intune 管理设备，你可能已经完成了所有这些操作。  如果不是，请执行以下操作：

1. 将 Intune MDM (移动设备管理) 机构。  如果你以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。 有关详细信息，请参阅 [设置移动设备管理机构](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。  这是在创建新的 Intune 租户时必须执行的一次性步骤。
2. 启用 Android 设备管理员注册。 基于 Android 的团队设备通过 Intune 作为设备管理员设备进行管理。  默认情况下，对于新创建的租户，设备管理员注册处于关闭状态。  有关详细信息，请参阅 [Android 设备管理员注册](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. 为用户分配许可证。 必须为要注册到 Intune 的团队设备用户分配一个有效的 Intune 许可证。 有关详细信息，请参阅 [为用户分配许可证，以便他们可以在 Intune 中注册设备](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。
4. 分配设备管理员合规性策略。  创建一个 Android 设备管理员合规性策略，并将其分配给 Azure Active Directory 组，其中包含将登录到团队设备的用户。 有关详细信息，请参阅 [使用合规性策略为使用 Intune 管理的设备设置规则](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="manage-your-phones"></a>管理您的手机

租户管理员可以通过团队管理中心管理所有团队设备并使其保持最新状态。 有关详细信息，请参阅 [在 Microsoft 团队中管理设备](https://docs.microsoft.com/microsoftteams/devices/device-management)。 

## <a name="see-also"></a>另请参阅

[团队市场](https://office.com/teamsdevices)

[适用于 Microsoft 团队的 IP 手机认证](teams-ip-phones.md)
