---
title: 使用新式验证登录 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 如何使用新式身份验证登录到 Microsoft 团队。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563119"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="64091-103">使用新式验证登录 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64091-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="64091-104">Microsoft 团队使用新式身份验证来保持登录体验简单而又安全。</span><span class="sxs-lookup"><span data-stu-id="64091-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="64091-105">若要查看用户如何登录到团队，请阅读[登录团队](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="64091-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="64091-106">新式身份验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="64091-106">How modern authentication works</span></span>

<span data-ttu-id="64091-107">新式验证是让团队知道用户已在其他位置输入其凭据（如工作电子邮件和密码）的过程，并且不需要再次输入它们来启动应用。</span><span class="sxs-lookup"><span data-stu-id="64091-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="64091-108">根据几个因素（如用户在 Windows 或在 Mac 上工作），体验会有所不同。</span><span class="sxs-lookup"><span data-stu-id="64091-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="64091-109">它还会根据你的组织是否已启用单因素身份验证或多重身份验证而有所不同（多重身份验证通常涉及通过电话验证凭据、提供唯一代码、输入 PIN 或演示指纹）。</span><span class="sxs-lookup"><span data-stu-id="64091-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="64091-110">下面是每个新式身份验证方案的一个断开。</span><span class="sxs-lookup"><span data-stu-id="64091-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="64091-111">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="64091-111">Windows users</span></span> 

- <span data-ttu-id="64091-112">如果用户已通过其 Office 365 企业帐户登录到其他 Office 应用，则当用户启动团队时，他们将直接转到该应用。</span><span class="sxs-lookup"><span data-stu-id="64091-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="64091-113">无需他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="64091-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="64091-114">如果用户未登录到任何其他位置的 Office 365 企业帐户，则当用户启动团队时，系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织决定需要的流程。</span><span class="sxs-lookup"><span data-stu-id="64091-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="64091-115">如果用户登录到加入域的计算机，则当用户启动团队时，可能会要求他们执行一个更多身份验证步骤，具体取决于你的组织选择是需要 MFA 还是计算机已要求进行 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="64091-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="64091-116">如果其计算机已要求进行 MFA 登录，则当用户打开团队时，应用会自动启动。</span><span class="sxs-lookup"><span data-stu-id="64091-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="64091-117">Mac 用户</span><span class="sxs-lookup"><span data-stu-id="64091-117">Mac users</span></span> 

<span data-ttu-id="64091-118">用户启动团队时，其计算机将无法从其 Office 365 企业帐户或任何其他 Office 应用程序中提取其凭据。</span><span class="sxs-lookup"><span data-stu-id="64091-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="64091-119">他们将看到一条提示，要求他们提供 SFA 或 MFA （具体取决于您的组织的设置）。</span><span class="sxs-lookup"><span data-stu-id="64091-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="64091-120">用户输入其凭据后，不需要再次提供它们。</span><span class="sxs-lookup"><span data-stu-id="64091-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="64091-121">从此时起，团队会在它们在同一台计算机上工作时自动启动。</span><span class="sxs-lookup"><span data-stu-id="64091-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="64091-122">完成新式身份验证后切换帐户</span><span class="sxs-lookup"><span data-stu-id="64091-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="64091-123">如果用户正在使用加入域的计算机（例如，如果其租户已启用 Kerberos），则他们在完成新式身份验证后无法切换用户帐户。</span><span class="sxs-lookup"><span data-stu-id="64091-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="64091-124">如果用户不在已加入域的计算机上工作，则他们可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="64091-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="64091-125">在完成新式身份验证后注销 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="64091-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="64091-126">若要注销团队，用户可以单击应用顶部的个人资料图片，然后选择 "**注销**"。他们还可以右键单击任务栏中的应用程序图标，然后选择 "**注销**"。注销团队后，他们需要再次输入其凭据以启动该应用。</span><span class="sxs-lookup"><span data-stu-id="64091-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="64091-127">新式验证疑难解答</span><span class="sxs-lookup"><span data-stu-id="64091-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="64091-128">现代身份验证适用于使用团队的每个组织，因此，如果用户无法完成此过程，则您的域或组织的 Office 365 企业帐户可能有问题。</span><span class="sxs-lookup"><span data-stu-id="64091-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="64091-129">有关详细信息，请参阅[为什么我在登录 Microsoft 团队时遇到问题？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。</span><span class="sxs-lookup"><span data-stu-id="64091-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

