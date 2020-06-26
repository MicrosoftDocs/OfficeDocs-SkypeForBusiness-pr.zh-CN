---
title: 使用新式验证登录 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 了解新式验证的工作原理、如何切换帐户，以及如何解决新式验证中的问题。 包括如何告诉 Teams 在登录时忽略用户名 (UPN) 预填充。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d6e4e8989bf26e4a907deec550d18f344728129
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868299"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式验证登录 Microsoft Teams
==========================

Microsoft 建议组织使用带有“混合域加入”或“Azure AD 加入”配置的最新版 Windows 10。 这可以确保在 Windows 的 Web 帐户管理器中预先准备用户帐户，进而启用 Teams 和其他 Microsoft 应用程序的单一登录。 这样可以带来更好的用户体验（静默式登录）和更好的安全状态。

Microsoft Teams 使用新式验证保持登录体验简单而安全。 若要了解用户如何登录 Teams，请阅读[登录 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式验证的工作原理

新式验证是一种使 Teams 知道用户已在其他位置输入凭据（如工作电子邮件和密码）而不再需要再次输入凭据即可启动应用的过程。 体验将因几个因素（如用户在 Windows 上还是在 Mac 上工作）而异。 具体将取决于你的组织启用了单重身份验证还是多重身份验证（多重身份验证通常涉及通过手机验证凭据、提供唯一代码、输入 PIN 或提供指纹）。 下面是每个新式身份验证应用场景的描述。

### <a name="windows-users"></a>Windows 用户

- 如果用户已通过其工作或学校帐户登录到 Windows 或其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。 他们无需输入凭据。

- Microsoft 建议使用 Windows 10 版本 1903 或更高版本获取最佳单一登录体验。

- 如果用户未在任何其他位置登录其 Microsoft 工作或学校帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA），具体验证方式取决于你的组织已决定采用的必要验证过程。

- 如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。 如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。

- 在加入域的电脑上，如果无法进行 SSO，Teams 可能会使用用户主体名称 (UPN) 预填充其登录屏幕。 在某些情况下，你可能不希望采取这种做法，尤其是在你的组织在本地和 Azure Active Directory 中使用不同 UPN 的情况下。 如果是这种情况，则可以使用以下 Windows 注册表项来关闭 UPN 的预填充：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。


### <a name="mac-users"></a>Mac 用户

在 MacOS 上，Teams 将提示用户输入其用户名和凭据，并且可能会根据组织的设置提示进行多重身份验证。 用户输入其凭据后，他们无需再次提供凭据。 此后，只要是在同一台计算机上工作，Teams 都将自动启动。

## <a name="teams-for-ios-and-android-users"></a>iOS 和 Android 版 Teams 用户

登录时，移动用户将看到当前已登录的或其设备上以前登录的所有 Microsoft 365 帐户的列表。 用户可点击任意帐户进行登录。 移动登录有两种方案：
    
1. 如果所选帐户当前已登录到其他 Office 365 或 Microsoft 365 应用，则用户将直接进入 Teams。 用户无需输入其凭据。
    
2. 如果用户未在其他任何位置登录到其 Microsoft 365 帐户，则系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织已针对”移动登录”策略配置的内容。

### <a name="adding-multiple-accounts-to-teams"></a>添加多个帐户至 Teams

IOS 和 Android 版 Teams 支持将多个帐户从单个设备添加到 Teams。 以下图像显示用户如何在 Teams 中添加多个帐户。
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="添加多个帐户至 Teams 中":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>使用企业移动性管理来控制可登录 Teams 的帐户

IOS 和 Android 版 Teams 向 IT 管理员提供将帐户配置推送到 Microsoft 365 帐户的功能。 此功能适用于使用 [托管应用配置](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道（适用于iOS）或 [ Android Enterprise ](https://developer.android.com/work/managed-configurations) 通道（适用于Android）的任何移动设备管理（MDM）提供商。

对于已注册 Microsoft Intune 的用户，可以使用 Azure 门户中的 Intune 部署帐户配置设置。

在 MDM 提供程序中设置帐户设置配置后，用户注册其设备后，iOS 和 Android 版 Teams 将仅显示 Teams 登录页面上的允许帐户。 用户可以在此页面上点击任何允许的帐户来登录。

在 Azure Intune 门户中为托管设备设置以下配置参数。


|平台 |密钥  |值  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **启用**：唯一允许的帐户是 IntuneMAMUPN 密钥定义的托管用户帐户。<br> **禁用**（或者与**启用**不匹配的任何区分大小写的值）：允许任何帐户。        |
|iOS     |   **IntuneMAMUPN**      |   允许登录到 Teams 的帐户的 UPN。<br> 对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    仅允许的账户是此密钥定义的托管用户账户。<br> 一个或多个分号 [;] 分隔的 UPN。<br> 对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。

设置帐户设置配置后，Teams 将限制登录功能，以使只有已注册设备上的允许账户才能获得访问权限。

若要创建托管 iOS/iPadOS 设备的应用配置策略，请参阅 [添加托管 iOS/iPadOS 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。

若要创建托管 Android 设备的应用配置策略，请参阅 [添加托管 Android 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。


## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式验证后切换帐户

如果用户在加入域的计算机上工作（例如，如果他们的租户已启用 Kerberos），则他们在完成新式验证后无法切换用户帐户。 如果用户不在加入域的计算机上工作，则可以切换帐户。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>完成新式验证后注销 Teams

若要注销 Teams，用户可以单击应用顶部的个人资料图片，然后选择“**注销**”。他们还可以右键单击任务栏中的应用图标，然后选择“**注销**”。注销 Teams 后，他们需要再次输入凭据才能启动该应用。

### <a name="signing-out-of-teams-for-ios-and-android"></a>退出 iOS 和 Android 版 Teams

移动用户可以通过以下方法退出小组：进入菜单，然后选择“**更多**”菜单，然后选择“**退出**”。退出后，用户下次启动该应用程序时需要重新输入其凭据。

> [!NOTE]
> Android 版 Teams 使用单一登录（SSO）来简化登录体验。 除了 Teams 之外，用户应确保退出**所有** Microsoft 应用，以便完全退出 Android 平台。

## <a name="urls-and-ip-address-ranges"></a>URL 和 IP 地址范围

Teams 需要连接到 Internet。 若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!IMPORTANT]
> 目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务 (<https://ssl.gstatic.com)>；即使你不使用 Gstatic，也是如此。 Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。

## <a name="troubleshooting-modern-authentication"></a>新式验证疑难解答

使用 Teams 的每个组织均可使用新式验证，因此如果用户无法完成该过程，则你的域或组织的 Microsoft 工作或学习帐户可能存在问题。

有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)
