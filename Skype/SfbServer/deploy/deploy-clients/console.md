---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。
ms.openlocfilehash: 6ca029fa7f5560dfdfebd789938d9b53ff2e9abc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="169fb-103">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="169fb-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="169fb-104">本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。</span><span class="sxs-lookup"><span data-stu-id="169fb-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="169fb-105">如果有必要 Skype 业务和 Exchange 帐户已经创建并测试[部署 Skype 的空间系统 v2](room-systems-v2.md)中所述，只应执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="169fb-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="169fb-106">您需要的硬件和软件[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="169fb-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="169fb-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="169fb-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="169fb-108">准备安装映像</span><span class="sxs-lookup"><span data-stu-id="169fb-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="169fb-109">在 tablet 设备上安装专用的 CA 证书</span><span class="sxs-lookup"><span data-stu-id="169fb-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="169fb-110">安装 Windows 10 和 Skype 的空间系统 v2 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="169fb-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="169fb-111">初始设置的控制台</span><span class="sxs-lookup"><span data-stu-id="169fb-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="169fb-112">Skype 的空间系统 v2 部署检查表</span><span class="sxs-lookup"><span data-stu-id="169fb-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="169fb-113">Skype 的空间系统 v2 仅在正确配置的 Skype 的其中设备帐户正确设置[部署 Skype 的空间系统 v2](room-systems-v2.md)中所述的业务环境中工作。</span><span class="sxs-lookup"><span data-stu-id="169fb-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="169fb-114">准备安装映像</span><span class="sxs-lookup"><span data-stu-id="169fb-114">Prepare the installation image</span></span>
<span data-ttu-id="169fb-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-115"></span></span>

<span data-ttu-id="169fb-116">Surface Pro 4 或 Surface Pro 上安装 Skype 的空间系统 v2 应用程序需要至少 32 gb 内存格式化为 FAT32 磁盘的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="169fb-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="169fb-117">应该有该设备上的任何其他文件、 USB 存储上的现有文件将会丢失。</span><span class="sxs-lookup"><span data-stu-id="169fb-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="169fb-118">如果未按照这些说明创建你的控制台映像，将很可能导致发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="169fb-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="169fb-119">Skype 的空间系统 v2 图像创建不再支持 Windows 10 企业纪念日更新 (版本 1607)。</span><span class="sxs-lookup"><span data-stu-id="169fb-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="169fb-120">现有的 Skype 的空间系统 v2 与 Windows 10 企业纪念日更新移动到 Windows 应用商店通过 Skype 的空间系统 v2 更新 3 起作用，但新的安装应按如下所述。</span><span class="sxs-lookup"><span data-stu-id="169fb-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="169fb-121">下载[KB4056892 的 MSU](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)。</span><span class="sxs-lookup"><span data-stu-id="169fb-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="169fb-122">下载[CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="169fb-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="169fb-123">CreateSrsMedia.ps1 脚本所在的目录中的 KB4056892 为 MSU 的地方。</span><span class="sxs-lookup"><span data-stu-id="169fb-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="169fb-124">Windows 10 机器上从提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="169fb-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="169fb-125">按照该脚本的说明创建 Skype 的空间系统 v2 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="169fb-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="169fb-126">完成后，从计算机上删除 U 盘，继续[安装 Windows 10 和 Skype 的空间系统 v2 控制台应用程序](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="169fb-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="169fb-127">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用 </span><span class="sxs-lookup"><span data-stu-id="169fb-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="169fb-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-128"></span></span>

<span data-ttu-id="169fb-129">现在，你需要应用创建的映像。</span><span class="sxs-lookup"><span data-stu-id="169fb-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="169fb-130">图形输入板作为一种设备将运行并将设置默认用户只能运行 Skype 的空间系统 v2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="169fb-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="169fb-131">应该将平板电脑连接到电源。</span><span class="sxs-lookup"><span data-stu-id="169fb-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="169fb-132">从完全断电的状态开始。</span><span class="sxs-lookup"><span data-stu-id="169fb-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="169fb-133">如有必要，请按下并按住电源按钮，直至平板电脑关闭。</span><span class="sxs-lookup"><span data-stu-id="169fb-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="169fb-134">将 USB 安装磁盘插入平板电脑。</span><span class="sxs-lookup"><span data-stu-id="169fb-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="169fb-135">按下并一直按住平板电脑上的调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="169fb-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="169fb-136">按下并释放平板电脑上的电源按钮。</span><span class="sxs-lookup"><span data-stu-id="169fb-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="169fb-137">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="169fb-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="169fb-138">Skype 的空间系统 v2 设备启动后第一次，其行为将取决于在 AutoUnattend.xml 文件中使用 Sysprep.exe 哪个版本 （请参阅[准备安装映像](console.md#Prep_Image)的步骤 7）：</span><span class="sxs-lookup"><span data-stu-id="169fb-138">When the Skype Room Systems v2 device starts for the first time, its behavior will depend on which version of Sysprep.exe is used in the AutoUnattend.xml file (see step 7 of [Prepare the installation image](console.md#Prep_Image)):</span></span>
    
   - <span data-ttu-id="169fb-p107">如果启用了 /shutdown 版本的命令，系统将继续执行安装并最终关闭。关闭后，你可以引导至包含 Windows PE 的外部媒体，并使用 DISM 安装语言包、应用映像、从计算机捕获引用映像或执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="169fb-p107">If the /shutdown version of the command was enabled, the system will proceed with installation and eventually shut down. Once it is shut down, you may boot to external media containing Windows PE and use DISM to install language packs, apply images, capture your reference image from the machine, or perform other actions.</span></span>
    
   - <span data-ttu-id="169fb-141">如果启用了 /reboot 版本的命令，系统将继续执行安装并最终要求用户选择其区域设置。</span><span class="sxs-lookup"><span data-stu-id="169fb-141">If the /reboot version of the command was enabled, the system will proceed with installation, and eventually ask the user to select their locale settings.</span></span> <span data-ttu-id="169fb-142">选择此选项后，Skype 的空间系统 v2 设备将引导至其初始启动进程。</span><span class="sxs-lookup"><span data-stu-id="169fb-142">After making this selection, the Skype Room Systems v2 device will boot into its initial startup process.</span></span> <span data-ttu-id="169fb-143">请参阅[控制台的初始设置](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="169fb-143">See [Initial set up of the Console ](console.md#Initial)</span></span>
    
<span data-ttu-id="169fb-144">关闭或重新启动系统后，安全做法是移除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="169fb-144">After the system has shut down or rebooted, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="169fb-145">此时，可以将平板电脑置于扩展坞中，并连接会议室所需的外围设备。</span><span class="sxs-lookup"><span data-stu-id="169fb-145">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="169fb-146">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="169fb-146">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="169fb-147">在 Creator Update 中选择语言</span><span class="sxs-lookup"><span data-stu-id="169fb-147">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="169fb-148">在创建者的更新，您需要选择隐式语言不提供用户提供他们所需的实际应用程序语言在方案中使用 ApplyCurrentRegionAndLanguage.ps1 脚本 （例如，他们想要的应用程序采用法语，但它是在接下来英语）。</span><span class="sxs-lookup"><span data-stu-id="169fb-148">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="169fb-149">以下说明仅适用于使用 Windows Creator Update 创建的设备。</span><span class="sxs-lookup"><span data-stu-id="169fb-149">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="169fb-150">尚未正确地重新映像至新设置系统的传统/已上市系统将无法使用这些说明，但应该不会受到需要手动干预的初始问题困扰（Anniversary Edition 允许你在设置中显式选择应用语言）。</span><span class="sxs-lookup"><span data-stu-id="169fb-150">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="169fb-151">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="169fb-151">To apply your desired language</span></span>

1. <span data-ttu-id="169fb-152">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="169fb-152">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="169fb-153">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="169fb-153">Select the Start menu.</span></span>
    
3. <span data-ttu-id="169fb-154">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="169fb-154">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="169fb-155">选择**时间&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="169fb-155">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="169fb-156">选择**地区&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="169fb-156">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="169fb-157">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="169fb-157">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="169fb-158">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="169fb-158">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="169fb-159">选择刚刚添加到"语言"列表中的语言。</span><span class="sxs-lookup"><span data-stu-id="169fb-159">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="169fb-160">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="169fb-160">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="169fb-161">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="169fb-161">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="169fb-162">a.</span><span class="sxs-lookup"><span data-stu-id="169fb-162">a.</span></span> <span data-ttu-id="169fb-163">选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="169fb-163">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="169fb-164">b.</span><span class="sxs-lookup"><span data-stu-id="169fb-164">b.</span></span> <span data-ttu-id="169fb-165">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="169fb-165">Select **Remove**.</span></span>
    
11. <span data-ttu-id="169fb-166">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="169fb-166">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="169fb-167">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="169fb-167">Run the following command:</span></span> 
    
    <span data-ttu-id="169fb-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="169fb-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="169fb-169">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="169fb-169">Restart the system.</span></span>
    
<span data-ttu-id="169fb-170">现在到 Skype 的空间系统 v2 设备应用所需的语言。</span><span class="sxs-lookup"><span data-stu-id="169fb-170">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="169fb-171">控制台的初始设置 </span><span class="sxs-lookup"><span data-stu-id="169fb-171">Initial set up of the Console</span></span>
<span data-ttu-id="169fb-172"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-172"></span></span>

<span data-ttu-id="169fb-173">在安装 Windows 之后，在启动下一步时，或如果 /reboot 选项选择 Skype 的空间系统 v2 应用程序将进入其初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="169fb-173">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="169fb-p113">将显示“用户帐户”屏幕。输入要在该设备中使用的会议室帐户的 Skype 登录地址（格式为 user@domain）。</span><span class="sxs-lookup"><span data-stu-id="169fb-p113">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="169fb-176">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="169fb-176">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="169fb-177">在"配置域"下设置 FQDN Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="169fb-177">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="169fb-178">如果业务 SIP 域的 Skype 是从用户的 Exchange 域不同，在此字段中输入 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="169fb-178">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="169fb-179">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="169fb-179">Click **Next**.</span></span>
    
5. <span data-ttu-id="169fb-180">选择功能在屏幕上的指示的设备，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="169fb-180">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="169fb-181">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="169fb-181">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="169fb-182">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="169fb-182">The devices to select are:</span></span>
    
   - <span data-ttu-id="169fb-183">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="169fb-183">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="169fb-184">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="169fb-184">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="169fb-185">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="169fb-185">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="169fb-p116">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="169fb-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="169fb-188">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="169fb-188">Click **Finish**.</span></span>
    
<span data-ttu-id="169fb-189">应用程序应立即开始登录 Skype 业务服务器 2015年的上面，输入凭据，应开始使用这些相同的凭据交换与同步其日历。</span><span class="sxs-lookup"><span data-stu-id="169fb-189">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="169fb-190">有关使用应用程序的详细信息，请参阅[Skype 的空间系统第 2 版的帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="169fb-190">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="169fb-191">Skype 的空间系统 v2 依赖认证的控制台硬件 (Logitech SmartDock) 的存在。</span><span class="sxs-lookup"><span data-stu-id="169fb-191">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="169fb-192">即使正确创建的映像包含加载 Surface Pro 4 或 Surface Pro Skype 的空间系统 v2 应用程序无法启动过去的初始安装过程除非检测到该控制台的硬件。</span><span class="sxs-lookup"><span data-stu-id="169fb-192">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="169fb-193">在初始安装过程中，如果发生触摸键盘不支持某些符号的情况，一些非英语用户可能需要连接到控制台的物理键盘。</span><span class="sxs-lookup"><span data-stu-id="169fb-193">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="169fb-194">在平板电脑设备上安装私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="169fb-194">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="169fb-195"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-195"></span></span>

<span data-ttu-id="169fb-196">Skype 的空间系统 v2 设备都需要信任通过 Skype 使用它连接到您的业务和 Exchange 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="169fb-196">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="169fb-197">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="169fb-197">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="169fb-198">在证书颁发机构是私有的其中一个用例实例与 Active Directory 和 Windows 证书颁发机构，在内部部署中可以将证书添加到 Skype 的空间系统 v2 设备采用两种方法：</span><span class="sxs-lookup"><span data-stu-id="169fb-198">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="169fb-199">如果证书颁发机构已发布至 Active Directory（标准部署选项），则可将设备加入 Active Directory，此操作会自动添加所需证书。</span><span class="sxs-lookup"><span data-stu-id="169fb-199">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="169fb-p120">可以在映像过程后手动安装证书。在此之前，必须完成[控制台的初始设置](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="169fb-p120">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="169fb-202">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="169fb-202">To manually install the certificate</span></span>

1. <span data-ttu-id="169fb-203">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="169fb-203">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="169fb-204">在管理员模式下放置曲面 4 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="169fb-204">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="169fb-205">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="169fb-205">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="169fb-206">加入 Active Directory 域（可选）</span><span class="sxs-lookup"><span data-stu-id="169fb-206">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="169fb-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-207"></span></span>

<span data-ttu-id="169fb-208">Skype 的空间系统 v2 设备可以加入域。</span><span class="sxs-lookup"><span data-stu-id="169fb-208">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="169fb-209">Skype 的空间系统 v2 设备应位于 PC 工作站从一个单独的 OU，因为许多工作站策略不兼容与 Skype 的空间系统 v2。</span><span class="sxs-lookup"><span data-stu-id="169fb-209">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="169fb-210">一个常见的例子是，以防 Skype 的空间系统 v2 自动启动密码实施策略。</span><span class="sxs-lookup"><span data-stu-id="169fb-210">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="169fb-211">GPO 设置的管理有关的信息，请参阅[管理 Skype 的空间系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="169fb-211">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="169fb-212">将 Skype 会议室系统 v2 加入域</span><span class="sxs-lookup"><span data-stu-id="169fb-212">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="169fb-213">登录到控制台的管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="169fb-213">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="169fb-214">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="169fb-214">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="169fb-215">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="169fb-215">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="169fb-216">例如，如果您完全限定的域名是 redmond.corp.microsoft.com 并且要 Skype 的空间系统 v2 设备处于"Skype 的空间系统 v2""资源"OU 的子 OU 中，该命令将是：</span><span class="sxs-lookup"><span data-stu-id="169fb-216">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="169fb-217">如果您想要重命名此计算机加入一个域时，请使用跟计算机的新名称的新标志。</span><span class="sxs-lookup"><span data-stu-id="169fb-217">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="169fb-218">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="169fb-218">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="169fb-219"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-219"></span></span>

<span data-ttu-id="169fb-220">在最终验证控制台设备及其所有外围设备是否已进行完全配置时，请使用下面的清单：</span><span class="sxs-lookup"><span data-stu-id="169fb-220">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="169fb-221">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="169fb-221">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="169fb-222">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-222">☐</span></span>  <br/> |<span data-ttu-id="169fb-223">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="169fb-223">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="169fb-224">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-224">☐</span></span>  <br/> |<span data-ttu-id="169fb-225">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="169fb-225">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="169fb-226">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-226">☐</span></span>  <br/> |<span data-ttu-id="169fb-227">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="169fb-227">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="169fb-228">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-228">☐</span></span>  <br/> |<span data-ttu-id="169fb-229">已应用所有 Surface Pro 4 或 Surface Pro 系统更新</span><span class="sxs-lookup"><span data-stu-id="169fb-229">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="169fb-230">**音频/视频外设**</span><span class="sxs-lookup"><span data-stu-id="169fb-230">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="169fb-231">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-231">☐</span></span>  <br/> |<span data-ttu-id="169fb-232">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="169fb-232">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="169fb-233">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-233">☐</span></span>  <br/> |<span data-ttu-id="169fb-234">照相机功能和最佳定位</span><span class="sxs-lookup"><span data-stu-id="169fb-234">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="169fb-235">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-235">☐</span></span>  <br/> |<span data-ttu-id="169fb-236">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="169fb-236">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="169fb-237">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-237">☐</span></span>  <br/> |<span data-ttu-id="169fb-238">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="169fb-238">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="169fb-239">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-239">☐</span></span>  <br/> |<span data-ttu-id="169fb-240">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="169fb-240">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="169fb-241">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-241">☐</span></span>  <br/> |<span data-ttu-id="169fb-242">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="169fb-242">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="169fb-243">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-243">☐</span></span>  <br/> |<span data-ttu-id="169fb-244">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="169fb-244">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="169fb-245">**坞站**</span><span class="sxs-lookup"><span data-stu-id="169fb-245">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="169fb-246">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-246">☐</span></span>  <br/> |<span data-ttu-id="169fb-247">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="169fb-247">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="169fb-248">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-248">☐</span></span>  <br/> |<span data-ttu-id="169fb-249">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="169fb-249">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="169fb-250">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-250">☐</span></span>  <br/> |<span data-ttu-id="169fb-251">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="169fb-251">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="169fb-252">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-252">☐</span></span>  <br/> |<span data-ttu-id="169fb-253">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="169fb-253">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="169fb-254">☐</span><span class="sxs-lookup"><span data-stu-id="169fb-254">☐</span></span>  <br/> |<span data-ttu-id="169fb-255">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="169fb-255">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="169fb-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="169fb-256">See also</span></span>
<span data-ttu-id="169fb-257"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="169fb-257"></span></span>

#### 

[<span data-ttu-id="169fb-258">Skype 的空间规划系统 v2</span><span class="sxs-lookup"><span data-stu-id="169fb-258">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="169fb-259">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="169fb-259">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="169fb-260">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="169fb-260">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="169fb-261">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="169fb-261">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

