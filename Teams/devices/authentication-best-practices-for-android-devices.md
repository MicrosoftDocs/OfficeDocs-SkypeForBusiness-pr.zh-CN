---
title: 有关在 Android Microsoft Teams共享设备管理的身份验证最佳做法。
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 有关在 Teams 中共享 android 设备管理Teams。 此功能包括条件访问、密码策略、多重身份验证建议等。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279230"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>有关在 Android 设备上Teams设备管理的身份验证最佳做法

与设备一起使用的设备Teams需要不同的设备管理策略。 例如，单个销售人员使用的个人商业平板电脑与许多客户服务人员共享的呼叫电话具有不同的需求集。

安全管理员和运营团队必须规划可在组织中使用的设备。 它们必须 *实施* 最适合每个用途的安全措施。 本文的建议使其中一些决策更容易。

>[!NOTE]
>条件访问需要Azure Active Directory (Azure AD) 高级版订阅。

>[!NOTE]
>Android 移动设备的策略可能不适用于 Teams Android 设备。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>对于个人设备与共享 Android 设备，身份验证建议不同

共享Teams设备不能对个人设备上使用的注册和符合性使用相同的要求。 将个人设备身份验证要求应用到共享设备将导致登录问题。

1.  **由于密码策略，设备已退出。**

在设备上Teams帐户具有密码过期策略。 与共享设备一起使用的帐户没有特定用户，因此无法更新密码，在密码过期时将其还原到工作状态。 如果组织偶尔要求密码过期和重置，这些帐户将停止在 Teams 设备上工作，直到管理员重置密码Teams重新登录。

**挑战**：访问时。 Teams，则用户的帐户具有密码过期策略。 密码即将过期时，只需更改密码。 但是，在共享设备上 *(* 资源) 帐户帐户可能不会与可更改密码的单个人员连接。 这意味着密码可能会过期，让工作人员留在现场，不知道如何继续工作。

当组织需要密码重置或强制密码过期时，请确保Teams管理员已准备好重置密码，以便这些共享帐户可以重新登录。

2.  **设备因条件访问策略而未能登录。**

**挑战**：共享设备不符合用户帐户Azure AD个人设备的条件访问策略。 如果共享设备与用于条件访问策略的用户帐户或个人设备分组，则登录 *会失败*。

例如，如果需要多重身份验证才能访问 Teams，则用户需要输入代码才能完成该身份验证。 共享设备通常没有可以配置和完成多重身份验证的单个用户。 此外，如果帐户必须每隔 X 天重新进行身份验证，则共享设备在没有用户干预的情况下无法解决质询。

共享设备不支持多重身份验证。 下面概述了要改为使用的方法。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>使用 Teams 部署共享 android 设备Teams

在组织中部署Teams时，Microsoft 建议以下设置。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**使用资源帐户并延长其密码过期时间**

Teams共享设备应该使用Exchange[邮箱](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 创建这些邮箱会自动生成帐户。 这些帐户可以同步到 Active Directory Azure AD直接在 Active Directory 中创建Azure AD。 用户的任何密码过期策略也适用于 Teams 共享设备上使用的帐户，因此，为了避免密码过期策略导致的中断，请为共享设备设置密码过期策略，使该策略永不过期。

从 Teams 设备 CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams 版本 1449/1.0.94.2021022403 开始，适合 Teams 手机) 和 [CY202 更新 #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Android) 上的 Microsoft Teams 会议室 版本 1449/1.0.96.2021051904，租户管理员可以远程登录到 Teams 设备。 租户管理员应该使用远程登录来发出验证码，而不是与技术人员共享密码来设置设备。 可以从管理中心为这些设备Teams登录。

有关详细信息，请参阅 Android 设备的远程预配[Teams登录](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="review-these-conditional-access-policies"></a>**查看这些条件访问策略**

Azure AD条件访问设置设备登录必须满足的其他要求。 对于Teams，请查看以下指南，确定是否已创作允许共享设备用户执行其工作的策略。

> [!TIP]
> 有关条件访问的概述，请参阅 [什么是条件访问](/azure/active-directory/conditional-access/overview)？

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>不要对共享设备使用多重身份验证

共享设备的帐户链接到会议室或物理空间，而不是链接到最终用户帐户。 由于共享设备不支持多重身份验证，因此请从任何多重身份验证策略中排除共享设备。

>[!TIP]
>使用[命名位置或](/azure/active-directory/conditional-access/location-condition)[要求合规的设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)保护共享设备。

### <a name="you-can-use-location-based-access-with-named-locations"></a>可以将基于位置的访问用于命名位置

如果共享设备预配在可通过一系列 IP 地址标识的明确位置中，可以使用这些设备的命名位置配置条件访问。[](/azure/active-directory/conditional-access/location-condition) 此条件将允许这些设备仅在网络内部访问公司资源。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>何时不需要合规的共享设备

>[!NOTE]
>设备符合性需要 Intune 许可证。

如果要将共享设备注册到 Intune 中，可以将设备符合性配置为条件访问中的控件，以便只有合规的设备可以访问企业资源。 Teams基于设备符合性为条件访问策略配置设备。 有关详细信息，请参阅条件访问：要求符合要求或[Azure AD设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

若要使用 Intune 设置设备的符合性设置，请参阅使用符合性策略为使用 [Intune 管理的设备设置规则](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 用于热桌面的 *共享设备应* 排除在合规性策略之外。 合规性策略阻止设备注册到热桌面用户帐户。 **请改为使用命名位置保护这些设备**。
> 若要提高安全性，除了命名位置 [](/azure/active-directory/authentication/tutorial-enable-azure-mfa)策略外，还可以要求对热支持用户 */* 用户帐户进行多重身份验证。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>从登录频率条件中排除共享设备

在"条件访问"中[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)，可以配置登录频率，要求用户在指定的时间段后再次登录以访问资源。 如果对聊天室帐户强制实施登录频率，则共享设备将注销，直到管理员再次登录。Microsoft 建议从任何登录频率策略中排除共享设备。

### <a name="using-filters-for-devices"></a>使用设备的筛选器

[设备筛选器是](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)条件访问中的一项功能，可用于根据设备中可用的设备属性为设备配置更精细Azure AD。 还可在设备对象上设置扩展属性 1-15，然后使用这些值，以使用自己的自定义值。

在两个关键方案中使用设备的筛选器来标识公用区域设备并启用策略：

1.  从应用于个人设备的策略中排除共享设备。 例如，要求设备 *符合性* 不是针对用于热桌面的共享设备强制实施的，而是针对所有其他设备强制实施的，基于型号。

2.  在不应应用于个人设备的共享设备上强制实施特殊策略。 例如，仅根据为这些设备设置的扩展属性要求命名位置作为策略，例如 (CommonAreaPhone") 。

>[!NOTE] 
> 某些属性（例如 **模型**、 **制造商** 和 **operatingSystemVersion** ）只能在由 Intune 管理设备时设置。 如果设备不是由 Intune 管理的，请使用扩展属性。
