---
title: Microsoft Teams 共享设备管理 Android 设备的身份验证最佳做法。
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Teams 中共享 Android 设备管理的最佳做法。 此功能包括条件访问、密码策略、多重身份验证建议等。
ms.collection:
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0f658a70235440563d7cb3910830c56923b60f3e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270097"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android 设备上 Teams 共享设备管理的身份验证最佳做法

与 Teams 一起使用的设备的目标使得需要不同的设备管理策略。 例如，由单个销售人员使用的个人商业平板电脑与许多客户服务人员共享的通话电话具有不同的需求集。

安全管理员和操作团队必须规划可在组织中使用的设备。 它们必须实施最适合每个用途 *的安全* 措施。 本文的建议使其中一些决策更加简单。

>[!NOTE]
>条件访问需要 Azure Active Directory (Azure AD) 高级订阅。

>[!NOTE]
>Android 移动设备的策略可能不适用于 Teams Android 设备。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>个人设备与共享 android 设备的身份验证建议不同

共享 Teams 设备不能对个人设备上使用的注册和符合性使用相同的要求。 将个人设备身份验证要求应用于共享设备会导致登录问题。

1.  **设备由于密码策略而注销。**

Teams 设备上使用的帐户具有密码过期策略。 与共享设备一起使用的帐户没有特定用户在密码过期时更新并将其还原为工作状态。 如果你的组织要求密码过期并偶尔重置，这些帐户将停止在 Teams 设备上工作，直到 Teams 管理员重置密码并重新登录。

**挑战**：访问时。 来自设备的 Teams，人员的帐户具有密码过期策略。 密码过期时，只需更改密码即可。 但是，在 *共享设备* 上使用的帐户 (资源帐户) 可能无法连接到可以根据需要更改密码的单个人。 这意味着密码可以过期，并让工作人员当场离开，不知道如何恢复他们的工作。

当你的组织需要密码重置或强制密码过期时，请确保 Teams 管理员准备重置密码，以便这些共享帐户可以重新登录。

2.  **设备由于条件访问策略而无法登录。**

**挑战**：共享设备无法遵守用户帐户或个人设备的 Azure AD 条件访问策略。 如果共享设备与条件访问策略的用户帐户或个人设备分组，则登录将 *失败*。

例如，如果访问 Teams 需要多重身份验证，则需要输入代码来完成该身份验证。 共享设备通常没有可以配置和完成多重身份验证的单个用户。 此外，如果帐户必须每隔 X 天重新进行身份验证，则在没有用户干预的情况下，共享设备无法解决质询。

共享设备不支持多重身份验证。 下面概述了要使用的方法。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>使用 Teams 部署共享 android 设备的最佳做法

Microsoft 建议在组织中部署 Teams 设备时使用以下设置。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**使用资源帐户并限制其密码过期**

Teams 共享设备应使用 [Exchange 资源邮箱](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 创建这些邮箱会自动生成帐户。 这些帐户可以从 Active Directory 同步到 Azure AD，也可以直接在 Azure AD 中创建。 用户的任何密码过期策略也将应用于 Teams 共享设备上使用的帐户，因此，为了避免密码过期策略导致的中断，请将共享设备的密码过期策略设置为永不过期。

从 Teams 设备 [CY21 Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams 版本 1449/1.0.94.20210222403 开始，) 和 [CY2021 Update #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams 版本 1449/1.0.96.2021051904，适用于 Android) 上的Microsoft Teams 会议室， 租户管理员可以远程登录 Teams 设备。 租户管理员应使用远程登录来颁发验证码，而不是与技术人员共享密码来设置设备。 可以从 Teams 管理中心为这些设备进行登录。

有关详细信息，请参阅 [Teams Android 设备的远程预配和登录](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="review-these-conditional-access-policies"></a>**查看这些条件访问策略**

Azure AD 条件访问设置设备必须满足的其他要求才能登录。 对于 Teams 设备，请查看以下指南，以确定是否已创作了允许共享设备用户执行其工作的策略。

> [!TIP]
> 有关条件访问概述，请参阅 [什么是条件访问](/azure/active-directory/conditional-access/overview)？

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>不要对共享设备使用多重身份验证

共享设备的帐户链接到会议室或物理空间，而不是最终用户帐户。 由于共享设备不支持多重身份验证，因此从任何多重身份验证策略中排除共享设备。

>[!TIP]
>使用 [命名位置](/azure/active-directory/conditional-access/location-condition) 或 [需要符合条件的设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 来保护共享设备。

### <a name="you-can-use-location-based-access-with-named-locations"></a>可以对命名位置使用基于位置的访问

如果共享设备在定义明确的位置进行预配，可以使用一系列 IP 地址进行标识，则可以使用这些设备的 [命名位置](/azure/active-directory/conditional-access/location-condition) 配置条件访问。 此条件允许这些设备仅在网络中访问公司资源。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>何时以及何时不需要合规的共享设备

>[!NOTE]
>设备符合性需要Intune许可证。

如果要将共享设备注册到Intune，则可以在条件访问中将设备符合性配置为控件，以便只有符合条件的设备才能访问公司资源。 可以根据设备符合性为 Teams 设备配置条件访问策略。 有关详细信息，请参阅 [条件访问：需要符合或混合加入 Azure AD 的设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

若要使用Intune为设备设置符合性设置，请参阅[“使用符合性策略”为使用Intune管理的设备设置规则](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 应从符合性策略中排除用于 *热桌面的* 共享设备。 合规性策略会阻止设备注册到热桌用户帐户。 **而是使用命名位置来保护这些设备**。
> 为了提高安全性，除了命名位置策略之外，还可以要求对 *热桌面用户/用户帐户* 进行 [多重身份验证](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>从登录频率条件中排除共享设备

在条件访问中，可以 [配置登录频率](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) ，要求用户在指定的时间段后再次登录以访问资源。 如果对会议室帐户强制实施登录频率，共享设备将注销，直到管理员再次登录为止。Microsoft 建议从任何登录频率策略中排除共享设备。

### <a name="using-filters-for-devices"></a>对设备使用筛选器

[设备筛选器](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) 是条件访问中的一项功能，可用于根据 Azure AD 中提供的设备属性为设备配置更精细的策略。 还可以通过在设备对象上设置扩展属性 1-15，然后使用这些属性来使用自己的自定义值。

在两个关键方案中，使用设备筛选器标识常见区域设备并启用策略：

1.  从应用于个人设备的策略中排除共享设备。 例如，对于用于热桌面的共享设备 *，不强制要求* 设备符合性，而是根据模型号对所有其他设备 *强制实施* 。

2.  在 *不应* 应用于个人设备的共享设备上强制实施特殊策略。 例如，仅根据为这些 (设备设置的扩展属性要求命名位置作为策略，例如：“CommonAreaPhone”) 。

>[!NOTE] 
> 某些属性（如 **模型**、**制造商** 和 **operatingSystemVersion**）只能在设备由Intune管理时设置。 如果设备不是由Intune管理的，请使用扩展属性。
