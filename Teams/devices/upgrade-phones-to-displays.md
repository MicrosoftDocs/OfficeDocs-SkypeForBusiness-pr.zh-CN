---
title: 将团队的电话升级到团队显示
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 了解如何将团队中的电话升级到团队显示在 Microsoft 团队管理中心中。
ms.openlocfilehash: e741374ceb377dfec2f7b8a78f0d67b8e5a70bd1
ms.sourcegitcommit: 532205e5a3c28b44b86cd4d1376ebee9590b8266
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816112"
---
# <a name="upgrade-teams-phones-to-teams-displays"></a><span data-ttu-id="e5c0a-103">将团队的电话升级到团队显示</span><span class="sxs-lookup"><span data-stu-id="e5c0a-103">Upgrade Teams phones to Teams displays</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5c0a-104">升级到 "团队" 显示仅在 "联想 ThinkSmart" 视图设备上可用。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-104">Upgrading to Teams displays is available only on Lenovo ThinkSmart View devices.</span></span> <span data-ttu-id="e5c0a-105">本文中的信息仅适用于此设备模型。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-105">The information in this article applies only to this device model.</span></span>  

<span data-ttu-id="e5c0a-106">本文概述了如何将团队中的电话升级到团队显示 Microsoft 团队管理中心中的设备。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-106">This article gives you an overview of how to upgrade your Teams phones to Teams display devices in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e5c0a-107">执行此操作后，设备可为团队显示设备提供丰富的用户体验。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-107">Doing this allows the devices to provide a rich experience for your users as Teams display devices.</span></span>

<span data-ttu-id="e5c0a-108">团队显示是一种由多人专用团队设备组成的类别，其中包括环境触摸屏和由 Cortana 支持的无人参与体验。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-108">Teams displays are a category of all-in-one dedicated Teams devices with an ambient touchscreen and a hands-free experience powered by Cortana.</span></span> <span data-ttu-id="e5c0a-109">团队显示是团队手机的演变。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-109">Teams displays are the evolution of Teams phones.</span></span> <span data-ttu-id="e5c0a-110">除了 [团队手机支持的功能](phones-for-teams.md#features-supported-by-teams-phones)之外，团队还会显示一些功能，如 "始终显示"，其中 "所有团队活动" 和 "协作" 选项始终可用。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-110">In addition to [features supported by Teams phones](phones-for-teams.md#features-supported-by-teams-phones), Teams displays include features such as an always-on display in which all Teams activity and collaboration options are always available.</span></span> <span data-ttu-id="e5c0a-111">若要了解有关团队显示的独有功能的详细信息，请参阅 [Microsoft 团队显示](teams-displays.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-111">To learn more about features unique to Teams displays, see [Microsoft Teams displays](teams-displays.md).</span></span>

## <a name="what-you-need-to-know-about-upgrading-to-teams-displays"></a><span data-ttu-id="e5c0a-112">有关升级到团队的需要了解哪些内容</span><span class="sxs-lookup"><span data-stu-id="e5c0a-112">What you need to know about upgrading to Teams displays</span></span>

### <a name="which-teams-phones-can-be-upgraded"></a><span data-ttu-id="e5c0a-113">哪些团队的手机可以升级？</span><span class="sxs-lookup"><span data-stu-id="e5c0a-113">Which Teams phones can be upgraded?</span></span>

<span data-ttu-id="e5c0a-114">联想 ThinkSmart 查看设备可升级到团队显示。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-114">Lenovo ThinkSmart View devices can be upgraded to Teams displays.</span></span>

### <a name="how-can-i-prepare-users"></a><span data-ttu-id="e5c0a-115">如何准备用户？</span><span class="sxs-lookup"><span data-stu-id="e5c0a-115">How can I prepare users?</span></span>

<span data-ttu-id="e5c0a-116">若要让你的用户准备就绪，请与你的用户一起向 [团队显示](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6) "共享入门"，以帮助他们熟悉团队的使用。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-116">To get your users ready, share [Get started with Teams displays](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6) with your users to help them get familiar with using Teams displays.</span></span> <span data-ttu-id="e5c0a-117">我们建议你在升级之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-117">We recommend you do this well in advance of the upgrade.</span></span>

<span data-ttu-id="e5c0a-118">让他们知道升级后不会对其数据或首选项做任何更改。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-118">Let them know that there's no changes to their data or preferences after the upgrade.</span></span> <span data-ttu-id="e5c0a-119">例如，用户可以在团队显示中访问其所有会议、未接来电和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-119">For example, users can access all their meetings, missed calls, and voicemails in Teams displays.</span></span> 

### <a name="what-happens-after-the-upgrade"></a><span data-ttu-id="e5c0a-120">升级后会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e5c0a-120">What happens after the upgrade?</span></span>

<span data-ttu-id="e5c0a-121">将团队手机升级到团队显示设备后，设备将在 " **团队显示** " 页面上的 "Microsoft 团队管理中心" 的 " **设备** " 部分中列出。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-121">After you upgrade a Teams phone to a Teams display device, the device is listed on the **Teams displays** page in the **Devices** section of the Microsoft Teams admin center.</span></span> <span data-ttu-id="e5c0a-122">管理它的方式与管理任何其他团队设备的方式相同。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-122">You manage it in the same way that you manage any other Teams device.</span></span> <span data-ttu-id="e5c0a-123">若要了解详细信息，请参阅 [在团队中管理设备](device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-123">To learn more, see [Manage your devices in Teams](device-management.md).</span></span>

<span data-ttu-id="e5c0a-124">请记住，在将团队手机升级到团队显示设备后，操作不会撤消。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-124">Keep in mind that after you upgrade a Teams phone to a Teams display device, the action can't be reversed.</span></span> <span data-ttu-id="e5c0a-125">我们建议您首先在升级整个组织之前先向一组早期使用者运行试验。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-125">We recommend you first run a pilot with a group of early adopters before you upgrade your entire organization.</span></span> 

## <a name="upgrade-your-teams-phones-to-teams-displays"></a><span data-ttu-id="e5c0a-126">将团队的电话升级到团队显示</span><span class="sxs-lookup"><span data-stu-id="e5c0a-126">Upgrade your Teams phones to Teams displays</span></span>

1. <span data-ttu-id="e5c0a-127">在 Microsoft 团队管理中心的左侧导航中，转到 " **设备**  >  **电话** "。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-127">In the left navigation of the Microsoft Teams admin center, go to **Devices** > **Phones** .</span></span>
2. <span data-ttu-id="e5c0a-128">选择要升级的团队电话，然后选择 " **升级** "。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-128">Select the Teams phones you want to upgrade, and then select **Upgrade** .</span></span>

    :::image type="content" source="../media/upgrade-phones-to-displays-select.png" alt-text="显示选择用于升级到团队的团队手机的屏幕截图":::

3. <span data-ttu-id="e5c0a-130">在 " **升级到团队显示** " 对话框中，选择 " **计划升级** " 以设置升级或 **立即升级** 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-130">In the **Upgrade to Teams display** dialogue box, select **Schedule upgrade** to set a date and time for the upgrade or **Upgrade now** .</span></span>

    :::image type="content" source="../media/upgrade-phones-to-displays-upgrade.png" alt-text="显示 "升级到团队显示器" 对话框的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="e5c0a-132">如果您收到一条消息，提示您所选的电话无法升级，请检查以确保选择 [支持升级的电话](#which-teams-phones-can-be-upgraded)，然后重试。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-132">If you receive a message that says your selected phones can't be upgraded, check to make sure that you select [phones that support the upgrade](#which-teams-phones-can-be-upgraded), and then try again.</span></span>

<span data-ttu-id="e5c0a-133">在升级过程中，设备的固件将更新为团队显示设备，设备将重新启动，并且已准备好使用。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-133">During the upgrade process, the device's firmware is updated to a Teams display device, the device restarts, and is ready for use.</span></span> <span data-ttu-id="e5c0a-134">升级完成后，你将看到 " **团队显示** " 页面上列出了 "Microsoft 团队管理中心" 页面上列出的设备。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-134">When the upgrade is completed, you'll see the device listed on the **Teams displays** page in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="e5c0a-135">完成升级最多可能需要一小时。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-135">It can take up to an hour for the upgrade to complete.</span></span> <span data-ttu-id="e5c0a-136">如果一个小时后进程尚未完成，请重试升级。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-136">If the process hasn't completed after an hour, retry the upgrade.</span></span> <span data-ttu-id="e5c0a-137">您也可以转到 "设备详细信息" 页面的 " **历史记录** " 选项卡以查看状态。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-137">You can also go to the **History** tab of the device details page to see the status.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e5c0a-138">已知问题</span><span class="sxs-lookup"><span data-stu-id="e5c0a-138">Known issues</span></span>

### <a name="teams-displays-have-the-default-theme-instead-of-the-dark-theme"></a><span data-ttu-id="e5c0a-139">团队显示具有默认主题，而不是深色主题</span><span class="sxs-lookup"><span data-stu-id="e5c0a-139">Teams displays have the Default theme instead of the Dark theme</span></span>

<span data-ttu-id="e5c0a-140">团队显示的深色主题支持将在将来的更新中提供。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-140">Dark theme support on Teams displays will be available in a future update.</span></span> <span data-ttu-id="e5c0a-141">使用深色主题的团队电话将在 "升级到团队" 显示后获取默认主题。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-141">Teams phones that use the Dark theme will get the Default theme after the upgrade to Teams displays.</span></span>

### <a name="some-apps-are-missing-from-the-home-screen"></a><span data-ttu-id="e5c0a-142">主屏幕中缺少某些应用</span><span class="sxs-lookup"><span data-stu-id="e5c0a-142">Some apps are missing from the Home screen</span></span>

<span data-ttu-id="e5c0a-143">如果升级后主屏幕中缺少某些应用，请注销并再次登录。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-143">If certain apps are missing from the Home screen after the upgrade, sign out and sign in again.</span></span> <span data-ttu-id="e5c0a-144">此功能的修补程序将在将来的更新中提供。</span><span class="sxs-lookup"><span data-stu-id="e5c0a-144">The fix for this will be available in a future update.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5c0a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5c0a-145">See also</span></span>

[<span data-ttu-id="e5c0a-146">Microsoft 团队简介显示</span><span class="sxs-lookup"><span data-stu-id="e5c0a-146">Introducing Microsoft Teams displays</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[<span data-ttu-id="e5c0a-147">团队显示</span><span class="sxs-lookup"><span data-stu-id="e5c0a-147">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="e5c0a-148">团队市场</span><span class="sxs-lookup"><span data-stu-id="e5c0a-148">Teams Marketplace</span></span>](https://office.com/teamsdevices)

[<span data-ttu-id="e5c0a-149">Teams 电话</span><span class="sxs-lookup"><span data-stu-id="e5c0a-149">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="e5c0a-150">适用于 Microsoft 团队的 IP 手机认证</span><span class="sxs-lookup"><span data-stu-id="e5c0a-150">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="e5c0a-151">团队中的 Cortana 语音帮助</span><span class="sxs-lookup"><span data-stu-id="e5c0a-151">Cortana voice assistance in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/cortana-in-teams)
