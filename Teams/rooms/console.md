---
title: 配置 Microsoft Teams 会议室控制台
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置和配置主机Microsoft Teams 会议室及其外围设备。
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117570"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="5f768-103">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="5f768-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="5f768-104">本文介绍如何设置主机Microsoft Teams 会议室及其外围设备。</span><span class="sxs-lookup"><span data-stu-id="5f768-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="5f768-105">只有在已根据部署 Microsoft Teams 会议室 中所述创建Microsoft Teams Skype for Business Exchange帐户并测试帐户时，才[应执行Microsoft Teams 会议室。](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="5f768-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="5f768-106">需要满足以下要求中所述的[Microsoft Teams 会议室软件](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f768-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="5f768-107">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="5f768-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="5f768-108">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="5f768-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="5f768-109">在主机上安装专用 CA 证书</span><span class="sxs-lookup"><span data-stu-id="5f768-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="5f768-110">安装 Windows 10 和 Microsoft Teams 会议室 控制台应用</span><span class="sxs-lookup"><span data-stu-id="5f768-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="5f768-111">主机的初始设置</span><span class="sxs-lookup"><span data-stu-id="5f768-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="5f768-112">Microsoft Teams 会议室部署清单</span><span class="sxs-lookup"><span data-stu-id="5f768-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="5f768-113">Microsoft Teams 会议室仅在正确配置的 Microsoft Teams 或 Skype for Business 环境中工作，其中设备帐户已正确设置，如部署 Microsoft Teams 会议室[中所述](rooms-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="5f768-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="5f768-114">准备安装媒体</span><span class="sxs-lookup"><span data-stu-id="5f768-114">Prepare the installation media</span></span>
<span data-ttu-id="5f768-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="5f768-116">安装 Microsoft Teams 会议室主机应用需要至少具有 32GB 容量的 USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="5f768-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="5f768-117">设备上不应存在任何其他文件;USB 存储上的任何现有文件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="5f768-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f768-118">根据这些说明Microsoft Teams 会议室安装媒体可能会导致意外行为。</span><span class="sxs-lookup"><span data-stu-id="5f768-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="5f768-119">下面的过程用于创建安装媒体，以映像新的Microsoft Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="5f768-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="5f768-120">默认情况下，现有设备会从 Windows 应用商店Windows更新。</span><span class="sxs-lookup"><span data-stu-id="5f768-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f768-121">用于创建Windows 10安装媒体Microsoft Teams 会议室计算机必须位于目标安装媒体Windows或更高版本的安装媒体上。</span><span class="sxs-lookup"><span data-stu-id="5f768-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="5f768-122">下载 [CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="5f768-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="5f768-123">在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="5f768-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="5f768-124">按照脚本的说明创建 U 盘Microsoft Teams 会议室 U 盘。</span><span class="sxs-lookup"><span data-stu-id="5f768-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="5f768-125">每次启动CreateSrsMedia.ps1，屏幕输出将包含会话日志文件脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="5f768-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="5f768-126">如果运行脚本时发生问题，请确保在请求支持时提供该脚本的副本。</span><span class="sxs-lookup"><span data-stu-id="5f768-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="5f768-127">脚本CreateSrsMedia.ps1自动执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5f768-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="5f768-128">下载适用于 Microsoft Teams 会议室 的最新 MSI 安装程序。</span><span class="sxs-lookup"><span data-stu-id="5f768-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="5f768-129">确定用户Windows的生成。</span><span class="sxs-lookup"><span data-stu-id="5f768-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="5f768-130">最近发布的版本可能受测试，也可能不会受支持用于Microsoft Teams 会议室版本。</span><span class="sxs-lookup"><span data-stu-id="5f768-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="5f768-131">下载必要的支持组件。</span><span class="sxs-lookup"><span data-stu-id="5f768-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="5f768-132">在安装媒体上组装所需的组件。</span><span class="sxs-lookup"><span data-stu-id="5f768-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="5f768-133">需要特定版本的 Windows 10，并且此版本仅适用于批量许可客户。</span><span class="sxs-lookup"><span data-stu-id="5f768-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="5f768-134">可以从批量许可 [服务中心获取副本](https://www.microsoft.com/Licensing/servicecenter/)。</span><span class="sxs-lookup"><span data-stu-id="5f768-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="5f768-135">完成后，从计算机中删除 USB 磁盘，并继续执行安装 Windows 10[和Microsoft Teams 会议室控制台应用](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="5f768-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="5f768-136">安装 Windows 10 和 Microsoft Teams 会议室 控制台应用</span><span class="sxs-lookup"><span data-stu-id="5f768-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="5f768-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="5f768-138">现在需要应用已创建的设置媒体。</span><span class="sxs-lookup"><span data-stu-id="5f768-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="5f768-139">目标设备将作为设备运行，默认用户将设置为仅运行Microsoft Teams 会议室控制台应用。</span><span class="sxs-lookup"><span data-stu-id="5f768-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="5f768-140">如果目标设备将安装在扩展坞 (例如，Surface Pro) ，请将其与扩展坞断开连接。</span><span class="sxs-lookup"><span data-stu-id="5f768-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="5f768-141">确保目标设备未连接到网络。</span><span class="sxs-lookup"><span data-stu-id="5f768-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="5f768-142">确保目标设备已连接到交流电源。</span><span class="sxs-lookup"><span data-stu-id="5f768-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="5f768-143">将 USB 安装磁盘插入目标设备。</span><span class="sxs-lookup"><span data-stu-id="5f768-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="5f768-144">启动到 USB 安装磁盘。</span><span class="sxs-lookup"><span data-stu-id="5f768-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="5f768-145">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="5f768-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="5f768-146">如果目标设备是Surface Pro，请使用以下步骤启动到 USB 安装磁盘：</span><span class="sxs-lookup"><span data-stu-id="5f768-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="5f768-147">a.</span><span class="sxs-lookup"><span data-stu-id="5f768-147">a.</span></span> <span data-ttu-id="5f768-148">按并继续按" (按钮) 音量。</span><span class="sxs-lookup"><span data-stu-id="5f768-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="5f768-149">b.</span><span class="sxs-lookup"><span data-stu-id="5f768-149">b.</span></span> <span data-ttu-id="5f768-150">按下并松开电源按钮。</span><span class="sxs-lookup"><span data-stu-id="5f768-150">Press and release the power button.</span></span>

    <span data-ttu-id="5f768-151">c.</span><span class="sxs-lookup"><span data-stu-id="5f768-151">c.</span></span> <span data-ttu-id="5f768-152">启动 Windows 安装程序后，释放调低音量 (-) 按钮。</span><span class="sxs-lookup"><span data-stu-id="5f768-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="5f768-153">安装完成后，系统将关闭。</span><span class="sxs-lookup"><span data-stu-id="5f768-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="5f768-154">系统关闭后，可以安全地移除 USB 安装磁盘。</span><span class="sxs-lookup"><span data-stu-id="5f768-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="5f768-155">此时，如果使用基于扩展坞的产品 (，可以将目标设备放在其扩展坞) 附加会议室所需的外围设备，并连接到网络。</span><span class="sxs-lookup"><span data-stu-id="5f768-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="5f768-156">请参阅制造商说明。</span><span class="sxs-lookup"><span data-stu-id="5f768-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="5f768-157">系统会自动Microsoft Teams 会议室下载适用于 适用于企业的 Microsoft Store 的软件更新。</span><span class="sxs-lookup"><span data-stu-id="5f768-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="5f768-158">请参阅[适用于企业的 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business)和教育的先决条件，验证会议室主机是否能够访问应用商店和自我更新。</span><span class="sxs-lookup"><span data-stu-id="5f768-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="5f768-159">选择语言</span><span class="sxs-lookup"><span data-stu-id="5f768-159">Selecting a language</span></span> 

<span data-ttu-id="5f768-160">在创意者的更新中，你需要在隐式语言选择未为用户提供他们想要的实际应用程序语言的情况下使用 ApplyCurrentRegionAndLanguage.ps1 脚本 (例如，他们希望控制台应用以法语显示，但它以英语) 提供。</span><span class="sxs-lookup"><span data-stu-id="5f768-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f768-161">以下说明仅适用于使用创建者更新Windows创建的主机。</span><span class="sxs-lookup"><span data-stu-id="5f768-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="5f768-162">尚未将媒体与新预配系统一起设置的旧式/市场内系统将无法使用这些说明，但不应受到需要此手动干预的初始问题的影响 (周年版允许作为设置) 的一部分显式选取应用语言。</span><span class="sxs-lookup"><span data-stu-id="5f768-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="5f768-163">应用你需要的语言</span><span class="sxs-lookup"><span data-stu-id="5f768-163">To apply your desired language</span></span>

1. <span data-ttu-id="5f768-164">切换至管理模式。</span><span class="sxs-lookup"><span data-stu-id="5f768-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="5f768-165">选择“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="5f768-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="5f768-166">选择齿轮图标以启动“**设置**”应用。</span><span class="sxs-lookup"><span data-stu-id="5f768-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="5f768-167">选择 **"时间 &amp; 语言"。**</span><span class="sxs-lookup"><span data-stu-id="5f768-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="5f768-168">选择 **"区域 &amp; 语言"。**</span><span class="sxs-lookup"><span data-stu-id="5f768-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="5f768-169">选择“**添加语言**”。</span><span class="sxs-lookup"><span data-stu-id="5f768-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="5f768-170">选择要添加的语言。</span><span class="sxs-lookup"><span data-stu-id="5f768-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="5f768-171">选择刚刚添加到"语言"列表的语言。</span><span class="sxs-lookup"><span data-stu-id="5f768-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="5f768-172">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="5f768-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="5f768-173">对于要删除的任何语言：</span><span class="sxs-lookup"><span data-stu-id="5f768-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="5f768-p115">a. 选择要删除的语言。</span><span class="sxs-lookup"><span data-stu-id="5f768-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="5f768-p116">b. 选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="5f768-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="5f768-178">启动提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5f768-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="5f768-179">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f768-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="5f768-180">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="5f768-180">Restart the system.</span></span>
    
<span data-ttu-id="5f768-181">现在，所需语言将应用到 Microsoft Teams 会议室 控制台。</span><span class="sxs-lookup"><span data-stu-id="5f768-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="5f768-182">主机的初始设置</span><span class="sxs-lookup"><span data-stu-id="5f768-182">Initial set up of the console</span></span>
<span data-ttu-id="5f768-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="5f768-184">安装Windows后，Microsoft Teams 会议室应用将在下次启动时或选择 /reboot 选项时进入其初始安装过程。</span><span class="sxs-lookup"><span data-stu-id="5f768-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="5f768-185">将显示“用户帐户”屏幕。</span><span class="sxs-lookup"><span data-stu-id="5f768-185">The User Account screen appears.</span></span> <span data-ttu-id="5f768-186">以Skype主机 (user@domain) 帐户的格式输入登录地址。</span><span class="sxs-lookup"><span data-stu-id="5f768-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="5f768-187">输入会议室帐户的密码，再重新输入以进行确认。</span><span class="sxs-lookup"><span data-stu-id="5f768-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="5f768-188">在"配置域"下，设置域的 FQDN Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="5f768-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="5f768-189">如果Skype for Business SIP 域与用户的 Exchange 域不同，请在此字段Exchange域。</span><span class="sxs-lookup"><span data-stu-id="5f768-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="5f768-190">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5f768-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="5f768-191">在"功能"屏幕上选择指示的设备，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f768-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="5f768-192">默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="5f768-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="5f768-193">要选择的设备为：</span><span class="sxs-lookup"><span data-stu-id="5f768-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="5f768-194">用于会议的麦克风：此会议室的默认麦克风。</span><span class="sxs-lookup"><span data-stu-id="5f768-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="5f768-195">用于会议的扬声器：用于此会议的默认扬声器。</span><span class="sxs-lookup"><span data-stu-id="5f768-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="5f768-196">默认扬声器：用于来自 HDMI 采集的音频的扬声器。</span><span class="sxs-lookup"><span data-stu-id="5f768-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="5f768-p120">每项都有供选择的选项下列菜单。你必须为每个设备做出选择。</span><span class="sxs-lookup"><span data-stu-id="5f768-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="5f768-199">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="5f768-199">Click **Finish**.</span></span>
    
<span data-ttu-id="5f768-200">Microsoft Teams 会议室控制台应用应该立即开始使用上面输入的Skype for Business Server登录，并且还应使用这些相同的凭据开始将日历与 Exchange同步。</span><span class="sxs-lookup"><span data-stu-id="5f768-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="5f768-201">有关使用控制台应用的详细信息，请参阅 Microsoft Teams 会议室[帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="5f768-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f768-202">Microsoft Teams 会议室依赖于存在经过认证的主机硬件。</span><span class="sxs-lookup"><span data-stu-id="5f768-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="5f768-203">即使正确创建的映像包含主机Microsoft Teams 会议室，除非检测到主机硬件，否则不会启动初始设置过程。</span><span class="sxs-lookup"><span data-stu-id="5f768-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="5f768-204">对于Surface Pro的解决方案，Surface Pro必须连接到其随附的扩展坞硬件，以通过此检查。</span><span class="sxs-lookup"><span data-stu-id="5f768-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f768-205">如果触摸键盘不支持符号，某些非英语用户可能需要在初始设置期间连接到主机的物理键盘。</span><span class="sxs-lookup"><span data-stu-id="5f768-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="5f768-206">在主机上安装专用 CA 证书</span><span class="sxs-lookup"><span data-stu-id="5f768-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="5f768-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="5f768-208">Microsoft Teams 会议室主机需要信任它所连接到的服务器使用的证书。</span><span class="sxs-lookup"><span data-stu-id="5f768-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="5f768-209">对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="5f768-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="5f768-210">如果证书颁发机构是私有的，例如使用 Active Directory 和 Windows 证书颁发机构进行本地部署，可以通过多种方式将证书添加到 Microsoft Teams 会议室 控制台：</span><span class="sxs-lookup"><span data-stu-id="5f768-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="5f768-211">可以将主机加入 Active Directory，在证书颁发机构发布到 Active Directory 后，这会自动添加所需的证书， (常规部署选项) 。</span><span class="sxs-lookup"><span data-stu-id="5f768-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="5f768-212">可以在映像过程后手动安装证书。</span><span class="sxs-lookup"><span data-stu-id="5f768-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="5f768-213">在这样做之前，必须完成主机 [的初始设置](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="5f768-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="5f768-214">手动安装证书 </span><span class="sxs-lookup"><span data-stu-id="5f768-214">To manually install the certificate</span></span>

1. <span data-ttu-id="5f768-215">将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。</span><span class="sxs-lookup"><span data-stu-id="5f768-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="5f768-216">将主机放在管理模式下 ([管理模式和设备管理) 。](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="5f768-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="5f768-217">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f768-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="5f768-218">加入 Active Directory 域 (可选) </span><span class="sxs-lookup"><span data-stu-id="5f768-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="5f768-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="5f768-220">你可以将Microsoft Teams 会议室加入你的域。</span><span class="sxs-lookup"><span data-stu-id="5f768-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="5f768-221">Microsoft Teams 会议室主机应放置在与电脑工作站不同的 OU 中，因为许多工作站策略与 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="5f768-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="5f768-222">一个常见示例是密码强制策略，Microsoft Teams 会议室自动启动。</span><span class="sxs-lookup"><span data-stu-id="5f768-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="5f768-223">有关管理 GPO 设置的信息，请参阅管理[Microsoft Teams 会议室。](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="5f768-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="5f768-224">将Microsoft Teams 会议室域</span><span class="sxs-lookup"><span data-stu-id="5f768-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="5f768-225">从管理员帐户登录主机， ([管理模式和设备管理) 。](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="5f768-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="5f768-226">启动提升的 Powershell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5f768-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="5f768-227">在 Powershell 中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f768-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="5f768-228">例如，如果完全限定的域 redmond.corp.microsoft.com 并且希望 Microsoft Teams 会议室 主机位于"Microsoft Teams 会议室"OU 中，该 OU 是"Resources"OU 的子级，则命令将是：</span><span class="sxs-lookup"><span data-stu-id="5f768-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="5f768-229">如果要在将计算机加入域时重命名计算机，请使用 -NewName 标志，后跟计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="5f768-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="5f768-230">Microsoft Teams 会议室部署清单</span><span class="sxs-lookup"><span data-stu-id="5f768-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="5f768-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="5f768-232">在最终验证主机及其所有外围设备是否完全配置时，请使用以下清单：</span><span class="sxs-lookup"><span data-stu-id="5f768-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="5f768-233">**应用程序设置**</span><span class="sxs-lookup"><span data-stu-id="5f768-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f768-234">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-234">☐</span></span>  <br/> |<span data-ttu-id="5f768-235">在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）</span><span class="sxs-lookup"><span data-stu-id="5f768-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="5f768-236">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-236">☐</span></span>  <br/> |<span data-ttu-id="5f768-237">已正确设置 Windows 计算机名称（对于远程管理很有用）</span><span class="sxs-lookup"><span data-stu-id="5f768-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="5f768-238">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-238">☐</span></span>  <br/> |<span data-ttu-id="5f768-239">已设置并验证管理员帐户密码</span><span class="sxs-lookup"><span data-stu-id="5f768-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="5f768-240">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-240">☐</span></span>  <br/> |<span data-ttu-id="5f768-241">已应用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="5f768-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="5f768-242">**音频/视频外围设备**</span><span class="sxs-lookup"><span data-stu-id="5f768-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f768-243">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-243">☐</span></span>  <br/> |<span data-ttu-id="5f768-244">摄像头外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="5f768-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="5f768-245">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-245">☐</span></span>  <br/> |<span data-ttu-id="5f768-246">以最佳方式定位相机的功能和位置</span><span class="sxs-lookup"><span data-stu-id="5f768-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="5f768-247">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-247">☐</span></span>  <br/> |<span data-ttu-id="5f768-248">将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="5f768-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="5f768-249">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-249">☐</span></span>  <br/> |<span data-ttu-id="5f768-250">将用于录制默认通信设备的设置设为预期的音频外围设备</span><span class="sxs-lookup"><span data-stu-id="5f768-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="5f768-251">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-251">☐</span></span>  <br/> |<span data-ttu-id="5f768-252">音频外围设备固件版本正确（如果适用）</span><span class="sxs-lookup"><span data-stu-id="5f768-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="5f768-253">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-253">☐</span></span>  <br/> |<span data-ttu-id="5f768-254">音频输入设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="5f768-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="5f768-255">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-255">☐</span></span>  <br/> |<span data-ttu-id="5f768-256">音频输出设备工作正常且位置最佳</span><span class="sxs-lookup"><span data-stu-id="5f768-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="5f768-257">**扩展坞**</span><span class="sxs-lookup"><span data-stu-id="5f768-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f768-258">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-258">☐</span></span>  <br/> |<span data-ttu-id="5f768-259">电缆是安全的且未收缩</span><span class="sxs-lookup"><span data-stu-id="5f768-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="5f768-260">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-260">☐</span></span>  <br/> |<span data-ttu-id="5f768-261">通过 HDMI 进行的音频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="5f768-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="5f768-262">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-262">☐</span></span>  <br/> |<span data-ttu-id="5f768-263">通过 HDMI 进行的视频采集工作正常</span><span class="sxs-lookup"><span data-stu-id="5f768-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="5f768-264">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-264">☐</span></span>  <br/> |<span data-ttu-id="5f768-265">扩展坞可以自由旋转</span><span class="sxs-lookup"><span data-stu-id="5f768-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="5f768-266">☐</span><span class="sxs-lookup"><span data-stu-id="5f768-266">☐</span></span>  <br/> |<span data-ttu-id="5f768-267">显示亮度对于环境而言可接受</span><span class="sxs-lookup"><span data-stu-id="5f768-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5f768-268">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f768-268">See also</span></span>
<span data-ttu-id="5f768-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="5f768-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="5f768-270">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="5f768-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="5f768-271">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="5f768-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="5f768-272">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="5f768-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="5f768-273">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="5f768-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)