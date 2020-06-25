---
title: 已知问题
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 管理员可以了解 Microsoft 团队聊天室的已知问题列表，包括更新、用户界面、硬件、限制和预期行为。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1083ceb040f173aeef0a8a60d56a888a6b8fdb17
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874449"
---
# <a name="known-issues"></a><span data-ttu-id="01c4c-103">已知问题</span><span class="sxs-lookup"><span data-stu-id="01c4c-103">Known issues</span></span> 
 
<span data-ttu-id="01c4c-104">本文按功能区域列出了 Microsoft Teams 会议室的已知问题。</span><span class="sxs-lookup"><span data-stu-id="01c4c-104">This article lists the known issues for Microsoft Teams Rooms, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="01c4c-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="01c4c-105"><a name="update"> </a></span></span>  
## <a name="update"></a><span data-ttu-id="01c4c-106">更新</span><span class="sxs-lookup"><span data-stu-id="01c4c-106">Update</span></span> 

| <span data-ttu-id="01c4c-107">问题标题</span><span class="sxs-lookup"><span data-stu-id="01c4c-107">Issue title</span></span> |  <span data-ttu-id="01c4c-108">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="01c4c-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="01c4c-109">已知解决方法</span><span class="sxs-lookup"><span data-stu-id="01c4c-109">Known workaround</span></span> | <span data-ttu-id="01c4c-110">知识库文章</span><span class="sxs-lookup"><span data-stu-id="01c4c-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
| <span data-ttu-id="01c4c-111">应用程序不启动</span><span class="sxs-lookup"><span data-stu-id="01c4c-111">Application not launching</span></span> |  <span data-ttu-id="01c4c-112">更新到应用程序版本4.4.41.0 后，系统将启动到黑屏，或在几分钟后转到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="01c4c-112">After updating to application version 4.4.41.0, the system boots to black screen, or go to the logon screen after few minutes.</span></span> | <span data-ttu-id="01c4c-113">请按照[Microsoft 团队聊天室应用程序在更新到版本4.4.41.0 后无法启动](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)的步骤来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="01c4c-113">Follow the steps in [Microsoft Teams Rooms application does not start after update to version 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) to fix this issue.</span></span>  | <span data-ttu-id="01c4c-114">无</span><span class="sxs-lookup"><span data-stu-id="01c4c-114">None</span></span> |
|  <span data-ttu-id="01c4c-115">应用已过期</span><span class="sxs-lookup"><span data-stu-id="01c4c-115">App out of date</span></span>         |    <span data-ttu-id="01c4c-116">Microsoft Teams 会议室控制台显示“系统配置已过期”错误。</span><span class="sxs-lookup"><span data-stu-id="01c4c-116">The Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="01c4c-117">使用 Microsoft Teams 会议室恢复工具</span><span class="sxs-lookup"><span data-stu-id="01c4c-117">Use the Microsoft Teams Rooms recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="01c4c-118">无</span><span class="sxs-lookup"><span data-stu-id="01c4c-118">None</span></span> |
|  <span data-ttu-id="01c4c-119">设备更新为不受支持的 Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="01c4c-119">Device updated to unsupported version of Windows 10</span></span>   |    <span data-ttu-id="01c4c-120">Windows 10 设备从版本1803更新到版本1809，不受支持。</span><span class="sxs-lookup"><span data-stu-id="01c4c-120">Windows 10 device updated from version 1803 to version 1809, which is not supported.</span></span> <span data-ttu-id="01c4c-121">支持的版本为1903。</span><span class="sxs-lookup"><span data-stu-id="01c4c-121">The supported version is 1903.</span></span> |   <span data-ttu-id="01c4c-122">如果 DeferFeatureUpdatesPeriodinDays 设置的[组策略或 MDM 设置](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)（允许您将功能更新推迟到指定的天数内），则可能会发生这种情况，最大为365天。</span><span class="sxs-lookup"><span data-stu-id="01c4c-122">This can happen if the [Group Policy or MDM setting for DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) setting, which lets you defer feature updates for a specified number of days, is set to the maximum of 365 days.</span></span> <br><br> <span data-ttu-id="01c4c-123">Microsoft 团队聊天室不支持 Windows 10 版本1809，但支持版本1903。</span><span class="sxs-lookup"><span data-stu-id="01c4c-123">Windows 10 version 1809 isn't supported with Microsoft Teams Rooms, while version 1903 is supported.</span></span> <span data-ttu-id="01c4c-124">但是，从2020年3月27日起，版本1809超过365天。</span><span class="sxs-lookup"><span data-stu-id="01c4c-124">However, as of March 27, 2020, version 1809 is over 365 days old.</span></span> <span data-ttu-id="01c4c-125">如果此设置未更改，Windows 将尝试安装版本1809，这可能会导致 Microsoft 团队聊天室出现问题。</span><span class="sxs-lookup"><span data-stu-id="01c4c-125">If this setting isn't changed, Windows attempts to install version 1809, which may cause issues with Microsoft Teams Rooms.</span></span><br><br><span data-ttu-id="01c4c-126">为避免这种情况，请**删除**延迟更新的任何组策略或 MDM 设置。</span><span class="sxs-lookup"><span data-stu-id="01c4c-126">To avoid this situation, **remove** any Group Policy or MDM setting for deferring updates.</span></span> <span data-ttu-id="01c4c-127">这允许 Windows 更新到最新的受支持的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="01c4c-127">This allows Windows to update to the latest, supported OS version.</span></span> <br><br><span data-ttu-id="01c4c-128">**重要提示**必须**删除**"组策略" 或 "MDM" 设置（未配置），并且**未设置为 "0**"。</span><span class="sxs-lookup"><span data-stu-id="01c4c-128">**IMPORTANT** The Group Policy or MDM setting must be **removed** (left unconfigured) and **not set to 0**.</span></span> <span data-ttu-id="01c4c-129">如果该策略设置为0，则 Windows 会获得可能不受支持的最新可用版本。</span><span class="sxs-lookup"><span data-stu-id="01c4c-129">If the policy is set to 0, Windows takes the latest available version which may not be supported.</span></span> |  <span data-ttu-id="01c4c-130">无</span><span class="sxs-lookup"><span data-stu-id="01c4c-130">None</span></span> |



<span data-ttu-id="01c4c-131"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="01c4c-131"><a name="OS-conflicts"> </a></span></span>  
## <a name="user-interface"></a><span data-ttu-id="01c4c-132">用户界面</span><span class="sxs-lookup"><span data-stu-id="01c4c-132">User interface</span></span> 

| <span data-ttu-id="01c4c-133">问题标题</span><span class="sxs-lookup"><span data-stu-id="01c4c-133">Issue title</span></span> |  <span data-ttu-id="01c4c-134">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="01c4c-134">Behavior \/ Symptom</span></span> | <span data-ttu-id="01c4c-135">已知解决方法</span><span class="sxs-lookup"><span data-stu-id="01c4c-135">Known workaround</span></span> | <span data-ttu-id="01c4c-136">知识库文章</span><span class="sxs-lookup"><span data-stu-id="01c4c-136">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="01c4c-137">虚拟键盘缺失</span><span class="sxs-lookup"><span data-stu-id="01c4c-137">Virtual keyboard missing</span></span>   | <span data-ttu-id="01c4c-138">当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。</span><span class="sxs-lookup"><span data-stu-id="01c4c-138">The virtual keyboard doesn't appear when you need to enter information in Microsoft Teams Rooms.</span></span> <span data-ttu-id="01c4c-139">此问题出现在 Windows 10 版本1903中。</span><span class="sxs-lookup"><span data-stu-id="01c4c-139">This issue occurs in Windows 10, version 1903.</span></span> | <span data-ttu-id="01c4c-140">通过 Windows 更新为基于 x64 的系统的 Windows 10 版本1903安装2020-04 累积更新。</span><span class="sxs-lookup"><span data-stu-id="01c4c-140">Install 2020-04 Cumulative Update for Windows 10, version 1903 for x64-based Systems through Windows Updates.</span></span>  | <span data-ttu-id="01c4c-141">无</span><span class="sxs-lookup"><span data-stu-id="01c4c-141">None</span></span> | 

<span data-ttu-id="01c4c-142"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="01c4c-142"><a name="Hardware"> </a></span></span>  
## <a name="hardware"></a><span data-ttu-id="01c4c-143">硬件</span><span class="sxs-lookup"><span data-stu-id="01c4c-143">Hardware</span></span>

| <span data-ttu-id="01c4c-144">问题标题</span><span class="sxs-lookup"><span data-stu-id="01c4c-144">Issue title</span></span> |  <span data-ttu-id="01c4c-145">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="01c4c-145">Behavior \/ Symptom</span></span> | <span data-ttu-id="01c4c-146">已知解决方法</span><span class="sxs-lookup"><span data-stu-id="01c4c-146">Known workaround</span></span> | <span data-ttu-id="01c4c-147">知识库文章</span><span class="sxs-lookup"><span data-stu-id="01c4c-147">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="01c4c-148">未检测到监视器</span><span class="sxs-lookup"><span data-stu-id="01c4c-148">Monitors not detected</span></span> | <span data-ttu-id="01c4c-149">在 Surface Pro（2017 机型）设备上运行 Microsoft Teams 会议室时，检测不到监视器。</span><span class="sxs-lookup"><span data-stu-id="01c4c-149">When you run Microsoft Teams Rooms on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="01c4c-150">按住 Surface Pro 电源按钮 20 秒或更长时间。</span><span class="sxs-lookup"><span data-stu-id="01c4c-150">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="01c4c-151">执行此操作时，设备将重启并清除图形缓存。</span><span class="sxs-lookup"><span data-stu-id="01c4c-151">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="01c4c-152">KB4055681</span><span class="sxs-lookup"><span data-stu-id="01c4c-152">KB4055681</span></span>](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<span data-ttu-id="01c4c-153"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="01c4c-153"><a name="Limits"> </a></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="01c4c-154">限制和预期行为</span><span class="sxs-lookup"><span data-stu-id="01c4c-154">Limitations and expected behaviors</span></span>

***

<span data-ttu-id="01c4c-155">Microsoft Teams 会议室不支持 HDCP 输入，已发现它会导致 HDMI 采集功能（视频、音频）出现问题。</span><span class="sxs-lookup"><span data-stu-id="01c4c-155">Microsoft Teams Rooms does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="01c4c-156">请确保连接到 Microsoft Teams 会议室的交换机禁用了 HDCP 选项。</span><span class="sxs-lookup"><span data-stu-id="01c4c-156">Take care to ensure that switches connected to Microsoft Teams Rooms have HDCP options turned off.</span></span> 

***

<span data-ttu-id="01c4c-157">如果你希望在从待机模式唤醒源时自动切换到活动视频源（如 MTR 控制台），则必须满足某些条件。</span><span class="sxs-lookup"><span data-stu-id="01c4c-157">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="01c4c-158">此功能是可选的，但 Microsoft 团队工作室软件支持此功能，但提供的基础硬件支持此功能。</span><span class="sxs-lookup"><span data-stu-id="01c4c-158">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="01c4c-159">在室内显示时使用的消费者电视需要支持 HDMI 的 "消费者电子设备控制" （CEC）功能。</span><span class="sxs-lookup"><span data-stu-id="01c4c-159">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="01c4c-160">根据所选的坞站或控制台（可能不支持 CEC，请参阅制造商支持文档），可能需要[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad)之类的工作区控制器来启用所需的行为。</span><span class="sxs-lookup"><span data-stu-id="01c4c-160">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a workspace controller such as an [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) may be needed to enable the desired behavior.</span></span> 

***

<span data-ttu-id="01c4c-161">始终使用有线1至 Gbps 网络连接，确保您有所需的带宽。</span><span class="sxs-lookup"><span data-stu-id="01c4c-161">Always use a wired 1-Gbps network connection to assure you have the needed bandwidth.</span></span> 

***

<span data-ttu-id="01c4c-162">如果你的 Microsoft 团队聊天室设备失去了与域的信任，你将无法在设备上进行身份验证并打开 "设置"。</span><span class="sxs-lookup"><span data-stu-id="01c4c-162">If your Microsoft Teams Rooms device loses trust with the domain, you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="01c4c-163">例如，如果在域加入域后从域中删除 Microsoft 团队聊天室，则信任将丢失。</span><span class="sxs-lookup"><span data-stu-id="01c4c-163">For example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined, trust is lost.</span></span> <span data-ttu-id="01c4c-164">解决方法是使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="01c4c-164">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="01c4c-165">Microsoft 团队会议室是一个多窗口应用程序，需要将房间内的正面显示连接到设备的 HDMI 端口，才能使应用正常运行。</span><span class="sxs-lookup"><span data-stu-id="01c4c-165">Microsoft Teams Rooms is a multi-window application and requires a front of room display to be connected to the HDMI port of the device, for the app to function correctly.</span></span> <span data-ttu-id="01c4c-166">请确保你已连接 HDMI 显示器，或者使用虚拟 HDMI 插头（如果你正在测试，并且尚未购买显示器）。</span><span class="sxs-lookup"><span data-stu-id="01c4c-166">Make sure that you either have an HDMI display connected or use a dummy HDMI plug if you are testing and do not have a display purchased yet.</span></span>
***
<span data-ttu-id="01c4c-167"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="01c4c-167"><a name="See"> </a></span></span>  
## <a name="see-also"></a><span data-ttu-id="01c4c-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01c4c-168">See also</span></span>

[<span data-ttu-id="01c4c-169">Microsoft Teams 会议室帮助</span><span class="sxs-lookup"><span data-stu-id="01c4c-169">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="01c4c-170">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="01c4c-170">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
