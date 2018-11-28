---
title: 规划用户体验的 Microsoft 团队
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择团队客户端应用程序，规划终结点质量，获取有关部署 Wi-fi 终结点和选择音频设备的建议。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a44af03e694937c5e874f6d53c0795a0c61dd606
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716364"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="fbe97-103">规划我的用户体验</span><span class="sxs-lookup"><span data-stu-id="fbe97-103">Plan my users’ experience</span></span>

<span data-ttu-id="fbe97-104">本文概述了正确标识直接影响用户体验的元素的云语音服务部署的要求。</span><span class="sxs-lookup"><span data-stu-id="fbe97-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="fbe97-105">为这些项目在部署之前做好准备，可以将增加成功提供高质量、 可靠地为用户体验的可能性。</span><span class="sxs-lookup"><span data-stu-id="fbe97-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="fbe97-106">客户端部署</span><span class="sxs-lookup"><span data-stu-id="fbe97-106">Client deployment</span></span>

<span data-ttu-id="fbe97-107">Microsoft 团队具有客户端适用于网站，桌面 （Windows 和 Mac） 和移动设备 （Android 和 iOS）。</span><span class="sxs-lookup"><span data-stu-id="fbe97-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="fbe97-108">有关如何安装 （Windows 和 Mac） 的桌面和移动客户端的其他详细信息，请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="fbe97-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="client-updates"></a><span data-ttu-id="fbe97-109">客户端更新</span><span class="sxs-lookup"><span data-stu-id="fbe97-109">Client updates</span></span>

<span data-ttu-id="fbe97-110">一个团队的主要优点是，客户端保持最新自动。</span><span class="sxs-lookup"><span data-stu-id="fbe97-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="fbe97-111">PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。</span><span class="sxs-lookup"><span data-stu-id="fbe97-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="fbe97-112">规划终结点质量</span><span class="sxs-lookup"><span data-stu-id="fbe97-112">Plan for endpoint quality</span></span>

<span data-ttu-id="fbe97-113">下图从中可以看出，如终结点是中为用户提供用户体验质量重要构建基块。</span><span class="sxs-lookup"><span data-stu-id="fbe97-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="fbe97-114">![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。](media/plan-my-users-experience-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。")</span><span class="sxs-lookup"><span data-stu-id="fbe97-114">![Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="fbe97-115">团队终结点可以在多个设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="fbe97-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="fbe97-116">体验的一部分而不是只包括该设备，但用户如何连接到设备 — 例如，使用设备的内置的麦克风扬声器、 耳机或优化的耳麦。</span><span class="sxs-lookup"><span data-stu-id="fbe97-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="fbe97-117">使用优化耳机可以丰富整体用户体验。</span><span class="sxs-lookup"><span data-stu-id="fbe97-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="fbe97-118">以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。</span><span class="sxs-lookup"><span data-stu-id="fbe97-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="fbe97-119">终结点功能</span><span class="sxs-lookup"><span data-stu-id="fbe97-119">Endpoint capability</span></span>

<span data-ttu-id="fbe97-120">规划的第一部分是确保所有 Pc 和您的组织中的其他设备可以运行团队。</span><span class="sxs-lookup"><span data-stu-id="fbe97-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="fbe97-121">这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="fbe97-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="fbe97-122">许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。</span><span class="sxs-lookup"><span data-stu-id="fbe97-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="fbe97-123">有关团队的软件要求的信息 （web、 桌面和移动），每个平台上的客户端请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="fbe97-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="fbe97-124">终结点防火墙</span><span class="sxs-lookup"><span data-stu-id="fbe97-124">Endpoint firewalls</span></span>

<span data-ttu-id="fbe97-125">客户端防火墙会对用户体验产生很大影响。</span><span class="sxs-lookup"><span data-stu-id="fbe97-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="fbe97-126">客户端防火墙会影响通话质量，以及阻止建立通话。</span><span class="sxs-lookup"><span data-stu-id="fbe97-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="fbe97-127">应根据 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)中的信息在客户端防火墙上配置适当的排除项。</span><span class="sxs-lookup"><span data-stu-id="fbe97-127">Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span> <span data-ttu-id="fbe97-128">你的第三方供应商会提供有关如何创建排除项的具体指导。</span><span class="sxs-lookup"><span data-stu-id="fbe97-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="fbe97-129">Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="fbe97-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="fbe97-130">针对终结点的 Wi-Fi 建议</span><span class="sxs-lookup"><span data-stu-id="fbe97-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="fbe97-131">计重要规划部署优化的 Wi-fi 网络支持的 Microsoft 团队中的实时工作负荷。</span><span class="sxs-lookup"><span data-stu-id="fbe97-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="fbe97-132">以下各节提供了一些可帮助您规划终结点时应避免常见错误的一般指导。</span><span class="sxs-lookup"><span data-stu-id="fbe97-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="fbe97-133">Wi-Fi 驱动程序</span><span class="sxs-lookup"><span data-stu-id="fbe97-133">Wi-Fi drivers</span></span>

<span data-ttu-id="fbe97-134">某些 Wi-fi 驱动程序可能会产生问题。</span><span class="sxs-lookup"><span data-stu-id="fbe97-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="fbe97-135">例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。</span><span class="sxs-lookup"><span data-stu-id="fbe97-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="fbe97-136">这不是很常见，但务必确保已更新和部署之前测试 PC 上的 Wi-fi 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="fbe97-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="fbe97-137">Wi-Fi 频带</span><span class="sxs-lookup"><span data-stu-id="fbe97-137">Wi-Fi bands</span></span>

<span data-ttu-id="fbe97-138">当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。</span><span class="sxs-lookup"><span data-stu-id="fbe97-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="fbe97-139">如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。</span><span class="sxs-lookup"><span data-stu-id="fbe97-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="fbe97-140">在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。</span><span class="sxs-lookup"><span data-stu-id="fbe97-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="fbe97-141">此建议的前提是你已正确优化 5.0 GHz 网络频带。</span><span class="sxs-lookup"><span data-stu-id="fbe97-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="fbe97-142">Wi-Fi 无线电类型</span><span class="sxs-lookup"><span data-stu-id="fbe97-142">Wi-Fi radio type</span></span>

<span data-ttu-id="fbe97-143">规划支持较新 Wi-Fi 无线电类型的设备</span><span class="sxs-lookup"><span data-stu-id="fbe97-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="fbe97-144">如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。</span><span class="sxs-lookup"><span data-stu-id="fbe97-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="fbe97-145">避免使用无线</span><span class="sxs-lookup"><span data-stu-id="fbe97-145">Wireless avoidance</span></span>

<span data-ttu-id="fbe97-146">一些组织倾向于完全避免使用 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="fbe97-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="fbe97-147">有时，此指导以建议用户直接连接有线网络来体现。</span><span class="sxs-lookup"><span data-stu-id="fbe97-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="fbe97-148">在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。</span><span class="sxs-lookup"><span data-stu-id="fbe97-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="fbe97-149">为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。</span><span class="sxs-lookup"><span data-stu-id="fbe97-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="fbe97-150">802.11 节能协议</span><span class="sxs-lookup"><span data-stu-id="fbe97-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="fbe97-151">如果您的组织使用无线访问点或不支持的 802.11 节能协议的路由器，您可能会遇到丢弃的呼叫或质量欠佳的呼叫质量在 Windows 设备上运行的 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="fbe97-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="fbe97-152">如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。</span><span class="sxs-lookup"><span data-stu-id="fbe97-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="fbe97-153">以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。</span><span class="sxs-lookup"><span data-stu-id="fbe97-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="fbe97-154">决策点</span><span class="sxs-lookup"><span data-stu-id="fbe97-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="fbe97-155">将您的组织中部署哪些团队客户端？</span><span class="sxs-lookup"><span data-stu-id="fbe97-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="fbe97-156">如何将您最初部署团队客户端到您的用户？</span><span class="sxs-lookup"><span data-stu-id="fbe97-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="fbe97-157">它们由谁来负责评估终结点和设备，以验证符合团队要求用户体验质量？</span><span class="sxs-lookup"><span data-stu-id="fbe97-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="fbe97-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fbe97-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="fbe97-159">记录将先部署团队客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="fbe97-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="fbe97-160">评估终结点和设备，并执行和所需的补救措施。</span><span class="sxs-lookup"><span data-stu-id="fbe97-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="fbe97-161">支持 Teams 的设备</span><span class="sxs-lookup"><span data-stu-id="fbe97-161">Devices for Teams</span></span>

<span data-ttu-id="fbe97-162">Microsoft Teams 可以用于会议或用作电话系统。</span><span class="sxs-lookup"><span data-stu-id="fbe97-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="fbe97-163">在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。</span><span class="sxs-lookup"><span data-stu-id="fbe97-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="fbe97-164">使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。</span><span class="sxs-lookup"><span data-stu-id="fbe97-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="fbe97-165">通常情况下，这些设备不适合干扰取消，但任何类型的环境的噪音上可能具有下游影响其他人在调用。</span><span class="sxs-lookup"><span data-stu-id="fbe97-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="fbe97-166">利用针对这些情况优化的设备有助于确保获得高质量体验。</span><span class="sxs-lookup"><span data-stu-id="fbe97-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="fbe97-167">每个设备都需要满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="fbe97-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="fbe97-168">你需要为你组织中的不同角色和用例定制设备（例如耳机）。</span><span class="sxs-lookup"><span data-stu-id="fbe97-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="fbe97-169">应在规划流程中完成角色-设备映射操作。</span><span class="sxs-lookup"><span data-stu-id="fbe97-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="fbe97-170">选择了设备后，将其包含在试点测试计划中以便进行最终验证。</span><span class="sxs-lookup"><span data-stu-id="fbe97-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="fbe97-171">应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。</span><span class="sxs-lookup"><span data-stu-id="fbe97-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="fbe97-172">目前，建议使用通过 Skype for Business 认证计划认证的音频设备。</span><span class="sxs-lookup"><span data-stu-id="fbe97-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="fbe97-173">若要查找此计划认证的设备，请参阅[USB 设备认证可用于 for Business 的 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。</span><span class="sxs-lookup"><span data-stu-id="fbe97-173">To find devices certified under this program, see the [USB Devices Certified for Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) solutions catalog.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="fbe97-174">决策点</span><span class="sxs-lookup"><span data-stu-id="fbe97-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="fbe97-175">确定用户和会议室内体验的组织的总体设备策略。</span><span class="sxs-lookup"><span data-stu-id="fbe97-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="fbe97-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fbe97-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="fbe97-177">完成您的组织个人到设备映射练习。</span><span class="sxs-lookup"><span data-stu-id="fbe97-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="fbe97-178">文档获取用户的设备和会议室的过程。</span><span class="sxs-lookup"><span data-stu-id="fbe97-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="fbe97-179">文档的用户和会议室的部署和配置设备的过程。</span><span class="sxs-lookup"><span data-stu-id="fbe97-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="fbe97-180">获取初始设备开始部署。</span><span class="sxs-lookup"><span data-stu-id="fbe97-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->