---
title: 登录 Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: 了解新式身份验证的工作方式、如何切换帐户，以及如何排除新式身份验证故障，以及如何在登录时告诉团队忽略预先填充的用户名称（UPN）。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7adc2d1cf040c778251784b19c92b1f79d7071fe
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711639"
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="23adc-104">登录 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23adc-104">Sign in to Microsoft Teams</span></span>
==========================

## <a name="windows-users"></a><span data-ttu-id="23adc-105">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="23adc-105">Windows users</span></span>

<span data-ttu-id="23adc-p102">Microsoft 建议组织使用具有混合域Join或 Azure AD Join 配置的最新版本 Windows 10。使用最新版本可确保在 Windows 的 Web 帐户管理器中准备好用户帐户，进而支持团队和其他 Microsoft 应用程序的单一登录。单一登录可提供更好的用户体验（静默式登录）和更好的安全态势。</span><span class="sxs-lookup"><span data-stu-id="23adc-p102">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration. Using recent versions ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turn enables single sign-on to Teams and other Microsoft applications. Single sign-on provides a better user experience (silent sign in) and a better security posture.</span></span>

<span data-ttu-id="23adc-p103">Microsoft Teams 使用新式身份验证使登录体验简单而安全。若要了解用户如何登录Teams，请参阅 [登录Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="23adc-p103">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure. To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

### <a name="how-modern-authentication-works"></a><span data-ttu-id="23adc-111">新式验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="23adc-111">How modern authentication works</span></span>

<span data-ttu-id="23adc-112">新式验证是一种使 Teams 知道用户已在其他位置输入其凭据，如工作电子邮件和密码，而不再需要再次输入凭据即可启动应用。</span><span class="sxs-lookup"><span data-stu-id="23adc-112">Modern authentication is a process that lets Teams know that users have already entered their credentials, such as their work email and password elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="23adc-113">体验的不同因几个因素而异，如用户在 Windows 上还是在 Mac 上工作异。</span><span class="sxs-lookup"><span data-stu-id="23adc-113">The experience varies depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="23adc-114">具体取决于你的组织是否启用了单因素身份验证还是多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="23adc-114">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication.</span></span> <span data-ttu-id="23adc-115">多重身份验证通常涉及通过电话验证凭据、提供唯一代码、输入 PIN 或者出示拇指指纹。</span><span class="sxs-lookup"><span data-stu-id="23adc-115">Multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint.</span></span> <span data-ttu-id="23adc-116">下面是每个新式身份验证应用场景的描述。</span><span class="sxs-lookup"><span data-stu-id="23adc-116">Here's a rundown of each modern authentication scenario.</span></span>

<span data-ttu-id="23adc-117">每个使用 Teams 的组织都可以使用现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="23adc-117">Modern authentication is available for every organization that uses Teams.</span></span> <span data-ttu-id="23adc-118">如果用户无法完成此过程，则你的组织的 Azure AD 配置可能存在基础问题。</span><span class="sxs-lookup"><span data-stu-id="23adc-118">If users aren't able to complete the process, there might be an underlying issue with your organization's Azure AD configuration.</span></span> <span data-ttu-id="23adc-119">有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="23adc-119">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

- <span data-ttu-id="23adc-120">如果用户已通过其工作或学校帐户登录到 Windows 或其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。</span><span class="sxs-lookup"><span data-stu-id="23adc-120">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="23adc-121">他们无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="23adc-121">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="23adc-122">Microsoft 建议使用 Windows 10 版本 1903 或更高版本获取最佳单一登录体验。</span><span class="sxs-lookup"><span data-stu-id="23adc-122">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="23adc-123">如果用户未在任何其他位置登录其 Microsoft 工作或学校帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA）。</span><span class="sxs-lookup"><span data-stu-id="23adc-123">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA).</span></span> <span data-ttu-id="23adc-124">此过程取决于你的组织决定需要登录过程的要求。</span><span class="sxs-lookup"><span data-stu-id="23adc-124">This process depends on what your organization has decided they'd like the sign-in procedure to require.</span></span>

- <span data-ttu-id="23adc-125">如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="23adc-125">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="23adc-126">如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。</span><span class="sxs-lookup"><span data-stu-id="23adc-126">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="23adc-127">在加入域的电脑上，如果无法进行 SSO，Teams 可能会使用用户主体名称 (UPN) 预填充其登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="23adc-127">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="23adc-128">在某些情况下，你可能不希望采取这种做法，尤其是在你的组织在本地和 Azure Active Directory 中使用不同 UPN 的情况下。</span><span class="sxs-lookup"><span data-stu-id="23adc-128">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="23adc-129">如果是这种情况，则可以使用以下 Windows 注册表项来关闭 UPN 的预填充：</span><span class="sxs-lookup"><span data-stu-id="23adc-129">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="23adc-130">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="23adc-130">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="23adc-131">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="23adc-131">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="23adc-132">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="23adc-132">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="23adc-133">默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="23adc-133">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

### <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="23adc-134">完成新式身份验证后注销 Teams</span><span class="sxs-lookup"><span data-stu-id="23adc-134">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="23adc-135">若要注销 Teams，用户可以选择应用顶部的个人资料图片，然后选择 **注销**。他们还可以右键单击任务栏中的应用图标，然后选择 **注销**。注销 Teams 后，他们需要再次输入凭据才能启动该应用。</span><span class="sxs-lookup"><span data-stu-id="23adc-135">To sign out of Teams, users can select their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a><span data-ttu-id="23adc-136">在加入域的计算机上登录到另一个帐户</span><span class="sxs-lookup"><span data-stu-id="23adc-136">Signing in to another account on a Domain Joined computer</span></span>

<span data-ttu-id="23adc-137">在加入域的计算机上的用户可能无法使用同一 Active Directory 域中的其他帐户登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="23adc-137">Users on domain-joined computer may not be able to sign in to Teams with another account in the same Active Directory domain.</span></span>

## <a name="macos-users"></a><span data-ttu-id="23adc-138">MacOS 用户</span><span class="sxs-lookup"><span data-stu-id="23adc-138">MacOS users</span></span>

<span data-ttu-id="23adc-139">在 MacOS 上，Teams 将提示用户输入其用户名和凭据，并且可能会根据组织的设置提示进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="23adc-139">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="23adc-140">用户输入其凭据后，他们无需再次提供凭据。</span><span class="sxs-lookup"><span data-stu-id="23adc-140">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="23adc-141">此后，只要是在同一台计算机上工作，Teams 都将自动启动。</span><span class="sxs-lookup"><span data-stu-id="23adc-141">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="teams-on-ios-and-android-users"></a><span data-ttu-id="23adc-142">iOS 和 Android 版 Teams 用户</span><span class="sxs-lookup"><span data-stu-id="23adc-142">Teams on iOS and Android users</span></span>

<span data-ttu-id="23adc-143">登录时，移动用户将看到当前已登录的或其设备上以前登录的所有 Microsoft 365 帐户的列表。</span><span class="sxs-lookup"><span data-stu-id="23adc-143">Upon sign in, mobile users will see a list of all the Microsoft 365 accounts that are either currently signed-in or were previously signed-in on their device.</span></span> <span data-ttu-id="23adc-144">用户可点击任意帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="23adc-144">Users can tap on any of the accounts to sign in.</span></span> <span data-ttu-id="23adc-145">移动登录有两种方案：</span><span class="sxs-lookup"><span data-stu-id="23adc-145">There are two scenarios for mobile sign in:</span></span>

1. <span data-ttu-id="23adc-146">如果所选帐户当前已登录到其他 Office 365 或 Microsoft 365 应用，则用户将直接进入 Teams。</span><span class="sxs-lookup"><span data-stu-id="23adc-146">If the selected account is currently signed in to other Office 365 or Microsoft 365 apps, then the user will be taken straight to Teams.</span></span> <span data-ttu-id="23adc-147">用户无需输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="23adc-147">There's no need for the user to enter their credentials.</span></span>

2. <span data-ttu-id="23adc-148">如果用户未在其他任何位置登录到其 Microsoft 365 帐户，则系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织已针对“移动登录”策略配置的内容。</span><span class="sxs-lookup"><span data-stu-id="23adc-148">If user isn't signed in to their Microsoft 365 account anywhere else, they will be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign-in policies.</span></span>

> [!NOTE]
> <span data-ttu-id="23adc-149">对于要体验本部分中所述的登录体验的用户，其设备必须正在运行 Teams for iOS 版本2.0.13（内部版本 2020061704）或更高版本，或者 Teams for Android 版本 1416/1.0.0.2020061702 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="23adc-149">For users to experience the sign on experience as described in this section, their devices must be running Teams for iOS version 2.0.13 (build 2020061704) or later, or Teams for Android version 1416/1.0.0.2020061702 or later.</span></span>

## <a name="using-teams-with-multiple-accounts"></a><span data-ttu-id="23adc-150">使用多个 Teams 帐户</span><span class="sxs-lookup"><span data-stu-id="23adc-150">Using Teams with multiple accounts</span></span>

<span data-ttu-id="23adc-151">Teams for iOS 和 Android 支持多个工作、学校和多个个人帐户并行使用。</span><span class="sxs-lookup"><span data-stu-id="23adc-151">Teams for iOS and Android supports the use of multiple work or school and multiple personal accounts side by side.</span></span> <span data-ttu-id="23adc-152">Teams 桌面应用程序将在 2020 年 12 月支持并行使用一个工作/学校和一个个人帐户，随后将推出支持多个工作/学校帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-152">Teams desktop applications will support one work/school and one personal account side by side in December 2020, with support for multiple work/school accounts coming at a later date.</span></span>

<span data-ttu-id="23adc-153">以下图像显示用户如何在 Teams 移动应用中添加多个帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-153">The following images show how users can add multiple accounts in Teams mobile applications.</span></span>

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="添加多个帐户至 Teams":::

## <a name="restrict-sign-in-to-teams"></a><span data-ttu-id="23adc-155">无法登录到 Teams</span><span class="sxs-lookup"><span data-stu-id="23adc-155">Restrict sign in to Teams</span></span>

<span data-ttu-id="23adc-156">组织可能希望限制在受管理的设备上使用公司许可的应用的方式，例如，限制学生或员工访问其他组织中的数据，或将公司许可的应用用于个人的情况。</span><span class="sxs-lookup"><span data-stu-id="23adc-156">Organization may want to restrict how corporate-approved apps are used on managed devices, for example to restrict students' or employees’ ability to access data from other organizations or use corporate-approved apps for personal scenarios.</span></span> <span data-ttu-id="23adc-157">可通过设置 Teams 应用程序识别的设备策略来强制实施这些限制。</span><span class="sxs-lookup"><span data-stu-id="23adc-157">These restrictions can be enforced by setting Devices Policies that Teams applications recognize.</span></span>   

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a><span data-ttu-id="23adc-158">如何限制移动设备上的登录</span><span class="sxs-lookup"><span data-stu-id="23adc-158">How to restrict sign in on mobile devices</span></span>

<span data-ttu-id="23adc-159">Teams for iOS 和 Android 提供 IT 管理员将帐户配置推送到 Microsoft 365 帐户的功能。</span><span class="sxs-lookup"><span data-stu-id="23adc-159">Teams for iOS and Android offers IT administrators the ability to push account configurations to Microsoft 365 accounts.</span></span> <span data-ttu-id="23adc-160">此功能适用于使用[托管应用配置](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)通道（适用于iOS）或 [Android Enterprise](https://developer.android.com/work/managed-configurations) 通道（适用于Android）的任何移动设备管理（MDM）提供商。</span><span class="sxs-lookup"><span data-stu-id="23adc-160">This capability works with any Mobile Device Management (MDM) provider that uses the [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) channel for iOS or the [Android Enterprise](https://developer.android.com/work/managed-configurations) channel for Android.</span></span>

<span data-ttu-id="23adc-161">对于已注册 Microsoft Intune 的用户，可以使用 Azure 门户中的 Intune 部署帐户配置设置。</span><span class="sxs-lookup"><span data-stu-id="23adc-161">For users enrolled in Microsoft Intune, you can deploy the account configuration settings using Intune in the Azure portal.</span></span>

<span data-ttu-id="23adc-162">在 MDM 提供商配置帐户设置配置且用户注册其设备后，在登录页面上，Teams for iOS 和 Android 在 Teams 登录页面上仅会显示允许帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-162">Once account setup configuration has been configured in the MDM provider, and after the user enrolls their device, on the sign-in page, Teams for iOS and Android will only show the allowed account(s) on the Teams sign-in page.</span></span> <span data-ttu-id="23adc-163">用户可以在此页面上点击任何允许的帐户来登录。</span><span class="sxs-lookup"><span data-stu-id="23adc-163">The user can tap on any of the allowed accounts on this page to sign in.</span></span>

<span data-ttu-id="23adc-164">在 Azure Intune 门户中为托管设备设置以下配置参数。</span><span class="sxs-lookup"><span data-stu-id="23adc-164">Set the following configuration parameters in the Azure Intune portal for managed devices.</span></span>

|<span data-ttu-id="23adc-165">平台</span><span class="sxs-lookup"><span data-stu-id="23adc-165">Platform</span></span> |<span data-ttu-id="23adc-166">密钥</span><span class="sxs-lookup"><span data-stu-id="23adc-166">Key</span></span>  |<span data-ttu-id="23adc-167">值</span><span class="sxs-lookup"><span data-stu-id="23adc-167">Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="23adc-168">iOS</span><span class="sxs-lookup"><span data-stu-id="23adc-168">iOS</span></span>     |  <span data-ttu-id="23adc-169">**IntuneMAMAllowedAccountsOnly**</span><span class="sxs-lookup"><span data-stu-id="23adc-169">**IntuneMAMAllowedAccountsOnly**</span></span>       | <span data-ttu-id="23adc-170">**启用**：唯一允许的帐户是 IntuneMAMUPN 密钥定义的托管用户帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-170">**Enabled**: The only account allowed is the managed user account defined by the IntuneMAMUPN key.</span></span><br> <span data-ttu-id="23adc-171">**禁用**（或者与 **启用** 不匹配的任何区分大小写的值）：允许任何帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-171">**Disabled** (or any value that is not a case insensitive match to **Enabled**): Any account is allowed.</span></span>        |
|<span data-ttu-id="23adc-172">iOS</span><span class="sxs-lookup"><span data-stu-id="23adc-172">iOS</span></span>     |   <span data-ttu-id="23adc-173">**IntuneMAMUPN**</span><span class="sxs-lookup"><span data-stu-id="23adc-173">**IntuneMAMUPN**</span></span>      |   <span data-ttu-id="23adc-174">允许登录到 Teams 的帐户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="23adc-174">UPN of the account allowed to sign in to Teams.</span></span><br> <span data-ttu-id="23adc-175">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-175">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>       |
|<span data-ttu-id="23adc-176">Android</span><span class="sxs-lookup"><span data-stu-id="23adc-176">Android</span></span>     |<span data-ttu-id="23adc-177">**com.microsoft.intune.mam.AllowedAccountUPNs**</span><span class="sxs-lookup"><span data-stu-id="23adc-177">**com.microsoft.intune.mam.AllowedAccountUPNs**</span></span>         |    <span data-ttu-id="23adc-178">仅允许的账户是此密钥定义的托管用户账户。</span><span class="sxs-lookup"><span data-stu-id="23adc-178">Only account(s) allowed are the managed user account(s) defined by this key.</span></span><br> <span data-ttu-id="23adc-179">一个或多个分号；] - 分隔的UPN。</span><span class="sxs-lookup"><span data-stu-id="23adc-179">One or more semi-colons;]- delimited UPNs.</span></span><br> <span data-ttu-id="23adc-180">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-180">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>

<span data-ttu-id="23adc-181">设置帐户设置配置后，Teams 将限制登录功能，以使只有已注册设备上的允许账户才能获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="23adc-181">Once the account setup configuration has been set, Teams will restrict the ability to sign in, so that only allowed accounts on enrolled devices will be granted access.</span></span>

<span data-ttu-id="23adc-182">若要创建托管 iOS/iPadOS 设备的应用配置策略，请参阅[添加托管 iOS/iPadOS 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。</span><span class="sxs-lookup"><span data-stu-id="23adc-182">To create an app configuration policy for managed iOS/iPadOS devices, see [Add app configuration policies for managed iOS/iPadOS devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).</span></span>

<span data-ttu-id="23adc-183">若要创建托管 Android 设备的应用配置策略，请参阅[添加托管 Android 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。</span><span class="sxs-lookup"><span data-stu-id="23adc-183">To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).</span></span>

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a><span data-ttu-id="23adc-184">如何限制台式机设备上的登录</span><span class="sxs-lookup"><span data-stu-id="23adc-184">How to restrict sign in on desktop devices</span></span>
<span data-ttu-id="23adc-185">Windows 和 MacOS 上的 Teams 应用将支持限制登录到组织的设备策略。</span><span class="sxs-lookup"><span data-stu-id="23adc-185">Teams apps on Windows and MacOS are gaining support for device policies that restrict sign in to your organization.</span></span> <span data-ttu-id="23adc-186">可通过常规设备管理解决方案（例如 MDM（移动设备管理）或 GPO（组策略对象））设置策略。</span><span class="sxs-lookup"><span data-stu-id="23adc-186">The policies can be set via usual Device Management solutions such as MDM (Mobile Device Management) or GPO (Group Policy Object).</span></span> 

<span data-ttu-id="23adc-187">在设备上配置此策略时，用户仅可使用位于 Azure AD 租户（包含于策略中定义的 “租户允许列表” ）中的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="23adc-187">When this policy is configured on a device, users can only sign in with accounts homed in an Azure AD tenant that is included in the “Tenant Allow List” defined in the policy.</span></span> <span data-ttu-id="23adc-188">该策略应用于所有登录，包括第一个和其他帐户。</span><span class="sxs-lookup"><span data-stu-id="23adc-188">The policy applies to all sign-ins, including first and additional accounts.</span></span> <span data-ttu-id="23adc-189">如果你的组织包括多个 Azure AD 租户，则可以在允许列表中包含多个租户 ID。</span><span class="sxs-lookup"><span data-stu-id="23adc-189">If your organization spans multiple Azure AD tenants, you can include multiple Tenant IDs in the Allow List.</span></span> <span data-ttu-id="23adc-190">Teams 应用中的 “添加其他帐户” 的链接可能仍处于可见状态，但它们不可操作。</span><span class="sxs-lookup"><span data-stu-id="23adc-190">Links to add another account may continue to be visible in the Teams app, but they won't be operable.</span></span>

> [!NOTE]
>1. <span data-ttu-id="23adc-191">该策略仅限制登录。它不限制用户在其他 Azure AD 租户中被邀请为来宾，或切换到其他租户。</span><span class="sxs-lookup"><span data-stu-id="23adc-191">The policy only restricts sign-ins. It does not restrict the ability for users to be invited as guest in other Azure AD tenants, or switch to other tenants.</span></span>
>2. <span data-ttu-id="23adc-192">该策略要求 Teams for Windows 版本1.3.00.30866 或更高版本以及Teams for MacOS 版本1.3.00.30882 （发布时间为 2020 年 11 月中）。</span><span class="sxs-lookup"><span data-stu-id="23adc-192">The policy requires Teams for Windows version 1.3.00.30866 or higher, and Teams for MacOS version 1.3.00.30882 (released mid-November 2020).</span></span>

<span data-ttu-id="23adc-193">可从 [下载中心](https://www.microsoft.com/download/details.aspx?id=49030)获取 **Windows适用策略** 管理模板文件（ADMX/ADML）。</span><span class="sxs-lookup"><span data-stu-id="23adc-193">**Policies for Windows** Administrative Template files (ADMX/ADML) are available from the [Download center](https://www.microsoft.com/download/details.aspx?id=49030).</span></span> <span data-ttu-id="23adc-194">另外，你可以在 Windows 注册表中手动设置密钥：</span><span class="sxs-lookup"><span data-stu-id="23adc-194">Additionally, you can manually set keys in Windows Registry:</span></span>

- <span data-ttu-id="23adc-195">值名称： RestrictTeamsSignInToAccountsFromTenantList</span><span class="sxs-lookup"><span data-stu-id="23adc-195">Value Name: RestrictTeamsSignInToAccountsFromTenantList</span></span>
- <span data-ttu-id="23adc-196">值类型：字符串</span><span class="sxs-lookup"><span data-stu-id="23adc-196">Value Type: String</span></span>
- <span data-ttu-id="23adc-197">值数据：租户 ID 或以逗号分隔的租户 ID 列表</span><span class="sxs-lookup"><span data-stu-id="23adc-197">Value Data: Tenant ID, or comma-separated list of Tenant IDs</span></span>
- <span data-ttu-id="23adc-198">路径：使用下列内容之一</span><span class="sxs-lookup"><span data-stu-id="23adc-198">Path: use one of the following</span></span>

 <span data-ttu-id="23adc-199">Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams</span><span class="sxs-lookup"><span data-stu-id="23adc-199">Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams</span></span>

<span data-ttu-id="23adc-200">示例： SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 或 SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3</span><span class="sxs-lookup"><span data-stu-id="23adc-200">Example: SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID or SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3</span></span>

<span data-ttu-id="23adc-201">**MacOS适用策略** 对于MacOS 的托管设备，使用 .plist 来部署登录限制。</span><span class="sxs-lookup"><span data-stu-id="23adc-201">**Policies for MacOS** For MacOS managed devices, use .plist to deploy sign-in restrictions.</span></span> <span data-ttu-id="23adc-202">配置文件是一个 plist 文件，其中包含由键标识的项（表示首选项名称），后跟一个值（该值取决于首选项的特性）。</span><span class="sxs-lookup"><span data-stu-id="23adc-202">The configuration profile is a .plist file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="23adc-203">值可以是简单的（如数值）或复杂的（如首选项的嵌套列表）。</span><span class="sxs-lookup"><span data-stu-id="23adc-203">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

- <span data-ttu-id="23adc-204">域：com.microsoft.teams</span><span class="sxs-lookup"><span data-stu-id="23adc-204">Domain: com.microsoft.teams</span></span>
- <span data-ttu-id="23adc-205">密钥： RestrictTeamsSignInToAccountsFromTenantList</span><span class="sxs-lookup"><span data-stu-id="23adc-205">Key: RestrictTeamsSignInToAccountsFromTenantList</span></span>
- <span data-ttu-id="23adc-206">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="23adc-206">Data Type: String</span></span>
- <span data-ttu-id="23adc-207">备注：输入逗号分隔的 Azure AD 租户 ID 列表</span><span class="sxs-lookup"><span data-stu-id="23adc-207">Comments: Enter comma separate list of Azure AD tenant ID(s)</span></span>


## <a name="sign-out-on-mobile-devices"></a><span data-ttu-id="23adc-208">在移动设备上注销</span><span class="sxs-lookup"><span data-stu-id="23adc-208">Sign out on mobile devices</span></span>

<span data-ttu-id="23adc-209">移动用户可以通过进入菜单，选择 **更多** 菜单，然后选择 **退出** 来注销Teams。一旦注销，用户下次启动应用程序时需要重新输入其凭证。</span><span class="sxs-lookup"><span data-stu-id="23adc-209">Mobile users can sign out of Teams by going to the menu, selecting the **More** menu, and then selecting **Sign out**. Once signed out, users will need to reenter their credentials the next time they launch the app.</span></span>

> [!NOTE]
> <span data-ttu-id="23adc-210">Android 版 Teams 使用单一登录（SSO）来简化登录体验。</span><span class="sxs-lookup"><span data-stu-id="23adc-210">Teams for Android uses single sign-on (SSO) to simplify the sign in experience.</span></span> <span data-ttu-id="23adc-211">除了 Teams 之外，用户应确保退出 **所有** Microsoft 应用，以便完全退出 Android 平台。</span><span class="sxs-lookup"><span data-stu-id="23adc-211">Users should make sure to log out of **all** Microsoft apps, in addition to Teams, in order to completely log out on the Android platform.</span></span>

### <a name="global-sign-in-and-sign-out"></a><span data-ttu-id="23adc-212">全局登录和注销</span><span class="sxs-lookup"><span data-stu-id="23adc-212">Global sign in and sign out</span></span>

<span data-ttu-id="23adc-213">现在，Teams Android 应用支持全局登录和注销，为第一线工作者提供简便的登录和注销体验。</span><span class="sxs-lookup"><span data-stu-id="23adc-213">The Teams Android app now supports Global sign-in and sign-out, to provide a hassle free sign-in and sign-out experience for Frontline Workers.</span></span> <span data-ttu-id="23adc-214">员工可以从共享设备池中选取设备，使其在排班期间单一登录到“归为己有”。</span><span class="sxs-lookup"><span data-stu-id="23adc-214">Employees can pick a device from the shared device pool and do a single sign in to "make it theirs" for the duration of their shift.</span></span> <span data-ttu-id="23adc-215">在他们值班结束后，应能够执行注销，以便在设备上全局注销。</span><span class="sxs-lookup"><span data-stu-id="23adc-215">At the end of their shift, they should be able to perform sign out to globally sign out on the device.</span></span> <span data-ttu-id="23adc-216">这将从设备中删除其所有个人和公司信息，以便可将设备返回到设备池。</span><span class="sxs-lookup"><span data-stu-id="23adc-216">This with remove all of their personal and company information from the device so they can return the device to the device pool.</span></span> <span data-ttu-id="23adc-217">若要获取此功能，设备必须处于共享模式。</span><span class="sxs-lookup"><span data-stu-id="23adc-217">To get this capability, the device must be in shared mode.</span></span> <span data-ttu-id="23adc-218">若要了解如何设置共享设备，请参阅[如何使用 Android中的共享设备模式](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。</span><span class="sxs-lookup"><span data-stu-id="23adc-218">To learn how to set up a shared device, see [How to use a shared device mode in Android](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).</span></span>

<span data-ttu-id="23adc-219">登录体验看起来类似于我们的标准 Teams 登录体验，而注销看起来将如下两个图像所示：</span><span class="sxs-lookup"><span data-stu-id="23adc-219">The sign-in experience looks similar to our standard Teams sign experience, while sign out will look like the following two images:</span></span>

![注销的移动设备演示](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="23adc-221">URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="23adc-221">URLs and IP address ranges</span></span>

<span data-ttu-id="23adc-222">Teams 需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="23adc-222">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="23adc-223">若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="23adc-223">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government, and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23adc-224">目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务（即使你不使用 Gstatic，也是如此）。</span><span class="sxs-lookup"><span data-stu-id="23adc-224">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="23adc-225">Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。</span><span class="sxs-lookup"><span data-stu-id="23adc-225">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="related-topics"></a><span data-ttu-id="23adc-226">相关主题</span><span class="sxs-lookup"><span data-stu-id="23adc-226">Related topics</span></span>

[<span data-ttu-id="23adc-227">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="23adc-227">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
