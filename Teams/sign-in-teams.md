---
title: 登录到 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 使用现代身份验证登录到 Microsoft 团队的指南。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e44b05bd0daed8867247512d38f22b764351127d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882027"
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="8f111-103">登录到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="8f111-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="8f111-104">Microsoft 团队使用现代身份验证以保持登录体验简单和安全。</span><span class="sxs-lookup"><span data-stu-id="8f111-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="8f111-105">如何现代验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="8f111-105">How modern authentication works</span></span>

<span data-ttu-id="8f111-106">现代身份验证是一个过程，可让团队知道用户已经输入其凭据 （如其工作电子邮件和密码中） 到其他位置，并且他们不应需要输入其再次启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f111-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="8f111-107">体验异几个因素，如如果用户正在在 Windows 或 mac。</span><span class="sxs-lookup"><span data-stu-id="8f111-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="8f111-108">它还将有所不同，具体取决于您的组织是否已启用单双因素身份验证或多因素身份验证 (多因素身份验证通常需要验证凭据的电话，提供一个唯一的代码，输入 PIN，通过或演示指纹）。</span><span class="sxs-lookup"><span data-stu-id="8f111-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="8f111-109">以下是一个每种现代身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="8f111-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="8f111-110">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="8f111-110">Windows users</span></span> 

- <span data-ttu-id="8f111-111">如果用户具有已登录到其 Office 365 企业版帐户，通过其他 Office 应用程序启动团队时他们正在执行直线的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f111-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="8f111-112">则无需为他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="8f111-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="8f111-113">如果用户未登录到其他任何位置，其 Office 365 企业版帐户启动团队时，需要提供一元或多因素身份验证 （SFA 或 MFA），具体取决于什么您的组织已决定他们希望伴有过程。</span><span class="sxs-lookup"><span data-stu-id="8f111-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="8f111-114">如果用户要登录到加入域的计算机上，启动团队，它们可能会要求穿过一个多个身份验证的步骤，具体取决于您的组织选择是否加入需要 MFA 或如果其计算机已需要 MFA 登录时。</span><span class="sxs-lookup"><span data-stu-id="8f111-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="8f111-115">如果其计算机已要求 MFA 登录，当其打开团队，应用程序自动启动。</span><span class="sxs-lookup"><span data-stu-id="8f111-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="8f111-116">Mac 用户</span><span class="sxs-lookup"><span data-stu-id="8f111-116">Mac users</span></span> 

<span data-ttu-id="8f111-117">当用户启动团队时，其计算机不能以打开其 Office 365 企业版客户或任何其他 Office 应用程序从其凭据。</span><span class="sxs-lookup"><span data-stu-id="8f111-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="8f111-118">相反，他们将看到一个提示，询问他们 SFA 或 MFA （具体取决于组织的设置）。</span><span class="sxs-lookup"><span data-stu-id="8f111-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="8f111-119">一旦用户输入凭据，它们不需要再次将它们提供。</span><span class="sxs-lookup"><span data-stu-id="8f111-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="8f111-120">从上的点，团队自动启动时正在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="8f111-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="8f111-121">切换后完成现代身份验证的帐户</span><span class="sxs-lookup"><span data-stu-id="8f111-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="8f111-122">如果用户正在 （例如，如果其租户已启用 Kerberos） 的加入域的计算机上，他们不能在他们已完成现代身份验证之后切换用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f111-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="8f111-123">如果用户加入域的计算机上不工作，他们可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="8f111-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="8f111-124">注销完成现代身份验证后的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="8f111-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="8f111-125">要注销团队，用户可以单击顶部的应用程序，其配置文件图片，然后选择**注销**。它们可以右键单击其任务栏上，在应用程序图标，然后选择**注销**。一旦他们已超出团队登录，他们需要输入其凭据重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f111-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="8f111-126">疑难解答现代的身份验证</span><span class="sxs-lookup"><span data-stu-id="8f111-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="8f111-127">现代身份验证是适用于每个组织使用团队，因此如果用户不是能够完成此过程，可能有错与您的域或组织的 Office 365 企业版帐户。</span><span class="sxs-lookup"><span data-stu-id="8f111-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="8f111-128">有关详细信息，请参阅[为什么我不能登录到 Microsoft 团队？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。</span><span class="sxs-lookup"><span data-stu-id="8f111-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

