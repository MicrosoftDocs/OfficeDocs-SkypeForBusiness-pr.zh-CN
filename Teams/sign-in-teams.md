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
ms.openlocfilehash: f9b11fca87ce8cda8bc5d61198eb640fecd5b787
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158819"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="ae1f5-104">使用新式验证登录 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae1f5-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="ae1f5-105">Microsoft Teams 使用新式验证保持登录体验简单而安全。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-105">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="ae1f5-106">若要了解用户如何登录 Teams，请阅读[登录 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-106">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="ae1f5-107">新式验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="ae1f5-107">How modern authentication works</span></span>

<span data-ttu-id="ae1f5-108">新式验证是一种使 Teams 知道用户已在其他位置输入凭据（如工作电子邮件和密码）而不再需要再次输入凭据即可启动应用的过程。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-108">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="ae1f5-109">体验将因几个因素（如用户在 Windows 上还是在 Mac 上工作）而异。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-109">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="ae1f5-110">具体将取决于你的组织启用了单重身份验证还是多重身份验证（多重身份验证通常涉及通过手机验证凭据、提供唯一代码、输入 PIN 或提供指纹）。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-110">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="ae1f5-111">下面是每个新式身份验证应用场景的描述。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-111">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="ae1f5-112">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="ae1f5-112">Windows users</span></span> 

- <span data-ttu-id="ae1f5-113">如果用户已通过其 Office 365 企业版帐户登录到其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-113">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="ae1f5-114">他们无需输入凭据。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-114">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="ae1f5-115">如果用户未在任何其他位置登录其 Office 365 企业版帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA），具体验证方式取决于你的组织已决定采用的必要验证过程。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-115">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="ae1f5-116">如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-116">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="ae1f5-117">如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-117">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="ae1f5-118">如果用户登录到了加入域的计算机，并且你**不希望他们的用户名预填充在 Teams 登录屏幕上**，则管理员可以设置以下 Windows 注册表来关闭用户名预填充 (UPN)：</span><span class="sxs-lookup"><span data-stu-id="ae1f5-118">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="ae1f5-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="ae1f5-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="ae1f5-120">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="ae1f5-120">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="ae1f5-121">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="ae1f5-121">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="ae1f5-122">默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-122">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="ae1f5-123">Mac 用户</span><span class="sxs-lookup"><span data-stu-id="ae1f5-123">Mac users</span></span> 

<span data-ttu-id="ae1f5-124">用户启动 Teams 后，其计算机将无法从其 Office 365 企业版帐户或任何其他 Office 应用程序中拉取凭据。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-124">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="ae1f5-125">事实上，他们将看到一条提示，要求他们进行 SFA 或 MFA 验证（具体取决于组织的设置）。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-125">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="ae1f5-126">用户输入其凭据后，他们无需再次提供凭据。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-126">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="ae1f5-127">此后，只要是在同一台计算机上工作，Teams 都将自动启动。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-127">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="ae1f5-128">完成新式验证后切换帐户</span><span class="sxs-lookup"><span data-stu-id="ae1f5-128">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="ae1f5-129">如果用户在加入域的计算机上工作（例如，如果他们的租户已启用 Kerberos），则他们在完成新式验证后无法切换用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-129">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="ae1f5-130">如果用户不在加入域的计算机上工作，则可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-130">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="ae1f5-131">完成新式验证后注销 Teams</span><span class="sxs-lookup"><span data-stu-id="ae1f5-131">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="ae1f5-132">若要注销 Teams，用户可以单击应用顶部的个人资料图片，然后选择“**注销**”。他们还可以右键单击任务栏中的应用图标，然后选择“**注销**”。注销 Teams 后，他们需要再次输入凭据才能启动该应用。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-132">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="ae1f5-133">URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="ae1f5-133">URLs and IP address ranges</span></span>
<span data-ttu-id="ae1f5-134">Teams 需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-134">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="ae1f5-135">若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-135">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ae1f5-136">目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务 (https://ssl.gstatic.com)；即使你不使用 Gstatic，也是如此。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-136">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="ae1f5-137">Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-137">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="ae1f5-138">新式验证疑难解答</span><span class="sxs-lookup"><span data-stu-id="ae1f5-138">Troubleshooting modern authentication</span></span>

<span data-ttu-id="ae1f5-139">使用 Teams 的每个组织均可使用新式验证，因此如果用户无法完成该过程，则你的域或组织的 Office 365 企业版帐户可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="ae1f5-139">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="ae1f5-140">有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="ae1f5-140">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

