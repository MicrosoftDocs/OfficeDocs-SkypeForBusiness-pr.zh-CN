---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。
ms.openlocfilehash: e9675b091723dc3b021543acedd278404788be13
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013694"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="f0e26-103">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="f0e26-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="f0e26-104">本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。</span><span class="sxs-lookup"><span data-stu-id="f0e26-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="f0e26-105">如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述，应仅执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f0e26-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="f0e26-106">您将需要的硬件和软件[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="f0e26-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="f0e26-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="f0e26-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="f0e26-108">准备安装映像</span><span class="sxs-lookup"><span data-stu-id="f0e26-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="f0e26-109">在平板电脑设备上安装私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="f0e26-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="f0e26-110">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="f0e26-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="f0e26-111">初始设置控制台</span><span class="sxs-lookup"><span data-stu-id="f0e26-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="f0e26-112">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="f0e26-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="f0e26-113">Skype 会议室系统 v2 将其中的设备帐户正确设置[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述的业务环境正确配置 Skype 仅适用。</span><span class="sxs-lookup"><span data-stu-id="f0e26-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="f0e26-114">准备安装映像</span><span class="sxs-lookup"><span data-stu-id="f0e26-114">Prepare the installation image</span></span>
<span data-ttu-id="f0e26-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-115"></span></span>

<span data-ttu-id="f0e26-116">Surface Pro 4 或 Surface Pro 上安装 Skype 会议室系统 v2 应用程序需要具有至少 32 GB 内存格式设置为 FAT32 磁盘上的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="f0e26-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="f0e26-117">设备上不能有其他文件，USB 存储上的所有现有文件都会丢失。</span><span class="sxs-lookup"><span data-stu-id="f0e26-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0e26-118">如果未按照这些说明创建你的控制台映像，将很可能导致发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="f0e26-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="f0e26-119">Skype 会议室系统 v2 图像创建不再支持 Windows 10 企业周年日 Update (版本 1607)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0e26-120">与 Windows 10 企业周年日更新将移至通过 Windows 应用商店的 Skype 会议室系统 v2 更新 3 现有 Skype 会议室系统 v2，但应该执行全新安装，如下所述。</span><span class="sxs-lookup"><span data-stu-id="f0e26-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="f0e26-121">下载[CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="f0e26-122">（可选）下载并置于同一目录为脚本的任何所需的语言包 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="f0e26-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="f0e26-123">该脚本将指示其中您可以下载语言包文件适用于您要创建的介质的类型，如果您不确定获取从的语言包的位置。</span><span class="sxs-lookup"><span data-stu-id="f0e26-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="f0e26-124">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="f0e26-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="f0e26-125">按照脚本的说明创建 Skype 会议室系统 v2 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="f0e26-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="f0e26-126">完成后将 USB 磁盘从你的计算机上移除，并继续[安装 Windows 10 和 Skype 会议室系统 v2 控制台应用](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="f0e26-127">安装 Windows 10 和 Skype 会议室系统 v2 控制台应用</span><span class="sxs-lookup"><span data-stu-id="f0e26-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="f0e26-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-128"></span></span>

<span data-ttu-id="f0e26-129">现在，你需要应用创建的映像。</span><span class="sxs-lookup"><span data-stu-id="f0e26-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="f0e26-130">平板电脑将运行作为一种设备，并将设置的默认用户仅运行 Skype 会议室系统 v2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0e26-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="f0e26-131">应该将平板电脑连接到电源。</span><span class="sxs-lookup"><span data-stu-id="f0e26-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="f0e26-132">从完全断电的状态开始。</span><span class="sxs-lookup"><span data-stu-id="f0e26-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="f0e26-133">如有必要，请按下并按住电源按钮，直至平板电脑关闭。</span><span class="sxs-lookup"><span data-stu-id="f0e26-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="f0e26-134">将 USB 安装磁盘插入平板电脑。</span><span class="sxs-lookup"><span data-stu-id="f0e26-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="f0e26-135">按下并一直按住平板电脑上的调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f0e26-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="f0e26-136">按下并释放平板电脑上的电源按钮。</span><span class="sxs-lookup"><span data-stu-id="f0e26-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="f0e26-137">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f0e26-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="f0e26-138">安装完成后，系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="f0e26-138">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="f0e26-139">系统已关闭后，它是安全地移除 USB 安装盘。</span><span class="sxs-lookup"><span data-stu-id="f0e26-139">After the system has shut down, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="f0e26-140">此时，可以将平板电脑置于扩展坞中，并连接会议室所需的外围设备。</span><span class="sxs-lookup"><span data-stu-id="f0e26-140">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="f0e26-141">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="f0e26-141">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="f0e26-142">在 Creator Update 中选择语言</span><span class="sxs-lookup"><span data-stu-id="f0e26-142">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="f0e26-143">在创建者的更新中，您将需要使用 ApplyCurrentRegionAndLanguage.ps1 脚本方案中隐式语言选择不提供所需的实际的应用程序语言的用户 （例如，所需应用程序采用法语，但它是在接下来英语） （英文）。</span><span class="sxs-lookup"><span data-stu-id="f0e26-143">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0e26-144">以下说明仅适用于使用 Windows Creator Update 创建的设备。</span><span class="sxs-lookup"><span data-stu-id="f0e26-144">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="f0e26-145">尚未正确地重新映像至新设置系统的传统/已上市系统将无法使用这些说明，但应该不会受到需要手动干预的初始问题困扰（Anniversary Edition 允许你在设置中显式选择应用语言）。</span><span class="sxs-lookup"><span data-stu-id="f0e26-145">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="f0e26-146">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="f0e26-146">To apply your desired language</span></span>

1. <span data-ttu-id="f0e26-147">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="f0e26-147">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="f0e26-148">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="f0e26-148">Select the Start menu.</span></span>
    
3. <span data-ttu-id="f0e26-149">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="f0e26-149">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="f0e26-150">选中**时间&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="f0e26-150">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="f0e26-151">选中**区域&amp;语言**。</span><span class="sxs-lookup"><span data-stu-id="f0e26-151">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="f0e26-152">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-152">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="f0e26-153">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="f0e26-153">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="f0e26-154">选择您刚刚添加到"语言"列表的语言。</span><span class="sxs-lookup"><span data-stu-id="f0e26-154">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="f0e26-155">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-155">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="f0e26-156">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="f0e26-156">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="f0e26-157">a.</span><span class="sxs-lookup"><span data-stu-id="f0e26-157">a.</span></span> <span data-ttu-id="f0e26-158">选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="f0e26-158">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="f0e26-159">b.</span><span class="sxs-lookup"><span data-stu-id="f0e26-159">b.</span></span> <span data-ttu-id="f0e26-160">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-160">Select **Remove**.</span></span>
    
11. <span data-ttu-id="f0e26-161">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f0e26-161">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="f0e26-162">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0e26-162">Run the following command:</span></span> 
    
    <span data-ttu-id="f0e26-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="f0e26-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="f0e26-164">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="f0e26-164">Restart the system.</span></span>
    
<span data-ttu-id="f0e26-165">所需的语言立即应用于 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="f0e26-165">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="f0e26-166">控制台的初始设置 </span><span class="sxs-lookup"><span data-stu-id="f0e26-166">Initial set up of the Console</span></span>
<span data-ttu-id="f0e26-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-167"></span></span>

<span data-ttu-id="f0e26-168">安装 Windows 后，Skype 会议室系统 v2 应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。</span><span class="sxs-lookup"><span data-stu-id="f0e26-168">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="f0e26-p112">将显示“用户帐户”屏幕。输入要在该设备中使用的会议室帐户的 Skype 登录地址（格式为 user@domain）。</span><span class="sxs-lookup"><span data-stu-id="f0e26-p112">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="f0e26-171">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="f0e26-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="f0e26-172">在"配置域"下的 FQDN 设置为 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="f0e26-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="f0e26-173">如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。</span><span class="sxs-lookup"><span data-stu-id="f0e26-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="f0e26-174">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="f0e26-175">选择功能屏幕上的指定的设备，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f0e26-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="f0e26-176">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="f0e26-177">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="f0e26-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="f0e26-178">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="f0e26-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="f0e26-179">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="f0e26-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="f0e26-180">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="f0e26-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="f0e26-p115">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="f0e26-p115">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="f0e26-183">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-183">Click **Finish**.</span></span>
    
<span data-ttu-id="f0e26-184">应用程序应立即启动登录到 Skype 业务服务器与上面，输入的凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。</span><span class="sxs-lookup"><span data-stu-id="f0e26-184">The app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="f0e26-185">有关使用应用程序的详细信息，请参阅[Skype 会议室系统版本 2 帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-185">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f0e26-186">Skype 会议室系统 v2 依赖于认证的控制台硬件 (Logitech SmartDock) 的状态。</span><span class="sxs-lookup"><span data-stu-id="f0e26-186">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="f0e26-187">除非检测到控制台硬件，即使包含 Skype 会议室系统 v2 应用程序 Surface Pro 4 或 Surface Pro 上加载的正确创建的图像将无法启动过去的初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="f0e26-187">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f0e26-188">在初始安装过程中，如果发生触摸键盘不支持某些符号的情况，一些非英语用户可能需要连接到控制台的物理键盘。</span><span class="sxs-lookup"><span data-stu-id="f0e26-188">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="f0e26-189">在平板电脑设备上安装私有 CA 证书</span><span class="sxs-lookup"><span data-stu-id="f0e26-189">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="f0e26-190"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-190"></span></span>

<span data-ttu-id="f0e26-191">Skype 会议室系统 v2 设备都需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="f0e26-191">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="f0e26-192">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="f0e26-192">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="f0e26-193">在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Skype 会议室系统 v2 设备的证书：</span><span class="sxs-lookup"><span data-stu-id="f0e26-193">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="f0e26-194">如果证书颁发机构已发布至 Active Directory（标准部署选项），则可将设备加入 Active Directory，此操作会自动添加所需证书。</span><span class="sxs-lookup"><span data-stu-id="f0e26-194">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="f0e26-p119">可以在映像过程后手动安装证书。在此之前，必须完成[控制台的初始设置](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-p119">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="f0e26-197">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="f0e26-197">To manually install the certificate</span></span>

1. <span data-ttu-id="f0e26-198">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="f0e26-198">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="f0e26-199">曲面 4 置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="f0e26-199">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="f0e26-200">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0e26-200">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="f0e26-201">加入 Active Directory 域（可选）</span><span class="sxs-lookup"><span data-stu-id="f0e26-201">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="f0e26-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-202"></span></span>

<span data-ttu-id="f0e26-203">Skype 会议室系统 v2 设备可以加入您的域。</span><span class="sxs-lookup"><span data-stu-id="f0e26-203">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="f0e26-204">应将 Skype 会议室系统 v2 设备放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Skype 会议室系统 v2 兼容。</span><span class="sxs-lookup"><span data-stu-id="f0e26-204">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="f0e26-205">常见的示例是将阻止自动启动 Skype 会议室系统 v2 的密码实施策略。</span><span class="sxs-lookup"><span data-stu-id="f0e26-205">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="f0e26-206">有关管理 GPO 设置的信息，请参阅[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="f0e26-206">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="f0e26-207">将 Skype 会议室系统 v2 加入域</span><span class="sxs-lookup"><span data-stu-id="f0e26-207">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="f0e26-208">登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。</span><span class="sxs-lookup"><span data-stu-id="f0e26-208">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="f0e26-209">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f0e26-209">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="f0e26-210">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0e26-210">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="f0e26-211">例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 且您希望 Skype 会议室系统 v2 设备处于"Skype 会议室系统 v2"是"Resources"OU 的子级的 OU，则可该命令：</span><span class="sxs-lookup"><span data-stu-id="f0e26-211">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="f0e26-212">如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。</span><span class="sxs-lookup"><span data-stu-id="f0e26-212">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="f0e26-213">Skype 会议室系统 v2 部署清单</span><span class="sxs-lookup"><span data-stu-id="f0e26-213">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="f0e26-214"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-214"></span></span>

<span data-ttu-id="f0e26-215">在最终验证控制台设备及其所有外围设备是否已进行完全配置时，请使用下面的清单：</span><span class="sxs-lookup"><span data-stu-id="f0e26-215">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="f0e26-216">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="f0e26-216">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0e26-217">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-217">☐</span></span>  <br/> |<span data-ttu-id="f0e26-218">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="f0e26-218">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="f0e26-219">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-219">☐</span></span>  <br/> |<span data-ttu-id="f0e26-220">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="f0e26-220">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="f0e26-221">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-221">☐</span></span>  <br/> |<span data-ttu-id="f0e26-222">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="f0e26-222">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="f0e26-223">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-223">☐</span></span>  <br/> |<span data-ttu-id="f0e26-224">已应用所有 Surface Pro 4 或 Surface Pro 系统更新</span><span class="sxs-lookup"><span data-stu-id="f0e26-224">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="f0e26-225">**音频/视频外围设备**</span><span class="sxs-lookup"><span data-stu-id="f0e26-225">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0e26-226">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-226">☐</span></span>  <br/> |<span data-ttu-id="f0e26-227">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="f0e26-227">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="f0e26-228">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-228">☐</span></span>  <br/> |<span data-ttu-id="f0e26-229">摄像机功能和定位以最佳方式</span><span class="sxs-lookup"><span data-stu-id="f0e26-229">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="f0e26-230">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-230">☐</span></span>  <br/> |<span data-ttu-id="f0e26-231">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="f0e26-231">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="f0e26-232">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-232">☐</span></span>  <br/> |<span data-ttu-id="f0e26-233">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="f0e26-233">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="f0e26-234">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-234">☐</span></span>  <br/> |<span data-ttu-id="f0e26-235">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="f0e26-235">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="f0e26-236">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-236">☐</span></span>  <br/> |<span data-ttu-id="f0e26-237">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="f0e26-237">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="f0e26-238">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-238">☐</span></span>  <br/> |<span data-ttu-id="f0e26-239">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="f0e26-239">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="f0e26-240">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="f0e26-240">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0e26-241">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-241">☐</span></span>  <br/> |<span data-ttu-id="f0e26-242">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="f0e26-242">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="f0e26-243">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-243">☐</span></span>  <br/> |<span data-ttu-id="f0e26-244">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="f0e26-244">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="f0e26-245">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-245">☐</span></span>  <br/> |<span data-ttu-id="f0e26-246">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="f0e26-246">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="f0e26-247">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-247">☐</span></span>  <br/> |<span data-ttu-id="f0e26-248">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="f0e26-248">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="f0e26-249">☐</span><span class="sxs-lookup"><span data-stu-id="f0e26-249">☐</span></span>  <br/> |<span data-ttu-id="f0e26-250">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="f0e26-250">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f0e26-251">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0e26-251">See also</span></span>
<span data-ttu-id="f0e26-252"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="f0e26-252"></span></span>

[<span data-ttu-id="f0e26-253">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f0e26-253">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="f0e26-254">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f0e26-254">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="f0e26-255">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="f0e26-255">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="f0e26-256">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f0e26-256">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)