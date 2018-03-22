---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 811c27a48a0e9bbccfbea7ac12e54ef0697b3f2b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="16f5c-103">在 Outlook 中使用 Teams 会议外接程序</span><span class="sxs-lookup"><span data-stu-id="16f5c-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="16f5c-104">对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="16f5c-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="16f5c-105">用户将在其 Outlook 日历功能区中看到 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="16f5c-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Outlook 功能区中的 Teams 外接程序屏幕截图。](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="16f5c-107">如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="16f5c-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="16f5c-108">当前未面向 Mac 用户提供 Outlook 的 Teams 会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="16f5c-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="16f5c-109">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="16f5c-109">Authentication requirements</span></span>

<span data-ttu-id="16f5c-110">Teams 会议外接程序要求用户使用新式身份验证登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="16f5c-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="16f5c-111">如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。</span><span class="sxs-lookup"><span data-stu-id="16f5c-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="16f5c-112">可以通过以下方式之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="16f5c-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="16f5c-113">如果贵组织未配置新式身份验证，则应配置新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="16f5c-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="16f5c-114">如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。</span><span class="sxs-lookup"><span data-stu-id="16f5c-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="16f5c-115">要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="16f5c-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="16f5c-116">启用私人会议</span><span class="sxs-lookup"><span data-stu-id="16f5c-116">Enable private meetings</span></span>

<span data-ttu-id="16f5c-117">必须在 [Office 365 管理中心](https://portal.office.com/adminportal/home)中启用“允许安排私人会议”，才能部署该插件。</span><span class="sxs-lookup"><span data-stu-id="16f5c-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Office 365 管理中心中“通话和会议”部分中设置的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="16f5c-119">Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。</span><span class="sxs-lookup"><span data-stu-id="16f5c-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="16f5c-120">在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="16f5c-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="16f5c-121">其他考虑事项</span><span class="sxs-lookup"><span data-stu-id="16f5c-121">Other considerations</span></span>

<span data-ttu-id="16f5c-122">Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="16f5c-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="16f5c-123">一些在线会议功能（例如，录制、投票和白板）还不可用。</span><span class="sxs-lookup"><span data-stu-id="16f5c-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="16f5c-124">会议选项当前不可用。</span><span class="sxs-lookup"><span data-stu-id="16f5c-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="16f5c-125">当前只能邀请公司内部的人员，因为外部用户还不能加入会议。</span><span class="sxs-lookup"><span data-stu-id="16f5c-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="16f5c-126">此外接程序用于特定参与者的安排会议，而非用于频道中的会议。</span><span class="sxs-lookup"><span data-stu-id="16f5c-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="16f5c-127">频道会议必须从 Teams 中安排。</span><span class="sxs-lookup"><span data-stu-id="16f5c-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="16f5c-128">当前，仅面向 Windows 用户提供 Outlook 中的 Teams 会议外接程序，但即将面向 Mac 用户提供。</span><span class="sxs-lookup"><span data-stu-id="16f5c-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="16f5c-129">如果用户的 PC 和 Teams 服务的网络路径中存在身份验证代理，则此外接程序将无法工作。</span><span class="sxs-lookup"><span data-stu-id="16f5c-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="16f5c-130">有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="16f5c-130">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="16f5c-131">详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="16f5c-131">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

