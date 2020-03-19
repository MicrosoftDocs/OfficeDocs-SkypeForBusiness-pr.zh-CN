---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
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
ms.openlocfilehash: e1cdd071dfe19c50650d6f18605a5aeed5b39300
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327844"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="bc830-103">在 Outlook 中使用 Teams 会议外接程序</span><span class="sxs-lookup"><span data-stu-id="bc830-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="bc830-104">借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="bc830-105">此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。</span><span class="sxs-lookup"><span data-stu-id="bc830-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="bc830-106">Windows 版 Outlook 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc830-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="bc830-107">对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2010、Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc830-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="bc830-108">用户将在 Outlook 日历功能区看到 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc830-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能区中的 Teams 会议加载项屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="bc830-110">执行 Regsvr32.exe 文件的用户权限是将 Teams 会议加载项安装在计算机上的最低要求。</span><span class="sxs-lookup"><span data-stu-id="bc830-110">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="bc830-111">如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="bc830-111">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="bc830-112">如果使用的是来自 Microsoft Store 的 Office Outlook 安装，则不支持 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc830-112">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="bc830-113">建议需要此加载项的用户安装 Office 的即点即用版本，如[在 Windows 10 S 模式中的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 一文中所述。</span><span class="sxs-lookup"><span data-stu-id="bc830-113">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="bc830-114">Outlook for Mac 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc830-114">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="bc830-115">如果 Outlook 运行生产内部版本 16.24.414.0 和更高版本并使用 Office 365 客户端订阅激活，则 Outlook for Mac 中的“Teams 会议”按钮将显示在 Outlook for Mac 功能区中。</span><span class="sxs-lookup"><span data-stu-id="bc830-115">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with an Office 365 client subscription.</span></span>

<span data-ttu-id="bc830-116">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-116">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="bc830-117">Outlook Web App 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc830-117">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="bc830-118">若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。</span><span class="sxs-lookup"><span data-stu-id="bc830-118">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="bc830-119">若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。</span><span class="sxs-lookup"><span data-stu-id="bc830-119">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-web.png)

<span data-ttu-id="bc830-121">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-121">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="bc830-122">Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc830-122">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="bc830-123">“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。</span><span class="sxs-lookup"><span data-stu-id="bc830-123">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 移动版中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="bc830-125">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="bc830-126">Teams 会议加载项和 Outlook 的 FindTime</span><span class="sxs-lookup"><span data-stu-id="bc830-126">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="bc830-127">FindTime 是帮助公司之间在会议时间上达成一致的 Outlook 加载项。</span><span class="sxs-lookup"><span data-stu-id="bc830-127">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="bc830-128">会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="bc830-128">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="bc830-129">若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-129">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="bc830-130">（FindTime 会将组织设置的内容用作默认的联机会议频道。）</span><span class="sxs-lookup"><span data-stu-id="bc830-130">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="bc830-131">若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bc830-131">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="bc830-132">若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。</span><span class="sxs-lookup"><span data-stu-id="bc830-132">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="bc830-133">有关详细信息，请参阅[使用 FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。</span><span class="sxs-lookup"><span data-stu-id="bc830-133">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="bc830-134">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="bc830-134">Authentication requirements</span></span>

<span data-ttu-id="bc830-135">Teams 会议外接程序要求用户使用新式身份验证登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="bc830-135">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="bc830-136">如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-136">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="bc830-137">可以通过以下方式之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="bc830-137">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="bc830-138">如果贵组织未配置新式身份验证，则应配置新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="bc830-138">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="bc830-139">如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。</span><span class="sxs-lookup"><span data-stu-id="bc830-139">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="bc830-140">要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="bc830-140">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="bc830-141">启用私人会议</span><span class="sxs-lookup"><span data-stu-id="bc830-141">Enable private meetings</span></span>

<span data-ttu-id="bc830-142">必须在 Microsoft Teams 管理中心中启用“允许安排私人会议”，才能部署该加载项。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-142">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="bc830-143">在管理中心中，转到“会议” > “会议策略”，然后在“常规”部分中将“允许安排私人会议”切换为“启用”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc830-143">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 管理中心中的设置屏幕截图。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="bc830-145">Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。</span><span class="sxs-lookup"><span data-stu-id="bc830-145">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="bc830-146">在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="bc830-146">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="bc830-147">Teams 升级策略和适用于 Outlook 的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc830-147">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="bc830-148">客户可以[选择从 Skype for Business 到 Teams 的升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bc830-148">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="bc830-149">租户管理员可以使用 Teams 共存模式来定义用户的这一过程。</span><span class="sxs-lookup"><span data-stu-id="bc830-149">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="bc830-150">租户管理员可以选择允许用户并行使用 Teams 和 Skype for Business（孤岛模式）。</span><span class="sxs-lookup"><span data-stu-id="bc830-150">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="bc830-151">处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-151">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="bc830-152">在 Outlook 网页版、Outlook Windows 和 Outlook Mac 中，用户处于孤岛模式时将同时看到 Skype for Business 和 Teams 加载项。</span><span class="sxs-lookup"><span data-stu-id="bc830-152">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="bc830-153">由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-153">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="bc830-154">有关详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bc830-154">See the following table for details.</span></span>

| <span data-ttu-id="bc830-155">Teams 管理中心中的共存模式</span><span class="sxs-lookup"><span data-stu-id="bc830-155">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="bc830-156">Outlook 移动版中的默认会议提供商</span><span class="sxs-lookup"><span data-stu-id="bc830-156">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="bc830-157">孤岛</span><span class="sxs-lookup"><span data-stu-id="bc830-157">Islands</span></span> | <span data-ttu-id="bc830-158">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc830-158">Skype for Business</span></span> |
| <span data-ttu-id="bc830-159">仅 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc830-159">Skype for Business only</span></span> | <span data-ttu-id="bc830-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc830-160">Skype for Business</span></span> |
| <span data-ttu-id="bc830-161">Skype for Business 和 Teams 协作</span><span class="sxs-lookup"><span data-stu-id="bc830-161">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="bc830-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc830-162">Skype for Business</span></span> |
| <span data-ttu-id="bc830-163">Skype for Business 和 Teams 协作及会议</span><span class="sxs-lookup"><span data-stu-id="bc830-163">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="bc830-164">Teams</span><span class="sxs-lookup"><span data-stu-id="bc830-164">Teams</span></span> |
| <span data-ttu-id="bc830-165">仅 Teams</span><span class="sxs-lookup"><span data-stu-id="bc830-165">Teams only</span></span> | <span data-ttu-id="bc830-166">Teams</span><span class="sxs-lookup"><span data-stu-id="bc830-166">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="bc830-167">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="bc830-167">Other considerations</span></span>

<span data-ttu-id="bc830-168">Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="bc830-168">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="bc830-169">此外接程序用于特定参与者的安排会议，而非用于频道中的会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-169">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="bc830-170">频道会议必须从 Teams 中安排。</span><span class="sxs-lookup"><span data-stu-id="bc830-170">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="bc830-171">若身份验证代理在用户电脑和 Teams 服务的网络路径中，此加载项将无法运行。</span><span class="sxs-lookup"><span data-stu-id="bc830-171">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="bc830-172">用户无法在 Outlook 中安排直播活动。</span><span class="sxs-lookup"><span data-stu-id="bc830-172">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="bc830-173">若要安排直播活动，请转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="bc830-173">Go to Teams to schedule live events.</span></span> <span data-ttu-id="bc830-174">有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="bc830-174">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bc830-175">故障排除</span><span class="sxs-lookup"><span data-stu-id="bc830-175">Troubleshooting</span></span>

<span data-ttu-id="bc830-176">若无法安装 Outlook 的 Teams 会议加载项，请尝试下列故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="bc830-176">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="bc830-177">确保已应用所有可用的 Outlook 桌面客户端更新。</span><span class="sxs-lookup"><span data-stu-id="bc830-177">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="bc830-178">重启 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc830-178">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="bc830-179">注销，然后重新登录到 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc830-179">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="bc830-180">重启 Outlook 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc830-180">Restart the Outlook desktop client.</span></span> <span data-ttu-id="bc830-181">（请确保 Outlook 未运行管理员模式。）</span><span class="sxs-lookup"><span data-stu-id="bc830-181">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="bc830-182">确保登录的用户帐户名称不包含空格。</span><span class="sxs-lookup"><span data-stu-id="bc830-182">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="bc830-183">（这是一个已知问题，将在后续更新中修复。）</span><span class="sxs-lookup"><span data-stu-id="bc830-183">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="bc830-184">确保单一登录 (SSO) 已启用。</span><span class="sxs-lookup"><span data-stu-id="bc830-184">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="bc830-185">若管理员已配置 Microsoft Exchange 来[控制对 Exchange Web Server (EWS) 的访问](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，则代理无法代表上级安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc830-185">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="bc830-186">此配置的解决方案正在开发中，未来将予以发布。</span><span class="sxs-lookup"><span data-stu-id="bc830-186">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="bc830-187">有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="bc830-187">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="bc830-188">详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="bc830-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
