---
title: 规划 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: 本文介绍部署 Skype 会议室系统 v2 下, 一代 Skype 会议室系统相关的规划的注意事项。
ms.openlocfilehash: 7b36e9bc9c85a57b81be542f09d65c357f6020c0
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="plan-for-skype-room-systems-v2"></a><span data-ttu-id="1ee0f-103">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="1ee0f-103">Plan for Skype Room Systems v2</span></span>
 
<span data-ttu-id="1ee0f-104">本文介绍部署 Skype 会议室系统 v2 下, 一代 Skype 会议室系统相关的规划的注意事项。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-104">This article explains the relevant planning considerations for deploying Skype Room Systems v2, the next generation of Skype Room Systems.</span></span> 
  
 <span data-ttu-id="1ee0f-105">Skype 会议室系统 v2 是 Microsoft 的最新设计用来转换为业务体验丰富的、 协作 Skype 您会议室的会议解决方案。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="1ee0f-106">用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="1ee0f-107">Skype 会议室系统 v2 旨在利用现有的设备，如 LCD 面板为了简化安装将 Skype for Business 导入您的会议室。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="1ee0f-108">Skype 会议室系统 v2 使用充当 Skype 会议用户界面的专门 UWP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-108">Skype Room Systems v2 uses a purpose-built UWP app which acts as the Skype Meeting user interface.</span></span> <span data-ttu-id="1ee0f-109">在控制台模式 Surface Pro 4 或 Surface Pro 上运行 （部署 UWP 应用程序之后是将在设备运行的唯一应用程序） 和业务实现需要在您 Skype 自己设备帐户。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-109">It runs on a Surface Pro 4 or Surface Pro in a console mode (once deployed the UWP app is the only app that will run on the device) and it requires its own device account on your Skype for Business implementation.</span></span> <span data-ttu-id="1ee0f-110">它利用液晶显示屏以及相对便宜的外围摄像头和麦克风等现有设备来提供高品质的会议室体验。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-110">It leverages existing equipment like LCD panels and relatively inexpensive peripheral cameras and microphones to provide a quality meeting room experience.</span></span> <span data-ttu-id="1ee0f-111">软件通过 Windows 应用商店和 Windows 更新来更新。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-111">Software is updated via both Windows store and Windows Update.</span></span>
  
<span data-ttu-id="1ee0f-112">准备您的环境之前，确保您具有必需的硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-112">Before you begin preparing your environment, be sure you have the necessary hardware and software.</span></span> <span data-ttu-id="1ee0f-113">有关详细信息，请参阅[Skype 会议室系统 v2 要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-113">For more information, see [Skype Room Systems v2 requirements](requirements.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ee0f-114">Skype 会议室系统 v2 旨在用于与 Skype 业务服务器 2015年或 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-114">Skype Room Systems v2 is intended for use with Skype for Business Server 2015 or Skype for Business Online.</span></span> <span data-ttu-id="1ee0f-115">早期平台，如 Lync Server 2013 不会使用 Skype 会议室系统 v2。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-115">Earlier platforms like Lync Server 2013 are not expected to work with Skype Room Systems v2.</span></span> 
  

  
 <span data-ttu-id="1ee0f-116">**为 Skype for Business 而构建**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-116">**Built for Skype for Business**</span></span>
  
- <span data-ttu-id="1ee0f-117">一键式加入 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="1ee0f-117">One-touch join of Skype Meetings</span></span>
    
- <span data-ttu-id="1ee0f-118">为配有满屏高清视频和高清宽带音频的会议室优化的 Skype 会议体验</span><span class="sxs-lookup"><span data-stu-id="1ee0f-118">Skype Meeting experience optimized for rooms with screen-filling HD video and HD wideband audio</span></span>
    
- <span data-ttu-id="1ee0f-119">所有参与者均可使用所选设备从任意位置连接到 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="1ee0f-119">All participants can connect to the Skype Meeting using their device of choice from wherever they may be located</span></span>
    
- <span data-ttu-id="1ee0f-120">从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-120">Invite people from your directory where you can instantly see their availability or via a phone call</span></span>
    
- <span data-ttu-id="1ee0f-121">支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话</span><span class="sxs-lookup"><span data-stu-id="1ee0f-121">Supports Skype for Business PSTN Conferencing and PSTN Calling to replace the stand-alone conference phone in your room</span></span>
    
 <span data-ttu-id="1ee0f-122">**转换任何会议室**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-122">**Transform Any Meeting Room**</span></span>
  
- <span data-ttu-id="1ee0f-123">专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化</span><span class="sxs-lookup"><span data-stu-id="1ee0f-123">Dedicated Skype Meeting app optimized for center of table touch controller and large front of room display</span></span>
    
- <span data-ttu-id="1ee0f-124">重用会议室显示屏和投影仪的现有投资</span><span class="sxs-lookup"><span data-stu-id="1ee0f-124">Re-use existing investments in your front of room display or projectors</span></span>
    
- <span data-ttu-id="1ee0f-125">适用于各种类型的会议室，从小型到大型会议室</span><span class="sxs-lookup"><span data-stu-id="1ee0f-125">Works in all types of meeting spaces from huddle spaces to large conference rooms</span></span>
    
- <span data-ttu-id="1ee0f-126">经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室</span><span class="sxs-lookup"><span data-stu-id="1ee0f-126">Certified Skype for Business audio and video devices are available for various room sizes</span></span>
    
- <span data-ttu-id="1ee0f-127">内置的有线采集可用于将桌面共享投影到会议室和 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="1ee0f-127">Built-in wired ingest for to project desktop sharing to the room and to the Skype Meeting</span></span>
    
- <span data-ttu-id="1ee0f-128">在应用程序用户选择会议的会议室音频和视频 USB 设备和 #x 2776;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-128">In-app user selection of meeting room audio and video USB devices &#x2776;</span></span>
    
- <span data-ttu-id="1ee0f-129">（对于旧系统奇偶校验） 的双屏幕支持与 #x 2777;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-129">Dual-Screen support (for legacy system parity) &#x2777;</span></span>
    
- <span data-ttu-id="1ee0f-130">Themability （内置主题和能够设置自定义主题） 和 #x 2777;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-130">Themability (built-in themes and the ability to set custom theme) &#x2777;</span></span>
    
 <span data-ttu-id="1ee0f-131">**易于部署、便于管理**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-131">**Easy to Deploy, Simple to Manage**</span></span>
  
- <span data-ttu-id="1ee0f-132">常开式设备会在检测到会议室中有人时自动唤醒显示屏</span><span class="sxs-lookup"><span data-stu-id="1ee0f-132">Always-on appliance that will automatically wake up the displays when it detects people in the room</span></span>
    
- <span data-ttu-id="1ee0f-133">UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单</span><span class="sxs-lookup"><span data-stu-id="1ee0f-133">Simple deployment and updating of the UWP (Universal Windows Platform) Skype Meeting App</span></span>
    
- <span data-ttu-id="1ee0f-134">Windows AppLocker 可将设备锁定至 Skype 会议应用</span><span class="sxs-lookup"><span data-stu-id="1ee0f-134">Windows AppLocker locks down the device to the Skype Meeting app</span></span>
    
- <span data-ttu-id="1ee0f-135">通过 Intune 和 SCCM (MDM) 作为 Windows 10 企业版设备来监控和管理</span><span class="sxs-lookup"><span data-stu-id="1ee0f-135">Monitored and managed as a Windows 10 Enterprise device via Intune and SCCM (MDM)</span></span>
    
- <span data-ttu-id="1ee0f-136">企业级可靠性</span><span class="sxs-lookup"><span data-stu-id="1ee0f-136">Enterprise-grade reliability</span></span>
    
- <span data-ttu-id="1ee0f-137">由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训</span><span class="sxs-lookup"><span data-stu-id="1ee0f-137">Low training effort of end-users due to familiar Skype user interface</span></span>
    
- <span data-ttu-id="1ee0f-138">在 Surface Pro 4 平板电脑上运行</span><span class="sxs-lookup"><span data-stu-id="1ee0f-138">Runs on Surface Pro 4 tablet</span></span>
    
- <span data-ttu-id="1ee0f-139">集成会议室控制台状态报告的客户使用 Microsoft 操作管理套件 （请参阅[规划 Skype 会议室系统 v2 管理与 OMS](oms-management.md)） & #x 2776;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-139">Integrated room console status reporting for customers using Microsoft Operations Management Suite (see [Plan Skype Room Systems v2 management with OMS](oms-management.md)) &#x2776;</span></span>
    
- <span data-ttu-id="1ee0f-140">为公共生成 #x 2777; 能够提供反馈</span><span class="sxs-lookup"><span data-stu-id="1ee0f-140">Ability to Give Feedback for public builds &#x2777;</span></span>
    
- <span data-ttu-id="1ee0f-141">改进了的遥测周围会议加入可靠性和 #x 2777;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-141">Improved Telemetry around meeting join reliability &#x2777;</span></span>
    
- <span data-ttu-id="1ee0f-142">其他 OMS 报告与 #x 2777;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-142">Additional OMS reporting &#x2777;</span></span>
    
- <span data-ttu-id="1ee0f-143">面向 IT 管理员来远程配置设备和 #x 2777; 功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-143">Ability for IT Admin to configure devices remotely &#x2777;</span></span>
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- <span data-ttu-id="1ee0f-144">Surface Pro 平板电脑和 #x 2778; 上运行</span><span class="sxs-lookup"><span data-stu-id="1ee0f-144">Runs on Surface Pro tablet &#x2778;</span></span>
    
- <span data-ttu-id="1ee0f-145">支持 Windows 10 企业创建者 （英语、 生成 1703年） 的更新和 #x 2778;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-145">Supports Windows 10 Enterprise Creator's Update (English language, build 1703) &#x2778;</span></span>
    
- <span data-ttu-id="1ee0f-146">支持[Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)停靠硬件和 #x 2778;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-146">Support for [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) dock hardware &#x2778;</span></span>
    
- <span data-ttu-id="1ee0f-147">对环境控件 (Crestron) 和 #x 2778; OEM 支持</span><span class="sxs-lookup"><span data-stu-id="1ee0f-147">OEM Support for Environment Controls (Crestron) &#x2778;</span></span>
    
- <span data-ttu-id="1ee0f-148">[Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)系列支持停靠硬件和 #x 2779;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-148">Support for [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) dock hardware &#x2779;</span></span>
    
- <span data-ttu-id="1ee0f-149">对[Logitech Brio](https://www.logitech.com/en-us/product/brio)和 #x 2779; 支持</span><span class="sxs-lookup"><span data-stu-id="1ee0f-149">Support for the [Logitech Brio](https://www.logitech.com/en-us/product/brio) &#x2779;</span></span>

- <span data-ttu-id="1ee0f-150">支持[联想集线器 500](https://www3.lenovo.com/us/en/hub500)停靠硬件和 #x277A;</span><span class="sxs-lookup"><span data-stu-id="1ee0f-150">Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) dock hardware &#x277A;</span></span>  
    
<span data-ttu-id="1ee0f-151">& #x 2776;-在更新 1 （软件 ver.中引入的功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-151">&#x2776; - Feature introduced in Update 1 (SW Ver.</span></span> <span data-ttu-id="1ee0f-152">2.0.2.0)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-152">2.0.2.0).</span></span>
  
<span data-ttu-id="1ee0f-153">& #x 2777;-在更新 2 （软件 ver.中引入的功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-153">&#x2777; - Feature introduced in Update 2 (SW Ver.</span></span> <span data-ttu-id="1ee0f-154">3.0.6.0)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-154">3.0.6.0).</span></span> 
  
<span data-ttu-id="1ee0f-155">& #x 2778;-更新 3 （软件 ver.中引入的功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-155">&#x2778; - Feature introduced in Update 3 (SW Ver.</span></span> <span data-ttu-id="1ee0f-156">3.0.12.0)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-156">3.0.12.0).</span></span> 
  
<span data-ttu-id="1ee0f-157">& #x 2779;-更新 4 （软件 ver.中引入的功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-157">&#x2779; - Feature introduced in Update 4 (SW Ver.</span></span> <span data-ttu-id="1ee0f-158">3.0.15.0)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-158">3.0.15.0).</span></span> 

<span data-ttu-id="1ee0f-159">& #x277A;-更新 5 （软件 ver.中引入的功能</span><span class="sxs-lookup"><span data-stu-id="1ee0f-159">&#x277A; - Feature introduced in Update 5 (SW Ver.</span></span> <span data-ttu-id="1ee0f-160">3.1.98.0)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-160">3.1.98.0).</span></span> 
  
## <a name="preparing-your-skype-for-business-environment"></a><span data-ttu-id="1ee0f-161">准备 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="1ee0f-161">Preparing your Skype for Business Environment</span></span>

<span data-ttu-id="1ee0f-162">本节包含概述准备您的环境，以便您可以使用的所有的 Skype 会议室系统 v2 功能所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-162">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Skype Room Systems v2.</span></span>
  
1. <span data-ttu-id="1ee0f-163">为每个 Skype 会议室系统 v2 控制台准备设备帐户。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-163">Prepare a device account for each Skype Room Systems v2 console.</span></span> <span data-ttu-id="1ee0f-164">有关详细信息，请参阅[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-164">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
    
2. <span data-ttu-id="1ee0f-165">确保有运行良好的网络/Internet 连接可供设备使用。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-165">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
  - <span data-ttu-id="1ee0f-166">它必须能够接收 IP 地址使用 DHCP (注意： Skype 会议室系统 v2 不能配置静态 IP 地址在第一个单元启动时使用)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-166">It must be able to receive an IP address using DHCP (note: Skype Room Systems v2 cannot be configured with a static IP address at the first unit startup)</span></span>
    
  - <span data-ttu-id="1ee0f-167">除了打开用于 Skype for Business 媒体的常规端口之外，还必须打开以下端口：</span><span class="sxs-lookup"><span data-stu-id="1ee0f-167">It must have these ports open (in addition to opening the normal ports for Skype for Business media):</span></span>
    
  - <span data-ttu-id="1ee0f-168">HTTPS：443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-168">HTTPS: 443</span></span>
    
  - <span data-ttu-id="1ee0f-169">HTTP：80</span><span class="sxs-lookup"><span data-stu-id="1ee0f-169">HTTP: 80</span></span>
    
  - <span data-ttu-id="1ee0f-170">如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-170">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ee0f-171">V2 不支持 HDCP 输入，观察到与 HDMI 会导致问题的 Skype 会议室系统接收功能 （视频、 音频）。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-171">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="1ee0f-172">注意确保交换机连接到 Skype 会议室系统 v2 已关闭的 HDCP 选项。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-172">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
  
3. <span data-ttu-id="1ee0f-p112">为了改进你的体验，Microsoft 将收集数据。为了收集数据，我们需要将以下网站列入允许名单：</span><span class="sxs-lookup"><span data-stu-id="1ee0f-p112">In order to improve your experience, Microsoft collects data. To collect data, we need these sites whitelisted:</span></span>
    
  - <span data-ttu-id="1ee0f-175">遥测客户端终结点：https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="1ee0f-175">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
    
  - <span data-ttu-id="1ee0f-176">遥测设置终结点：https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="1ee0f-176">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="1ee0f-177">创建和测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-177">Create and test a device account</span></span>

<span data-ttu-id="1ee0f-178">*设备的帐户*是 Skype 会议室系统 v2 客户端使用 exchange，访问功能，如日历，以及启用 for Business 的 Skype 的帐户。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-178">A  *device account*  is an account that the Skype Room Systems v2 client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="1ee0f-179">有关详细信息，请参阅[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-179">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="1ee0f-180">检查网络可用性</span><span class="sxs-lookup"><span data-stu-id="1ee0f-180">Check network availability</span></span>

<span data-ttu-id="1ee0f-181">才能正常工作，Skype 会议室系统 v2 设备必须有权访问有线网络满足这些要求：</span><span class="sxs-lookup"><span data-stu-id="1ee0f-181">In order to function properly, the Skype Room Systems v2 device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="1ee0f-182">可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-182">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>
    
- <span data-ttu-id="1ee0f-183">可访问能够使用 DHCP 提供 IP 地址的服务器。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-183">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="1ee0f-184">Skype 会议室系统 v2 不能配置使用静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-184">Skype Room Systems v2 cannot be configured with a static IP address.</span></span>
    
- <span data-ttu-id="1ee0f-185">访问 HTTP 端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-185">Access to HTTP ports 80 and 443.</span></span>
    
- <span data-ttu-id="1ee0f-186">TCP 和 UDP 端口配置为内部 Skype 业务实施或[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)的 Skype 的业务联机实施的[Lync Server 2013 的端口要求](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-186">TCP and UDP ports configured as described in [Port requirements for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) for on premise Skype for Business implementations, or [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Skype for Business online implementations.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1ee0f-187">务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-187">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
  
### <a name="certificates"></a><span data-ttu-id="1ee0f-188">证书</span><span class="sxs-lookup"><span data-stu-id="1ee0f-188">Certificates</span></span>

<span data-ttu-id="1ee0f-189">Skype 会议室系统 v2 设备使用证书的 Exchange Web 服务、 Skype 业务、 网络使用情况和身份验证。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-189">Your Skype Room Systems v2 device uses certificates for Exchange Web Services, Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="1ee0f-190">如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-190">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="1ee0f-191">另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-191">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="1ee0f-192">将设备添加到域时，可以自动执行此任务。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-192">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="1ee0f-193">安装证书的方式与任何其他 Windows 客户端一样。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-193">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ee0f-194">让业务服务器使用 Skype 的 Skype 会议室系统 v2 可能需要证书。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-194">Certificates may be required in order to have Skype Room Systems v2 use Skype for Business Server.</span></span> 
  
### <a name="proxy"></a><span data-ttu-id="1ee0f-195">代理</span><span class="sxs-lookup"><span data-stu-id="1ee0f-195">Proxy</span></span>

<span data-ttu-id="1ee0f-196">Skype 会议室系统 v2 旨在继承 Windows 操作系统的代理设置。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-196">Skype Room Systems v2 is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="1ee0f-197">通过以下方式访问 Windows OS：</span><span class="sxs-lookup"><span data-stu-id="1ee0f-197">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="1ee0f-198">在 Skype 会议室系统 v2 UI 中，单击设置齿轮图标，其中将提示您 （默认密码为"sfb"） 的设备上的本地管理员密码。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-198">In the Skype Room Systems v2 UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is "sfb").</span></span>
    
2. <span data-ttu-id="1ee0f-199">点击"设置"上的"转到 Windows"按钮，然后点击上打开后跟上"获得管理员登录到中"按钮，然后单击"管理员"按钮 (如果计算机加入域选择"其他用户"，然后使用。 \admin 作为用户名)。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-199">Tap on "Settings" followed by tapping on the "Go to Windows" button and then tapping on the "got to Admin Sign In" button and then clicking the "Administrator" button (if the computer is domain joined choose "Other User," then use .\admin as the user name).</span></span>
    
3. <span data-ttu-id="1ee0f-200">在"搜索 Windows"框在注册表编辑器 （长按屏幕或右单击，然后选择"以管理员身份运行"） 中的底部左侧的类型。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-200">In the "Search Windows" box bottom left type in regedit (either long press the screen or right click and choose "Run as administrator").</span></span>
    
4. <span data-ttu-id="1ee0f-201">单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-201">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
    
    <span data-ttu-id="1ee0f-202">系统将提示您为您的新加载配置单元; 键名称键入的 Skype （您会看到 Skype 用户的注册表设置）。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-202">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
    
5. <span data-ttu-id="1ee0f-203">单击“文件”，然后选择“加载配置单元”。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-203">Click on File and then choose "Load Hive."</span></span>
    
6. <span data-ttu-id="1ee0f-204">浏览到文件夹“C:\Users\Skype”，在“文件名”框中键入 NTUSER.dat 并按“打开”按钮</span><span class="sxs-lookup"><span data-stu-id="1ee0f-204">Browse the to the following folder "C:\Users\Skype" and type in the File name box NTUSER.dat and press the open button</span></span>
    
7. <span data-ttu-id="1ee0f-205">打开 Skype 注册表项并浏览到 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 设置，然后确保输入这些设置：</span><span class="sxs-lookup"><span data-stu-id="1ee0f-205">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    <span data-ttu-id="1ee0f-206">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span><span class="sxs-lookup"><span data-stu-id="1ee0f-206">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span></span>
    
    <span data-ttu-id="1ee0f-207">"MigrateProxy"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="1ee0f-207">"MigrateProxy"=dword:00000001</span></span>
    
    <span data-ttu-id="1ee0f-208">"ProxyEnable"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="1ee0f-208">"ProxyEnable"=dword:00000001</span></span>
    
    <span data-ttu-id="1ee0f-209">"ProxyServer"="xx.xx.xx.xx:8080"</span><span class="sxs-lookup"><span data-stu-id="1ee0f-209">"ProxyServer"="xx.xx.xx.xx:8080"</span></span>
    
    <span data-ttu-id="1ee0f-210">如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-210">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
    
8. <span data-ttu-id="1ee0f-211">完成更改突出显示 Skype 用户主要 （根文件夹 Skype），并且选择卸载配置单元，从注册表文件菜单 （将提示您确认-选择**是**） 后。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-211">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes** ).</span></span>
    
9. <span data-ttu-id="1ee0f-212">现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-212">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
10. <span data-ttu-id="1ee0f-213">返回登录屏幕，选择 **Skype** 用户。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-213">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="1ee0f-214">如果上述所有步骤都是成功，Skype 会议室系统 v2 设备将登录成功。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-214">If all the previous steps were successful, the Skype Room Systems v2 device will sign-in successfully.</span></span>
    
<span data-ttu-id="1ee0f-p118">要使用此应用程序，你必须能够连接至下面所述的终结点。要查看 IP 地址，请展开描述通信流的表下面的 IP 地址部分。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-p118">To use this application, you must be able to connect to the endpoints described below. To see the IP addresses, expand the IP address section below the table describing the traffic flow.</span></span>
  
<span data-ttu-id="1ee0f-217">**防火墙代理主机名称/端口示例**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-217">**Firewall Proxy Host Name/Port Examples**</span></span>

|<span data-ttu-id="1ee0f-218">**用途**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-218">**Purpose**</span></span>|<span data-ttu-id="1ee0f-219">**源或凭据**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-219">**Source or Credentials**</span></span>|<span data-ttu-id="1ee0f-220">**源端口**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-220">**Source Port**</span></span>|<span data-ttu-id="1ee0f-221">**目标**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-221">**Destination**</span></span>|<span data-ttu-id="1ee0f-222">**CDN**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-222">**CDN**</span></span>|<span data-ttu-id="1ee0f-223">**Office 365 的 ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-223">**ExpressRoute for Office 365**</span></span>|<span data-ttu-id="1ee0f-224">**目标 IP**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-224">**Destination IP**</span></span>|<span data-ttu-id="1ee0f-225">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-225">**Destination Port**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ee0f-226">身份验证与标识</span><span class="sxs-lookup"><span data-stu-id="1ee0f-226">Authentication and identity</span></span>  <br/> |<span data-ttu-id="1ee0f-227">请参阅[Office 365 身份验证和标识](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-227">See [Office 365 authentication and identity](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)</span></span> <br/> |||
|<span data-ttu-id="1ee0f-228">门户与共享</span><span class="sxs-lookup"><span data-stu-id="1ee0f-228">Portal and shared</span></span>  <br/> |<span data-ttu-id="1ee0f-229">请参阅[Office 365 门户和共享](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-229">See [Office 365 portal and shared](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)</span></span> <br/> |||
|<span data-ttu-id="1ee0f-230">SIP 信号</span><span class="sxs-lookup"><span data-stu-id="1ee0f-230">SIP Signaling</span></span>  <br/> |<span data-ttu-id="1ee0f-231">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-231">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-232">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-232">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-233">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-233">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-234">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-234">No</span></span>  <br/> |<span data-ttu-id="1ee0f-235">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-235">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-236">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-236">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-237">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-237">TCP 443</span></span>  <br/> |
|<span data-ttu-id="1ee0f-238">持久型共享对象模型 (PSOM) 连接 Web 会议</span><span class="sxs-lookup"><span data-stu-id="1ee0f-238">Persistent Shared Object Model (PSOM) connections web conferencing</span></span>  <br/> |<span data-ttu-id="1ee0f-239">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-239">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-240">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-240">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-241">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-241">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-242">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-242">No</span></span>  <br/> |<span data-ttu-id="1ee0f-243">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-243">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-244">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-244">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-245">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-245">TCP 443</span></span>  <br/> |
|<span data-ttu-id="1ee0f-246">HTTPS 下载</span><span class="sxs-lookup"><span data-stu-id="1ee0f-246">HTTPS downloads</span></span>  <br/> |<span data-ttu-id="1ee0f-247">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-247">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-248">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-248">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-249">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-249">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-250">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-250">No</span></span>  <br/> |<span data-ttu-id="1ee0f-251">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-251">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-252">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-252">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-253">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-253">TCP 443</span></span>  <br/> |
|<span data-ttu-id="1ee0f-254">音频</span><span class="sxs-lookup"><span data-stu-id="1ee0f-254">Audio</span></span>  <br/> |<span data-ttu-id="1ee0f-255">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-255">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-256">TCP/UDP 50,000-50019</span><span class="sxs-lookup"><span data-stu-id="1ee0f-256">TCP/UDP 50,000-50019</span></span>  <br/> |<span data-ttu-id="1ee0f-257">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-257">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-258">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-258">No</span></span>  <br/> |<span data-ttu-id="1ee0f-259">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-259">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-260">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-260">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-261">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="1ee0f-261">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="1ee0f-262">视频</span><span class="sxs-lookup"><span data-stu-id="1ee0f-262">Video</span></span>  <br/> |<span data-ttu-id="1ee0f-263">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-263">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-264">TCP/UDP 50,020-50039</span><span class="sxs-lookup"><span data-stu-id="1ee0f-264">TCP/UDP 50,020-50039</span></span>  <br/> |<span data-ttu-id="1ee0f-265">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-265">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-266">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-266">No</span></span>  <br/> |<span data-ttu-id="1ee0f-267">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-267">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-268">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-268">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-269">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="1ee0f-269">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="1ee0f-270">桌面共享</span><span class="sxs-lookup"><span data-stu-id="1ee0f-270">Desktop Sharing</span></span>  <br/> |<span data-ttu-id="1ee0f-271">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-271">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-272">TCP/UDP 50,040-50059</span><span class="sxs-lookup"><span data-stu-id="1ee0f-272">TCP/UDP 50,040-50059</span></span>  <br/> |<span data-ttu-id="1ee0f-273">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-273">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-274">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-274">No</span></span>  <br/> |<span data-ttu-id="1ee0f-275">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-275">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-276">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-276">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-277">TCP 443，50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="1ee0f-277">TCP 443, 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="1ee0f-p119">用于 iOS 设备中的 Lync Mobile 2010 的 Lync Mobile 推送通知 Android、Nokia Symbian 或 Windows Phone 移动设备不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-p119">Lync Mobile push notifications for Lync Mobile 2010 on iOS devices. You don't need this for Android, Nokia Symbian or Windows Phone mobile devices.</span></span>  <br/> |<span data-ttu-id="1ee0f-280">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-280">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-281">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-281">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-282">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-282">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="1ee0f-283">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-283">No</span></span>  <br/> |<span data-ttu-id="1ee0f-284">是</span><span class="sxs-lookup"><span data-stu-id="1ee0f-284">Yes</span></span>  <br/> |[<span data-ttu-id="1ee0f-285">业务 IP 范围的的 Skype</span><span class="sxs-lookup"><span data-stu-id="1ee0f-285">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="1ee0f-286">TCP 5223</span><span class="sxs-lookup"><span data-stu-id="1ee0f-286">TCP 5223</span></span>  <br/> |
|<span data-ttu-id="1ee0f-287">Skype Telemetry</span><span class="sxs-lookup"><span data-stu-id="1ee0f-287">Skype Telemetry</span></span>  <br/> |<span data-ttu-id="1ee0f-288">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-288">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-289">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-289">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-290">skypemaprdsitus.trafficmanager.net</span><span class="sxs-lookup"><span data-stu-id="1ee0f-290">skypemaprdsitus.trafficmanager.net</span></span>  <br/> <span data-ttu-id="1ee0f-291">pipe.skype.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-291">pipe.skype.com</span></span>  <br/> |<span data-ttu-id="1ee0f-292">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-292">No</span></span>  <br/> |<span data-ttu-id="1ee0f-293">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-293">No</span></span>  <br/> |<span data-ttu-id="1ee0f-294">不适用</span><span class="sxs-lookup"><span data-stu-id="1ee0f-294">N/A</span></span>  <br/> |<span data-ttu-id="1ee0f-295">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-295">TCP 443</span></span>  <br/> |
|<span data-ttu-id="1ee0f-296">Skype 客户端快速提示</span><span class="sxs-lookup"><span data-stu-id="1ee0f-296">Skype client quicktips</span></span>  <br/> |<span data-ttu-id="1ee0f-297">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-297">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="1ee0f-298">临时端口</span><span class="sxs-lookup"><span data-stu-id="1ee0f-298">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="1ee0f-299">quicktips.skypeforbusiness.com</span><span class="sxs-lookup"><span data-stu-id="1ee0f-299">quicktips.skypeforbusiness.com</span></span>  <br/> |<span data-ttu-id="1ee0f-300">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-300">No</span></span>  <br/> |<span data-ttu-id="1ee0f-301">否</span><span class="sxs-lookup"><span data-stu-id="1ee0f-301">No</span></span>  <br/> |<span data-ttu-id="1ee0f-302">不适用</span><span class="sxs-lookup"><span data-stu-id="1ee0f-302">N/A</span></span>  <br/> |<span data-ttu-id="1ee0f-303">TCP 443</span><span class="sxs-lookup"><span data-stu-id="1ee0f-303">TCP 443</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1ee0f-304">用于 contoso.com 和 broadcast.skype.com 的通配符表示供 Office 365 独占使用的长节点列表。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-304">The wildcard for contoso.com and broadcast.skype.com represents a long list of nodes that are exclusively used for Office 365.</span></span> 
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="1ee0f-305">创建设置包</span><span class="sxs-lookup"><span data-stu-id="1ee0f-305">Create provisioning packages</span></span>

<span data-ttu-id="1ee0f-306">使用该设置包可在使用 Exchange Server 或 Skype for Business Server 时进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-306">You will use provisioning packages to authenticate to Exchange Server or Skype for Business Server.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="1ee0f-307">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="1ee0f-307">Admin group management</span></span>

<span data-ttu-id="1ee0f-308">加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-308">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="1ee0f-309">该安全组的任何成员均可输入其凭据并解锁设置。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-309">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ee0f-310">如果 Skype 会议室系统 v2 设备丢失与 （例如，如果您 Skype 会议室系统 v2 从域中删除后加入域） 域的信任，您将无法进行身份验证到设备，然后打开设置。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-310">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="1ee0f-311">解决方法是使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-311">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="1ee0f-312">本地帐户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-312">Local accounts</span></span>

### <a name="skype-room-systems-local-user-account"></a><span data-ttu-id="1ee0f-313">Skype 会议室系统本地用户帐户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-313">Skype Room Systems Local User Account</span></span>

<span data-ttu-id="1ee0f-314">该设备帐户通常不使用密码。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-314">The Device Account does not typically use a password.</span></span> <span data-ttu-id="1ee0f-315">可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-315">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="1ee0f-316">因此，管理员应确保不允许密码过期。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-316">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="1ee0f-317">“Admin”- 本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-317">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="1ee0f-318">Skype 会议室系统 v2 的默认密码设置为"sfb"。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-318">Skype Room Systems v2 default password is set to "sfb".</span></span> <span data-ttu-id="1ee0f-319">可以转到 Windows 设置本地更改密码\>转到 Windows 或 AutoUnattend.xml 文件 （使用从 ADK 到 xml 文件中进行更改的 Windows 系统映像管理器） 中。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-319">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1ee0f-320">请务必尽快更改的 Skype 会议室系统 v2 密码。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-320">Be sure to change the Skype Room Systems v2 password as soon as possible.</span></span> 
  
<span data-ttu-id="1ee0f-321">还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-321">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="1ee0f-322">本地管理员密码安装过程中不包括作为选项。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-322">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="1ee0f-323">计算机帐户</span><span class="sxs-lookup"><span data-stu-id="1ee0f-323">Machine Account</span></span>

<span data-ttu-id="1ee0f-324">得多任何 Windows 设备，如计算机名称可以重命名通过设置中右键单击\>有关\>重命名 PC。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-324">Much like any Windows device, the Machine Name can be renamed by right clicking in Settings \> About \> Rename PC.</span></span>
  
 <span data-ttu-id="1ee0f-325">如果您希望将计算机加入到域后重命名，使用计算机的新名称后跟重命名计算机 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="1ee0f-325">If you would like to rename the computer after joining it to a domain, use the Rename-Computer PowerShell command followed by the computer's new name.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ee0f-326">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee0f-326">See also</span></span>

#### 

[<span data-ttu-id="1ee0f-327">Skype 会议室系统 v2 要求</span><span class="sxs-lookup"><span data-stu-id="1ee0f-327">Skype Room Systems v2 requirements</span></span>](requirements.md)
  
[<span data-ttu-id="1ee0f-328">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="1ee0f-328">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="1ee0f-329">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="1ee0f-329">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="1ee0f-330">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="1ee0f-330">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

