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
description: 本文介绍了用于部署 Skype 的空间系统的下一代的 Skype 的空间系统 v2 相关规划的考虑因素。
ms.openlocfilehash: 3d958c5d07cfafd2eeddd6076182a635cfff19de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-room-systems-v2"></a><span data-ttu-id="b7069-103">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="b7069-103">Plan for Skype Room Systems v2</span></span>
 
<span data-ttu-id="b7069-104">本文介绍了用于部署 Skype 的空间系统的下一代的 Skype 的空间系统 v2 相关规划的考虑因素。</span><span class="sxs-lookup"><span data-stu-id="b7069-104">This article explains the relevant planning considerations for deploying Skype Room Systems v2, the next generation of Skype Room Systems.</span></span> 
  
 <span data-ttu-id="b7069-105">Skype 的空间系统 v2 是 Microsoft 的最新会议解决方案，旨在转换为业务经验丰富、 协作 Skype 的会议室内。</span><span class="sxs-lookup"><span data-stu-id="b7069-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="b7069-106">用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="b7069-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="b7069-107">Skype 的空间系统 v2 旨在利用现有的设备，如液晶屏，以方便的安装 Skype 业务置于您的会议室。</span><span class="sxs-lookup"><span data-stu-id="b7069-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="b7069-108">Skype 的空间系统 v2 使用专门构建的 UWP 应用程序充当 Skype 会议用户界面。</span><span class="sxs-lookup"><span data-stu-id="b7069-108">Skype Room Systems v2 uses a purpose-built UWP app which acts as the Skype Meeting user interface.</span></span> <span data-ttu-id="b7069-109">以控制台模式运行 Surface Pro 4 或 Surface Pro （UWP 应用程序在部署后是仅将在设备上运行的应用程序），它需要您 Skype 上自己设备的帐户业务实现。</span><span class="sxs-lookup"><span data-stu-id="b7069-109">It runs on a Surface Pro 4 or Surface Pro in a console mode (once deployed the UWP app is the only app that will run on the device) and it requires its own device account on your Skype for Business implementation.</span></span> <span data-ttu-id="b7069-110">它利用液晶显示屏以及相对便宜的外围摄像头和麦克风等现有设备来提供高品质的会议室体验。</span><span class="sxs-lookup"><span data-stu-id="b7069-110">It leverages existing equipment like LCD panels and relatively inexpensive peripheral cameras and microphones to provide a quality meeting room experience.</span></span> <span data-ttu-id="b7069-111">软件通过 Windows 应用商店和 Windows 更新来更新。</span><span class="sxs-lookup"><span data-stu-id="b7069-111">Software is updated via both Windows store and Windows Update.</span></span>
  
<span data-ttu-id="b7069-112">在准备环境之前，请确保你具有必要的硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="b7069-112">Before you being preparing your environment, be sure you have the necessary hardware and software.</span></span> <span data-ttu-id="b7069-113">有关详细信息，请参阅[Skype 的空间系统 v2 要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7069-113">For more information, see [Skype Room Systems v2 requirements](requirements.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b7069-114">Skype 的空间系统 v2 旨在用于与 Skype 业务服务器 2015年或 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="b7069-114">Skype Room Systems v2 is intended for use with Skype for Business Server 2015 or Skype for Business Online.</span></span> <span data-ttu-id="b7069-115">早期的平台，如 Lync Server 2013 不需要使用 Skype 的空间系统 v2。</span><span class="sxs-lookup"><span data-stu-id="b7069-115">Earlier platforms like Lync Server 2013 are not expected to work with Skype Room Systems v2.</span></span> 
  
<span data-ttu-id="b7069-116">Skype 的空间系统 v2 是 Microsoft 的最新会议解决方案，旨在转换为业务经验丰富、 协作 Skype 的会议室内。</span><span class="sxs-lookup"><span data-stu-id="b7069-116">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="b7069-117">用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="b7069-117">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="b7069-118">Skype 的空间系统 v2 旨在利用现有的设备，如液晶屏，以方便的安装 Skype 业务置于您的会议室。</span><span class="sxs-lookup"><span data-stu-id="b7069-118">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
 <span data-ttu-id="b7069-119">**为 Skype for Business 而构建**</span><span class="sxs-lookup"><span data-stu-id="b7069-119">**Built for Skype for Business**</span></span>
  
- <span data-ttu-id="b7069-120">一键式加入 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="b7069-120">One-touch join of Skype Meetings</span></span>
    
- <span data-ttu-id="b7069-121">为配有满屏高清视频和高清宽带音频的会议室优化的 Skype 会议体验</span><span class="sxs-lookup"><span data-stu-id="b7069-121">Skype Meeting experience optimized for rooms with screen-filling HD video and HD wideband audio</span></span>
    
- <span data-ttu-id="b7069-122">所有参与者均可使用所选设备从任意位置连接到 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="b7069-122">All participants can connect to the Skype Meeting using their device of choice from wherever they may be located</span></span>
    
- <span data-ttu-id="b7069-123">从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户</span><span class="sxs-lookup"><span data-stu-id="b7069-123">Invite people from your directory where you can instantly see their availability or via a phone call</span></span>
    
- <span data-ttu-id="b7069-124">支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话</span><span class="sxs-lookup"><span data-stu-id="b7069-124">Supports Skype for Business PSTN Conferencing and PSTN Calling to replace the stand-alone conference phone in your room</span></span>
    
 <span data-ttu-id="b7069-125">**转换任何会议室**</span><span class="sxs-lookup"><span data-stu-id="b7069-125">**Transform Any Meeting Room**</span></span>
  
- <span data-ttu-id="b7069-126">专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化</span><span class="sxs-lookup"><span data-stu-id="b7069-126">Dedicated Skype Meeting app optimized for center of table touch controller and large front of room display</span></span>
    
- <span data-ttu-id="b7069-127">重用会议室显示屏和投影仪的现有投资</span><span class="sxs-lookup"><span data-stu-id="b7069-127">Re-use existing investments in your front of room display or projectors</span></span>
    
- <span data-ttu-id="b7069-128">适用于各种类型的会议室，从小型到大型会议室</span><span class="sxs-lookup"><span data-stu-id="b7069-128">Works in all types of meeting spaces from huddle spaces to large conference rooms</span></span>
    
- <span data-ttu-id="b7069-129">经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室</span><span class="sxs-lookup"><span data-stu-id="b7069-129">Certified Skype for Business audio and video devices are available for various room sizes</span></span>
    
- <span data-ttu-id="b7069-130">内置的有线采集可用于将桌面共享投影到会议室和 Skype 会议</span><span class="sxs-lookup"><span data-stu-id="b7069-130">Built-in wired ingest for to project desktop sharing to the room and to the Skype Meeting</span></span>
    
- <span data-ttu-id="b7069-131">在应用程序用户所选的会议房间音频和视频的 USB 设备 U1</span><span class="sxs-lookup"><span data-stu-id="b7069-131">In-app user selection of meeting room audio and video USB devices U1</span></span>
    
- <span data-ttu-id="b7069-132">双屏幕支持 （对于旧系统的奇偶校验） U2</span><span class="sxs-lookup"><span data-stu-id="b7069-132">Dual-Screen support (for legacy system parity) U2</span></span>
    
- <span data-ttu-id="b7069-133">Themability （内置主题和设置自定义主题的能力） U2</span><span class="sxs-lookup"><span data-stu-id="b7069-133">Themability (built-in themes and the ability to set custom theme) U2</span></span>
    
 <span data-ttu-id="b7069-134">**易于部署、便于管理**</span><span class="sxs-lookup"><span data-stu-id="b7069-134">**Easy to Deploy, Simple to Manage**</span></span>
  
- <span data-ttu-id="b7069-135">常开式设备会在检测到会议室中有人时自动唤醒显示屏</span><span class="sxs-lookup"><span data-stu-id="b7069-135">Always-on appliance that will automatically wake up the displays when it detects people in the room</span></span>
    
- <span data-ttu-id="b7069-136">UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单</span><span class="sxs-lookup"><span data-stu-id="b7069-136">Simple deployment and updating of the UWP (Universal Windows Platform) Skype Meeting App</span></span>
    
- <span data-ttu-id="b7069-137">Windows AppLocker 可将设备锁定至 Skype 会议应用</span><span class="sxs-lookup"><span data-stu-id="b7069-137">Windows AppLocker locks down the device to the Skype Meeting app</span></span>
    
- <span data-ttu-id="b7069-138">通过 Intune 和 SCCM (MDM) 作为 Windows 10 企业版设备来监控和管理</span><span class="sxs-lookup"><span data-stu-id="b7069-138">Monitored and managed as a Windows 10 Enterprise device via Intune and SCCM (MDM)</span></span>
    
- <span data-ttu-id="b7069-139">企业级可靠性</span><span class="sxs-lookup"><span data-stu-id="b7069-139">Enterprise-grade reliability</span></span>
    
- <span data-ttu-id="b7069-140">由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训</span><span class="sxs-lookup"><span data-stu-id="b7069-140">Low training effort of end-users due to familiar Skype user interface</span></span>
    
- <span data-ttu-id="b7069-141">在 Surface Pro 4 平板电脑上运行</span><span class="sxs-lookup"><span data-stu-id="b7069-141">Runs on Surface Pro 4 tablet</span></span>
    
- <span data-ttu-id="b7069-142">集成文件室控制台状态报告功能，为客户使用 Microsoft 操作管理套件 （请参见[计划 Skype 的空间系统 v2 管理与 OMS](oms-management.md)） U1</span><span class="sxs-lookup"><span data-stu-id="b7069-142">Integrated room console status reporting for customers using Microsoft Operations Management Suite (see [Plan Skype Room Systems v2 management with OMS](oms-management.md)) U1</span></span>
    
- <span data-ttu-id="b7069-143">为公众提供反馈能力生成 U2</span><span class="sxs-lookup"><span data-stu-id="b7069-143">Ability to Give Feedback for public builds U2</span></span>
    
- <span data-ttu-id="b7069-144">围绕会议 U2 的联接可靠性的改进的遥测</span><span class="sxs-lookup"><span data-stu-id="b7069-144">Improved Telemetry around meeting join reliability U2</span></span>
    
- <span data-ttu-id="b7069-145">其他报告 U2 的 OMS</span><span class="sxs-lookup"><span data-stu-id="b7069-145">Additional OMS reporting U2</span></span>
    
- <span data-ttu-id="b7069-146">IT 管理员可以远程配置设备能力 U2</span><span class="sxs-lookup"><span data-stu-id="b7069-146">Ability for IT Admin to configure devices remotely U2</span></span>
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- <span data-ttu-id="b7069-147">在 U3 的 Surface Pro tablet 上运行</span><span class="sxs-lookup"><span data-stu-id="b7069-147">Runs on Surface Pro tablet U3</span></span>
    
- <span data-ttu-id="b7069-148">支持 Windows 10 企业创建者更新 （英语语言，生成 1703年） U3</span><span class="sxs-lookup"><span data-stu-id="b7069-148">Supports Windows 10 Enterprise Creator's Update (English language, build 1703) U3</span></span>
    
- <span data-ttu-id="b7069-149">支持[SR Crestron](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)停靠 U3 的硬件</span><span class="sxs-lookup"><span data-stu-id="b7069-149">Support for [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) dock hardware U3</span></span>
    
- <span data-ttu-id="b7069-150">环境控制 (Crestron) U3 的 OEM 支持</span><span class="sxs-lookup"><span data-stu-id="b7069-150">OEM Support for Environment Controls (Crestron) U3</span></span>
    
- <span data-ttu-id="b7069-151">支持[Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)坞站 hardwareU4</span><span class="sxs-lookup"><span data-stu-id="b7069-151">Support for [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) dock hardwareU4</span></span>
    
- <span data-ttu-id="b7069-152">[Logitech Brio](https://www.logitech.com/en-us/product/brio)U4 的支持</span><span class="sxs-lookup"><span data-stu-id="b7069-152">Support for the [Logitech Brio](https://www.logitech.com/en-us/product/brio)U4</span></span>

- <span data-ttu-id="b7069-153">对[联想中心 500](https://www3.lenovo.com/us/en/hub500)U5 支持停靠硬件</span><span class="sxs-lookup"><span data-stu-id="b7069-153">Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)U5 dock hardware</span></span>  
    
<span data-ttu-id="b7069-154">U1 的更新 1 （ver.软件中引入的功能</span><span class="sxs-lookup"><span data-stu-id="b7069-154">U1 - Feature introduced in Update 1 (SW Ver.</span></span> <span data-ttu-id="b7069-155">2.0.2.0)。</span><span class="sxs-lookup"><span data-stu-id="b7069-155">2.0.2.0).</span></span>
  
<span data-ttu-id="b7069-156">U2 的更新 2 （ver.软件中引入的功能</span><span class="sxs-lookup"><span data-stu-id="b7069-156">U2- Feature introduced in Update 2 (SW Ver.</span></span> <span data-ttu-id="b7069-157">3.0.6.0)。</span><span class="sxs-lookup"><span data-stu-id="b7069-157">3.0.6.0).</span></span> 
  
<span data-ttu-id="b7069-158">U3-更新 3 （ver.软件中引入的功能</span><span class="sxs-lookup"><span data-stu-id="b7069-158">U3- Feature introduced in Update 3 (SW Ver.</span></span> <span data-ttu-id="b7069-159">3.0.12.0)。</span><span class="sxs-lookup"><span data-stu-id="b7069-159">3.0.12.0).</span></span> 
  
<span data-ttu-id="b7069-160">U4-更新 4 （ver.软件中引入的功能</span><span class="sxs-lookup"><span data-stu-id="b7069-160">U4- Feature introduced in Update 4 (SW Ver.</span></span> <span data-ttu-id="b7069-161">3.0.15.0)。</span><span class="sxs-lookup"><span data-stu-id="b7069-161">3.0.15.0).</span></span> 

<span data-ttu-id="b7069-162">U5-更新 5 （ver.软件中引入的功能</span><span class="sxs-lookup"><span data-stu-id="b7069-162">U5- Feature introduced in Update 5 (SW Ver.</span></span> <span data-ttu-id="b7069-163">3.1.98.0)。</span><span class="sxs-lookup"><span data-stu-id="b7069-163">3.1.98.0).</span></span> 
  
## <a name="preparing-your-skype-for-business-environment"></a><span data-ttu-id="b7069-164">准备 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="b7069-164">Preparing your Skype for Business Environment</span></span>

<span data-ttu-id="b7069-165">本部分包含准备您的环境，以便您可以使用所有的 Skype 的空间系统 v2 的功能所需步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="b7069-165">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Skype Room Systems v2.</span></span>
  
1. <span data-ttu-id="b7069-166">准备每个 Skype 的空间系统 v2 控制台设备的帐户。</span><span class="sxs-lookup"><span data-stu-id="b7069-166">Prepare a device account for each Skype Room Systems v2 console.</span></span> <span data-ttu-id="b7069-167">详细信息，请参阅[部署 Skype 的空间系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。</span><span class="sxs-lookup"><span data-stu-id="b7069-167">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
    
2. <span data-ttu-id="b7069-168">确保有运行良好的网络/Internet 连接可供设备使用。</span><span class="sxs-lookup"><span data-stu-id="b7069-168">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
  - <span data-ttu-id="b7069-169">它必须能够接收 IP 地址使用 DHCP (注意： 不能与在第一单元启动时的静态 IP 地址配置 Skype 的空间系统 v2)</span><span class="sxs-lookup"><span data-stu-id="b7069-169">It must be able to receive an IP address using DHCP (note: Skype Room Systems v2 cannot be configured with a static IP address at the first unit startup)</span></span>
    
  - <span data-ttu-id="b7069-170">除了打开用于 Skype for Business 媒体的常规端口之外，还必须打开以下端口：</span><span class="sxs-lookup"><span data-stu-id="b7069-170">It must have these ports open (in addition to opening the normal ports for Skype for Business media):</span></span>
    
  - <span data-ttu-id="b7069-171">HTTPS：443</span><span class="sxs-lookup"><span data-stu-id="b7069-171">HTTPS: 443</span></span>
    
  - <span data-ttu-id="b7069-172">HTTP：80</span><span class="sxs-lookup"><span data-stu-id="b7069-172">HTTP: 80</span></span>
    
  - <span data-ttu-id="b7069-173">如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。</span><span class="sxs-lookup"><span data-stu-id="b7069-173">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7069-174">Skype 的空间系统第 2 版不支持 HDCP 输入，经观察发现，导致问题具有 hdmi 接口接收功能 （视频，音频）。</span><span class="sxs-lookup"><span data-stu-id="b7069-174">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="b7069-175">请注意确保与 Skype 的空间系统 v2 相连的交换机具有 HDCP 选项已关闭。</span><span class="sxs-lookup"><span data-stu-id="b7069-175">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
  
3. <span data-ttu-id="b7069-p113">为了改进你的体验，Microsoft 将收集数据。为了收集数据，我们需要将以下网站列入允许名单：</span><span class="sxs-lookup"><span data-stu-id="b7069-p113">In order to improve your experience, Microsoft collects data. To collect data, we need these sites whitelisted:</span></span>
    
  - <span data-ttu-id="b7069-178">遥测客户端终结点：https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="b7069-178">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
    
  - <span data-ttu-id="b7069-179">遥测设置终结点：https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="b7069-179">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="b7069-180">创建和测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="b7069-180">Create and test a device account</span></span>

<span data-ttu-id="b7069-181">一个*设备的帐户*是 Skype 的空间系统 v2 客户端使用，以从交换，访问功能，如日历，并使业务的 Skype 的帐户。</span><span class="sxs-lookup"><span data-stu-id="b7069-181">A  *device account*  is an account that the Skype Room Systems v2 client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="b7069-182">详细信息，请参阅[部署 Skype 的空间系统 v2](../../deploy/deploy-clients/room-systems-v2.md) 。</span><span class="sxs-lookup"><span data-stu-id="b7069-182">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="b7069-183">检查网络可用性</span><span class="sxs-lookup"><span data-stu-id="b7069-183">Check network availability</span></span>

<span data-ttu-id="b7069-184">才能正常工作，Skype 的空间系统 v2 设备必须满足这些要求的有线网络的访问权限：</span><span class="sxs-lookup"><span data-stu-id="b7069-184">In order to function properly, the Skype Room Systems v2 device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="b7069-185">可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="b7069-185">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>
    
- <span data-ttu-id="b7069-186">可访问能够使用 DHCP 提供 IP 地址的服务器。</span><span class="sxs-lookup"><span data-stu-id="b7069-186">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="b7069-187">Skype 的空间系统 v2 无法使用静态 IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="b7069-187">Skype Room Systems v2 cannot be configured with a static IP address.</span></span>
    
- <span data-ttu-id="b7069-188">访问 HTTP 端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="b7069-188">Access to HTTP ports 80 and 443.</span></span>
    
- <span data-ttu-id="b7069-189">TCP 和 UDP 端口配置中所述的[Lync Server 2013 的端口要求](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx)内部部署 Skype 业务实施或[Office 365 的 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)为 Skype 业务在线实现。</span><span class="sxs-lookup"><span data-stu-id="b7069-189">TCP and UDP ports configured as described in [Port requirements for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) for on premise Skype for Business implementations, or [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Skype for Business online implementations.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b7069-190">务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。</span><span class="sxs-lookup"><span data-stu-id="b7069-190">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
  
### <a name="certificates"></a><span data-ttu-id="b7069-191">证书</span><span class="sxs-lookup"><span data-stu-id="b7069-191">Certificates</span></span>

<span data-ttu-id="b7069-192">Skype 的空间系统 v2 设备交换 Web 服务、 Skype 使用证书来获得业务、 网络使用情况和身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7069-192">Your Skype Room Systems v2 device uses certificates for Exchange Web Services, Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="b7069-193">如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。</span><span class="sxs-lookup"><span data-stu-id="b7069-193">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="b7069-194">另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。</span><span class="sxs-lookup"><span data-stu-id="b7069-194">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="b7069-195">将设备添加到域时，可以自动执行此任务。</span><span class="sxs-lookup"><span data-stu-id="b7069-195">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="b7069-196">安装证书的方式与任何其他 Windows 客户端一样。</span><span class="sxs-lookup"><span data-stu-id="b7069-196">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b7069-197">证书可能需要具有的业务服务器使用 Skype 的 Skype 的空间系统 v2。</span><span class="sxs-lookup"><span data-stu-id="b7069-197">Certificates may be required in order to have Skype Room Systems v2 use Skype for Business Server.</span></span> 
  
### <a name="proxy"></a><span data-ttu-id="b7069-198">代理</span><span class="sxs-lookup"><span data-stu-id="b7069-198">Proxy</span></span>

<span data-ttu-id="b7069-199">Skype 的空间系统 v2 旨在继承 Windows 操作系统的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="b7069-199">Skype Room Systems v2 is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="b7069-200">通过以下方式访问 Windows OS：</span><span class="sxs-lookup"><span data-stu-id="b7069-200">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="b7069-201">在 Skype 的空间系统 v2 UI 中，请单击设置齿轮图标位置您将被提示输入设备 （默认密码为"sfb"） 上的本地管理员密码。</span><span class="sxs-lookup"><span data-stu-id="b7069-201">In the Skype Room Systems v2 UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is "sfb").</span></span>
    
2. <span data-ttu-id="b7069-202">请点击"设置"，点击"转到窗口"按钮，然后点击上跟上"讲到管理员登录中"按钮，然后单击"管理员"按钮 (如果计算机加入域中选择"其他用户"，然后使用。 \admin 作为用户名)。</span><span class="sxs-lookup"><span data-stu-id="b7069-202">Tap on "Settings" followed by tapping on the "Go to Windows" button and then tapping on the "got to Admin Sign In" button and then clicking the "Administrator" button (if the computer is domain joined choose "Other User," then use .\admin as the user name).</span></span>
    
3. <span data-ttu-id="b7069-203">在"搜索 Windows"框的底部左的键入 regedit （长按屏幕，或者右单击，选择"以管理员身份运行"）。</span><span class="sxs-lookup"><span data-stu-id="b7069-203">In the "Search Windows" box bottom left type in regedit (either long press the screen or right click and choose "Run as administrator").</span></span>
    
4. <span data-ttu-id="b7069-204">单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。</span><span class="sxs-lookup"><span data-stu-id="b7069-204">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
    
    <span data-ttu-id="b7069-205">系统将提示您为密钥名称为您新加载的配置单元;键入在 Skype （您应该现在看到 Skype 用户的注册表设置）。</span><span class="sxs-lookup"><span data-stu-id="b7069-205">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
    
5. <span data-ttu-id="b7069-206">单击“文件”，然后选择“加载配置单元”。</span><span class="sxs-lookup"><span data-stu-id="b7069-206">Click on File and then choose "Load Hive."</span></span>
    
6. <span data-ttu-id="b7069-207">浏览到文件夹“C:\Users\Skype”，在“文件名”框中键入 NTUSER.dat 并按“打开”按钮</span><span class="sxs-lookup"><span data-stu-id="b7069-207">Browse the to the following folder "C:\Users\Skype" and type in the File name box NTUSER.dat and press the open button</span></span>
    
7. <span data-ttu-id="b7069-208">打开 Skype 键并浏览到 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 的设置，然后确保输入这些设置：</span><span class="sxs-lookup"><span data-stu-id="b7069-208">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    <span data-ttu-id="b7069-209">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span><span class="sxs-lookup"><span data-stu-id="b7069-209">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span></span>
    
    <span data-ttu-id="b7069-210">"MigrateProxy"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="b7069-210">"MigrateProxy"=dword:00000001</span></span>
    
    <span data-ttu-id="b7069-211">"ProxyEnable"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="b7069-211">"ProxyEnable"=dword:00000001</span></span>
    
    <span data-ttu-id="b7069-212">"ProxyServer"="xx.xx.xx.xx:8080"</span><span class="sxs-lookup"><span data-stu-id="b7069-212">"ProxyServer"="xx.xx.xx.xx:8080"</span></span>
    
    <span data-ttu-id="b7069-213">如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。</span><span class="sxs-lookup"><span data-stu-id="b7069-213">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
    
8. <span data-ttu-id="b7069-214">一旦您完成更改突出显示 Skype 用户密钥 （Skype 的根文件夹），然后选择卸载配置单元从注册表文件菜单中 （您将被提示输入确认-选择**是**）。</span><span class="sxs-lookup"><span data-stu-id="b7069-214">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes** ).</span></span>
    
9. <span data-ttu-id="b7069-215">现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。</span><span class="sxs-lookup"><span data-stu-id="b7069-215">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
10. <span data-ttu-id="b7069-216">返回登录屏幕，选择 **Skype** 用户。</span><span class="sxs-lookup"><span data-stu-id="b7069-216">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="b7069-217">如果前面的所有步骤都是否成功，Skype 的空间系统 v2 设备将登录成功。</span><span class="sxs-lookup"><span data-stu-id="b7069-217">If all the previous steps were successful, the Skype Room Systems v2 device will sign-in successfully.</span></span>
    
<span data-ttu-id="b7069-p119">要使用此应用程序，你必须能够连接至下面所述的终结点。要查看 IP 地址，请展开描述通信流的表下面的 IP 地址部分。</span><span class="sxs-lookup"><span data-stu-id="b7069-p119">To use this application, you must be able to connect to the endpoints described below. To see the IP addresses, expand the IP address section below the table describing the traffic flow.</span></span>
  
<span data-ttu-id="b7069-220">**防火墙代理主机/端口名称的示例**</span><span class="sxs-lookup"><span data-stu-id="b7069-220">**Firewall Proxy Host Name/Port Examples**</span></span>

|<span data-ttu-id="b7069-221">**目的**</span><span class="sxs-lookup"><span data-stu-id="b7069-221">**Purpose**</span></span>|<span data-ttu-id="b7069-222">**源或凭据**</span><span class="sxs-lookup"><span data-stu-id="b7069-222">**Source or Credentials**</span></span>|<span data-ttu-id="b7069-223">**源端口**</span><span class="sxs-lookup"><span data-stu-id="b7069-223">**Source Port**</span></span>|<span data-ttu-id="b7069-224">**目标**</span><span class="sxs-lookup"><span data-stu-id="b7069-224">**Destination**</span></span>|<span data-ttu-id="b7069-225">**CDN**</span><span class="sxs-lookup"><span data-stu-id="b7069-225">**CDN**</span></span>|<span data-ttu-id="b7069-226">**Office 365 的 ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="b7069-226">**ExpressRoute for Office 365**</span></span>|<span data-ttu-id="b7069-227">**目标 IP**</span><span class="sxs-lookup"><span data-stu-id="b7069-227">**Destination IP**</span></span>|<span data-ttu-id="b7069-228">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="b7069-228">**Destination Port**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7069-229">身份验证与标识</span><span class="sxs-lookup"><span data-stu-id="b7069-229">Authentication and identity</span></span>  <br/> |<span data-ttu-id="b7069-230">请参阅[Office 365 提供身份验证和身份](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)</span><span class="sxs-lookup"><span data-stu-id="b7069-230">See [Office 365 authentication and identity](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)</span></span> <br/> |||
|<span data-ttu-id="b7069-231">门户与共享</span><span class="sxs-lookup"><span data-stu-id="b7069-231">Portal and shared</span></span>  <br/> |<span data-ttu-id="b7069-232">请参阅[Office 365 门户和共享](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)</span><span class="sxs-lookup"><span data-stu-id="b7069-232">See [Office 365 portal and shared](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)</span></span> <br/> |||
|<span data-ttu-id="b7069-233">SIP 信号</span><span class="sxs-lookup"><span data-stu-id="b7069-233">SIP Signaling</span></span>  <br/> |<span data-ttu-id="b7069-234">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-234">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-235">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-235">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-236">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-236">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-237">否</span><span class="sxs-lookup"><span data-stu-id="b7069-237">No</span></span>  <br/> |<span data-ttu-id="b7069-238">是</span><span class="sxs-lookup"><span data-stu-id="b7069-238">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-239">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-239">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-240">TCP 443</span><span class="sxs-lookup"><span data-stu-id="b7069-240">TCP 443</span></span>  <br/> |
|<span data-ttu-id="b7069-241">持久型共享对象模型 (PSOM) 连接 Web 会议</span><span class="sxs-lookup"><span data-stu-id="b7069-241">Persistent Shared Object Model (PSOM) connections web conferencing</span></span>  <br/> |<span data-ttu-id="b7069-242">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-242">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-243">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-243">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-244">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-244">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-245">否</span><span class="sxs-lookup"><span data-stu-id="b7069-245">No</span></span>  <br/> |<span data-ttu-id="b7069-246">是</span><span class="sxs-lookup"><span data-stu-id="b7069-246">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-247">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-247">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-248">TCP 443</span><span class="sxs-lookup"><span data-stu-id="b7069-248">TCP 443</span></span>  <br/> |
|<span data-ttu-id="b7069-249">HTTPS 下载</span><span class="sxs-lookup"><span data-stu-id="b7069-249">HTTPS downloads</span></span>  <br/> |<span data-ttu-id="b7069-250">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-250">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-251">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-251">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-252">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-252">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-253">否</span><span class="sxs-lookup"><span data-stu-id="b7069-253">No</span></span>  <br/> |<span data-ttu-id="b7069-254">是</span><span class="sxs-lookup"><span data-stu-id="b7069-254">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-255">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-255">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-256">TCP 443</span><span class="sxs-lookup"><span data-stu-id="b7069-256">TCP 443</span></span>  <br/> |
|<span data-ttu-id="b7069-257">音频</span><span class="sxs-lookup"><span data-stu-id="b7069-257">Audio</span></span>  <br/> |<span data-ttu-id="b7069-258">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-258">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-259">TCP/UDP 50,000-50019</span><span class="sxs-lookup"><span data-stu-id="b7069-259">TCP/UDP 50,000-50019</span></span>  <br/> |<span data-ttu-id="b7069-260">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-260">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-261">否</span><span class="sxs-lookup"><span data-stu-id="b7069-261">No</span></span>  <br/> |<span data-ttu-id="b7069-262">是</span><span class="sxs-lookup"><span data-stu-id="b7069-262">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-263">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-263">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-264">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="b7069-264">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="b7069-265">视频</span><span class="sxs-lookup"><span data-stu-id="b7069-265">Video</span></span>  <br/> |<span data-ttu-id="b7069-266">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-266">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-267">TCP/UDP 50,020-50039</span><span class="sxs-lookup"><span data-stu-id="b7069-267">TCP/UDP 50,020-50039</span></span>  <br/> |<span data-ttu-id="b7069-268">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-268">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-269">否</span><span class="sxs-lookup"><span data-stu-id="b7069-269">No</span></span>  <br/> |<span data-ttu-id="b7069-270">是</span><span class="sxs-lookup"><span data-stu-id="b7069-270">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-271">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-271">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-272">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="b7069-272">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="b7069-273">桌面共享</span><span class="sxs-lookup"><span data-stu-id="b7069-273">Desktop Sharing</span></span>  <br/> |<span data-ttu-id="b7069-274">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-274">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-275">TCP/UDP 50,040-50059</span><span class="sxs-lookup"><span data-stu-id="b7069-275">TCP/UDP 50,040-50059</span></span>  <br/> |<span data-ttu-id="b7069-276">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-276">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-277">否</span><span class="sxs-lookup"><span data-stu-id="b7069-277">No</span></span>  <br/> |<span data-ttu-id="b7069-278">是</span><span class="sxs-lookup"><span data-stu-id="b7069-278">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-279">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-279">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-280">TCP 443，50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="b7069-280">TCP 443, 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="b7069-p120">用于 iOS 设备中的 Lync Mobile 2010 的 Lync Mobile 推送通知 Android、Nokia Symbian 或 Windows Phone 移动设备不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="b7069-p120">Lync Mobile push notifications for Lync Mobile 2010 on iOS devices. You don't need this for Android, Nokia Symbian or Windows Phone mobile devices.</span></span>  <br/> |<span data-ttu-id="b7069-283">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-283">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-284">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-284">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-285">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7069-285">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="b7069-286">否</span><span class="sxs-lookup"><span data-stu-id="b7069-286">No</span></span>  <br/> |<span data-ttu-id="b7069-287">是</span><span class="sxs-lookup"><span data-stu-id="b7069-287">Yes</span></span>  <br/> |[<span data-ttu-id="b7069-288">Skype 业务 IP 范围</span><span class="sxs-lookup"><span data-stu-id="b7069-288">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="b7069-289">TCP 5223</span><span class="sxs-lookup"><span data-stu-id="b7069-289">TCP 5223</span></span>  <br/> |
|<span data-ttu-id="b7069-290">Skype Telemetry</span><span class="sxs-lookup"><span data-stu-id="b7069-290">Skype Telemetry</span></span>  <br/> |<span data-ttu-id="b7069-291">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-291">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-292">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-292">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-293">skypemaprdsitus.trafficmanager.net</span><span class="sxs-lookup"><span data-stu-id="b7069-293">skypemaprdsitus.trafficmanager.net</span></span>  <br/> <span data-ttu-id="b7069-294">pipe.skype.com</span><span class="sxs-lookup"><span data-stu-id="b7069-294">pipe.skype.com</span></span>  <br/> |<span data-ttu-id="b7069-295">否</span><span class="sxs-lookup"><span data-stu-id="b7069-295">No</span></span>  <br/> |<span data-ttu-id="b7069-296">否</span><span class="sxs-lookup"><span data-stu-id="b7069-296">No</span></span>  <br/> |<span data-ttu-id="b7069-297">不适用</span><span class="sxs-lookup"><span data-stu-id="b7069-297">N/A</span></span>  <br/> |<span data-ttu-id="b7069-298">TCP 443</span><span class="sxs-lookup"><span data-stu-id="b7069-298">TCP 443</span></span>  <br/> |
|<span data-ttu-id="b7069-299">Skype 客户端快速提示</span><span class="sxs-lookup"><span data-stu-id="b7069-299">Skype client quicktips</span></span>  <br/> |<span data-ttu-id="b7069-300">客户端计算机或已登录用户</span><span class="sxs-lookup"><span data-stu-id="b7069-300">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="b7069-301">临时端口</span><span class="sxs-lookup"><span data-stu-id="b7069-301">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="b7069-302">quicktips.skypeforbusiness.com</span><span class="sxs-lookup"><span data-stu-id="b7069-302">quicktips.skypeforbusiness.com</span></span>  <br/> |<span data-ttu-id="b7069-303">否</span><span class="sxs-lookup"><span data-stu-id="b7069-303">No</span></span>  <br/> |<span data-ttu-id="b7069-304">否</span><span class="sxs-lookup"><span data-stu-id="b7069-304">No</span></span>  <br/> |<span data-ttu-id="b7069-305">不适用</span><span class="sxs-lookup"><span data-stu-id="b7069-305">N/A</span></span>  <br/> |<span data-ttu-id="b7069-306">TCP 443</span><span class="sxs-lookup"><span data-stu-id="b7069-306">TCP 443</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b7069-307">用于 contoso.com 和 broadcast.skype.com 的通配符表示供 Office 365 独占使用的长节点列表。</span><span class="sxs-lookup"><span data-stu-id="b7069-307">The wildcard for contoso.com and broadcast.skype.com represents a long list of nodes that are exclusively used for Office 365.</span></span> 
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="b7069-308">创建设置包</span><span class="sxs-lookup"><span data-stu-id="b7069-308">Create provisioning packages</span></span>

<span data-ttu-id="b7069-309">使用该设置包可在使用 Exchange Server 或 Skype for Business Server 时进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7069-309">You will use provisioning packages to authenticate to Exchange Server or Skype for Business Server.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="b7069-310">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="b7069-310">Admin group management</span></span>

<span data-ttu-id="b7069-311">加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。</span><span class="sxs-lookup"><span data-stu-id="b7069-311">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="b7069-312">该安全组的任何成员均可输入其凭据并解锁设置。</span><span class="sxs-lookup"><span data-stu-id="b7069-312">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7069-313">如果 Skype 的空间系统 v2 设备丢失 （例如，如果您 Skype 的空间系统 v2 从域中删除后，加入域） 的域的信任关系，您将无法插入设备进行身份验证，然后打开设置。</span><span class="sxs-lookup"><span data-stu-id="b7069-313">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="b7069-314">解决方法是使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b7069-314">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="b7069-315">本地帐户</span><span class="sxs-lookup"><span data-stu-id="b7069-315">Local accounts</span></span>

### <a name="skype-room-systems-local-user-account"></a><span data-ttu-id="b7069-316">Skype 会议室系统本地用户帐户</span><span class="sxs-lookup"><span data-stu-id="b7069-316">Skype Room Systems Local User Account</span></span>

<span data-ttu-id="b7069-317">该设备帐户通常不使用密码。</span><span class="sxs-lookup"><span data-stu-id="b7069-317">The Device Account does not typically use a password.</span></span> <span data-ttu-id="b7069-318">可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。</span><span class="sxs-lookup"><span data-stu-id="b7069-318">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="b7069-319">因此，管理员应确保不允许密码过期。</span><span class="sxs-lookup"><span data-stu-id="b7069-319">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="b7069-320">“Admin”- 本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b7069-320">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="b7069-321">Skype 的空间系统 v2 默认密码设置为"sfb"。</span><span class="sxs-lookup"><span data-stu-id="b7069-321">Skype Room Systems v2 default password is set to "sfb".</span></span> <span data-ttu-id="b7069-322">可以通过直接转至 Windows 设置本地更改密码\>转到 Windows 或 AutoUnattend.xml 文件 （使用 Windows 系统映像管理器从 ADK 到 xml 文件中进行更改）。</span><span class="sxs-lookup"><span data-stu-id="b7069-322">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b7069-323">请务必尽快更改 Skype 的空间系统 v2 密码。</span><span class="sxs-lookup"><span data-stu-id="b7069-323">Be sure to change the Skype Room Systems v2 password as soon as possible.</span></span> 
  
<span data-ttu-id="b7069-324">还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。</span><span class="sxs-lookup"><span data-stu-id="b7069-324">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="b7069-325">本地管理员密码在安装过程中不作为一种选择。</span><span class="sxs-lookup"><span data-stu-id="b7069-325">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="b7069-326">计算机帐户</span><span class="sxs-lookup"><span data-stu-id="b7069-326">Machine Account</span></span>

<span data-ttu-id="b7069-327">得像任何 Windows 设备，计算机名称可以重命名方法是右键单击设置中\>有关\>重命名计算机。</span><span class="sxs-lookup"><span data-stu-id="b7069-327">Much like any Windows device, the Machine Name can be renamed by right clicking in Settings \> About \> Rename PC.</span></span>
  
 <span data-ttu-id="b7069-328">如果您想要加入域之后重命名计算机，使用重命名计算机 PowerShell 命令跟计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="b7069-328">If you would like to rename the computer after joining it to a domain, use the Rename-Computer PowerShell command followed by the computer's new name.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7069-329">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7069-329">See also</span></span>

#### 

[<span data-ttu-id="b7069-330">Skype 的空间系统 v2 要求</span><span class="sxs-lookup"><span data-stu-id="b7069-330">Skype Room Systems v2 requirements</span></span>](requirements.md)
  
[<span data-ttu-id="b7069-331">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="b7069-331">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="b7069-332">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="b7069-332">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="b7069-333">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="b7069-333">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

