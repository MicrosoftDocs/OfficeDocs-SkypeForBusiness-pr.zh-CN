---
title: 规划用户的 Microsoft Teams 体验
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择 "团队客户端应用", 规划终结点质量, 获取有关部署 Wi-fi 终结点和选择音频设备的建议。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c7bf332c3d85445ccb9bcfe41e6d7417948ca15
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344606"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="1aad3-103">规划我的用户体验</span><span class="sxs-lookup"><span data-stu-id="1aad3-103">Plan my users’ experience</span></span>

<span data-ttu-id="1aad3-104">本文概述了正确识别云语音服务部署中直接影响用户体验的元素的要求。</span><span class="sxs-lookup"><span data-stu-id="1aad3-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="1aad3-105">通过在部署之前准备这些项目, 你将提高为用户成功提供优质、可靠体验的机会。</span><span class="sxs-lookup"><span data-stu-id="1aad3-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="1aad3-106">客户端部署</span><span class="sxs-lookup"><span data-stu-id="1aad3-106">Client deployment</span></span>

<span data-ttu-id="1aad3-107">Microsoft 团队拥有适用于 web、桌面 (Windows 和 Mac) 和移动设备 (Android 和 iOS) 的客户端。</span><span class="sxs-lookup"><span data-stu-id="1aad3-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="1aad3-108">有关如何安装桌面 (Windows 和 Mac) 和移动客户端的其他详细信息, 请参阅[获取 Microsoft 团队客户端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="1aad3-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="client-updates"></a><span data-ttu-id="1aad3-109">客户端更新</span><span class="sxs-lookup"><span data-stu-id="1aad3-109">Client updates</span></span>

<span data-ttu-id="1aad3-110">团队的一个主要好处是客户自动保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="1aad3-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="1aad3-111">PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。</span><span class="sxs-lookup"><span data-stu-id="1aad3-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="1aad3-112">规划终结点质量</span><span class="sxs-lookup"><span data-stu-id="1aad3-112">Plan for endpoint quality</span></span>

<span data-ttu-id="1aad3-113">正如您可以从下图中看到的, 终结点是为用户提供质量体验的重要构建基块。</span><span class="sxs-lookup"><span data-stu-id="1aad3-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="1aad3-114">![描述三个质量组件以及服务管理如何与所有三个组件重叠的图表](media/plan-my-users-experience-image1.png "描述三种质量组件以及服务管理如何与所有三个组件重叠的图表。重点关注终结点。")</span><span class="sxs-lookup"><span data-stu-id="1aad3-114">![Diagram describing the three components of quality, and how service management overlaps all three components](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="1aad3-115">团队终结点可以在许多设备上运行, 包括电脑、Mac、平板电脑和移动设备。</span><span class="sxs-lookup"><span data-stu-id="1aad3-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="1aad3-116">部分体验不仅包括设备, 还包括用户如何连接到设备-例如, 使用设备的内置麦克风/扬声器、earbuds 或优化的耳机。</span><span class="sxs-lookup"><span data-stu-id="1aad3-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="1aad3-117">使用优化耳机可以丰富整体用户体验。</span><span class="sxs-lookup"><span data-stu-id="1aad3-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="1aad3-118">以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。</span><span class="sxs-lookup"><span data-stu-id="1aad3-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="1aad3-119">终结点功能</span><span class="sxs-lookup"><span data-stu-id="1aad3-119">Endpoint capability</span></span>

<span data-ttu-id="1aad3-120">规划的第一部分是确保组织中的所有 Pc 和其他设备都可以运行团队。</span><span class="sxs-lookup"><span data-stu-id="1aad3-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="1aad3-121">这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="1aad3-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="1aad3-122">许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。</span><span class="sxs-lookup"><span data-stu-id="1aad3-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="1aad3-123">有关每个平台 (web、桌面和移动版) 上的团队客户端的软件要求的信息, 请参阅[获取 Microsoft 团队客户端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="1aad3-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="1aad3-124">终结点防火墙</span><span class="sxs-lookup"><span data-stu-id="1aad3-124">Endpoint firewalls</span></span>

<span data-ttu-id="1aad3-125">客户端防火墙会对用户体验产生很大影响。</span><span class="sxs-lookup"><span data-stu-id="1aad3-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="1aad3-126">客户端防火墙会影响通话质量，以及阻止建立通话。</span><span class="sxs-lookup"><span data-stu-id="1aad3-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="1aad3-127">应根据 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)中的信息在客户端防火墙上配置适当的排除项。</span><span class="sxs-lookup"><span data-stu-id="1aad3-127">Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span> <span data-ttu-id="1aad3-128">你的第三方供应商会提供有关如何创建排除项的具体指导。</span><span class="sxs-lookup"><span data-stu-id="1aad3-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="1aad3-129">Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="1aad3-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="1aad3-130">针对终结点的 Wi-Fi 建议</span><span class="sxs-lookup"><span data-stu-id="1aad3-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="1aad3-131">部署已优化的 Wlan 网络以支持 Microsoft 团队中的实时工作负载, 这一计划需要进行重大计划。</span><span class="sxs-lookup"><span data-stu-id="1aad3-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="1aad3-132">以下各部分提供了一些常规指南, 可帮助你避免在规划终结点时遇到常见的缺陷。</span><span class="sxs-lookup"><span data-stu-id="1aad3-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="1aad3-133">Wi-Fi 驱动程序</span><span class="sxs-lookup"><span data-stu-id="1aad3-133">Wi-Fi drivers</span></span>

<span data-ttu-id="1aad3-134">某些 Wi-fi 驱动程序可能会有问题。</span><span class="sxs-lookup"><span data-stu-id="1aad3-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="1aad3-135">例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。</span><span class="sxs-lookup"><span data-stu-id="1aad3-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="1aad3-136">这不是一种常见情况, 但确保电脑上的 Wi-fi 驱动程序在部署之前已更新和测试非常重要。</span><span class="sxs-lookup"><span data-stu-id="1aad3-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="1aad3-137">Wi-Fi 频带</span><span class="sxs-lookup"><span data-stu-id="1aad3-137">Wi-Fi bands</span></span>

<span data-ttu-id="1aad3-138">当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。</span><span class="sxs-lookup"><span data-stu-id="1aad3-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="1aad3-139">如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。</span><span class="sxs-lookup"><span data-stu-id="1aad3-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="1aad3-140">在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。</span><span class="sxs-lookup"><span data-stu-id="1aad3-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="1aad3-141">此建议的前提是你已正确优化 5.0 GHz 网络频带。</span><span class="sxs-lookup"><span data-stu-id="1aad3-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="1aad3-142">Wi-Fi 无线电类型</span><span class="sxs-lookup"><span data-stu-id="1aad3-142">Wi-Fi radio type</span></span>

<span data-ttu-id="1aad3-143">规划支持较新 Wi-Fi 无线电类型的设备</span><span class="sxs-lookup"><span data-stu-id="1aad3-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="1aad3-144">如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。</span><span class="sxs-lookup"><span data-stu-id="1aad3-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="1aad3-145">避免使用无线</span><span class="sxs-lookup"><span data-stu-id="1aad3-145">Wireless avoidance</span></span>

<span data-ttu-id="1aad3-146">一些组织倾向于完全避免使用 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="1aad3-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="1aad3-147">有时，此指导以建议用户直接连接有线网络来体现。</span><span class="sxs-lookup"><span data-stu-id="1aad3-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="1aad3-148">在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。</span><span class="sxs-lookup"><span data-stu-id="1aad3-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="1aad3-149">为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。</span><span class="sxs-lookup"><span data-stu-id="1aad3-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="1aad3-150">802.11 节能协议</span><span class="sxs-lookup"><span data-stu-id="1aad3-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="1aad3-151">如果您的组织使用不支持802.11 节能协议的无线访问点或路由器, 则在 Windows 设备上运行的 Microsoft 团队中, 可能会遇到呼叫中断或不好的通话质量。</span><span class="sxs-lookup"><span data-stu-id="1aad3-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="1aad3-152">如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。</span><span class="sxs-lookup"><span data-stu-id="1aad3-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="1aad3-153">以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。</span><span class="sxs-lookup"><span data-stu-id="1aad3-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="1aad3-154">决策点</span><span class="sxs-lookup"><span data-stu-id="1aad3-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="1aad3-155">将在您的组织中部署哪些团队客户？</span><span class="sxs-lookup"><span data-stu-id="1aad3-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="1aad3-156">如何开始将团队客户端部署到你的用户？</span><span class="sxs-lookup"><span data-stu-id="1aad3-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="1aad3-157">谁负责评估终结点和设备以验证它们是否满足优质体验的团队要求？</span><span class="sxs-lookup"><span data-stu-id="1aad3-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="1aad3-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1aad3-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="1aad3-159">记录部署团队客户端所遵循的流程。</span><span class="sxs-lookup"><span data-stu-id="1aad3-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="1aad3-160">评估终结点和设备, 并执行所需的执行和更正。</span><span class="sxs-lookup"><span data-stu-id="1aad3-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="1aad3-161">支持 Teams 的设备</span><span class="sxs-lookup"><span data-stu-id="1aad3-161">Devices for Teams</span></span>

<span data-ttu-id="1aad3-162">Microsoft Teams 可以用于会议或用作电话系统。</span><span class="sxs-lookup"><span data-stu-id="1aad3-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="1aad3-163">在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。</span><span class="sxs-lookup"><span data-stu-id="1aad3-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="1aad3-164">使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。</span><span class="sxs-lookup"><span data-stu-id="1aad3-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="1aad3-165">但通常情况下, 这些设备不会针对噪声取消进行优化, 并且任何类型的环境噪音都可能会对其他人在通话中产生下游影响。</span><span class="sxs-lookup"><span data-stu-id="1aad3-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="1aad3-166">利用针对这些情况优化的设备有助于确保获得高质量体验。</span><span class="sxs-lookup"><span data-stu-id="1aad3-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="1aad3-167">每个设备都需要满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="1aad3-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="1aad3-168">你需要为你组织中的不同角色和用例定制设备（例如耳机）。</span><span class="sxs-lookup"><span data-stu-id="1aad3-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="1aad3-169">应在规划流程中完成角色-设备映射操作。</span><span class="sxs-lookup"><span data-stu-id="1aad3-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="1aad3-170">选择了设备后，将其包含在试点测试计划中以便进行最终验证。</span><span class="sxs-lookup"><span data-stu-id="1aad3-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="1aad3-171">应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。</span><span class="sxs-lookup"><span data-stu-id="1aad3-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="1aad3-172">目前，建议使用通过 Skype for Business 认证计划认证的音频设备。</span><span class="sxs-lookup"><span data-stu-id="1aad3-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="1aad3-173">若要查找此程序下认证的设备, 请参阅[经认证的适用于 Skype for](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) business 解决方案目录的 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="1aad3-173">To find devices certified under this program, see the [USB Devices Certified for Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) solutions catalog.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="1aad3-174">决策点</span><span class="sxs-lookup"><span data-stu-id="1aad3-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="1aad3-175">确定你的组织的整体设备策略以了解用户和会议室体验。</span><span class="sxs-lookup"><span data-stu-id="1aad3-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="1aad3-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1aad3-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="1aad3-177">为你的组织完成一个角色到设备的映射练习。</span><span class="sxs-lookup"><span data-stu-id="1aad3-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="1aad3-178">记录为用户和会议室获取设备的流程。</span><span class="sxs-lookup"><span data-stu-id="1aad3-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="1aad3-179">记录为用户和会议室部署和配置设备的流程。</span><span class="sxs-lookup"><span data-stu-id="1aad3-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="1aad3-180">购买初始设备以开始部署。</span><span class="sxs-lookup"><span data-stu-id="1aad3-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->