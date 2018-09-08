---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。
ms.openlocfilehash: d652f4e7ccfd8b8630ce48b028f8f4ce7226a693
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887512"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c8a42-103">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="c8a42-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c8a42-104">本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。</span><span class="sxs-lookup"><span data-stu-id="c8a42-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="c8a42-105">如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述，应仅执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c8a42-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c8a42-106">您将需要的硬件和软件[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="c8a42-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c8a42-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="c8a42-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c8a42-108">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="c8a42-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="c8a42-109">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="c8a42-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c8a42-110">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用</span><span class="sxs-lookup"><span data-stu-id="c8a42-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c8a42-111">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="c8a42-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="c8a42-112">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="c8a42-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c8a42-113">Skype 会议室系统 v2 将其中的设备帐户正确设置[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述的业务环境正确配置 Skype 仅适用。</span><span class="sxs-lookup"><span data-stu-id="c8a42-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c8a42-114">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="c8a42-114">Prepare the installation media</span></span>
<span data-ttu-id="c8a42-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-115"></span></span>

<span data-ttu-id="c8a42-116">安装 Skype 会议室系统 v2 控制台应用程序需要具有至少 32 GB 内存格式设置为 FAT32 磁盘上的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="c8a42-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="c8a42-117">设备上不能有其他文件，USB 存储上的所有现有文件都会丢失。</span><span class="sxs-lookup"><span data-stu-id="c8a42-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8a42-118">未能创建 Skype 会议室系统 v2 安装媒体根据这些说明可能会导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="c8a42-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="c8a42-119">创建 Skype 会议室系统 v2 安装介质不再支持 Windows 10 企业周年日 Update (版本 1607)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8a42-120">与 Windows 10 企业周年日更新将移至通过 Windows 应用商店的 Skype 会议室系统 v2 更新 3 现有 Skype 会议室系统 v2，但应该执行全新安装，如下所述。</span><span class="sxs-lookup"><span data-stu-id="c8a42-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="c8a42-121">下载[CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c8a42-122">（可选）下载并置于同一目录为脚本的任何所需的语言包 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="c8a42-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="c8a42-123">该脚本将指示其中您可以下载语言包文件适用于您要创建的介质的类型，如果您不确定获取从的语言包的位置。</span><span class="sxs-lookup"><span data-stu-id="c8a42-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="c8a42-124">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="c8a42-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="c8a42-125">按照脚本的说明创建 Skype 会议室系统 v2 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c8a42-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="c8a42-126">完成后，从计算机中删除 USB 磁盘，并继续[安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c8a42-127">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用</span><span class="sxs-lookup"><span data-stu-id="c8a42-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c8a42-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-128"></span></span>

<span data-ttu-id="c8a42-129">您现在需要应用您已创建的安装媒体。</span><span class="sxs-lookup"><span data-stu-id="c8a42-129">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c8a42-130">目标设备将作为一种设备运行，并将设置的默认用户仅运行 Skype 会议室系统 v2 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8a42-130">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="c8a42-131">如果目标设备将安装中停靠 (如 Surface Pro)，断开与停靠连接。</span><span class="sxs-lookup"><span data-stu-id="c8a42-131">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c8a42-132">确保目标设备未连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c8a42-132">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c8a42-133">确保目标设备连接到 AC 电源。</span><span class="sxs-lookup"><span data-stu-id="c8a42-133">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c8a42-134">将插入目标设备在 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c8a42-134">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c8a42-135">引导到 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c8a42-135">Boot to the USB setup disk.</span></span> <span data-ttu-id="c8a42-136">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="c8a42-136">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c8a42-137">如果 Surface Pro 目标设备，使用以下步骤引导到 USB 安装磁盘：</span><span class="sxs-lookup"><span data-stu-id="c8a42-137">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="c8a42-138">按并继续按住下 （-） 按钮的卷。</span><span class="sxs-lookup"><span data-stu-id="c8a42-138">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="c8a42-139">按下并释放高级按钮。</span><span class="sxs-lookup"><span data-stu-id="c8a42-139">Press and release the power button.</span></span>

    3. <span data-ttu-id="c8a42-140">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c8a42-140">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c8a42-141">安装完成后，系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="c8a42-141">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c8a42-142">系统已关闭后，它是安全地移除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="c8a42-142">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c8a42-143">此时，可以将目标 devcie 放入其停靠 （如果使用基于停靠的产品）、 附加外围设备所需的会议室中，并连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c8a42-143">At this point, you can place the target devcie in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c8a42-144">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="c8a42-144">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="c8a42-145">在 Creator Update 中选择语言</span><span class="sxs-lookup"><span data-stu-id="c8a42-145">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="c8a42-146">创建者的更新，您需要在方案中使用 ApplyCurrentRegionAndLanguage.ps1 脚本隐式语言选择不提供所需的实际的应用程序语言的用户 (例如，需控制台应用程序采用法语，但它在接下来英语） （英文）。</span><span class="sxs-lookup"><span data-stu-id="c8a42-146">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8a42-147">以下说明仅工时控制台创建使用 Windows 创建者的更新。</span><span class="sxs-lookup"><span data-stu-id="c8a42-147">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c8a42-148">不使用媒体与新设置系统已设置的旧/市场系统不能使用这些说明，但应也不会受到影响从初始问题需要此手动干预 (周年日 Edition 让您选取您应用程序语言显式作为安装的一部分）。</span><span class="sxs-lookup"><span data-stu-id="c8a42-148">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c8a42-149">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="c8a42-149">To apply your desired language</span></span>

1. <span data-ttu-id="c8a42-150">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="c8a42-150">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c8a42-151">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="c8a42-151">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c8a42-152">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="c8a42-152">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c8a42-153">选中**时间&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="c8a42-153">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c8a42-154">选中**区域&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="c8a42-154">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c8a42-155">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-155">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c8a42-156">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="c8a42-156">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c8a42-157">选择您刚刚添加到"语言"列表的语言。</span><span class="sxs-lookup"><span data-stu-id="c8a42-157">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c8a42-158">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-158">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c8a42-159">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="c8a42-159">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c8a42-160">a.</span><span class="sxs-lookup"><span data-stu-id="c8a42-160">a.</span></span> <span data-ttu-id="c8a42-161">选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="c8a42-161">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c8a42-162">b.</span><span class="sxs-lookup"><span data-stu-id="c8a42-162">b.</span></span> <span data-ttu-id="c8a42-163">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-163">Select **Remove**.</span></span>
    
11. <span data-ttu-id="c8a42-164">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c8a42-164">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c8a42-165">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c8a42-165">Run the following command:</span></span> 
    
    <span data-ttu-id="c8a42-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="c8a42-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="c8a42-167">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="c8a42-167">Restart the system.</span></span>
    
<span data-ttu-id="c8a42-168">Skype 会议室系统 v2 控制台现在应用所需的语言。</span><span class="sxs-lookup"><span data-stu-id="c8a42-168">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c8a42-169">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="c8a42-169">Initial set up of the console</span></span>
<span data-ttu-id="c8a42-170"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-170"></span></span>

<span data-ttu-id="c8a42-171">安装 Windows 后，Skype 会议室系统 v2 控制台应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。</span><span class="sxs-lookup"><span data-stu-id="c8a42-171">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c8a42-172">将显示“用户帐户”屏幕。</span><span class="sxs-lookup"><span data-stu-id="c8a42-172">The User Account screen appears.</span></span> <span data-ttu-id="c8a42-173">输入的 Skype 登录地址 （以 user@domain 格式） 的会议室帐户将与控制台一起使用。</span><span class="sxs-lookup"><span data-stu-id="c8a42-173">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c8a42-174">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="c8a42-174">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c8a42-175">在"配置域"下的 FQDN 设置为 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="c8a42-175">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c8a42-176">如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="c8a42-176">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c8a42-177">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-177">Click **Next**.</span></span>
    
5. <span data-ttu-id="c8a42-178">选择功能屏幕上的指定的设备，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c8a42-178">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c8a42-179">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-179">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c8a42-180">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="c8a42-180">The devices to select are:</span></span>
    
   - <span data-ttu-id="c8a42-181">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="c8a42-181">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c8a42-182">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="c8a42-182">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c8a42-183">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="c8a42-183">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="c8a42-p115">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="c8a42-p115">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c8a42-186">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-186">Click **Finish**.</span></span>
    
<span data-ttu-id="c8a42-187">Skype 会议室系统 v2 控制台应用程序应立即启动登录到 Skype 业务服务器与上面，输入的凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。</span><span class="sxs-lookup"><span data-stu-id="c8a42-187">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c8a42-188">有关使用控制台应用程序的详细信息，请参阅[Skype 会议室系统版本 2 帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-188">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8a42-189">Skype 会议室系统 v2 依赖于认证的控制台硬件的状态。</span><span class="sxs-lookup"><span data-stu-id="c8a42-189">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c8a42-190">除非检测到控制台硬件，即使包含 Skype 会议室系统 v2 控制台应用程序的正确创建的图像将无法启动过去的初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="c8a42-190">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c8a42-191">对于 Surface Pro 基于解决方案，Surface Pro 必须连接到其相应的停靠硬件，传递此检查。</span><span class="sxs-lookup"><span data-stu-id="c8a42-191">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8a42-192">某些非英语用户可能需要物理键盘初始安装过程中连接到控制台，在的触摸键盘上不支持符号。</span><span class="sxs-lookup"><span data-stu-id="c8a42-192">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c8a42-193">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="c8a42-193">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c8a42-194"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-194"></span></span>

<span data-ttu-id="c8a42-195">Skype 会议室系统 v2 控制台需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="c8a42-195">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c8a42-196">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="c8a42-196">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c8a42-197">在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Skype 会议室系统 v2 控制台证书：</span><span class="sxs-lookup"><span data-stu-id="c8a42-197">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="c8a42-198">可将控制台加入 Active Directory 和，将自动添加给定证书颁发机构所需的证书发布到 Active Directory （正常的部署选项）。</span><span class="sxs-lookup"><span data-stu-id="c8a42-198">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c8a42-199">可以在映像过程后手动安装证书。</span><span class="sxs-lookup"><span data-stu-id="c8a42-199">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c8a42-200">执行此操作之前，您必须完成[初始设置的控制台](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-200">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c8a42-201">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="c8a42-201">To manually install the certificate</span></span>

1. <span data-ttu-id="c8a42-202">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="c8a42-202">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c8a42-203">控制台置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="c8a42-203">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c8a42-204">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c8a42-204">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c8a42-205">加入 Active Directory 域 （可选）</span><span class="sxs-lookup"><span data-stu-id="c8a42-205">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c8a42-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-206"></span></span>

<span data-ttu-id="c8a42-207">Skype 会议室系统 v2 控制台可以加入您的域。</span><span class="sxs-lookup"><span data-stu-id="c8a42-207">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="c8a42-208">应将 Skype 会议室系统 v2 控制台放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Skype 会议室系统 v2 兼容。</span><span class="sxs-lookup"><span data-stu-id="c8a42-208">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c8a42-209">常见的示例是将阻止自动启动 Skype 会议室系统 v2 的密码实施策略。</span><span class="sxs-lookup"><span data-stu-id="c8a42-209">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c8a42-210">有关管理 GPO 设置的信息，请参阅[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a42-210">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c8a42-211">将 Skype 会议室系统 v2 加入域</span><span class="sxs-lookup"><span data-stu-id="c8a42-211">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c8a42-212">登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="c8a42-212">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c8a42-213">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c8a42-213">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c8a42-214">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="c8a42-214">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="c8a42-215">例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 且您希望您 Skype 会议室系统 v2 控制台中"Skype 会议室系统 v2"是"Resources"OU 的子级的 OU，则可该命令：</span><span class="sxs-lookup"><span data-stu-id="c8a42-215">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c8a42-216">如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。</span><span class="sxs-lookup"><span data-stu-id="c8a42-216">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c8a42-217">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="c8a42-217">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="c8a42-218"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-218"></span></span>

<span data-ttu-id="c8a42-219">执行操作完全配置了控制台和所有外围设备最终验证时，使用以下清单：</span><span class="sxs-lookup"><span data-stu-id="c8a42-219">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c8a42-220">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="c8a42-220">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c8a42-221">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-221">☐</span></span>  <br/> |<span data-ttu-id="c8a42-222">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="c8a42-222">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c8a42-223">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-223">☐</span></span>  <br/> |<span data-ttu-id="c8a42-224">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="c8a42-224">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c8a42-225">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-225">☐</span></span>  <br/> |<span data-ttu-id="c8a42-226">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="c8a42-226">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c8a42-227">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-227">☐</span></span>  <br/> |<span data-ttu-id="c8a42-228">已应用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="c8a42-228">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c8a42-229">**音频/视频外围设备**</span><span class="sxs-lookup"><span data-stu-id="c8a42-229">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c8a42-230">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-230">☐</span></span>  <br/> |<span data-ttu-id="c8a42-231">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="c8a42-231">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c8a42-232">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-232">☐</span></span>  <br/> |<span data-ttu-id="c8a42-233">摄像机功能和定位以最佳方式</span><span class="sxs-lookup"><span data-stu-id="c8a42-233">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c8a42-234">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-234">☐</span></span>  <br/> |<span data-ttu-id="c8a42-235">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="c8a42-235">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c8a42-236">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-236">☐</span></span>  <br/> |<span data-ttu-id="c8a42-237">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="c8a42-237">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c8a42-238">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-238">☐</span></span>  <br/> |<span data-ttu-id="c8a42-239">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="c8a42-239">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c8a42-240">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-240">☐</span></span>  <br/> |<span data-ttu-id="c8a42-241">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="c8a42-241">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c8a42-242">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-242">☐</span></span>  <br/> |<span data-ttu-id="c8a42-243">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="c8a42-243">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c8a42-244">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="c8a42-244">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c8a42-245">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-245">☐</span></span>  <br/> |<span data-ttu-id="c8a42-246">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="c8a42-246">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c8a42-247">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-247">☐</span></span>  <br/> |<span data-ttu-id="c8a42-248">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="c8a42-248">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c8a42-249">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-249">☐</span></span>  <br/> |<span data-ttu-id="c8a42-250">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="c8a42-250">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c8a42-251">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-251">☐</span></span>  <br/> |<span data-ttu-id="c8a42-252">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="c8a42-252">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c8a42-253">☐</span><span class="sxs-lookup"><span data-stu-id="c8a42-253">☐</span></span>  <br/> |<span data-ttu-id="c8a42-254">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="c8a42-254">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c8a42-255">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8a42-255">See also</span></span>
<span data-ttu-id="c8a42-256"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a42-256"></span></span>

[<span data-ttu-id="c8a42-257">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="c8a42-257">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c8a42-258">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="c8a42-258">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c8a42-259">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="c8a42-259">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c8a42-260">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="c8a42-260">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)