---
title: 使用新式验证登录 Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: 了解新式验证的工作原理、如何切换帐户，以及如何解决新式验证中的问题。 包括如何告诉 Teams 在登录时忽略用户名 (UPN) 的预填充。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02c5889752ca730de84f8ca7bbaf240d30df63a2
ms.sourcegitcommit: 70ceb3a3c3483234ec9f3fed6117144abf59ca75
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48246129"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="f447d-104">使用新式验证登录 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f447d-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="f447d-105">Microsoft 建议组织使用带有“混合域加入”或“Azure AD 加入”配置的最新版 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="f447d-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="f447d-106">使用最近的版本可以确保用户的账户在Windows的Web账户管理器中处于预先准备状态，从而实现单点登录到Teams和其他Microsoft应用程序。</span><span class="sxs-lookup"><span data-stu-id="f447d-106">Using recent versions ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turn enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="f447d-107">单点登录提供了更好的用户体验（无声登录）和更好的安全状况。</span><span class="sxs-lookup"><span data-stu-id="f447d-107">Single sign-on provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="f447d-108">Microsoft Teams 使用新式验证保持登录体验简单而安全。</span><span class="sxs-lookup"><span data-stu-id="f447d-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="f447d-109">若要了解用户如何登录 Teams，请阅读[登录 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="f447d-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="f447d-110">新式验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="f447d-110">How modern authentication works</span></span>

<span data-ttu-id="f447d-111">新式验证是一种使 Teams 知道用户已在其他位置输入其凭据，如工作电子邮件和密码，而不再需要再次输入凭据即可启动应用。</span><span class="sxs-lookup"><span data-stu-id="f447d-111">Modern authentication is a process that lets Teams know that users have already entered their credentials, such as their work email and password elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="f447d-112">体验的不同因几个因素而异，如用户在 Windows 上还是在 Mac 上工作异。</span><span class="sxs-lookup"><span data-stu-id="f447d-112">The experience varies depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="f447d-113">具体取决于你的组织是否启用了单因素身份验证还是多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="f447d-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication.</span></span> <span data-ttu-id="f447d-114">多重身份验证通常涉及通过电话验证凭据、提供唯一代码、输入 PIN 或者出示拇指指纹。</span><span class="sxs-lookup"><span data-stu-id="f447d-114">Multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint.</span></span> <span data-ttu-id="f447d-115">下面是每个新式身份验证应用场景的描述。</span><span class="sxs-lookup"><span data-stu-id="f447d-115">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="f447d-116">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="f447d-116">Windows users</span></span>

- <span data-ttu-id="f447d-117">如果用户已通过其工作或学校帐户登录到 Windows 或其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。</span><span class="sxs-lookup"><span data-stu-id="f447d-117">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="f447d-118">他们无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="f447d-118">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="f447d-119">Microsoft 建议使用 Windows 10 版本 1903 或更高版本获取最佳单一登录体验。</span><span class="sxs-lookup"><span data-stu-id="f447d-119">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="f447d-120">如果用户未在任何其他位置登录其 Microsoft 工作或学校帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA）。</span><span class="sxs-lookup"><span data-stu-id="f447d-120">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA).</span></span> <span data-ttu-id="f447d-121">此过程取决于你的组织决定需要登录过程的要求。</span><span class="sxs-lookup"><span data-stu-id="f447d-121">This process depends on what your organization has decided they'd like the sign-in procedure to require.</span></span>

- <span data-ttu-id="f447d-122">如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="f447d-122">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="f447d-123">如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。</span><span class="sxs-lookup"><span data-stu-id="f447d-123">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="f447d-124">在加入域的电脑上，如果无法进行 SSO，Teams 可能会使用用户主体名称 (UPN) 预填充其登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="f447d-124">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="f447d-125">在某些情况下，你可能不希望采取这种做法，尤其是在你的组织在本地和 Azure Active Directory 中使用不同 UPN 的情况下。</span><span class="sxs-lookup"><span data-stu-id="f447d-125">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="f447d-126">如果是这种情况，则可以使用以下 Windows 注册表项来关闭 UPN 的预填充：</span><span class="sxs-lookup"><span data-stu-id="f447d-126">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="f447d-127">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="f447d-127">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="f447d-128">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="f447d-128">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="f447d-129">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="f447d-129">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="f447d-130">默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="f447d-130">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

### <a name="mac-users"></a><span data-ttu-id="f447d-131">Mac 用户</span><span class="sxs-lookup"><span data-stu-id="f447d-131">Mac users</span></span>

<span data-ttu-id="f447d-132">在 macOS 上，Teams 将提示用户输入其用户名和凭据，并且可能会根据组织设置的提示进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="f447d-132">On macOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="f447d-133">用户输入其凭据后，他们无需再次提供凭据。</span><span class="sxs-lookup"><span data-stu-id="f447d-133">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="f447d-134">此后，只要是在同一台计算机上工作，Teams 都将自动启动。</span><span class="sxs-lookup"><span data-stu-id="f447d-134">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="teams-for-ios-and-android-users"></a><span data-ttu-id="f447d-135">iOS 和 Android 版 Teams 用户</span><span class="sxs-lookup"><span data-stu-id="f447d-135">Teams for iOS and Android users</span></span>

<span data-ttu-id="f447d-136">登录时，移动用户将看到当前已登录的或其设备上以前登录的所有 Microsoft 365 帐户的列表。</span><span class="sxs-lookup"><span data-stu-id="f447d-136">Upon sign in, mobile users will see a list of all the Microsoft 365 accounts that are either currently signed-in or were previously signed-in on their device.</span></span> <span data-ttu-id="f447d-137">用户可点击任意帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="f447d-137">Users can tap on any of the accounts to sign in.</span></span> <span data-ttu-id="f447d-138">移动登录有两种方案：</span><span class="sxs-lookup"><span data-stu-id="f447d-138">There are two scenarios for mobile sign-in:</span></span>

1. <span data-ttu-id="f447d-139">如果所选帐户当前已登录到其他 Office 365 或 Microsoft 365 应用，则用户将直接进入 Teams。</span><span class="sxs-lookup"><span data-stu-id="f447d-139">If the selected account is currently signed in to other Office 365 or Microsoft 365 apps, then the user will be taken straight to Teams.</span></span> <span data-ttu-id="f447d-140">用户无需输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="f447d-140">There is no need for the user to enter their credentials.</span></span>

2. <span data-ttu-id="f447d-141">如果用户未在其他任何位置登录到其 Microsoft 365 帐户，则系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织已针对“移动登录”策略配置的内容。</span><span class="sxs-lookup"><span data-stu-id="f447d-141">If user isn't signed in to their Microsoft 365 account anywhere else, they will be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign-in policies.</span></span>

> [!NOTE]
> <span data-ttu-id="f447d-142">对于要体验本部分中所述的登录体验的用户，其设备必须正在运行 Teams for iOS 版本2.0.13（内部版本 2020061704）或更高版本，或者 Teams for Android 版本 1416/1.0.0.2020061702 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f447d-142">For users to experience the sign on experience as described in this section, their devices must be running Teams for iOS version 2.0.13 (build 2020061704) or later, or Teams for Android version 1416/1.0.0.2020061702 or later.</span></span>

### <a name="adding-multiple-accounts-to-teams"></a><span data-ttu-id="f447d-143">添加多个帐户至 Teams</span><span class="sxs-lookup"><span data-stu-id="f447d-143">Adding multiple accounts to Teams</span></span>

<span data-ttu-id="f447d-144">IOS 和 Android 版 Teams 支持将多个帐户从单个设备添加到 Teams。</span><span class="sxs-lookup"><span data-stu-id="f447d-144">Teams for iOS and Android supports adding multiple accounts from a single device to Teams.</span></span> <span data-ttu-id="f447d-145">以下图像显示用户如何在 Teams 中添加多个帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-145">The following images show how users can add multiple accounts in Teams.</span></span>

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="添加多个帐户至 Teams 中":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a><span data-ttu-id="f447d-147">使用企业移动性管理来控制可登录 Teams 的帐户</span><span class="sxs-lookup"><span data-stu-id="f447d-147">Use enterprise mobility management to control which accounts can sign in to Teams</span></span>

<span data-ttu-id="f447d-148">IOS 和 Android 版 Teams 向 IT 管理员提供将帐户配置推送到 Microsoft 365 帐户的功能。</span><span class="sxs-lookup"><span data-stu-id="f447d-148">Teams for iOS and Android offers IT administrators the ability to push account configurations to Microsoft 365 accounts.</span></span> <span data-ttu-id="f447d-149">此功能适用于使用 [托管应用配置](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道（适用于iOS）或 [ Android Enterprise ](https://developer.android.com/work/managed-configurations) 通道（适用于Android）的任何移动设备管理（MDM）提供商。</span><span class="sxs-lookup"><span data-stu-id="f447d-149">This capability works with any Mobile Device Management (MDM) provider who uses the [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) channel for iOS or the [Android Enterprise](https://developer.android.com/work/managed-configurations) channel for Android.</span></span>

<span data-ttu-id="f447d-150">对于已注册 Microsoft Intune 的用户，可以使用 Azure 门户中的 Intune 部署帐户配置设置。</span><span class="sxs-lookup"><span data-stu-id="f447d-150">For users enrolled in Microsoft Intune, you can deploy the account configuration settings using Intune in the Azure Portal.</span></span>

<span data-ttu-id="f447d-151">在 MDM 提供程序中配置帐户设置配置后，用户注册其设备后，在登录页面上，iOS 和 Android 版 Teams 将仅显示 Teams 登录页面上的允许帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-151">Once account setup configuration has been configured in the MDM provider, and after the user enrolls their device, on the login page, Teams for iOS and Android will only show the allowed account(s) on the Teams login page.</span></span> <span data-ttu-id="f447d-152">用户可以在此页面上点击任何允许的帐户来登录。</span><span class="sxs-lookup"><span data-stu-id="f447d-152">The user can tap on any of the allowed accounts on this page to sign in.</span></span>

<span data-ttu-id="f447d-153">在 Azure Intune 门户中为托管设备设置以下配置参数。</span><span class="sxs-lookup"><span data-stu-id="f447d-153">Set the following configuration parameters in the Azure Intune portal for managed devices.</span></span>

|<span data-ttu-id="f447d-154">平台</span><span class="sxs-lookup"><span data-stu-id="f447d-154">Platform</span></span> |<span data-ttu-id="f447d-155">密钥</span><span class="sxs-lookup"><span data-stu-id="f447d-155">Key</span></span>  |<span data-ttu-id="f447d-156">值</span><span class="sxs-lookup"><span data-stu-id="f447d-156">Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f447d-157">iOS</span><span class="sxs-lookup"><span data-stu-id="f447d-157">iOS</span></span>     |  <span data-ttu-id="f447d-158">**IntuneMAMAllowedAccountsOnly**</span><span class="sxs-lookup"><span data-stu-id="f447d-158">**IntuneMAMAllowedAccountsOnly**</span></span>       | <span data-ttu-id="f447d-159">**启用**：唯一允许的帐户是 IntuneMAMUPN 密钥定义的托管用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-159">**Enabled**: The only account allowed is the managed user account defined by the IntuneMAMUPN key.</span></span><br> <span data-ttu-id="f447d-160">**禁用**（或者与**启用**不匹配的任何区分大小写的值）：允许任何帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-160">**Disabled** (or any value that is not a case insensitive match to **Enabled**): Any account is allowed.</span></span>        |
|<span data-ttu-id="f447d-161">iOS</span><span class="sxs-lookup"><span data-stu-id="f447d-161">iOS</span></span>     |   <span data-ttu-id="f447d-162">**IntuneMAMUPN**</span><span class="sxs-lookup"><span data-stu-id="f447d-162">**IntuneMAMUPN**</span></span>      |   <span data-ttu-id="f447d-163">允许登录到 Teams 的帐户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="f447d-163">UPN of the account allowed to sign in to Teams.</span></span><br> <span data-ttu-id="f447d-164">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-164">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>       |
|<span data-ttu-id="f447d-165">Android</span><span class="sxs-lookup"><span data-stu-id="f447d-165">Android</span></span>     |<span data-ttu-id="f447d-166">**com.microsoft.intune.mam.AllowedAccountUPNs**</span><span class="sxs-lookup"><span data-stu-id="f447d-166">**com.microsoft.intune.mam.AllowedAccountUPNs**</span></span>         |    <span data-ttu-id="f447d-167">仅允许的账户是此密钥定义的托管用户账户。</span><span class="sxs-lookup"><span data-stu-id="f447d-167">Only account(s) allowed are the managed user account(s) defined by this key.</span></span><br> <span data-ttu-id="f447d-168">一个或多个分号；] - 分隔的UPN。</span><span class="sxs-lookup"><span data-stu-id="f447d-168">One or more semi-colon;]- delmited UPNs.</span></span><br> <span data-ttu-id="f447d-169">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-169">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>

<span data-ttu-id="f447d-170">设置帐户设置配置后，Teams 将限制登录功能，以使只有已注册设备上的允许账户才能获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="f447d-170">Once the account setup configuration has been set, Teams will restrict the ability to sign in, so that only allowed accounts on enrolled devices will be granted access.</span></span>

<span data-ttu-id="f447d-171">若要创建托管 iOS/iPadOS 设备的应用配置策略，请参阅 [添加托管 iOS/iPadOS 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。</span><span class="sxs-lookup"><span data-stu-id="f447d-171">To create an app configuration policy for managed iOS/iPadOS devices, see [Add app configuration policies for managed iOS/iPadOS devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).</span></span>

<span data-ttu-id="f447d-172">若要创建托管 Android 设备的应用配置策略，请参阅 [添加托管 Android 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。</span><span class="sxs-lookup"><span data-stu-id="f447d-172">To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="f447d-173">完成新式验证后切换帐户</span><span class="sxs-lookup"><span data-stu-id="f447d-173">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="f447d-174">如果用户在加入域的计算机上工作（例如，如果他们的租户已启用 Kerberos），则他们在完成新式验证后无法切换用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-174">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="f447d-175">如果用户不在加入域的计算机上工作，则可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="f447d-175">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="f447d-176">完成新式验证后注销 Teams</span><span class="sxs-lookup"><span data-stu-id="f447d-176">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="f447d-177">若要注销 Teams，用户可以单击应用顶部的个人资料图片，然后选择“**注销**”。他们还可以右键单击任务栏中的应用图标，然后选择“**注销**”。注销 Teams 后，他们需要再次输入凭据才能启动该应用。</span><span class="sxs-lookup"><span data-stu-id="f447d-177">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

### <a name="signing-out-of-teams-for-ios-and-android"></a><span data-ttu-id="f447d-178">退出 iOS 和 Android 版 Teams</span><span class="sxs-lookup"><span data-stu-id="f447d-178">Signing out of Teams for iOS and Android</span></span>

<span data-ttu-id="f447d-179">移动用户可以通过进入菜单，选择**更多**菜单，然后选择**退出**来注销Teams。一旦注销，用户下次启动应用程序时需要重新输入其凭证。</span><span class="sxs-lookup"><span data-stu-id="f447d-179">Mobile users can sign out of Teams by going to the menu, selecting the **More** menu, and then selecting **Sign out**. Once signed out, users will need to reenter their credentials the next time they launch the app.</span></span>

> [!NOTE]
> <span data-ttu-id="f447d-180">Android 版 Teams 使用单一登录（SSO）来简化登录体验。</span><span class="sxs-lookup"><span data-stu-id="f447d-180">Teams for Android uses single sign-on (SSO) to simplify the sign in experience.</span></span> <span data-ttu-id="f447d-181">除了 Teams 之外，用户应确保退出**所有** Microsoft 应用，以便完全退出 Android 平台。</span><span class="sxs-lookup"><span data-stu-id="f447d-181">Users should make sure to log out of **all** Microsoft apps, in addition to Teams, in order to completely log out on the Android platform.</span></span>

## <a name="global-sign-in-and-sign-out"></a><span data-ttu-id="f447d-182">全球登录和注销</span><span class="sxs-lookup"><span data-stu-id="f447d-182">Global sign-in and sign-out</span></span>

<span data-ttu-id="f447d-183">现在，Teams Android 应用支持全局登录和注销，为第一线工作者提供免费的登录和退出体验。</span><span class="sxs-lookup"><span data-stu-id="f447d-183">The Teams Android app now supports Global sign-in and sign-out, to provide a hassle free sign-in and sign-out experience for firstline workers.</span></span> <span data-ttu-id="f447d-184">员工可以从共享设备池中选取设备，使其在排班期间单一登录到“归为己有”。</span><span class="sxs-lookup"><span data-stu-id="f447d-184">Employees can pick a device from the shared device pool and do a single sign in to "make it theirs" for the duration of their shift.</span></span> <span data-ttu-id="f447d-185">在他们值班结束后，应能够执行注销，以便在设备上全局注销。</span><span class="sxs-lookup"><span data-stu-id="f447d-185">At the end of their shift, they should be able to perform sign out to globally log out on the device.</span></span> <span data-ttu-id="f447d-186">这将从设备中删除其所有个人和公司信息，以便可将设备返回到设备池。</span><span class="sxs-lookup"><span data-stu-id="f447d-186">This with remove all of their personal and company information from the device so they can return the device to the device pool.</span></span> <span data-ttu-id="f447d-187">若要获取此功能，设备必须处于共享模式。</span><span class="sxs-lookup"><span data-stu-id="f447d-187">To get this capability, the device must be in shared mode.</span></span> <span data-ttu-id="f447d-188">若要了解如何设置共享设备，请参阅[如何使用 Android中的共享设备模式](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。</span><span class="sxs-lookup"><span data-stu-id="f447d-188">To learn how to set up a shared device, see [How to use a shared device mode in Android](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).</span></span>

<span data-ttu-id="f447d-189">登录体验看起来类似于我们的标准Teams签名体验，而注销将如下两图所示：</span><span class="sxs-lookup"><span data-stu-id="f447d-189">The sign-in experience looks similar to our standard Teams sign experience, while sign-out will look like the following two images:</span></span>

![注销的移动设备演示](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="f447d-191">URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="f447d-191">URLs and IP address ranges</span></span>

<span data-ttu-id="f447d-192">Teams 需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="f447d-192">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="f447d-193">若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="f447d-193">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government, and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f447d-194">目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务 (<https://ssl.gstatic.com)>；即使你不使用 Gstatic，也是如此。</span><span class="sxs-lookup"><span data-stu-id="f447d-194">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="f447d-195">Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。</span><span class="sxs-lookup"><span data-stu-id="f447d-195">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="f447d-196">新式验证疑难解答</span><span class="sxs-lookup"><span data-stu-id="f447d-196">Troubleshooting modern authentication</span></span>

<span data-ttu-id="f447d-197">每个使用Teams的组织都可以使用现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="f447d-197">Modern authentication is available for every organization that uses Teams.</span></span> <span data-ttu-id="f447d-198">如果用户无法完成这个过程，可能是域或组织的Microsoft工作或学校账户出现了问题。</span><span class="sxs-lookup"><span data-stu-id="f447d-198">If users aren't able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="f447d-199">有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="f447d-199">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

## <a name="related-topics"></a><span data-ttu-id="f447d-200">相关主题</span><span class="sxs-lookup"><span data-stu-id="f447d-200">Related topics</span></span>

[<span data-ttu-id="f447d-201">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="f447d-201">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
