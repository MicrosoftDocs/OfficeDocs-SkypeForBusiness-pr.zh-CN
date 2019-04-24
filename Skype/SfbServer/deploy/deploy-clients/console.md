---
title: 配置 Microsoft 团队聊天室控制台
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Microsoft 团队聊天室控制台和其外围设备。
ms.openlocfilehash: 2d3d9acdc3c72754232304364812fd2af9f3f6cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212752"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="e48b4-103">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="e48b4-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="e48b4-104">本文介绍如何设置 Microsoft 团队聊天室控制台和其外围设备。</span><span class="sxs-lookup"><span data-stu-id="e48b4-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="e48b4-105">如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署的 Microsoft 团队聊天室](room-systems-v2.md)中所述，应仅执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e48b4-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="e48b4-106">您将需要的硬件和软件[Microsoft 团队聊天室要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="e48b4-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="e48b4-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="e48b4-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="e48b4-108">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="e48b4-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="e48b4-109">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="e48b4-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="e48b4-110">安装 Windows 10 和 Microsoft 团队聊天室控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="e48b4-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="e48b4-111">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="e48b4-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="e48b4-112">Microsoft 团队聊天室部署清单</span><span class="sxs-lookup"><span data-stu-id="e48b4-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="e48b4-113">其中设备帐户正确设置[部署 Microsoft 团队聊天室](room-systems-v2.md)中所述的业务环境正确配置 Skype 将仅适用 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="e48b4-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="e48b4-114">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="e48b4-114">Prepare the installation media</span></span>
<span data-ttu-id="e48b4-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-115"></span></span>

<span data-ttu-id="e48b4-116">安装 Microsoft 团队聊天室控制台应用程序需要 USB 存储设备具有至少 32 GB 的容量。</span><span class="sxs-lookup"><span data-stu-id="e48b4-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="e48b4-117">应在设备; 上的没有其他文件在 USB 存储任何现有文件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="e48b4-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e48b4-118">未能创建 Microsoft 团队聊天室安装媒体根据这些说明可能会导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="e48b4-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="e48b4-119">下面的过程是用于创建到图像新的 Microsoft 团队聊天室设备的安装介质中。</span><span class="sxs-lookup"><span data-stu-id="e48b4-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="e48b4-120">现有的设备，默认情况下自动更新从 Windows Update 和 Windows 应用商店。</span><span class="sxs-lookup"><span data-stu-id="e48b4-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="e48b4-121">下载[CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="e48b4-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="e48b4-122">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="e48b4-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="e48b4-123">按照脚本的说明创建 Microsoft 团队聊天室 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="e48b4-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="e48b4-124">在每次启动 CreateSrsMedia.ps1 脚本，屏幕输出将会话包含日志文件或脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="e48b4-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="e48b4-125">如果运行脚本问题，请确保已提供该脚本的副本时请求支持。</span><span class="sxs-lookup"><span data-stu-id="e48b4-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="e48b4-126">CreateSrsMedia.ps1 脚本自动执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e48b4-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="e48b4-127">下载最新的 MSI 安装程序的 Microsoft 团队会议室。</span><span class="sxs-lookup"><span data-stu-id="e48b4-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="e48b4-128">确定用户必须提供的 Windows 的版本。</span><span class="sxs-lookup"><span data-stu-id="e48b4-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="e48b4-129">最近发布的版本可能或不能测试且支持用于与 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="e48b4-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="e48b4-130">下载所需的支持组件。</span><span class="sxs-lookup"><span data-stu-id="e48b4-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="e48b4-131">在安装介质中组合所需的组件。</span><span class="sxs-lookup"><span data-stu-id="e48b4-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="e48b4-132">Windows 10 的特定版本是必需的并且仅适用于批量许可客户此版本。</span><span class="sxs-lookup"><span data-stu-id="e48b4-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="e48b4-133">从[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/)，可以获得的副本。</span><span class="sxs-lookup"><span data-stu-id="e48b4-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="e48b4-134">完成后，从计算机中删除 USB 磁盘，并继续[安装 Windows 10 和 Microsoft 团队聊天室控制台应用程序](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="e48b4-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="e48b4-135">安装 Windows 10 和 Microsoft 团队聊天室控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="e48b4-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="e48b4-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-136"></span></span>

<span data-ttu-id="e48b4-137">您现在需要应用您已创建的安装媒体。</span><span class="sxs-lookup"><span data-stu-id="e48b4-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="e48b4-138">目标设备将作为一种设备运行，并将设置的默认用户仅运行 Microsoft 团队聊天室控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="e48b4-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="e48b4-139">如果目标设备将安装中停靠 (如 Surface Pro)，断开与停靠连接。</span><span class="sxs-lookup"><span data-stu-id="e48b4-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="e48b4-140">确保目标设备未连接到网络。</span><span class="sxs-lookup"><span data-stu-id="e48b4-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="e48b4-141">确保目标设备连接到 AC 电源。</span><span class="sxs-lookup"><span data-stu-id="e48b4-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="e48b4-142">将插入目标设备在 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="e48b4-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="e48b4-143">引导到 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="e48b4-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="e48b4-144">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="e48b4-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="e48b4-145">如果 Surface Pro 目标设备，使用以下步骤引导到 USB 安装磁盘：</span><span class="sxs-lookup"><span data-stu-id="e48b4-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="e48b4-146">a.</span><span class="sxs-lookup"><span data-stu-id="e48b4-146">a.</span></span> <span data-ttu-id="e48b4-147">按并继续按住下 （-） 按钮的卷。</span><span class="sxs-lookup"><span data-stu-id="e48b4-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="e48b4-148">b.</span><span class="sxs-lookup"><span data-stu-id="e48b4-148">b.</span></span> <span data-ttu-id="e48b4-149">按下并释放高级按钮。</span><span class="sxs-lookup"><span data-stu-id="e48b4-149">Press and release the power button.</span></span>

    <span data-ttu-id="e48b4-150">c.</span><span class="sxs-lookup"><span data-stu-id="e48b4-150">c.</span></span> <span data-ttu-id="e48b4-151">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="e48b4-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="e48b4-152">安装完成后，系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="e48b4-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="e48b4-153">系统已关闭后，它是安全地移除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="e48b4-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="e48b4-154">此时，可以将目标设备放置在其停靠 （如果使用基于停靠的产品）、 附加外围设备所需的会议室中，并连接到网络。</span><span class="sxs-lookup"><span data-stu-id="e48b4-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="e48b4-155">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="e48b4-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="e48b4-156">选择语言</span><span class="sxs-lookup"><span data-stu-id="e48b4-156">Selecting a language</span></span> 

<span data-ttu-id="e48b4-157">创建者的更新，您需要在方案中使用 ApplyCurrentRegionAndLanguage.ps1 脚本隐式语言选择不提供所需的实际的应用程序语言的用户 (例如，需控制台应用程序采用法语，但它在接下来英语） （英文）。</span><span class="sxs-lookup"><span data-stu-id="e48b4-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e48b4-158">以下说明仅工时控制台创建使用 Windows 创建者的更新。</span><span class="sxs-lookup"><span data-stu-id="e48b4-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="e48b4-159">不使用媒体与新设置系统已设置的旧/市场系统不能使用这些说明，但应也不会受到影响从初始问题需要此手动干预 (周年日 Edition 让您选取您应用程序语言显式作为安装的一部分）。</span><span class="sxs-lookup"><span data-stu-id="e48b4-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="e48b4-160">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="e48b4-160">To apply your desired language</span></span>

1. <span data-ttu-id="e48b4-161">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="e48b4-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="e48b4-162">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="e48b4-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="e48b4-163">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="e48b4-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="e48b4-164">选中**时间&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="e48b4-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="e48b4-165">选中**区域&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="e48b4-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="e48b4-166">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="e48b4-167">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="e48b4-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="e48b4-168">选择您刚刚添加到"语言"列表的语言。</span><span class="sxs-lookup"><span data-stu-id="e48b4-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="e48b4-169">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="e48b4-170">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="e48b4-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="e48b4-p114">a. 选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="e48b4-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="e48b4-p115">b. 选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="e48b4-175">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e48b4-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="e48b4-176">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e48b4-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="e48b4-177">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="e48b4-177">Restart the system.</span></span>
    
<span data-ttu-id="e48b4-178">Microsoft 团队聊天室控制台现在应用所需的语言。</span><span class="sxs-lookup"><span data-stu-id="e48b4-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="e48b4-179">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="e48b4-179">Initial set up of the console</span></span>
<span data-ttu-id="e48b4-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-180"></span></span>

<span data-ttu-id="e48b4-181">安装 Windows 后，Microsoft 团队聊天室控制台应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。</span><span class="sxs-lookup"><span data-stu-id="e48b4-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="e48b4-182">将显示“用户帐户”屏幕。</span><span class="sxs-lookup"><span data-stu-id="e48b4-182">The User Account screen appears.</span></span> <span data-ttu-id="e48b4-183">输入的 Skype 登录地址 （以 user@domain 格式） 的会议室帐户将与控制台一起使用。</span><span class="sxs-lookup"><span data-stu-id="e48b4-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="e48b4-184">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="e48b4-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="e48b4-185">在"配置域"下的 FQDN 设置为 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="e48b4-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="e48b4-186">如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="e48b4-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="e48b4-187">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e48b4-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="e48b4-188">选择功能屏幕上的指定的设备，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e48b4-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="e48b4-189">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="e48b4-190">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="e48b4-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="e48b4-191">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="e48b4-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="e48b4-192">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="e48b4-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="e48b4-193">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="e48b4-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="e48b4-p119">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="e48b4-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="e48b4-196">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-196">Click **Finish**.</span></span>
    
<span data-ttu-id="e48b4-197">Microsoft 团队聊天室控制台应用程序应立即启动登录到 Skype 业务服务器与上面，输入的凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。</span><span class="sxs-lookup"><span data-stu-id="e48b4-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="e48b4-198">有关使用控制台应用程序的详细信息，请参阅[Microsoft 团队聊天室帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="e48b4-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e48b4-199">Microsoft 团队聊天室依赖于认证的控制台硬件的状态。</span><span class="sxs-lookup"><span data-stu-id="e48b4-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="e48b4-200">除非检测到控制台硬件，即使包含 Microsoft 团队聊天室控制台应用程序的正确创建的图像将无法启动过去的初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="e48b4-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="e48b4-201">对于 Surface Pro 基于解决方案，Surface Pro 必须连接到其相应的停靠硬件，传递此检查。</span><span class="sxs-lookup"><span data-stu-id="e48b4-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e48b4-202">某些非英语用户可能需要物理键盘初始安装过程中连接到控制台，在的触摸键盘上不支持符号。</span><span class="sxs-lookup"><span data-stu-id="e48b4-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="e48b4-203">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="e48b4-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="e48b4-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-204"></span></span>

<span data-ttu-id="e48b4-205">Microsoft 团队聊天室控制台需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="e48b4-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="e48b4-206">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="e48b4-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="e48b4-207">在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Microsoft 团队聊天室控制台证书：</span><span class="sxs-lookup"><span data-stu-id="e48b4-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="e48b4-208">可将控制台加入 Active Directory 和，将自动添加给定证书颁发机构所需的证书发布到 Active Directory （正常的部署选项）。</span><span class="sxs-lookup"><span data-stu-id="e48b4-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="e48b4-209">可以在映像过程后手动安装证书。</span><span class="sxs-lookup"><span data-stu-id="e48b4-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="e48b4-210">执行此操作之前，您必须完成[初始设置的控制台](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="e48b4-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="e48b4-211">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="e48b4-211">To manually install the certificate</span></span>

1. <span data-ttu-id="e48b4-212">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="e48b4-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="e48b4-213">控制台置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="e48b4-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="e48b4-214">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e48b4-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="e48b4-215">加入 Active Directory 域 （可选）</span><span class="sxs-lookup"><span data-stu-id="e48b4-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="e48b4-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-216"></span></span>

<span data-ttu-id="e48b4-217">Microsoft 团队聊天室控制台可以加入您的域。</span><span class="sxs-lookup"><span data-stu-id="e48b4-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="e48b4-218">应将 Microsoft 团队聊天室控制台放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Microsoft 团队聊天室兼容。</span><span class="sxs-lookup"><span data-stu-id="e48b4-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="e48b4-219">常见的示例是将阻止自动启动 Microsoft 团队聊天室的密码实施策略。</span><span class="sxs-lookup"><span data-stu-id="e48b4-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="e48b4-220">有关管理 GPO 设置的信息，请参阅[Manage Microsoft 团队 Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="e48b4-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="e48b4-221">若要加入到域的 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="e48b4-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="e48b4-222">登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="e48b4-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="e48b4-223">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e48b4-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="e48b4-224">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e48b4-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="e48b4-225">例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 并且您希望您的 Microsoft 团队聊天室控制台中的"资源"OU 的子级"Microsoft 团队聊天室"OU，将为该命令：</span><span class="sxs-lookup"><span data-stu-id="e48b4-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="e48b4-226">如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。</span><span class="sxs-lookup"><span data-stu-id="e48b4-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="e48b4-227">Microsoft 团队聊天室部署清单</span><span class="sxs-lookup"><span data-stu-id="e48b4-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="e48b4-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-228"></span></span>

<span data-ttu-id="e48b4-229">执行操作完全配置了控制台和所有外围设备最终验证时，使用以下清单：</span><span class="sxs-lookup"><span data-stu-id="e48b4-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="e48b4-230">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="e48b4-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e48b4-231">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-231">☐</span></span>  <br/> |<span data-ttu-id="e48b4-232">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="e48b4-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="e48b4-233">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-233">☐</span></span>  <br/> |<span data-ttu-id="e48b4-234">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="e48b4-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="e48b4-235">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-235">☐</span></span>  <br/> |<span data-ttu-id="e48b4-236">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="e48b4-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="e48b4-237">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-237">☐</span></span>  <br/> |<span data-ttu-id="e48b4-238">已应用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="e48b4-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="e48b4-239">**音频/视频外围设备**</span><span class="sxs-lookup"><span data-stu-id="e48b4-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e48b4-240">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-240">☐</span></span>  <br/> |<span data-ttu-id="e48b4-241">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="e48b4-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e48b4-242">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-242">☐</span></span>  <br/> |<span data-ttu-id="e48b4-243">摄像机功能和定位以最佳方式</span><span class="sxs-lookup"><span data-stu-id="e48b4-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="e48b4-244">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-244">☐</span></span>  <br/> |<span data-ttu-id="e48b4-245">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="e48b4-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e48b4-246">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-246">☐</span></span>  <br/> |<span data-ttu-id="e48b4-247">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="e48b4-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e48b4-248">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-248">☐</span></span>  <br/> |<span data-ttu-id="e48b4-249">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="e48b4-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e48b4-250">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-250">☐</span></span>  <br/> |<span data-ttu-id="e48b4-251">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="e48b4-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="e48b4-252">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-252">☐</span></span>  <br/> |<span data-ttu-id="e48b4-253">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="e48b4-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="e48b4-254">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="e48b4-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e48b4-255">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-255">☐</span></span>  <br/> |<span data-ttu-id="e48b4-256">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="e48b4-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="e48b4-257">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-257">☐</span></span>  <br/> |<span data-ttu-id="e48b4-258">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="e48b4-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e48b4-259">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-259">☐</span></span>  <br/> |<span data-ttu-id="e48b4-260">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="e48b4-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e48b4-261">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-261">☐</span></span>  <br/> |<span data-ttu-id="e48b4-262">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="e48b4-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="e48b4-263">☐</span><span class="sxs-lookup"><span data-stu-id="e48b4-263">☐</span></span>  <br/> |<span data-ttu-id="e48b4-264">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="e48b4-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e48b4-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e48b4-265">See also</span></span>
<span data-ttu-id="e48b4-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e48b4-266"></span></span>

[<span data-ttu-id="e48b4-267">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="e48b4-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e48b4-268">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="e48b4-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e48b4-269">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="e48b4-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="e48b4-270">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="e48b4-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
