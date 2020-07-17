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
description: 了解新式验证的工作原理、如何切换帐户，以及如何解决新式验证中的问题。 包括如何告诉 Teams 在登录时忽略用户名 (UPN) 预填充。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8db647d5021aee124dec794e8711662de9f0a1c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121362"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="8a331-104">使用新式验证登录 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a331-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="8a331-105">Microsoft 建议组织使用带有“混合域加入”或“Azure AD 加入”配置的最新版 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="8a331-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="8a331-106">这可以确保在 Windows 的 Web 帐户管理器中预先准备用户帐户，进而启用 Teams 和其他 Microsoft 应用程序的单一登录。</span><span class="sxs-lookup"><span data-stu-id="8a331-106">This ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turns enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="8a331-107">这样可以带来更好的用户体验（静默式登录）和更好的安全状态。</span><span class="sxs-lookup"><span data-stu-id="8a331-107">This provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="8a331-108">Microsoft Teams 使用新式验证保持登录体验简单而安全。</span><span class="sxs-lookup"><span data-stu-id="8a331-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="8a331-109">若要了解用户如何登录 Teams，请阅读[登录 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="8a331-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="8a331-110">新式验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="8a331-110">How modern authentication works</span></span>

<span data-ttu-id="8a331-111">新式验证是一种使 Teams 知道用户已在其他位置输入凭据（如工作电子邮件和密码）而不再需要再次输入凭据即可启动应用的过程。</span><span class="sxs-lookup"><span data-stu-id="8a331-111">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="8a331-112">体验将因几个因素（如用户在 Windows 上还是在 Mac 上工作）而异。</span><span class="sxs-lookup"><span data-stu-id="8a331-112">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="8a331-113">具体将取决于你的组织启用了单重身份验证还是多重身份验证（多重身份验证通常涉及通过手机验证凭据、提供唯一代码、输入 PIN 或提供指纹）。</span><span class="sxs-lookup"><span data-stu-id="8a331-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="8a331-114">下面是每个新式身份验证应用场景的描述。</span><span class="sxs-lookup"><span data-stu-id="8a331-114">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="8a331-115">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="8a331-115">Windows users</span></span>

- <span data-ttu-id="8a331-116">如果用户已通过其工作或学校帐户登录到 Windows 或其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。</span><span class="sxs-lookup"><span data-stu-id="8a331-116">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="8a331-117">他们无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="8a331-117">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="8a331-118">Microsoft 建议使用 Windows 10 版本 1903 或更高版本获取最佳单一登录体验。</span><span class="sxs-lookup"><span data-stu-id="8a331-118">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="8a331-119">如果用户未在任何其他位置登录其 Microsoft 工作或学校帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA），具体验证方式取决于你的组织已决定采用的必要验证过程。</span><span class="sxs-lookup"><span data-stu-id="8a331-119">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="8a331-120">如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="8a331-120">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="8a331-121">如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。</span><span class="sxs-lookup"><span data-stu-id="8a331-121">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="8a331-122">在加入域的电脑上，如果无法进行 SSO，Teams 可能会使用用户主体名称 (UPN) 预填充其登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="8a331-122">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="8a331-123">在某些情况下，你可能不希望采取这种做法，尤其是在你的组织在本地和 Azure Active Directory 中使用不同 UPN 的情况下。</span><span class="sxs-lookup"><span data-stu-id="8a331-123">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="8a331-124">如果是这种情况，则可以使用以下 Windows 注册表项来关闭 UPN 的预填充：</span><span class="sxs-lookup"><span data-stu-id="8a331-124">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="8a331-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="8a331-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="8a331-126">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="8a331-126">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="8a331-127">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="8a331-127">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a331-128">默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="8a331-128">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>


### <a name="mac-users"></a><span data-ttu-id="8a331-129">Mac 用户</span><span class="sxs-lookup"><span data-stu-id="8a331-129">Mac users</span></span>

<span data-ttu-id="8a331-130">在 MacOS 上，Teams 将提示用户输入其用户名和凭据，并且可能会根据组织的设置提示进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="8a331-130">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="8a331-131">用户输入其凭据后，他们无需再次提供凭据。</span><span class="sxs-lookup"><span data-stu-id="8a331-131">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="8a331-132">此后，只要是在同一台计算机上工作，Teams 都将自动启动。</span><span class="sxs-lookup"><span data-stu-id="8a331-132">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="teams-for-ios-and-android-users"></a><span data-ttu-id="8a331-133">iOS 和 Android 版 Teams 用户</span><span class="sxs-lookup"><span data-stu-id="8a331-133">Teams for iOS and Android users</span></span>

<span data-ttu-id="8a331-134">登录时，移动用户将看到当前已登录的或其设备上以前登录的所有 Microsoft 365 帐户的列表。</span><span class="sxs-lookup"><span data-stu-id="8a331-134">Upon sign in, mobile users will see a list of all the Microsoft 365 accounts that are either currently signed in or were previously signed in on their device.</span></span> <span data-ttu-id="8a331-135">用户可点击任意帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="8a331-135">Users can tap on any of the accounts to sign in.</span></span> <span data-ttu-id="8a331-136">移动登录有两种方案：</span><span class="sxs-lookup"><span data-stu-id="8a331-136">There are two scenarios for mobile sign in:</span></span>
    
1. <span data-ttu-id="8a331-137">如果所选帐户当前已登录到其他 Office 365 或 Microsoft 365 应用，则用户将直接进入 Teams。</span><span class="sxs-lookup"><span data-stu-id="8a331-137">If the selected account is currently signed in to other Office 365 or Microsoft 365 apps, then the user will be taken straight to Teams.</span></span> <span data-ttu-id="8a331-138">用户无需输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="8a331-138">There is no need for the user to enter their credentials.</span></span>
    
2. <span data-ttu-id="8a331-139">如果用户未在其他任何位置登录到其 Microsoft 365 帐户，则系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织已针对“移动登录”策略配置的内容。</span><span class="sxs-lookup"><span data-stu-id="8a331-139">If user isn't signed in to their Microsoft 365 account anywhere else, they will be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign in policies.</span></span>

> [!NOTE]
> <span data-ttu-id="8a331-140">对于要体验本部分中所述的登录体验的用户，其设备必须正在运行 Teams for iOS 版本2.0.13（内部版本 2020061704）或更高版本，或者 Teams for Android 版本 1416/1.0.0.2020061702 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8a331-140">For users to experience the sign on experience as described in this section, their devices must be running Teams for iOS version 2.0.13 (build 2020061704) or later, or Teams for Android version 1416/1.0.0.2020061702 or later.</span></span>


### <a name="adding-multiple-accounts-to-teams"></a><span data-ttu-id="8a331-141">添加多个帐户至 Teams</span><span class="sxs-lookup"><span data-stu-id="8a331-141">Adding multiple accounts to Teams</span></span>

<span data-ttu-id="8a331-142">IOS 和 Android 版 Teams 支持将多个帐户从单个设备添加到 Teams。</span><span class="sxs-lookup"><span data-stu-id="8a331-142">Teams for iOS and Android supports adding multiple accounts from a single device to Teams.</span></span> <span data-ttu-id="8a331-143">以下图像显示用户如何在 Teams 中添加多个帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-143">The following images show how users can add multiple accounts in Teams.</span></span>
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="添加多个帐户至 Teams 中":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a><span data-ttu-id="8a331-145">使用企业移动性管理来控制可登录 Teams 的帐户</span><span class="sxs-lookup"><span data-stu-id="8a331-145">Use enterprise mobility management to control which accounts can sign in to Teams</span></span>

<span data-ttu-id="8a331-146">IOS 和 Android 版 Teams 向 IT 管理员提供将帐户配置推送到 Microsoft 365 帐户的功能。</span><span class="sxs-lookup"><span data-stu-id="8a331-146">Teams for iOS and Android offers IT administrators the ability to push account configurations to Microsoft 365 accounts.</span></span> <span data-ttu-id="8a331-147">此功能适用于使用 [托管应用配置](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道（适用于iOS）或 [ Android Enterprise ](https://developer.android.com/work/managed-configurations) 通道（适用于Android）的任何移动设备管理（MDM）提供商。</span><span class="sxs-lookup"><span data-stu-id="8a331-147">This capability works with any Mobile Device Management (MDM) provider who uses the [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) channel for iOS or the [Android Enterprise](https://developer.android.com/work/managed-configurations) channel for Android.</span></span>

<span data-ttu-id="8a331-148">对于已注册 Microsoft Intune 的用户，可以使用 Azure 门户中的 Intune 部署帐户配置设置。</span><span class="sxs-lookup"><span data-stu-id="8a331-148">For users enrolled in Microsoft Intune, you can deploy the account configuration settings using Intune in the Azure Portal.</span></span>

<span data-ttu-id="8a331-149">在 MDM 提供程序中设置帐户设置配置后，用户注册其设备后，iOS 和 Android 版 Teams 将仅显示 Teams 登录页面上的允许帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-149">Once account setup configuration has been setup in the MDM provider, and after the user enrolls their device, on the login pgae, Teams for iOS and Android will only show the allowed account(s) on the Teams login page.</span></span> <span data-ttu-id="8a331-150">用户可以在此页面上点击任何允许的帐户来登录。</span><span class="sxs-lookup"><span data-stu-id="8a331-150">The user can tap on any of the allowed accounts on this page to sign in.</span></span>

<span data-ttu-id="8a331-151">在 Azure Intune 门户中为托管设备设置以下配置参数。</span><span class="sxs-lookup"><span data-stu-id="8a331-151">Set the following configuration parameters in the Azure Intune portal for managed devices.</span></span>


|<span data-ttu-id="8a331-152">平台</span><span class="sxs-lookup"><span data-stu-id="8a331-152">Platform</span></span> |<span data-ttu-id="8a331-153">密钥</span><span class="sxs-lookup"><span data-stu-id="8a331-153">Key</span></span>  |<span data-ttu-id="8a331-154">值</span><span class="sxs-lookup"><span data-stu-id="8a331-154">Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8a331-155">iOS</span><span class="sxs-lookup"><span data-stu-id="8a331-155">iOS</span></span>     |  <span data-ttu-id="8a331-156">**IntuneMAMAllowedAccountsOnly**</span><span class="sxs-lookup"><span data-stu-id="8a331-156">**IntuneMAMAllowedAccountsOnly**</span></span>       | <span data-ttu-id="8a331-157">**启用**：唯一允许的帐户是 IntuneMAMUPN 密钥定义的托管用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-157">**Enabled**: The only account allowed is the managed user account defined by the IntuneMAMUPN key.</span></span><br> <span data-ttu-id="8a331-158">**禁用**（或者与**启用**不匹配的任何区分大小写的值）：允许任何帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-158">**Disabled** (or any value that is not a case insensitive match to **Enabled**): Any account is allowed.</span></span>        |
|<span data-ttu-id="8a331-159">iOS</span><span class="sxs-lookup"><span data-stu-id="8a331-159">iOS</span></span>     |   <span data-ttu-id="8a331-160">**IntuneMAMUPN**</span><span class="sxs-lookup"><span data-stu-id="8a331-160">**IntuneMAMUPN**</span></span>      |   <span data-ttu-id="8a331-161">允许登录到 Teams 的帐户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="8a331-161">UPN of the account allowed to sign in to Teams.</span></span><br> <span data-ttu-id="8a331-162">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-162">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>       |
|<span data-ttu-id="8a331-163">Android</span><span class="sxs-lookup"><span data-stu-id="8a331-163">Android</span></span>     |<span data-ttu-id="8a331-164">**com.microsoft.intune.mam.AllowedAccountUPNs**</span><span class="sxs-lookup"><span data-stu-id="8a331-164">**com.microsoft.intune.mam.AllowedAccountUPNs**</span></span>         |    <span data-ttu-id="8a331-165">仅允许的账户是此密钥定义的托管用户账户。</span><span class="sxs-lookup"><span data-stu-id="8a331-165">Only account(s) allowed are the managed user account(s) defined by this key.</span></span><br> <span data-ttu-id="8a331-166">一个或多个分号 [;] 分隔的 UPN。</span><span class="sxs-lookup"><span data-stu-id="8a331-166">One or more semi-colon [;]- delmited UPNs.</span></span><br> <span data-ttu-id="8a331-167">对于注册 Intune 的设备，{{userprincipalname}}令牌可用于代表已注册的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-167">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>

<span data-ttu-id="8a331-168">设置帐户设置配置后，Teams 将限制登录功能，以使只有已注册设备上的允许账户才能获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="8a331-168">Once the account setup configuration has been set, Teams will restrict the ability to sign in, so that only allowed accounts on enrolled devices will be granted access.</span></span>

<span data-ttu-id="8a331-169">若要创建托管 iOS/iPadOS 设备的应用配置策略，请参阅 [添加托管 iOS/iPadOS 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。</span><span class="sxs-lookup"><span data-stu-id="8a331-169">To create an app configuration policy for managed iOS/iPadOS devices, see [Add app configuration policies for managed iOS/iPadOS devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).</span></span>

<span data-ttu-id="8a331-170">若要创建托管 Android 设备的应用配置策略，请参阅 [添加托管 Android 设备的应用配置策略](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。</span><span class="sxs-lookup"><span data-stu-id="8a331-170">To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).</span></span>


## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="8a331-171">完成新式验证后切换帐户</span><span class="sxs-lookup"><span data-stu-id="8a331-171">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="8a331-172">如果用户在加入域的计算机上工作（例如，如果他们的租户已启用 Kerberos），则他们在完成新式验证后无法切换用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-172">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="8a331-173">如果用户不在加入域的计算机上工作，则可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="8a331-173">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="8a331-174">完成新式验证后注销 Teams</span><span class="sxs-lookup"><span data-stu-id="8a331-174">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="8a331-175">若要注销 Teams，用户可以单击应用顶部的个人资料图片，然后选择“**注销**”。他们还可以右键单击任务栏中的应用图标，然后选择“**注销**”。注销 Teams 后，他们需要再次输入凭据才能启动该应用。</span><span class="sxs-lookup"><span data-stu-id="8a331-175">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

### <a name="signing-out-of-teams-for-ios-and-android"></a><span data-ttu-id="8a331-176">退出 iOS 和 Android 版 Teams</span><span class="sxs-lookup"><span data-stu-id="8a331-176">Signing out of Teams for iOS and Android</span></span>

<span data-ttu-id="8a331-177">移动用户可以通过以下方法退出小组：进入菜单，然后选择“**更多**”菜单，然后选择“**退出**”。退出后，用户下次启动该应用程序时需要重新输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="8a331-177">Mobile users can sign out of Teams by going to the menu and choosing the **More** menu, and then choosing **Sign out**. Once signed out, users will need to re-enter their credentials the next time they launch the app.</span></span>

> [!NOTE]
> <span data-ttu-id="8a331-178">Android 版 Teams 使用单一登录（SSO）来简化登录体验。</span><span class="sxs-lookup"><span data-stu-id="8a331-178">Teams for Android uses single sign-on (SSO) to simplify the sign in experience.</span></span> <span data-ttu-id="8a331-179">除了 Teams 之外，用户应确保退出**所有** Microsoft 应用，以便完全退出 Android 平台。</span><span class="sxs-lookup"><span data-stu-id="8a331-179">Users should make sure to log out of **all** Microsoft apps, in addition to Teams, in order to completely log out on the Android platform.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="8a331-180">URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="8a331-180">URLs and IP address ranges</span></span>

<span data-ttu-id="8a331-181">Teams 需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="8a331-181">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="8a331-182">若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="8a331-182">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a331-183">目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务 (<https://ssl.gstatic.com)>；即使你不使用 Gstatic，也是如此。</span><span class="sxs-lookup"><span data-stu-id="8a331-183">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="8a331-184">Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。</span><span class="sxs-lookup"><span data-stu-id="8a331-184">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="8a331-185">新式验证疑难解答</span><span class="sxs-lookup"><span data-stu-id="8a331-185">Troubleshooting modern authentication</span></span>

<span data-ttu-id="8a331-186">使用 Teams 的每个组织均可使用新式验证，因此如果用户无法完成该过程，则你的域或组织的 Microsoft 工作或学习帐户可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="8a331-186">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="8a331-187">有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="8a331-187">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>


## <a name="related-topics"></a><span data-ttu-id="8a331-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="8a331-188">Related topics</span></span>

[<span data-ttu-id="8a331-189">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="8a331-189">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)