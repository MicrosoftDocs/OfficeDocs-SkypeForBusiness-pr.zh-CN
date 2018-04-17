---
title: 登录到 Microsoft 小组
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 有关通过使用现代的身份验证登录到 Microsoft 小组指导。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443f20b1ecd8295acc4f731211c69d23a79f28dd
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="53302-103">登录到 Microsoft 小组</span><span class="sxs-lookup"><span data-stu-id="53302-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="53302-104">Microsoft 的小组使用现代身份验证来保持简单和安全的登录体验。</span><span class="sxs-lookup"><span data-stu-id="53302-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="53302-105">现代如何验证的工作原理</span><span class="sxs-lookup"><span data-stu-id="53302-105">How modern authentication works</span></span>

<span data-ttu-id="53302-106">现代身份验证是一个过程，它使工作组知道用户已经在其他地方，输入其凭据 （如工作电子邮件和密码），并且不应要求他们输入他们再次启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="53302-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="53302-107">经验有所不同取决于一些因素，像如果用户在使用 Windows 或 mac。</span><span class="sxs-lookup"><span data-stu-id="53302-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="53302-108">也将因您的组织是否已启用一元身份验证或多因素身份验证 (多因素身份验证通常涉及到验证凭据通过电话，提供一个唯一的代码，并输入 PIN，或显示缩略图）。</span><span class="sxs-lookup"><span data-stu-id="53302-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="53302-109">下面是每个现代的身份验证方案的简要介绍。</span><span class="sxs-lookup"><span data-stu-id="53302-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="53302-110">Windows 用户</span><span class="sxs-lookup"><span data-stu-id="53302-110">Windows users</span></span> 

- <span data-ttu-id="53302-111">如果用户已登录到其他 Office 应用程序通过其 Office 365 企业帐户，当他们开始他们正在采取直接到应用程序的团队。</span><span class="sxs-lookup"><span data-stu-id="53302-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="53302-112">没有必要为他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="53302-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="53302-113">如果用户未登录到其他任何地方，其 Office 365 企业帐户在启动团队时，被要求提供单因素或多因素身份验证 （SFA 或 MFA），这取决于什么您的组织决定他们想要以所需要的过程。</span><span class="sxs-lookup"><span data-stu-id="53302-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="53302-114">如果用户已登录到加入域的计算机，在启动团队，他们可能需要经过一个身份验证步骤，具体取决于您的组织选择是否要求 MFA 或如果他们的计算机已要求 MFA 登录时。</span><span class="sxs-lookup"><span data-stu-id="53302-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="53302-115">如果他们的计算机已经要求 MFA 登录，当他们打开团队，应用程序自动启动。</span><span class="sxs-lookup"><span data-stu-id="53302-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="53302-116">Mac 的用户</span><span class="sxs-lookup"><span data-stu-id="53302-116">Mac users</span></span> 

<span data-ttu-id="53302-117">当用户启动团队时，他们的计算机不能将他们从他们的 Office 365 企业帐户或任何其他 Office 应用程序的凭据。</span><span class="sxs-lookup"><span data-stu-id="53302-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="53302-118">相反，他们将看到一个提示，询问他们对于 SFA 或 MFA （具体取决于您的组织的设置）。</span><span class="sxs-lookup"><span data-stu-id="53302-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="53302-119">一旦用户输入其凭据，它们不需要再次提供它们。</span><span class="sxs-lookup"><span data-stu-id="53302-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="53302-120">从那一刻开始，团队自动启动时在同一台计算机上工作。</span><span class="sxs-lookup"><span data-stu-id="53302-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="53302-121">在完成新型身份验证后切换帐户</span><span class="sxs-lookup"><span data-stu-id="53302-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="53302-122">如果用户正在加入域的计算机 （例如，如果其租户已经启用了 Kerberos） 上，他们不能切换用户帐户，一旦他们完成了现代的身份验证。</span><span class="sxs-lookup"><span data-stu-id="53302-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="53302-123">如果用户不使用加入域的计算机上，则可以切换帐户。</span><span class="sxs-lookup"><span data-stu-id="53302-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="53302-124">现代身份验证完成后退出 Microsoft 小组</span><span class="sxs-lookup"><span data-stu-id="53302-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="53302-125">若要退出团队，用户可以单击顶部的应用程序，其个人资料图片，然后选择**退出**。他们可以应用程序图标在任务栏上，右键单击，然后选择**注销**。一旦他们已经超出团队的符号，它们需要输入其凭据再次启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="53302-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="53302-126">故障排除的现代身份验证</span><span class="sxs-lookup"><span data-stu-id="53302-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="53302-127">现代身份验证即可供使用团队，因此如果用户都不能完成此过程，可能会出现错您的域或您的组织的 Office 365 企业帐户每个组织。</span><span class="sxs-lookup"><span data-stu-id="53302-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="53302-128">有关详细信息，请参阅[为什么时遇到无法登录到 Microsoft 小组？](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。</span><span class="sxs-lookup"><span data-stu-id="53302-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

