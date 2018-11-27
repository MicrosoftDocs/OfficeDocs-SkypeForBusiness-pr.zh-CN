---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。
ms.openlocfilehash: 01bc2fe49fc56a4926563ad18e384455ef437b77
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699428"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="372c1-103">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="372c1-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="372c1-104">本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。</span><span class="sxs-lookup"><span data-stu-id="372c1-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="372c1-105">如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述，应仅执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="372c1-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="372c1-106">您将需要的硬件和软件[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="372c1-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="372c1-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="372c1-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="372c1-108">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="372c1-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="372c1-109">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="372c1-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="372c1-110">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用</span><span class="sxs-lookup"><span data-stu-id="372c1-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="372c1-111">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="372c1-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="372c1-112">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="372c1-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="372c1-113">Skype 会议室系统 v2 将其中的设备帐户正确设置[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述的业务环境正确配置 Skype 仅适用。</span><span class="sxs-lookup"><span data-stu-id="372c1-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="372c1-114">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="372c1-114">Prepare the installation media</span></span>
<span data-ttu-id="372c1-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-115"></span></span>

<span data-ttu-id="372c1-116">安装 Skype 会议室系统 v2 控制台应用程序需要具有至少 32 GB 内存格式设置为 FAT32 磁盘上的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="372c1-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="372c1-117">设备上不能有其他文件，USB 存储上的所有现有文件都会丢失。</span><span class="sxs-lookup"><span data-stu-id="372c1-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="372c1-118">未能创建 Skype 会议室系统 v2 安装媒体根据这些说明可能会导致意外的行为。</span><span class="sxs-lookup"><span data-stu-id="372c1-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="372c1-119">创建 Skype 会议室系统 v2 安装介质不再支持 Windows 10 企业周年日 Update (版本 1607)。</span><span class="sxs-lookup"><span data-stu-id="372c1-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="372c1-120">与 Windows 10 企业移动到作为 Windows 应用商店的 Skype 会议室系统 v2 更新 3 现有 Skype 会议室系统 v2，但应该执行全新安装，如下所述。</span><span class="sxs-lookup"><span data-stu-id="372c1-120">An existing Skype Room Systems v2 with Windows 10 Enterprise moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="372c1-121">下载 [CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。 </span><span class="sxs-lookup"><span data-stu-id="372c1-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="372c1-122">（可选）下载并置于同一目录为脚本的任何所需的语言包 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="372c1-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="372c1-123">该脚本将指示其中您可以下载语言包文件适用于您要创建的介质的类型，如果您不确定获取从的语言包的位置。</span><span class="sxs-lookup"><span data-stu-id="372c1-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="372c1-124">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="372c1-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="372c1-125">按照脚本的说明创建 Skype 会议室系统 v2 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="372c1-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="372c1-126">完成后，从计算机中删除 USB 磁盘，并继续[安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="372c1-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

> [!TIP]
> <span data-ttu-id="372c1-127">您可能已经注意到我们不再标注的驱动程序、 Skype 会议室系统 v2 客户端或 Windows 10 企业的特定版本。</span><span class="sxs-lookup"><span data-stu-id="372c1-127">You might have noticed that we no longer call out specific versions of the drivers, Skype Room Systems v2 client, or Windows 10 Enterprise.</span></span> <span data-ttu-id="372c1-128">这是谨慎，我们希望了脚本，以匹配项，并验证所有安装程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="372c1-128">This is deliberate, we want the script to match and verify compatibility for all installers.</span></span> <span data-ttu-id="372c1-129">该脚本将自动查找和获取的受支持的配置所需。</span><span class="sxs-lookup"><span data-stu-id="372c1-129">The script will automatically find and get what it needs for a supported configuration.</span></span>  
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="372c1-130">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用</span><span class="sxs-lookup"><span data-stu-id="372c1-130">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="372c1-131"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-131"></span></span>

<span data-ttu-id="372c1-132">您现在需要应用您已创建的安装媒体。</span><span class="sxs-lookup"><span data-stu-id="372c1-132">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="372c1-133">目标设备将作为一种设备运行，并将设置的默认用户仅运行 Skype 会议室系统 v2 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="372c1-133">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="372c1-134">如果目标设备将安装中停靠 (如 Surface Pro)，断开与停靠连接。</span><span class="sxs-lookup"><span data-stu-id="372c1-134">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="372c1-135">确保目标设备未连接到网络。</span><span class="sxs-lookup"><span data-stu-id="372c1-135">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="372c1-136">确保目标设备连接到 AC 电源。</span><span class="sxs-lookup"><span data-stu-id="372c1-136">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="372c1-137">将插入目标设备在 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="372c1-137">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="372c1-138">引导到 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="372c1-138">Boot to the USB setup disk.</span></span> <span data-ttu-id="372c1-139">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="372c1-139">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="372c1-140">如果 Surface Pro 目标设备，使用以下步骤引导到 USB 安装磁盘：</span><span class="sxs-lookup"><span data-stu-id="372c1-140">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="372c1-141">按并继续按住下 （-） 按钮的卷。</span><span class="sxs-lookup"><span data-stu-id="372c1-141">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="372c1-142">按下并释放高级按钮。</span><span class="sxs-lookup"><span data-stu-id="372c1-142">Press and release the power button.</span></span>

    3. <span data-ttu-id="372c1-143">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="372c1-143">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="372c1-144">安装完成后，系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="372c1-144">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="372c1-145">系统已关闭后，它是安全地移除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="372c1-145">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="372c1-146">此时，可以将目标 devcie 放入其停靠 （如果使用基于停靠的产品）、 附加外围设备所需的会议室中，并连接到网络。</span><span class="sxs-lookup"><span data-stu-id="372c1-146">At this point, you can place the target devcie in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="372c1-147">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="372c1-147">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="372c1-148">在 Creator Update 中选择语言</span><span class="sxs-lookup"><span data-stu-id="372c1-148">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="372c1-149">创建者的更新，您需要在方案中使用 ApplyCurrentRegionAndLanguage.ps1 脚本隐式语言选择不提供所需的实际的应用程序语言的用户 (例如，需控制台应用程序采用法语，但它在接下来英语） （英文）。</span><span class="sxs-lookup"><span data-stu-id="372c1-149">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="372c1-150">以下说明仅工时控制台创建使用 Windows 创建者的更新。</span><span class="sxs-lookup"><span data-stu-id="372c1-150">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="372c1-151">不使用媒体与新设置系统已设置的旧/市场系统不能使用这些说明，但应也不会受到影响从初始问题需要此手动干预 (周年日 Edition 让您选取您应用程序语言显式作为安装的一部分）。</span><span class="sxs-lookup"><span data-stu-id="372c1-151">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="372c1-152">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="372c1-152">To apply your desired language</span></span>

1. <span data-ttu-id="372c1-153">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="372c1-153">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="372c1-154">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="372c1-154">Select the Start menu.</span></span>
    
3. <span data-ttu-id="372c1-155">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="372c1-155">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="372c1-156">选中**时间&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="372c1-156">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="372c1-157">选中**区域&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="372c1-157">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="372c1-158">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="372c1-158">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="372c1-159">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="372c1-159">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="372c1-160">选择您刚刚添加到"语言"列表的语言。</span><span class="sxs-lookup"><span data-stu-id="372c1-160">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="372c1-161">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="372c1-161">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="372c1-162">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="372c1-162">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="372c1-p111">a. 选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="372c1-p111">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="372c1-p112">b. 选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="372c1-p112">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="372c1-167">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="372c1-167">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="372c1-168">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="372c1-168">Run the following command:</span></span> 
    
    <span data-ttu-id="372c1-169">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="372c1-169">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="372c1-170">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="372c1-170">Restart the system.</span></span>
    
<span data-ttu-id="372c1-171">Skype 会议室系统 v2 控制台现在应用所需的语言。</span><span class="sxs-lookup"><span data-stu-id="372c1-171">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="372c1-172">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="372c1-172">Initial set up of the console</span></span>
<span data-ttu-id="372c1-173"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-173"></span></span>

<span data-ttu-id="372c1-174">安装 Windows 后，Skype 会议室系统 v2 控制台应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。</span><span class="sxs-lookup"><span data-stu-id="372c1-174">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="372c1-175">将显示“用户帐户”屏幕。</span><span class="sxs-lookup"><span data-stu-id="372c1-175">The User Account screen appears.</span></span> <span data-ttu-id="372c1-176">输入的 Skype 登录地址 （以 user@domain 格式） 的会议室帐户将与控制台一起使用。</span><span class="sxs-lookup"><span data-stu-id="372c1-176">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="372c1-177">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="372c1-177">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="372c1-178">在"配置域"下的 FQDN 设置为 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="372c1-178">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="372c1-179">如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="372c1-179">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="372c1-180">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="372c1-180">Click **Next**.</span></span>
    
5. <span data-ttu-id="372c1-181">选择功能屏幕上的指定的设备，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="372c1-181">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="372c1-182">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="372c1-182">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="372c1-183">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="372c1-183">The devices to select are:</span></span>
    
   - <span data-ttu-id="372c1-184">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="372c1-184">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="372c1-185">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="372c1-185">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="372c1-186">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="372c1-186">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="372c1-p116">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="372c1-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="372c1-189">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="372c1-189">Click **Finish**.</span></span>
    
<span data-ttu-id="372c1-190">Skype 会议室系统 v2 控制台应用程序应立即启动登录到 Skype 业务服务器与上面，输入的凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。</span><span class="sxs-lookup"><span data-stu-id="372c1-190">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="372c1-191">有关使用控制台应用程序的详细信息，请参阅[Skype 会议室系统版本 2 帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="372c1-191">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="372c1-192">Skype 会议室系统 v2 依赖于认证的控制台硬件的状态。</span><span class="sxs-lookup"><span data-stu-id="372c1-192">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="372c1-193">除非检测到控制台硬件，即使包含 Skype 会议室系统 v2 控制台应用程序的正确创建的图像将无法启动过去的初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="372c1-193">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="372c1-194">对于 Surface Pro 基于解决方案，Surface Pro 必须连接到其相应的停靠硬件，传递此检查。</span><span class="sxs-lookup"><span data-stu-id="372c1-194">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="372c1-195">某些非英语用户可能需要物理键盘初始安装过程中连接到控制台，在的触摸键盘上不支持符号。</span><span class="sxs-lookup"><span data-stu-id="372c1-195">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="372c1-196">在控制台上安装一个私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="372c1-196">Install a private CA certificate on the console</span></span>
<span data-ttu-id="372c1-197"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-197"></span></span>

<span data-ttu-id="372c1-198">Skype 会议室系统 v2 控制台需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="372c1-198">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="372c1-199">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="372c1-199">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="372c1-200">在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Skype 会议室系统 v2 控制台证书：</span><span class="sxs-lookup"><span data-stu-id="372c1-200">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="372c1-201">可将控制台加入 Active Directory 和，将自动添加给定证书颁发机构所需的证书发布到 Active Directory （正常的部署选项）。</span><span class="sxs-lookup"><span data-stu-id="372c1-201">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="372c1-202">可以在映像过程后手动安装证书。</span><span class="sxs-lookup"><span data-stu-id="372c1-202">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="372c1-203">执行此操作之前，您必须完成[初始设置的控制台](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="372c1-203">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="372c1-204">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="372c1-204">To manually install the certificate</span></span>

1. <span data-ttu-id="372c1-205">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="372c1-205">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="372c1-206">控制台置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="372c1-206">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="372c1-207">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="372c1-207">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="372c1-208">加入 Active Directory 域 （可选）</span><span class="sxs-lookup"><span data-stu-id="372c1-208">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="372c1-209"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-209"></span></span>

<span data-ttu-id="372c1-210">Skype 会议室系统 v2 控制台可以加入您的域。</span><span class="sxs-lookup"><span data-stu-id="372c1-210">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="372c1-211">应将 Skype 会议室系统 v2 控制台放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Skype 会议室系统 v2 兼容。</span><span class="sxs-lookup"><span data-stu-id="372c1-211">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="372c1-212">常见的示例是将阻止自动启动 Skype 会议室系统 v2 的密码实施策略。</span><span class="sxs-lookup"><span data-stu-id="372c1-212">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="372c1-213">有关 GPO 设置管理的信息，请参阅[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="372c1-213">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="372c1-214">将 Skype 会议室系统 v2 加入域</span><span class="sxs-lookup"><span data-stu-id="372c1-214">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="372c1-215">登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="372c1-215">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="372c1-216">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="372c1-216">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="372c1-217">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="372c1-217">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="372c1-218">例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 且您希望您 Skype 会议室系统 v2 控制台中"Skype 会议室系统 v2"是"Resources"OU 的子级的 OU，则可该命令：</span><span class="sxs-lookup"><span data-stu-id="372c1-218">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="372c1-219">如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。</span><span class="sxs-lookup"><span data-stu-id="372c1-219">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="372c1-220">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="372c1-220">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="372c1-221"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-221"></span></span>

<span data-ttu-id="372c1-222">执行操作完全配置了控制台和所有外围设备最终验证时，使用以下清单：</span><span class="sxs-lookup"><span data-stu-id="372c1-222">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="372c1-223">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="372c1-223">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="372c1-224">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-224">☐</span></span>  <br/> |<span data-ttu-id="372c1-225">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="372c1-225">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="372c1-226">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-226">☐</span></span>  <br/> |<span data-ttu-id="372c1-227">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="372c1-227">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="372c1-228">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-228">☐</span></span>  <br/> |<span data-ttu-id="372c1-229">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="372c1-229">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="372c1-230">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-230">☐</span></span>  <br/> |<span data-ttu-id="372c1-231">已应用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="372c1-231">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="372c1-232">**音频/视频外围设备**</span><span class="sxs-lookup"><span data-stu-id="372c1-232">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="372c1-233">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-233">☐</span></span>  <br/> |<span data-ttu-id="372c1-234">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="372c1-234">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="372c1-235">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-235">☐</span></span>  <br/> |<span data-ttu-id="372c1-236">摄像机功能和定位以最佳方式</span><span class="sxs-lookup"><span data-stu-id="372c1-236">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="372c1-237">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-237">☐</span></span>  <br/> |<span data-ttu-id="372c1-238">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="372c1-238">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="372c1-239">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-239">☐</span></span>  <br/> |<span data-ttu-id="372c1-240">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="372c1-240">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="372c1-241">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-241">☐</span></span>  <br/> |<span data-ttu-id="372c1-242">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="372c1-242">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="372c1-243">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-243">☐</span></span>  <br/> |<span data-ttu-id="372c1-244">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="372c1-244">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="372c1-245">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-245">☐</span></span>  <br/> |<span data-ttu-id="372c1-246">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="372c1-246">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="372c1-247">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="372c1-247">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="372c1-248">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-248">☐</span></span>  <br/> |<span data-ttu-id="372c1-249">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="372c1-249">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="372c1-250">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-250">☐</span></span>  <br/> |<span data-ttu-id="372c1-251">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="372c1-251">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="372c1-252">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-252">☐</span></span>  <br/> |<span data-ttu-id="372c1-253">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="372c1-253">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="372c1-254">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-254">☐</span></span>  <br/> |<span data-ttu-id="372c1-255">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="372c1-255">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="372c1-256">☐</span><span class="sxs-lookup"><span data-stu-id="372c1-256">☐</span></span>  <br/> |<span data-ttu-id="372c1-257">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="372c1-257">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="372c1-258">另请参阅</span><span class="sxs-lookup"><span data-stu-id="372c1-258">See also</span></span>
<span data-ttu-id="372c1-259"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="372c1-259"></span></span>

[<span data-ttu-id="372c1-260">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="372c1-260">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="372c1-261">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="372c1-261">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="372c1-262">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="372c1-262">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="372c1-263">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="372c1-263">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)