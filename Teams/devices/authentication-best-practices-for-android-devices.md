---
title: Android 设备的身份验证最佳做法
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Android 设备身份验证Teams指南。
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
ms.openlocfilehash: 173986bdad846d27a7bd3ae5890269b88a58b3a2
ms.sourcegitcommit: cd4eb94d0b1e9316fca2e2b771b2286eaa866ba4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2021
ms.locfileid: "61566283"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>适用于 Android 设备的Teams最佳做法

本文提供有关为手机和呼叫设备部署Teams策略的一般指导和最佳做法。

>[!NOTE]
>条件访问需要Azure Active Directory (Azure AD) 高级版订阅。

>[!NOTE]
>Android 移动设备的策略可能不适用于 Teams Android 设备。 


## <a name="user-based-devices-vs-common-area-devices"></a>基于用户的设备与公用区设备

共享团队设备（如会议室设备或公用区域电话）不能对通常应用于个人设备的注册和合规性使用相同的要求。 将个人设备身份验证要求应用到共享设备将导致以下登录问题： 

1.  **由于密码策略，设备已退出**

在设备上Teams帐户具有密码过期策略。 与用户不同，与共享设备一起使用的帐户没有指定用户来更新和还原到密码过期时的有效状态。 如果组织要求密码定期过期和重置，这些帐户Teams，直到管理员重置密码Teams重新登录。

2.  **设备因条件访问策略而未能登录**

共享设备不符合用户帐户Azure AD设备的条件访问策略。 如果共享设备与用于条件访问策略的用户帐户或个人设备分组，则登录会失败。

例如，如果需要多重身份验证才能访问Teams身份验证，需要用户干预才能完成身份验证。 共享设备不支持多重身份验证。 同样，如果帐户配置为每隔 X 天重新进行身份验证，则共享设备在没有用户干预的情况下无法解决质询。

## <a name="best-practices-for-teams-shared-device-deployments"></a>共享设备Teams最佳做法

Microsoft 建议在组织中部署Teams以下设置。

### <a name="password-policy"></a>**密码策略**

Teams共享设备应该使用Exchange[资源帐户 。](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) 这些帐户可以从 Active Directory 同步，也可以直接在 Azure AD。 用户的任何密码过期策略也适用于在共享设备上Teams帐户。

为了避免密码过期策略导致中断，请为共享设备设置密码过期策略，使策略永不过期。

从 Teams 设备 CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams 版本 1449/1.0.94.2021022403 开始，适合 Teams 手机) 和[CY202 1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android)适用于 Android) 上的 Microsoft Teams 会议室 的更新 #2 (Teams 版本 1449/1.0.96.2021051904，租户管理员可以远程登录到 Teams 设备。 请勿与技术人员共享密码来设置设备。 管理员使用远程登录来发出验证码，然后从管理中心登录到Teams设备。

有关详细信息，请参阅 Android 设备的远程预配[Teams登录](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="conditional-access-policies"></a>**条件访问策略**

Azure AD条件访问设置设备登录必须满足的其他要求。 对于Teams，请查看以下指南，确定是否已编写相应的策略。 有关条件访问的概述，请参阅 [什么是条件访问](/azure/active-directory/conditional-access/overview)。

### <a name="multi-factor-authentication"></a>多因素身份验证

共享设备的帐户链接到会议室或物理空间，而不是用户帐户。 由于共享设备不支持多重身份验证，因此请从任何多重身份验证策略中排除共享设备。

>[!TIP]
>使用[命名位置或](/azure/active-directory/conditional-access/location-condition)[要求合规的设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)保护共享设备。

### <a name="location-based-access-with-named-locations"></a>具有命名位置的基于位置的访问

如果共享设备预配在可通过一系列 IP 地址标识的明确位置中，可以使用这些设备的命名位置配置条件访问。 [](/azure/active-directory/conditional-access/location-condition) 此条件将允许这些设备仅在网络内部访问公司资源。

### <a name="require-compliant-device"></a>需要合规的设备

>[!NOTE]
>设备符合性需要 Intune 许可证。

如果要将共享设备注册到 Intune 中，可以将设备符合性配置为条件访问中的控件，以便只有合规的设备可以访问企业资源。 Teams基于设备符合性为条件访问策略配置设备。 有关详细信息，请参阅条件[访问：要求符合或混合Azure AD设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

若要使用 Intune 设置设备的符合性设置，请参阅使用符合性策略为使用 [Intune 管理的设备设置规则](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 用于 hotdesking 的共享设备应从符合性策略中排除。 合规性策略阻止设备注册到热桌面用户帐户。 请改为使用命名位置保护这些设备。
> 若要提高安全性，除了命名位置[](/azure/active-directory/authentication/tutorial-enable-azure-mfa)策略外，还可以要求热支持用户进行多重身份验证。

### <a name="sign-in-frequency"></a>登录频率

在"条件访问"中[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)，可以配置登录频率，要求用户在指定的时间段后再次登录以访问资源。 如果对聊天室帐户强制实施登录频率，则共享设备将注销，直到管理员再次登录。Microsoft 建议从任何登录频率策略中排除共享设备。

### <a name="filters-for-devices"></a>设备的筛选器

[设备筛选器是](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)条件访问中的一项功能，可用于根据设备中可用的设备属性为设备配置更精细Azure AD。 还可在设备对象上设置扩展属性 1-15，然后使用这些值，以使用自己的自定义值。

在两个关键方案中使用设备的筛选器来标识公用区域设备并启用策略：

1.  从应用于个人设备的策略中排除共享设备。 例如，要求设备符合性不是针对用于热桌面的共享设备强制实施的，而是根据型号对所有其他设备强制实施。

2.  在不应应用于个人设备的共享设备上强制实施特殊策略。 例如，仅根据为这些设备设置的扩展属性要求命名位置作为策略，例如 (CommonAreaPhone") 。

>[!NOTE] 
> 某些属性（例如 **模型、****制造商** 和 **operatingSystemVersion）** 只能在由 Intune 管理设备时设置。 如果设备不是由 Intune 管理的，请使用扩展属性。