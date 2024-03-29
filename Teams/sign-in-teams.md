---
title: 不同的技术如何影响 Microsoft Teams 登录，包括限制登录和登录行为。
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: 了解单一登录和新式身份验证等技术如何影响 iOS、Android、macOS 和电脑上的登录行为。 如何将团队与多个帐户配合使用，并限制登录。 包括如何告诉 Teams 在登录时忽略用户名 (UPN) 的预填充。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c37d9fd2140aaae9ccce443c81c537dcfb92305e
ms.sourcegitcommit: 0181a62c8d5a3f5b28fbb5a15645f0e82a1b8f35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2022
ms.locfileid: "67734606"
---
# <a name="how-different-technologies-effect-microsoft-teams-sign-on"></a>不同的技术如何影响 Microsoft Teams 登录

如果需要了解单一登录 (SSO) 、新式身份验证 (MS) 以及多重身份验证 (MA) 如何影响用户的登录体验，本文将帮助阐明用户和管理员可以期待看到的内容。 它还概述了 macOS、android 和 iOS 设备的登录行为、使用多个帐户的登录工作原理、如何在登录屏幕上删除自动填充的凭据或“预填充”以及如何限制登录。

如果你的角色涉及了解 Microsoft 团队在登录期间的预期行为，请对本文进行书签。

## <a name="microsoft-teams-and-windows-users-sign-in-recommendations"></a>Microsoft Teams 和 Windows 用户：登录建议

Microsoft 建议组织使用带有“混合域加入”或“Azure AD 加入”配置的最新版 Windows 10。 使用最近的版本可以确保用户的账户在Windows的Web账户管理器中处于预先准备状态，从而实现单点登录到Teams和其他Microsoft应用程序。 单点登录提供了更好的用户体验（无声登录）和更好的安全状况。

Microsoft Teams 使用新式身份验证使登录体验简单而安全。若要了解用户如何登录Teams，请参阅 [登录Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

### <a name="how-modern-authentication-ma-effects-your-sign-in-what-users-will-see-when-ma-is-on"></a>新式身份验证 (MA) 如何影响登录：当 MA 处于打开状态时，用户将看到什么

新式身份验证是让 Teams 知道用户已在其他位置输入其凭据（如工作电子邮件和密码）的过程的一部分，不应要求他们再次输入以启动应用。 体验因多种因素而异，例如用户在 Windows 操作系统或 Mac 上工作。

登录行为也会有所不同，具体取决于组织是否已启用单因素身份验证或多重身份验证。 多重身份验证通常包括通过电话、提供唯一代码、输入 PIN 或者指纹验证凭据。 

每个使用 Teams 的组织都可以使用现代身份验证。 如果用户无法完成此过程，则你的组织的 Azure AD 配置可能存在基础问题。 有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

下面是用户在每个新式身份验证方案中可以期待的行为的破败。

- 如果用户已使用工作或学校帐户登录到 Windows 或其他 Office 应用，在启动 Teams 时将直接进入应用。无需输入其凭据。

- Microsoft 建议使用 Windows 10 版本 1903 或更高版本获取最佳单一登录体验。

- 如果用户未在任何其他位置登录其 Microsoft 工作或学校帐户，则当他们启动 Teams 时，系统会要求他们提供单一或多重身份验证（SFA 或 MFA）。此流程具体取决于组织已决定采用的必要登录程序。

- 如果用户登录到已加入域的计算机，则在启动 Teams 时，系统可能会要求他们再执行一个身份验证步骤，具体取决于你的组织是选择要求 MFA 还是其计算机已要求通过 MFA 登录。如果他们的计算机已要求通过 MFA 登录，则当他们打开 Teams 时，应用会自动启动。

- 在已加入域的电脑上，如果无法使用 SSO，Teams 可能会使用用户主体名称预填充其登录屏幕 (UPN) 。 在某些情况下，你可能不希望采取这种做法，尤其是在你的组织在本地和 Azure Active Directory 中使用不同 UPN 的情况下。 如果是这种情况， **可以使用以下 Windows 注册表项关闭 UPN 的预填充**：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。

### <a name="microsoft-teams-sign-on-to-another-account-on-a-domain-joined-computer"></a>Microsoft Teams 登录到已加入域的计算机上的另一个帐户

在加入域的计算机上的用户可能无法使用同一 Active Directory 域中的其他帐户登录 Teams。

## <a name="macos-users-and-microsoft-teams-sign-on-prompts"></a>macOS 用户和 Microsoft Teams 登录提示

在 macOS 上，Teams 将提示用户输入其用户名和凭据，并且可能会根据组织的设置提示进行多重身份验证。 用户输入其凭据后，他们无需再次提供凭据。 此后，只要是在同一台计算机上工作，Teams 都将自动启动。

## <a name="microsoft-teams-sign-on-for-ios-and-android-users"></a>适用于 iOS 和 Android 用户的 Microsoft Teams 登录

登录时，移动用户将看到当前已登录的或其设备上以前登录的所有 Microsoft 365 帐户的列表。 用户可点击任意帐户进行登录。 移动登录有两种方案：

1. 如果所选帐户当前已登录到其他 Office 365 或 Microsoft 365 应用，则用户将直接登录到 Teams。用户无需输入其凭据。

2. 如果用户未在其他任何位置登录到其 Microsoft 365 帐户，则系统会要求他们提供单一或多重身份验证（SFA 或 MFA），具体取决于组织对移动设备登录策略的配置。

> [!NOTE]
> 对于要体验本部分中所述的登录体验的用户，其设备必须正在运行 Teams for iOS 版本2.0.13（内部版本 2020061704）或更高版本，或者 Teams for Android 版本 1416/1.0.0.2020061702 或更高版本。

## <a name="using-microsoft-teams-with-multiple-sign-in-accounts"></a>将 Microsoft Teams 与多个登录帐户配合使用

Teams for iOS 和 Android 支持多个工作、学校和多个个人帐户并行使用。 Teams 桌面应用程序将在 2020 年 12 月支持并行使用一个工作/学校和一个个人帐户，随后将推出支持多个工作/学校帐户。

以下图像显示用户如何在 Teams 移动应用中添加多个帐户。

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="在 Teams 中添加多个账户。":::

## <a name="restrict-sign-in-to-microsoft-teams"></a>将登录限制为 Microsoft Teams

组织可能希望限制在受管理的设备上使用公司许可的应用的方式，例如，限制学生或员工访问其他组织中的数据，或将公司许可的应用用于个人的情况。 可通过设置 Teams 应用程序识别的设备策略来强制实施这些限制。

### <a name="how-to-restrict-microsoft-teams-sign-in-on-mobile-devices"></a>如何限制移动设备上的 Microsoft Teams 登录

Teams for iOS 和 Android 提供 IT 管理员将帐户配置推送到 Microsoft 365 帐户的功能。 此功能适用于使用[托管应用配置](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)通道（适用于iOS）或 [Android Enterprise](https://developer.android.com/work/managed-configurations) 通道（适用于Android）的任何移动设备管理（MDM）提供商。

对于已注册 Microsoft Intune 的用户，可以使用 Azure 门户中的 Intune 部署帐户配置设置。

在 MDM 提供程序中配置帐户设置配置后，用户注册其设备后，在登录页上，适用于 iOS 和 Android 的 Teams 将仅在 Teams 登录页上显示允许的帐户。用户可以点击此页面上允许的任何帐户进行登录。

在 Azure Intune 门户中为托管设备设置以下配置参数。

|平台 |密钥  |值  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **启用**：唯一允许的帐户是 IntuneMAMUPN 密钥定义的托管用户帐户。<br> **禁用**（或者与 **启用** 不匹配的任何区分大小写的值）：允许任何帐户。        |
|iOS     |   **IntuneMAMUPN**      |   允许登录到 Teams 的帐户的 UPN。<br> 对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    仅允许的账户是此密钥定义的托管用户账户。<br> 一个或多个分号；] - 分隔的UPN。<br> 对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。

设置帐户设置配置后，Teams 将限制登录功能，以使只有已注册设备上的允许账户才能获得访问权限。

若要创建托管 iOS/iPadOS 设备的应用配置策略，请参阅[添加托管 iOS/iPadOS 设备的应用配置策略](/mem/intune/apps/app-configuration-policies-use-ios)。

若要创建托管 Android 设备的应用配置策略，请参阅[添加托管 Android 设备的应用配置策略](/mem/intune/apps/app-configuration-policies-use-android)。

### <a name="how-to-restrict-teams-sign-in-on-desktop-devices"></a>如何限制桌面设备上的 Teams 登录

Windows 和 macOS 上的 Microsoft Teams 应用正在获得对限制登录到组织的设备策略的支持。 可通过常规设备管理解决方案（例如 MDM（移动设备管理）或 GPO（组策略对象））设置策略。

在设备上配置此策略时，用户仅可使用位于 Azure AD 租户（包含于策略中定义的 “租户允许列表” ）中的帐户登录。 该策略应用于所有登录，包括第一个和其他帐户。 如果你的组织包括多个 Azure AD 租户，则可以在允许列表中包含多个租户 ID。 Teams 应用中的 “添加其他帐户” 的链接可能仍处于可见状态，但它们不可操作。

> [!NOTE]
> 
>1. 策略仅限制登录，不会限制将用户邀请为其他 Azure AD 租户中的来宾，或切换到其他租户（其中已将用户邀请为来宾）的功能。
>2. 该策略要求 Teams for Windows 版本1.3.00.30866 或更高版本以及Teams for MacOS 版本1.3.00.30882 （发布时间为 2020 年 11 月中）。

**Windows** 管理模板文件 （ADMX/ADML） 策略从 [下载中心](https://www.microsoft.com/download/details.aspx?id=49030) 提供（管理模板文件中的策略设置描述性名称是"限制登录到特定租户中的 Teams 的帐户"）。此外，还可以在 Windows 注册表中手动设置密钥：

- 值名称： RestrictTeamsSignInToAccountsFromTenantList
- 值类型：字符串
- 值数据：租户 ID 或以逗号分隔的租户 ID 列表
- 路径：使用下列内容之一

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

示例： SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 或 SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3

**MacOS适用策略** 对于MacOS 的托管设备，使用 .plist 来部署登录限制。 配置文件是一个 plist 文件，其中包含由键标识的项（表示首选项名称），后跟一个值（该值取决于首选项的特性）。 值可以是简单的（如数值）或复杂的（如首选项的嵌套列表）。

- 域：com.microsoft.teams
- 密钥： RestrictTeamsSignInToAccountsFromTenantList
- 数据类型：字符串
- 备注：输入逗号分隔的 Azure AD 租户 ID 列表

### <a name="global-sign-in-and-microsoft-teams"></a>全局登录和 Microsoft Teams

现在，Teams Android 应用支持全局登录，为第一线工作者提供简便的登录体验。 员工可以从共享设备池中选取设备，使其在排班期间单一登录到“归为己有”。 在他们值班结束后，应能够执行注销，以便在设备上全局注销。 有关详细信息，请参阅[ Teams 注销](sign-out-of-teams.md)。 这将从设备中删除其所有个人和公司信息，以便其可以将设备返回设备池。 若要获取此功能，设备必须处于共享模式。 在退出之前，请确保在设备上结束任何活动会议或通话。若要了解如何设置共享设备，请参阅 [如何在 Android 中使用共享设备模式](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。

该登录体验看起来类似于标准的 Teams 登录体验。

## <a name="urls-and-ip-address-ranges-for-microsoft-teams"></a>Microsoft Teams 的 URL 和 IP 地址范围

Teams 需要连接到 Internet。若要了解在 Office 365 计划、政府云和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
