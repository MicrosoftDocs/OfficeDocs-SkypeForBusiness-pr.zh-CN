---
title: 配置 Microsoft 团队聊天室控制台
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Microsoft 团队聊天室控制台及其外围设备。
ms.openlocfilehash: bb21bf6386164f65411a62870e86e1b1883560e1
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428052"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="c56ea-103">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="c56ea-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="c56ea-104">本文介绍如何设置 Microsoft 团队聊天室控制台及其外围设备。</span><span class="sxs-lookup"><span data-stu-id="c56ea-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="c56ea-105">仅当已创建和测试必要的 Microsoft 团队或 Skype for business 和 Exchange 帐户时, 才应执行这些步骤, 如[部署 Microsoft 团队聊天室](room-systems-v2.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="c56ea-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="c56ea-106">你将需要[Microsoft 团队会议室要求](requirements.md)中所述的硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="c56ea-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="c56ea-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="c56ea-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c56ea-108">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="c56ea-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="c56ea-109">在控制台上安装专用 CA 证书</span><span class="sxs-lookup"><span data-stu-id="c56ea-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="c56ea-110">安装 Windows 10 和 Microsoft 团队聊天室控制台应用</span><span class="sxs-lookup"><span data-stu-id="c56ea-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="c56ea-111">控制台的初始设置</span><span class="sxs-lookup"><span data-stu-id="c56ea-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="c56ea-112">Microsoft 团队会议室部署清单</span><span class="sxs-lookup"><span data-stu-id="c56ea-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="c56ea-113">Microsoft 团队聊天室仅适用于正确配置的 Microsoft 团队或 Skype for business 环境, 在此环境中, 设备帐户按照[部署 Microsoft 团队聊天室](room-systems-v2.md)中的说明正确设置。</span><span class="sxs-lookup"><span data-stu-id="c56ea-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c56ea-114">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="c56ea-114">Prepare the installation media</span></span>
<span data-ttu-id="c56ea-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-115"></span></span>

<span data-ttu-id="c56ea-116">安装 Microsoft 团队聊天室控制台应用需要至少具有32GB 容量的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="c56ea-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="c56ea-117">设备上不应有任何其他文件;USB 存储上的任何现有文件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="c56ea-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c56ea-118">未能根据这些说明创建 Microsoft 团队聊天室安装媒体可能会导致意外行为。</span><span class="sxs-lookup"><span data-stu-id="c56ea-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="c56ea-119">下面的过程用于将安装媒体创建为映像新的 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="c56ea-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="c56ea-120">默认情况下, 现有设备将从 Windows 更新和 Windows 应用商店自动更新。</span><span class="sxs-lookup"><span data-stu-id="c56ea-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="c56ea-121">下载[CreateSrsMedia 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c56ea-122">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="c56ea-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="c56ea-123">按照脚本说明创建 Microsoft 团队聊天室 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c56ea-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="c56ea-124">每次 CreateSrsMedia 脚本启动时, 屏幕输出将包含该会话的日志文件或脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="c56ea-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="c56ea-125">如果运行脚本时出现问题, 请确保在请求支持时提供该脚本的副本。</span><span class="sxs-lookup"><span data-stu-id="c56ea-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="c56ea-126">CreateSrsMedia 脚本自动执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="c56ea-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="c56ea-127">下载适用于 Microsoft 团队聊天室的最新 MSI 安装程序。</span><span class="sxs-lookup"><span data-stu-id="c56ea-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="c56ea-128">确定用户必须提供的 Windows 的内部版本。</span><span class="sxs-lookup"><span data-stu-id="c56ea-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="c56ea-129">最新发布的版本可能会也可能不会经过测试, 并且支持与 Microsoft 团队聊天室设备配合使用。</span><span class="sxs-lookup"><span data-stu-id="c56ea-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="c56ea-130">下载必要的支持组件。</span><span class="sxs-lookup"><span data-stu-id="c56ea-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="c56ea-131">在安装媒体上组装所需的组件。</span><span class="sxs-lookup"><span data-stu-id="c56ea-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="c56ea-132">需要特定版本的 Windows 10, 并且此版本仅适用于批量许可客户。</span><span class="sxs-lookup"><span data-stu-id="c56ea-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="c56ea-133">您可以从[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/)获取副本。</span><span class="sxs-lookup"><span data-stu-id="c56ea-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="c56ea-134">完成后, 从计算机中删除 USB 磁盘并继续[安装 Windows 10 和 Microsoft 团队聊天室控制台应用](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="c56ea-135">安装 Windows 10 和 Microsoft 团队聊天室控制台应用</span><span class="sxs-lookup"><span data-stu-id="c56ea-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="c56ea-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-136"></span></span>

<span data-ttu-id="c56ea-137">您现在需要应用您创建的安装媒体。</span><span class="sxs-lookup"><span data-stu-id="c56ea-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c56ea-138">目标设备将作为装置运行, 并且默认用户将设置为仅运行 Microsoft 团队聊天室控制台应用。</span><span class="sxs-lookup"><span data-stu-id="c56ea-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="c56ea-139">如果目标设备将安装在插接设备 (如 Surface Pro) 中, 请断开其与坞站的连接。</span><span class="sxs-lookup"><span data-stu-id="c56ea-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c56ea-140">确保目标设备未连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c56ea-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c56ea-141">确保目标设备已连接到交流电源。</span><span class="sxs-lookup"><span data-stu-id="c56ea-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c56ea-142">将您的 USB 安装盘插入到目标设备中。</span><span class="sxs-lookup"><span data-stu-id="c56ea-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c56ea-143">启动到 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c56ea-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="c56ea-144">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="c56ea-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c56ea-145">如果目标设备是 Surface Pro, 请使用以下步骤启动到 USB 安装盘:</span><span class="sxs-lookup"><span data-stu-id="c56ea-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="c56ea-146">a.</span><span class="sxs-lookup"><span data-stu-id="c56ea-146">a.</span></span> <span data-ttu-id="c56ea-147">按下并继续按住音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c56ea-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="c56ea-148">b.</span><span class="sxs-lookup"><span data-stu-id="c56ea-148">b.</span></span> <span data-ttu-id="c56ea-149">按下并释放 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c56ea-149">Press and release the power button.</span></span>

    <span data-ttu-id="c56ea-150">c.</span><span class="sxs-lookup"><span data-stu-id="c56ea-150">c.</span></span> <span data-ttu-id="c56ea-151">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c56ea-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c56ea-152">安装完成后, 系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="c56ea-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c56ea-153">系统关闭后, 可以安全地删除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c56ea-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c56ea-154">此时, 你可以将目标设备放置在其 dock 中 (如果使用基于插接的产品), 附加会议室所需的外围设备, 并连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c56ea-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c56ea-155">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="c56ea-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="c56ea-156">选择语言</span><span class="sxs-lookup"><span data-stu-id="c56ea-156">Selecting a language</span></span> 

<span data-ttu-id="c56ea-157">在创建者的更新中, 你需要使用 ApplyCurrentRegionAndLanguage 脚本, 其中隐式语言选择不向用户提供所需的实际应用程序语言 (例如, 他们希望控制台应用使用法语, 但它将以英语提供。</span><span class="sxs-lookup"><span data-stu-id="c56ea-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c56ea-158">以下说明仅适用于使用 Windows 创建者更新创建的控制台。</span><span class="sxs-lookup"><span data-stu-id="c56ea-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c56ea-159">未使用新预配系统的媒体设置的旧/市场系统将无法使用这些说明, 但也不会受到需要此手动干预的初始问题 (周年纪念版本允许你选择在安装程序中显式应用语言。</span><span class="sxs-lookup"><span data-stu-id="c56ea-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c56ea-160">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="c56ea-160">To apply your desired language</span></span>

1. <span data-ttu-id="c56ea-161">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="c56ea-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c56ea-162">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="c56ea-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c56ea-163">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="c56ea-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c56ea-164">选择 **" &amp;时间语言**"。</span><span class="sxs-lookup"><span data-stu-id="c56ea-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c56ea-165">选择 **" &amp;地区语言**"。</span><span class="sxs-lookup"><span data-stu-id="c56ea-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c56ea-166">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c56ea-167">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="c56ea-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c56ea-168">选择您刚刚添加到 "语言" 列表的语言。</span><span class="sxs-lookup"><span data-stu-id="c56ea-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c56ea-169">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c56ea-170">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="c56ea-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c56ea-p114">a. 选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="c56ea-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c56ea-p115">b. 选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="c56ea-175">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c56ea-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c56ea-176">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c56ea-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="c56ea-177">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="c56ea-177">Restart the system.</span></span>
    
<span data-ttu-id="c56ea-178">您所需的语言现已应用于 Microsoft 团队聊天室控制台。</span><span class="sxs-lookup"><span data-stu-id="c56ea-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c56ea-179">控制台的初始设置</span><span class="sxs-lookup"><span data-stu-id="c56ea-179">Initial set up of the console</span></span>
<span data-ttu-id="c56ea-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-180"></span></span>

<span data-ttu-id="c56ea-181">安装 Windows 后, Microsoft 团队聊天室控制台应用将在下一次启动时转到其初始设置过程或选择了/reboot 选项。</span><span class="sxs-lookup"><span data-stu-id="c56ea-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c56ea-182">将显示“用户帐户”屏幕。</span><span class="sxs-lookup"><span data-stu-id="c56ea-182">The User Account screen appears.</span></span> <span data-ttu-id="c56ea-183">输入要与控制台一起使用的房间帐户的 Skype 登录地址 (用户 @ 域格式)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c56ea-184">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="c56ea-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c56ea-185">在 "配置域" 下, 设置 Skype for business 服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c56ea-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c56ea-186">如果 Skype for Business SIP 域不同于用户的 Exchange 域, 请在此字段中输入 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="c56ea-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c56ea-187">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c56ea-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="c56ea-188">在 "功能" 屏幕上选择指示的设备, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c56ea-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c56ea-189">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c56ea-190">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="c56ea-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="c56ea-191">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="c56ea-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c56ea-192">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="c56ea-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c56ea-193">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="c56ea-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="c56ea-p119">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="c56ea-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c56ea-196">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-196">Click **Finish**.</span></span>
    
<span data-ttu-id="c56ea-197">Microsoft 团队聊天室控制台应用应立即开始使用上面输入的凭据登录到 Skype for Business 服务器, 还应开始使用这些相同的凭据与 Exchange 同步其日历。</span><span class="sxs-lookup"><span data-stu-id="c56ea-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c56ea-198">有关使用控制台应用的详细信息, 请参阅[Microsoft 团队聊天室帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c56ea-199">Microsoft 团队聊天室依赖于已验证的控制台硬件的存在。</span><span class="sxs-lookup"><span data-stu-id="c56ea-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c56ea-200">即使在未检测到控制台硬件的情况中, 即使创建了包含 Microsoft 团队聊天室控制台应用的正确创建的图像, 也不会超过初始设置过程启动。</span><span class="sxs-lookup"><span data-stu-id="c56ea-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c56ea-201">对于基于 Surface Pro 的解决方案, Surface Pro 必须连接到其随附的 dock 硬件才能传递此检查。</span><span class="sxs-lookup"><span data-stu-id="c56ea-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c56ea-202">某些非英语语言用户可能需要在初始设置过程中连接到控制台的物理键盘在触摸键盘上不支持符号的情况中。</span><span class="sxs-lookup"><span data-stu-id="c56ea-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c56ea-203">在控制台上安装专用 CA 证书</span><span class="sxs-lookup"><span data-stu-id="c56ea-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c56ea-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-204"></span></span>

<span data-ttu-id="c56ea-205">Microsoft 团队聊天室控制台需要信任其连接的服务器所使用的证书。</span><span class="sxs-lookup"><span data-stu-id="c56ea-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="c56ea-206">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="c56ea-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c56ea-207">在证书颁发机构专用的情况下 (例如, 对于具有 Active Directory 和 Windows 证书颁发机构的内部部署), 你可以通过以下几种方式将证书添加到 Microsoft 团队聊天室控制台:</span><span class="sxs-lookup"><span data-stu-id="c56ea-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="c56ea-208">你可以将控制台加入 Active Directory, 并且将自动添加给定证书颁发机构的所需证书已发布到 Active Directory (常规部署选项)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c56ea-209">可以在映像过程后手动安装证书。</span><span class="sxs-lookup"><span data-stu-id="c56ea-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c56ea-210">在执行此操作之前, 必须完成[控制台的初始设置](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c56ea-211">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="c56ea-211">To manually install the certificate</span></span>

1. <span data-ttu-id="c56ea-212">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="c56ea-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c56ea-213">将控制台置于管理员模式下 (请参阅[管理员模式和设备管理](room-systems-v2-operations.md#AdminMode))。</span><span class="sxs-lookup"><span data-stu-id="c56ea-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c56ea-214">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c56ea-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c56ea-215">加入 Active Directory 域 (可选)</span><span class="sxs-lookup"><span data-stu-id="c56ea-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c56ea-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-216"></span></span>

<span data-ttu-id="c56ea-217">你可以将 Microsoft 团队聊天室控制台加入到你的域。</span><span class="sxs-lookup"><span data-stu-id="c56ea-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="c56ea-218">Microsoft 团队聊天室控制台应放置在电脑工作站的单独 OU 中, 因为许多工作站策略与 Microsoft 团队聊天室不兼容。</span><span class="sxs-lookup"><span data-stu-id="c56ea-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="c56ea-219">常见的示例是密码强制策略, 可防止 Microsoft 团队聊天室自动启动。</span><span class="sxs-lookup"><span data-stu-id="c56ea-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="c56ea-220">有关 GPO 设置管理的信息, 请参阅[管理 Microsoft 团队聊天室](room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="c56ea-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="c56ea-221">将 Microsoft 团队会议室加入域</span><span class="sxs-lookup"><span data-stu-id="c56ea-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="c56ea-222">从管理员帐户登录到控制台 (请参阅[管理员模式和设备管理](room-systems-v2-operations.md#AdminMode))。</span><span class="sxs-lookup"><span data-stu-id="c56ea-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c56ea-223">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c56ea-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c56ea-224">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="c56ea-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="c56ea-225">例如, 如果你的完全限定的域是 redmond.corp.microsoft.com, 而你希望 Microsoft 团队聊天室控制台位于 "Microsoft 团队聊天室" OU 中, 而该 OU 是 "Resources" OU 的子 ou, 则该命令将是:</span><span class="sxs-lookup"><span data-stu-id="c56ea-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c56ea-226">如果想要在将计算机加入到域时重命名该计算机, 请使用-NewName 标志, 后跟计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="c56ea-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="c56ea-227">Microsoft 团队会议室部署清单</span><span class="sxs-lookup"><span data-stu-id="c56ea-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="c56ea-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-228"></span></span>

<span data-ttu-id="c56ea-229">在最终验证是否已完全配置了控制台及其所有外围设备时, 请使用以下清单:</span><span class="sxs-lookup"><span data-stu-id="c56ea-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c56ea-230">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="c56ea-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c56ea-231">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-231">☐</span></span>  <br/> |<span data-ttu-id="c56ea-232">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="c56ea-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c56ea-233">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-233">☐</span></span>  <br/> |<span data-ttu-id="c56ea-234">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="c56ea-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c56ea-235">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-235">☐</span></span>  <br/> |<span data-ttu-id="c56ea-236">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="c56ea-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c56ea-237">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-237">☐</span></span>  <br/> |<span data-ttu-id="c56ea-238">已应用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="c56ea-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c56ea-239">**音频/视频外设**</span><span class="sxs-lookup"><span data-stu-id="c56ea-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c56ea-240">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-240">☐</span></span>  <br/> |<span data-ttu-id="c56ea-241">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="c56ea-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c56ea-242">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-242">☐</span></span>  <br/> |<span data-ttu-id="c56ea-243">相机功能和定位最佳</span><span class="sxs-lookup"><span data-stu-id="c56ea-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c56ea-244">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-244">☐</span></span>  <br/> |<span data-ttu-id="c56ea-245">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="c56ea-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c56ea-246">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-246">☐</span></span>  <br/> |<span data-ttu-id="c56ea-247">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="c56ea-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c56ea-248">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-248">☐</span></span>  <br/> |<span data-ttu-id="c56ea-249">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="c56ea-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c56ea-250">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-250">☐</span></span>  <br/> |<span data-ttu-id="c56ea-251">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="c56ea-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c56ea-252">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-252">☐</span></span>  <br/> |<span data-ttu-id="c56ea-253">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="c56ea-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c56ea-254">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="c56ea-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c56ea-255">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-255">☐</span></span>  <br/> |<span data-ttu-id="c56ea-256">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="c56ea-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c56ea-257">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-257">☐</span></span>  <br/> |<span data-ttu-id="c56ea-258">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="c56ea-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c56ea-259">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-259">☐</span></span>  <br/> |<span data-ttu-id="c56ea-260">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="c56ea-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c56ea-261">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-261">☐</span></span>  <br/> |<span data-ttu-id="c56ea-262">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="c56ea-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c56ea-263">☐</span><span class="sxs-lookup"><span data-stu-id="c56ea-263">☐</span></span>  <br/> |<span data-ttu-id="c56ea-264">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="c56ea-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c56ea-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c56ea-265">See also</span></span>
<span data-ttu-id="c56ea-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c56ea-266"></span></span>

[<span data-ttu-id="c56ea-267">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="c56ea-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c56ea-268">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="c56ea-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c56ea-269">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="c56ea-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c56ea-270">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="c56ea-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
