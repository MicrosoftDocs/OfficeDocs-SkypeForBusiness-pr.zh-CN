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
ms.openlocfilehash: dc543096965a3abc51964c5006795cf385a4cb55
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814098"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="bc60a-103">在 Outlook 中使用 Teams 会议外接程序</span><span class="sxs-lookup"><span data-stu-id="bc60a-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="bc60a-104">借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="bc60a-105">此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。</span><span class="sxs-lookup"><span data-stu-id="bc60a-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="bc60a-106">Windows 版 Outlook 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="bc60a-107">将为 Microsoft Teams 以及 Windows 电脑上安装了 Microsoft Teams、Office 2013、Office 2016 或 Office 2019 的用户自动安装 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="bc60a-108">用户将在 Outlook 日历功能区看到 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能区中的 Teams 会议加载项屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="bc60a-110">不 **存在直接链接** 到 Teams 外接内容的 URL。</span><span class="sxs-lookup"><span data-stu-id="bc60a-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="bc60a-111">如果你的组织同时运行 Teams 和 Skype for Business，还有其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="bc60a-112">在某些情况下，Teams 加载项在 Outlook 中不可用。</span><span class="sxs-lookup"><span data-stu-id="bc60a-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="bc60a-113">有关详细信息[，请参阅从 Skype for Business 升级到 Teams。](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)</span><span class="sxs-lookup"><span data-stu-id="bc60a-113">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="bc60a-114">执行 Regsvr32.exe 文件的用户权限是将 Teams 会议加载项安装在计算机上的最低要求。</span><span class="sxs-lookup"><span data-stu-id="bc60a-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="bc60a-115">如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="bc60a-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="bc60a-116">如果使用的是来自 Microsoft Store 的 Office Outlook 安装，则不支持 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="bc60a-117">建议需要此加载项的用户安装 Office 的即点即用版本，如[在 Windows 10 S 模式中的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 一文中所述。</span><span class="sxs-lookup"><span data-stu-id="bc60a-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="bc60a-118">Outlook for Mac 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="bc60a-119">如果 Outlook 运行生版版本 16.24.414.0 及更高版本并已使用 Microsoft 365 或 Office 365 客户端订阅激活，Outlook for Mac 功能区中的 Teams 会议按钮将显示在 Outlook for Mac 功能区中。</span><span class="sxs-lookup"><span data-stu-id="bc60a-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="bc60a-120">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="bc60a-121">Outlook Web App 中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="bc60a-122">若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。</span><span class="sxs-lookup"><span data-stu-id="bc60a-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="bc60a-123">若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-web.png)

<span data-ttu-id="bc60a-125">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="bc60a-126">Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="bc60a-127">“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。</span><span class="sxs-lookup"><span data-stu-id="bc60a-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 移动版中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="bc60a-129">用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a><span data-ttu-id="bc60a-130">Teams 会议加载项和 FindTime for Outlook</span><span class="sxs-lookup"><span data-stu-id="bc60a-130">Teams Meeting add-in and FindTime for Outlook</span></span>

<span data-ttu-id="bc60a-131">FindTime 是 Outlook 的加载项，可帮助用户在公司即将参加会议时间感知。</span><span class="sxs-lookup"><span data-stu-id="bc60a-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="bc60a-132">会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="bc60a-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="bc60a-133">若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="bc60a-134">（FindTime 会将组织设置的内容用作默认的联机会议频道。）</span><span class="sxs-lookup"><span data-stu-id="bc60a-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="bc60a-135">若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bc60a-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="bc60a-136">若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。</span><span class="sxs-lookup"><span data-stu-id="bc60a-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="bc60a-137">有关详细信息，请参阅"使用 [FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)"。</span><span class="sxs-lookup"><span data-stu-id="bc60a-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="bc60a-138">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="bc60a-138">Authentication requirements</span></span>

<span data-ttu-id="bc60a-139">Teams 会议外接程序要求用户使用新式身份验证登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="bc60a-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="bc60a-140">如果用户未使用此方法登录，则仍然可以使用 Teams 客户端，但无法使用 Outlook 加载项安排 Teams 联机会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="bc60a-141">可以通过以下方式之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="bc60a-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="bc60a-142">如果贵组织未配置新式身份验证，则应配置新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="bc60a-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="bc60a-143">如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。</span><span class="sxs-lookup"><span data-stu-id="bc60a-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="bc60a-144">要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="bc60a-145">启用私人会议</span><span class="sxs-lookup"><span data-stu-id="bc60a-145">Enable private meetings</span></span>

<span data-ttu-id="bc60a-146">必须在 Microsoft Teams 管理中心中启用“允许安排私人会议”，才能部署该加载项。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="bc60a-147">在管理中心中，转到“会议” > “会议策略”，然后在“常规”部分中将“允许安排私人会议”切换为“启用”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bc60a-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 管理中心中的设置屏幕截图。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="bc60a-149">Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。</span><span class="sxs-lookup"><span data-stu-id="bc60a-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="bc60a-150">在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="bc60a-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="bc60a-151">Teams 升级策略和适用于 Outlook 的 Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="bc60a-152">客户可以[选择从 Skype for Business 到 Teams 的升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="bc60a-153">租户管理员可以使用 Teams 共存模式来定义用户的这一过程。</span><span class="sxs-lookup"><span data-stu-id="bc60a-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="bc60a-154">租户管理员可以选择允许用户并行使用 Teams 和 Skype for Business（孤岛模式）。</span><span class="sxs-lookup"><span data-stu-id="bc60a-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="bc60a-155">处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="bc60a-156">在 Outlook 网页版、Outlook Windows 和 Outlook Mac 中，默认情况下，用户在使用群模式时同时看到 Skype for Business 和 Teams 加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="bc60a-157">你可以配置 Teams 会议策略设置来控制群值模式中的用户是否只能使用 Teams 会议加载项或同时使用 Teams 会议加载项和 Skype for Business 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="bc60a-158">由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="bc60a-159">有关详细信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bc60a-159">See the following table for details.</span></span>

| <span data-ttu-id="bc60a-160">Teams 管理中心中的共存模式</span><span class="sxs-lookup"><span data-stu-id="bc60a-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="bc60a-161">Outlook 移动版中的默认会议提供商</span><span class="sxs-lookup"><span data-stu-id="bc60a-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="bc60a-162">孤岛</span><span class="sxs-lookup"><span data-stu-id="bc60a-162">Islands</span></span> | <span data-ttu-id="bc60a-163">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc60a-163">Skype for Business</span></span> |
| <span data-ttu-id="bc60a-164">仅 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc60a-164">Skype for Business only</span></span> | <span data-ttu-id="bc60a-165">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc60a-165">Skype for Business</span></span> |
| <span data-ttu-id="bc60a-166">Skype for Business 和 Teams 协作</span><span class="sxs-lookup"><span data-stu-id="bc60a-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="bc60a-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc60a-167">Skype for Business</span></span> |
| <span data-ttu-id="bc60a-168">Skype for Business 和 Teams 协作及会议</span><span class="sxs-lookup"><span data-stu-id="bc60a-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="bc60a-169">Teams</span><span class="sxs-lookup"><span data-stu-id="bc60a-169">Teams</span></span> |
| <span data-ttu-id="bc60a-170">仅 Teams</span><span class="sxs-lookup"><span data-stu-id="bc60a-170">Teams only</span></span> | <span data-ttu-id="bc60a-171">Teams</span><span class="sxs-lookup"><span data-stu-id="bc60a-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="bc60a-172">设置群模式中的用户是只能使用 Teams 会议加载项，还是同时使用 Teams 会议加载项和 Skype for Business 会议加载项</span><span class="sxs-lookup"><span data-stu-id="bc60a-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="bc60a-173">作为管理员，你可以配置 Teams 会议策略设置以控制针对处于群内模式的用户使用的 Outlook *会议加载项*。</span><span class="sxs-lookup"><span data-stu-id="bc60a-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="bc60a-174">你可以指定用户是否只能使用 Teams 会议加载项，还可以同时使用 Teams 会议和 Skype for Business 会议加载项来安排 Outlook 中的会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="bc60a-175">只能将此策略应用于处于群摸模式且在 Teams 会议策略中 **将 AllowOutlookAddIn** **参数设置为 True** 的用户。</span><span class="sxs-lookup"><span data-stu-id="bc60a-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="bc60a-176">有关如何设置此策略的步骤，请参阅 [针对群体模式的用户设置会议提供商](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-176">For steps on how to set this policy, see [set the meeting provider for users in Islands mode](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="bc60a-177">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="bc60a-177">Other considerations</span></span>

<span data-ttu-id="bc60a-178">Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="bc60a-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="bc60a-179">Teams 会议加载项需要 Outlook 邮箱用于主要用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-179">The Teams Meeting add-in requires an Exchange mailbox for the primary user scheduling the meeting.</span></span> <span data-ttu-id="bc60a-180">确保已在 Outlook 配置文件中至少配置了一个 Exchange 邮箱，并使用它来安排与该外程序安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-180">Ensure that you have at least one Exchange mailbox configured in your Outlook profile and use it to schedule Teams meetings with the add-in.</span></span> <span data-ttu-id="bc60a-181">有关 Exchange 要求，请参阅 ["Exchange 与 Teams 如何交互](https://docs.microsoft.com/microsoftteams/exchange-teams-interact)"。</span><span class="sxs-lookup"><span data-stu-id="bc60a-181">For Exchange requirements, see [How Exchange and Teams interact](https://docs.microsoft.com/microsoftteams/exchange-teams-interact).</span></span>
- <span data-ttu-id="bc60a-182">此外接程序用于特定参与者的安排会议，而非用于频道中的会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-182">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="bc60a-183">频道会议必须从 Teams 中安排。</span><span class="sxs-lookup"><span data-stu-id="bc60a-183">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="bc60a-184">如果身份验证代理位于用户电脑和 Teams 服务的网络路径中，加载项将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="bc60a-184">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="bc60a-185">用户无法在 Outlook 中安排直播活动。</span><span class="sxs-lookup"><span data-stu-id="bc60a-185">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="bc60a-186">若要安排直播活动，请转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="bc60a-186">Go to Teams to schedule live events.</span></span> <span data-ttu-id="bc60a-187">有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-187">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="bc60a-188">详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="bc60a-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bc60a-189">故障排除</span><span class="sxs-lookup"><span data-stu-id="bc60a-189">Troubleshooting</span></span>

<span data-ttu-id="bc60a-190">使用以下步骤解决 Teams 会议加载项的问题。</span><span class="sxs-lookup"><span data-stu-id="bc60a-190">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="bc60a-191">Outlook for Windows 中的 Teams 会议加载项不显示</span><span class="sxs-lookup"><span data-stu-id="bc60a-191">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="bc60a-192">若无法安装 Outlook 的 Teams 会议加载项，请尝试下列故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="bc60a-192">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

<span data-ttu-id="bc60a-193">[下载](https://aka.ms/SaRA-TeamsAddInScenario) 并运行 [Microsoft 支持恢复助手，](https://aka.ms/SaRA_Home) 以执行自动化疑难解答步骤和修补程序。</span><span class="sxs-lookup"><span data-stu-id="bc60a-193">[Download](https://aka.ms/SaRA-TeamsAddInScenario) and run the [Microsoft Support Recovery Assistant](https://aka.ms/SaRA_Home) to perform automated troubleshooting steps and fixes.</span></span>

<span data-ttu-id="bc60a-194">或者，手动执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="bc60a-194">Alternatively, perform the following steps manually:</span></span>

- <span data-ttu-id="bc60a-195">Windows 7 用户必须安装 [Windows 中通用 C Runtime 的更新才能](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) 运行 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="bc60a-195">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="bc60a-196">检查用户是否具有 Teams 升级策略，该策略支持 Teams 中的安排会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-196">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="bc60a-197">有关详细信息[，请参阅从 Skype for Business 升级到 Teams。](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)</span><span class="sxs-lookup"><span data-stu-id="bc60a-197">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="bc60a-198">检查用户是否具有了允许 Outlook 加载项的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="bc60a-198">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="bc60a-199">有关详细信息 [，请参阅 Teams 中的"](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) 管理会议策略"。</span><span class="sxs-lookup"><span data-stu-id="bc60a-199">See [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="bc60a-200">确保用户已安装了 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc60a-200">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="bc60a-201">只有使用 Teams 网页版客户端时，会议加载项不会安装。</span><span class="sxs-lookup"><span data-stu-id="bc60a-201">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="bc60a-202">确保用户安装了 Outlook 2013 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bc60a-202">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="bc60a-203">确保用户有权执行regsvr32.exe。</span><span class="sxs-lookup"><span data-stu-id="bc60a-203">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="bc60a-204">确保已应用 Outlook 桌面客户端的所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="bc60a-204">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="bc60a-205">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bc60a-205">Follow these steps:</span></span>
  - <span data-ttu-id="bc60a-206">重启 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc60a-206">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="bc60a-207">注销，然后重新登录到 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc60a-207">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="bc60a-208">重启 Outlook 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="bc60a-208">Restart the Outlook desktop client.</span></span> <span data-ttu-id="bc60a-209"> (确保 Outlook 未在管理模式下运行。) </span><span class="sxs-lookup"><span data-stu-id="bc60a-209">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="bc60a-210">如果仍然看不到该加载项，请确保它未在 Outlook 中禁用。</span><span class="sxs-lookup"><span data-stu-id="bc60a-210">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="bc60a-211">在 Outlook 中，依 **次选择"文件** "和 **"选项**"。</span><span class="sxs-lookup"><span data-stu-id="bc60a-211">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="bc60a-212">选择 **Outlook"选项"对话框中** 的 **"加载项** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="bc60a-212">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="bc60a-213">确认"活动 **应用程序加载项"列表中Microsoft Office Microsoft Teams** **会议加载项** 已列入"可用</span><span class="sxs-lookup"><span data-stu-id="bc60a-213">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="bc60a-214">如果 Teams 会议加载项列在禁用 **的应用程序加载项** 列表中，请选择" **管理"** 中的 COM **加载项** ，然后选择 **"转到..."。**</span><span class="sxs-lookup"><span data-stu-id="bc60a-214">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="bc60a-215">在 Microsoft Teams 会议加载项**for Windows 网站版窗口旁边设置Microsoft Office。**</span><span class="sxs-lookup"><span data-stu-id="bc60a-215">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="bc60a-216">在 **所有** 对话框上选择"确定"并重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bc60a-216">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="bc60a-217">有关如何在 Office 程序中管理加载项的常规 [指导，请参阅"查看"、"管理"和"安装加载项](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)"。</span><span class="sxs-lookup"><span data-stu-id="bc60a-217">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="bc60a-218">如果仍未显示加载项，请使用下列步骤验证注册表设置。</span><span class="sxs-lookup"><span data-stu-id="bc60a-218">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="bc60a-219">编辑注册表不当可能严重损坏系统。</span><span class="sxs-lookup"><span data-stu-id="bc60a-219">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="bc60a-220">更改注册表之前，应备份计算机上任何有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="bc60a-220">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="bc60a-221">启动RegEdit.exe</span><span class="sxs-lookup"><span data-stu-id="bc60a-221">Launch RegEdit.exe</span></span>
- <span data-ttu-id="bc60a-222">导航到 HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span><span class="sxs-lookup"><span data-stu-id="bc60a-222">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="bc60a-223">确认团队Addin.FastConnect 存在。</span><span class="sxs-lookup"><span data-stu-id="bc60a-223">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="bc60a-224">在 TeamsAddin.FastConnect 内，验证是否存在 LoadBehavior，并且已设置为 3。</span><span class="sxs-lookup"><span data-stu-id="bc60a-224">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="bc60a-225">如果 LoadBehavior 具有 3 以外的值，请将其更改为 3 并重启 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bc60a-225">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="bc60a-226">代理的安排不工作</span><span class="sxs-lookup"><span data-stu-id="bc60a-226">Delegate scheduling does not work</span></span>

<span data-ttu-id="bc60a-227">若管理员已配置 Microsoft Exchange 来[控制对 Exchange Web Server (EWS) 的访问](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，则代理无法代表上级安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="bc60a-227">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="bc60a-228">此配置的解决方案正在开发中，未来将予以发布。</span><span class="sxs-lookup"><span data-stu-id="bc60a-228">The solution for this configuration is under development and will be released in the future.</span></span> <span data-ttu-id="bc60a-229">作为一种变通方法，管理员可以将以下字符串添加到 EWS 允许列表 *："SchedulingService"。*</span><span class="sxs-lookup"><span data-stu-id="bc60a-229">As a workaround, your administrator can add the following string to the EWS Allow List: "*SchedulingService*".</span></span> 


## <a name="related-topics"></a><span data-ttu-id="bc60a-230">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc60a-230">Related topics</span></span>

[<span data-ttu-id="bc60a-231">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="bc60a-231">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
