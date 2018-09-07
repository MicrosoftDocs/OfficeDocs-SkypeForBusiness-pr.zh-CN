---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f465b03aacbaa1c7cd3cd835d279a112d0f87891
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856870"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="592d5-103">在 Outlook 中使用 Teams 会议外接程序</span><span class="sxs-lookup"><span data-stu-id="592d5-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="592d5-104">对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="592d5-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="592d5-105">用户将在其 Outlook 日历功能区中看到 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="592d5-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Outlook 功能区中的 Teams 外接程序屏幕截图。](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="592d5-107">如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="592d5-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="592d5-108">当前未面向 Mac 用户提供 Outlook 的 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="592d5-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="592d5-109">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="592d5-109">Authentication requirements</span></span>

<span data-ttu-id="592d5-110">Teams 会议外接程序要求用户使用新式身份验证登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="592d5-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="592d5-111">如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。</span><span class="sxs-lookup"><span data-stu-id="592d5-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="592d5-112">可以通过以下方式之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="592d5-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="592d5-113">如果贵组织未配置新式身份验证，则应配置新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="592d5-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="592d5-114">如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。</span><span class="sxs-lookup"><span data-stu-id="592d5-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="592d5-115">要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="592d5-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="592d5-116">启用私人会议</span><span class="sxs-lookup"><span data-stu-id="592d5-116">Enable private meetings</span></span>

<span data-ttu-id="592d5-117">必须在 [Office 365 管理中心](https://portal.office.com/adminportal/home)中启用“允许安排私人会议”，才能部署该插件。</span><span class="sxs-lookup"><span data-stu-id="592d5-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Office 365 管理中心中“通话和会议”部分中设置的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="592d5-119">Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。</span><span class="sxs-lookup"><span data-stu-id="592d5-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="592d5-120">在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="592d5-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="592d5-121">其他考虑事项</span><span class="sxs-lookup"><span data-stu-id="592d5-121">Other considerations</span></span>

<span data-ttu-id="592d5-122">Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="592d5-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="592d5-123">一些在线会议功能（例如，录制、投票和白板）还不可用。</span><span class="sxs-lookup"><span data-stu-id="592d5-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="592d5-124">会议选项当前不可用。</span><span class="sxs-lookup"><span data-stu-id="592d5-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="592d5-125">当前只能邀请公司内部的人员，因为外部用户还不能加入会议。</span><span class="sxs-lookup"><span data-stu-id="592d5-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="592d5-126">此外接程序用于特定参与者的安排会议，而非用于频道中的会议。</span><span class="sxs-lookup"><span data-stu-id="592d5-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="592d5-127">频道会议必须从 Teams 中安排。</span><span class="sxs-lookup"><span data-stu-id="592d5-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="592d5-128">当前，仅面向 Windows 用户提供 Outlook 中的 Teams 会议外接程序，但即将面向 Mac 用户提供。</span><span class="sxs-lookup"><span data-stu-id="592d5-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="592d5-129">如果用户的 PC 和 Teams 服务的网络路径中存在身份验证代理，则此外接程序将无法工作。</span><span class="sxs-lookup"><span data-stu-id="592d5-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="592d5-130">外接程序要增量推出和可能不可用，贵组织尚未。</span><span class="sxs-lookup"><span data-stu-id="592d5-130">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="592d5-131">疑难解答</span><span class="sxs-lookup"><span data-stu-id="592d5-131">Troubleshooting</span></span>

<span data-ttu-id="592d5-132">如果无法让团队会议外接程序 Outlook 安装，请尝试以下疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="592d5-132">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="592d5-133">重新启动团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="592d5-133">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="592d5-134">注销并重新登录到团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="592d5-134">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="592d5-135">重新启动 Outlook 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="592d5-135">Restart the Outlook desktop client.</span></span> <span data-ttu-id="592d5-136">（确保 Outlook 没有运行管理员模式中。）</span><span class="sxs-lookup"><span data-stu-id="592d5-136">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="592d5-137">请确保已登录的用户帐户名不包含空格。</span><span class="sxs-lookup"><span data-stu-id="592d5-137">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="592d5-138">（这是一个已知的问题，并将在以后更新修复。）</span><span class="sxs-lookup"><span data-stu-id="592d5-138">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="592d5-139">请确保已启用单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="592d5-139">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="592d5-140">有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="592d5-140">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="592d5-141">详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="592d5-141">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

