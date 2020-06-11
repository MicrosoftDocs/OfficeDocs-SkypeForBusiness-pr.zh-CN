---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fdecae806c0e02efc9a440ce192528ab6017d994
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689808"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="6d7a4-103">在 Outlook 中使用 Teams 会议外接程序</span><span class="sxs-lookup"><span data-stu-id="6d7a4-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="6d7a4-104">借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="6d7a4-105">此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="6d7a4-106">Windows 版 Outlook 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="6d7a4-107">将为在 Windows 电脑上安装了 Microsoft 团队和 office 2013、Office 2016 或 Office 2019 的用户自动安装团队会议加载项。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="6d7a4-108">用户将在 Outlook 日历功能区看到 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能区中的 Teams 会议加载项屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="6d7a4-110">没有链接到团队外接程序的**直接 URL** 。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="6d7a4-111">如果你的组织同时运行团队和 Skype for business，则有其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="6d7a4-112">在某些情况下，"团队外接程序" 在 Outlook 中不可用。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="6d7a4-113">有关详细信息，请参阅[从 Skype For Business 升级到团队](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-113">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="6d7a4-114">执行 Regsvr32.exe 文件的用户权限是将 Teams 会议加载项安装在计算机上的最低要求。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="6d7a4-115">如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="6d7a4-116">如果使用的是来自 Microsoft Store 的 Office Outlook 安装，则不支持 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="6d7a4-117">建议需要此加载项的用户安装 Office 的即点即用版本，如[在 Windows 10 S 模式中的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 一文中所述。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="6d7a4-118">Outlook for Mac 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="6d7a4-119">Outlook for Mac 中的 "团队会议" 按钮将在 outlook for Mac 功能区中显示，前提是 Outlook 正在运行生产内部版本16.24.414.0 和更高版本，并且已使用 Microsoft 365 或 Office 365 客户端订阅激活。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="6d7a4-120">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="6d7a4-121">Outlook Web App 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="6d7a4-122">若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="6d7a4-123">若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-web.png)

<span data-ttu-id="6d7a4-125">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="6d7a4-126">Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="6d7a4-127">“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 移动版中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="6d7a4-129">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a><span data-ttu-id="6d7a4-130">适用于 Outlook 的团队会议加载项和 FindTime</span><span class="sxs-lookup"><span data-stu-id="6d7a4-130">Teams Meeting add-in and FindTime for Outlook</span></span>

<span data-ttu-id="6d7a4-131">FindTime 是 Outlook 的加载项，可帮助用户在各公司的会议时间达成共识。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="6d7a4-132">会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="6d7a4-133">若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="6d7a4-134">（FindTime 会将组织设置的内容用作默认的联机会议频道。）</span><span class="sxs-lookup"><span data-stu-id="6d7a4-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="6d7a4-135">若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="6d7a4-136">若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="6d7a4-137">有关详细信息，请参阅[通过 FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="6d7a4-138">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="6d7a4-138">Authentication requirements</span></span>

<span data-ttu-id="6d7a4-139">Teams 会议外接程序要求用户使用新式身份验证登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="6d7a4-140">如果用户不使用此方法登录，他们仍然能够使用团队客户端，但无法使用 Outlook 加载项安排团队联机会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="6d7a4-141">可以通过以下方式之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="6d7a4-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="6d7a4-142">如果贵组织未配置新式身份验证，则应配置新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="6d7a4-143">如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="6d7a4-144">要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="6d7a4-145">启用私人会议</span><span class="sxs-lookup"><span data-stu-id="6d7a4-145">Enable private meetings</span></span>

<span data-ttu-id="6d7a4-146">必须在 Microsoft Teams 管理中心中启用“允许安排私人会议”，才能部署该加载项。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="6d7a4-147">在管理中心中，转到“会议” > “会议策略”，然后在“常规”部分中将“允许安排私人会议”切换为“启用”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d7a4-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 管理中心中的设置屏幕截图。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="6d7a4-149">Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="6d7a4-150">在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="6d7a4-151">Teams 升级策略和适用于 Outlook 的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="6d7a4-152">客户可以[选择从 Skype for Business 到 Teams 的升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="6d7a4-153">租户管理员可以使用 Teams 共存模式来定义用户的这一过程。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="6d7a4-154">租户管理员可以选择允许用户并行使用 Teams 和 Skype for Business（孤岛模式）。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="6d7a4-155">处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="6d7a4-156">在 Outlook 网页版、Outlook 窗口和 Outlook Mac 版中，用户在默认情况下以 "孤岛" 模式查看 Skype for business 和团队外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="6d7a4-157">你可以配置团队会议策略设置，以控制孤岛模式中的用户是否只能使用团队会议加载项或同时使用团队会议外接程序和 Skype for business 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="6d7a4-158">由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="6d7a4-159">有关详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-159">See the following table for details.</span></span>

| <span data-ttu-id="6d7a4-160">Teams 管理中心中的共存模式</span><span class="sxs-lookup"><span data-stu-id="6d7a4-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="6d7a4-161">Outlook 移动版中的默认会议提供商</span><span class="sxs-lookup"><span data-stu-id="6d7a4-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="6d7a4-162">孤岛</span><span class="sxs-lookup"><span data-stu-id="6d7a4-162">Islands</span></span> | <span data-ttu-id="6d7a4-163">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d7a4-163">Skype for Business</span></span> |
| <span data-ttu-id="6d7a4-164">仅 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d7a4-164">Skype for Business only</span></span> | <span data-ttu-id="6d7a4-165">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d7a4-165">Skype for Business</span></span> |
| <span data-ttu-id="6d7a4-166">Skype for Business 和 Teams 协作</span><span class="sxs-lookup"><span data-stu-id="6d7a4-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="6d7a4-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d7a4-167">Skype for Business</span></span> |
| <span data-ttu-id="6d7a4-168">Skype for Business 和 Teams 协作及会议</span><span class="sxs-lookup"><span data-stu-id="6d7a4-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="6d7a4-169">Teams</span><span class="sxs-lookup"><span data-stu-id="6d7a4-169">Teams</span></span> |
| <span data-ttu-id="6d7a4-170">仅 Teams</span><span class="sxs-lookup"><span data-stu-id="6d7a4-170">Teams only</span></span> | <span data-ttu-id="6d7a4-171">Teams</span><span class="sxs-lookup"><span data-stu-id="6d7a4-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="6d7a4-172">设置 "孤岛" 模式中的用户是否只能使用团队会议加载项或同时使用团队会议和 Skype for business 会议加载项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="6d7a4-173">作为管理员，你可以配置团队会议策略设置，以控制将哪些 Outlook 会议加载项用于使用*孤岛模式的用户*。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="6d7a4-174">你可以指定用户是否只能使用团队会议加载项或团队会议和 Skype for business 会议加载项在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="6d7a4-175">你只能将此策略应用到处于孤岛模式的用户，并在其团队会议策略中将**AllowOutlookAddIn**参数设置为**True** 。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="6d7a4-176">有关如何设置此策略的步骤，请参阅为[用户在 "孤岛" 模式下设置会议提供商](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-176">For steps on how to set this policy, see [set the meeting provider for users in Islands mode](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="6d7a4-177">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-177">Other considerations</span></span>

<span data-ttu-id="6d7a4-178">Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="6d7a4-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="6d7a4-179">此外接程序用于特定参与者的安排会议，而非用于频道中的会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-179">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="6d7a4-180">频道会议必须从 Teams 中安排。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-180">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="6d7a4-181">如果身份验证代理位于用户的 PC 和团队服务的网络路径中，加载项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-181">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="6d7a4-182">用户无法在 Outlook 中安排直播活动。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-182">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="6d7a4-183">若要安排直播活动，请转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-183">Go to Teams to schedule live events.</span></span> <span data-ttu-id="6d7a4-184">有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-184">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="6d7a4-185">详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-185">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6d7a4-186">故障排除</span><span class="sxs-lookup"><span data-stu-id="6d7a4-186">Troubleshooting</span></span>

<span data-ttu-id="6d7a4-187">使用以下步骤解决团队会议外接程序的问题。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-187">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="6d7a4-188">Outlook for Windows 中的团队会议外接程序不会显示</span><span class="sxs-lookup"><span data-stu-id="6d7a4-188">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="6d7a4-189">若无法安装 Outlook 的 Teams 会议加载项，请尝试下列故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-189">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="6d7a4-190">Windows 7 用户必须安装[windows 中通用 C 运行时的更新](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)，团队会议外接程序才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-190">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="6d7a4-191">检查用户是否具有团队升级策略，该策略允许在团队中安排会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-191">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="6d7a4-192">有关详细信息，请参阅[从 Skype For Business 升级到团队](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-192">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="6d7a4-193">检查用户是否具有允许 Outlook 加载项使用的团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-193">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="6d7a4-194">有关详细信息，请参阅[管理团队中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-194">See [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="6d7a4-195">确保用户安装了团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-195">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="6d7a4-196">如果仅使用团队 web 客户端，则不会安装会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-196">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="6d7a4-197">确保用户安装了 Outlook 2013 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-197">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="6d7a4-198">请确保用户具有执行 regsvr32.exe 的权限。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-198">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="6d7a4-199">确保已应用 Outlook 桌面客户端的所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-199">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="6d7a4-200">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6d7a4-200">Follow these steps:</span></span>
  - <span data-ttu-id="6d7a4-201">重启 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-201">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="6d7a4-202">注销，然后重新登录到 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-202">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="6d7a4-203">重启 Outlook 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-203">Restart the Outlook desktop client.</span></span> <span data-ttu-id="6d7a4-204">（请确保 Outlook 未在管理员模式下运行。）</span><span class="sxs-lookup"><span data-stu-id="6d7a4-204">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="6d7a4-205">如果您仍然看不到该加载项，请确保它在 Outlook 中未被禁用。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-205">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="6d7a4-206">在 Outlook 中，依次选择 "**文件**" 和 "**选项**"。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-206">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="6d7a4-207">选择 " **Outlook 选项**" 对话框的 "**加载项**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-207">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="6d7a4-208">确认 "**活动应用程序加载项**" 列表中是否列出了 microsoft **Office 的 Microsoft 团队会议加载**项</span><span class="sxs-lookup"><span data-stu-id="6d7a4-208">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="6d7a4-209">如果 "团队会议加载项" 列在 "**已禁用的应用程序加载项**" 列表中，请在 "**管理**" 中选择 " **COM 加载项**"，然后选择 "**转到**" .。。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-209">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="6d7a4-210">将 microsoft **Office 的 "Microsoft 团队会议加载项**" 旁边的复选框设置为 "microsoft Office"。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-210">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="6d7a4-211">在所有对话框上选择 **"确定"** ，然后重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-211">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="6d7a4-212">有关如何管理加载项的一般指南，请参阅[在 Office 程序中查看、管理和安装加载项](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-212">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="6d7a4-213">如果外接程序仍未显示，请使用以下步骤验证注册表设置。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-213">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6d7a4-214">错误地编辑注册表可能会严重损坏你的系统。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-214">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="6d7a4-215">在对注册表进行更改之前，应备份计算机上的任何重要数据。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-215">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="6d7a4-216">启动 RegEdit.exe</span><span class="sxs-lookup"><span data-stu-id="6d7a4-216">Launch RegEdit.exe</span></span>
- <span data-ttu-id="6d7a4-217">导航到 HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins</span><span class="sxs-lookup"><span data-stu-id="6d7a4-217">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="6d7a4-218">验证 TeamsAddin 是否存在。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-218">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="6d7a4-219">在 TeamsAddin 内，验证 LoadBehavior 是否存在并设置为3。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-219">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="6d7a4-220">如果 LoadBehavior 具有3之外的值，请将其更改为3，然后重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-220">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="6d7a4-221">代理人计划不起作用</span><span class="sxs-lookup"><span data-stu-id="6d7a4-221">Delegate scheduling does not work</span></span>

<span data-ttu-id="6d7a4-222">若管理员已配置 Microsoft Exchange 来[控制对 Exchange Web Server (EWS) 的访问](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，则代理无法代表上级安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-222">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="6d7a4-223">此配置的解决方案正在开发中，未来将予以发布。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-223">The solution for this configuration is under development and will be released in the future.</span></span> <span data-ttu-id="6d7a4-224">作为解决方法，管理员可以将以下字符串添加到 EWS 允许列表： "*SchedulingService*"。</span><span class="sxs-lookup"><span data-stu-id="6d7a4-224">As a workaround, your administrator can add the following string to the EWS Allow List: "*SchedulingService*".</span></span> 


