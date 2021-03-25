---
title: Microsoft Teams 会议室维护和操作
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 阅读本主题，了解有关管理 Microsoft Teams 会议室（下一代 Skype 会议室系统）的信息。
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117430"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="a53fe-103">Microsoft Teams 会议室维护和操作</span><span class="sxs-lookup"><span data-stu-id="a53fe-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="a53fe-104">阅读本主题，了解有关管理 Microsoft Teams 会议室（下一代 Skype 会议室系统）的信息。</span><span class="sxs-lookup"><span data-stu-id="a53fe-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="a53fe-105">Microsoft Teams 会议室是 Microsoft 的最新会议解决方案，旨在将会议室转换为丰富的协作体验。</span><span class="sxs-lookup"><span data-stu-id="a53fe-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="a53fe-106">用户将享受熟悉的 Microsoft Teams 或 Skype for Business 界面，IT 管理员将喜欢一个易于部署和管理的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="a53fe-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="a53fe-107">Microsoft Teams 会议室旨在利用现有设备（例如，用于轻松安装的 MICROSOFT TEAMS 或 Skype for Business）来将 Microsoft Teams 或 Skype for Business 引入会议室。</span><span class="sxs-lookup"><span data-stu-id="a53fe-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="a53fe-108">通过附加配置，可以如使用 [Azure Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室管理、使用 Azure Monitor 部署 Microsoft Teams 会议室管理、使用 Azure Monitor 管理 Microsoft [Teams](azure-monitor-deploy.md)会议室设备中所述，使用 Microsoft Azure Monitor 进行 [远程管理](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="a53fe-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="a53fe-109">还可使用 [XML](xml-config-file.md)配置文件远程管理 Microsoft Teams 会议室主机设置，其中包括应用自定义显示主题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="a53fe-110">在 Microsoft Teams 会议室中收集日志</span><span class="sxs-lookup"><span data-stu-id="a53fe-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="a53fe-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="a53fe-112">若要收集日志，必须调用 Microsoft Teams 会议室应用附带日志收集脚本。</span><span class="sxs-lookup"><span data-stu-id="a53fe-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="a53fe-113">在管理模式中，启动提升的命令提示符并发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="a53fe-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="a53fe-114">日志将以 ZIP 文件的形式输出至 c:\rigel 中。</span><span class="sxs-lookup"><span data-stu-id="a53fe-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="a53fe-115">会议室前端显示屏设置</span><span class="sxs-lookup"><span data-stu-id="a53fe-115">Front of Room Display Settings</span></span>
<span data-ttu-id="a53fe-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-116"><a name="Display"> </a></span></span>

<span data-ttu-id="a53fe-117">将会议室前端显示屏配置为扩展模式。</span><span class="sxs-lookup"><span data-stu-id="a53fe-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="a53fe-118">这样做可确保当你在显示器上循环电源时，控制台 UI 不会重复显示。</span><span class="sxs-lookup"><span data-stu-id="a53fe-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a53fe-119">如果希望房间前显示自动切换到活动视频源 (例如当源从备用模式唤醒时) 的一个"市/站"控制台，则必须满足某些条件。</span><span class="sxs-lookup"><span data-stu-id="a53fe-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="a53fe-120">此功能是可选的，但 Microsoft Teams 会议室软件支持此功能，但基础硬件支持此功能。</span><span class="sxs-lookup"><span data-stu-id="a53fe-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="a53fe-121">用作房间前显示器的消费者电视需要支持 HDMI 的使用者 (CEC) 功能。</span><span class="sxs-lookup"><span data-stu-id="a53fe-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="a53fe-122">根据所选的扩展坞或主机 (可能不支持 CEC，请参阅制造商支持文档) ，需要来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Extron 的 [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 等控制器才能启用所需行为。</span><span class="sxs-lookup"><span data-stu-id="a53fe-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="a53fe-123">Microsoft Teams 会议室重置 (恢复出厂) </span><span class="sxs-lookup"><span data-stu-id="a53fe-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="a53fe-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="a53fe-125">如果 Microsoft Teams 会议室运行不佳，执行恢复出厂设置可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="a53fe-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="a53fe-126">为此，请使用 Microsoft [Teams Room 恢复工具并按照](recovery-tool.md) 恢复工厂说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="a53fe-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="a53fe-127">存在一个已知问题，即如果"保留我的文件 **-** 删除应用和设置，但保留个人文件"选项在 Windows 重置过程中选中，Microsoft Teams 会议室可能会变得不可用。</span><span class="sxs-lookup"><span data-stu-id="a53fe-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="a53fe-128">*请不要* 使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a53fe-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="a53fe-129">支持的远程选项</span><span class="sxs-lookup"><span data-stu-id="a53fe-129">Supported Remote Options</span></span>
<span data-ttu-id="a53fe-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="a53fe-131">下表汇总了可能的远程操作和可以用于完成这些操作的方法。</span><span class="sxs-lookup"><span data-stu-id="a53fe-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="a53fe-132">工作组 </span><span class="sxs-lookup"><span data-stu-id="a53fe-132">Workgroup</span></span>|<span data-ttu-id="a53fe-133">未加入域</span><span class="sxs-lookup"><span data-stu-id="a53fe-133">Not domain joined</span></span>|<span data-ttu-id="a53fe-134">加入域</span><span class="sxs-lookup"><span data-stu-id="a53fe-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a53fe-135">重新启动</span><span class="sxs-lookup"><span data-stu-id="a53fe-135">Restart</span></span>  <br/> |<span data-ttu-id="a53fe-136">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a53fe-136">Teams admin center</span></span>  <br/> <span data-ttu-id="a53fe-137">远程桌面</span><span class="sxs-lookup"><span data-stu-id="a53fe-137">Remote desktop</span></span>  <br/> <span data-ttu-id="a53fe-138">远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a53fe-138">Remote Powershell</span></span>  <br/> | <br/><span data-ttu-id="a53fe-139">远程桌面 (需要进一步配置) </span><span class="sxs-lookup"><span data-stu-id="a53fe-139">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="a53fe-140">远程 Powershell (需要进一步配置) </span><span class="sxs-lookup"><span data-stu-id="a53fe-140">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="a53fe-141">配置管理器</span><span class="sxs-lookup"><span data-stu-id="a53fe-141">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="a53fe-142">更新操作系统</span><span class="sxs-lookup"><span data-stu-id="a53fe-142">Update OS</span></span>  <br/> |<span data-ttu-id="a53fe-143">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="a53fe-143">Windows Update</span></span>  <br/> |<span data-ttu-id="a53fe-144">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="a53fe-144">Windows Update</span></span>  <br/> <span data-ttu-id="a53fe-145">WSUS</span><span class="sxs-lookup"><span data-stu-id="a53fe-145">WSUS</span></span>  <br/> |
|<span data-ttu-id="a53fe-146">应用更新</span><span class="sxs-lookup"><span data-stu-id="a53fe-146">App update</span></span>  <br/> |<span data-ttu-id="a53fe-147">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="a53fe-147">Windows Store</span></span>  <br/> |<span data-ttu-id="a53fe-148">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="a53fe-148">Windows Store</span></span>  <br/> <span data-ttu-id="a53fe-149">配置管理器</span><span class="sxs-lookup"><span data-stu-id="a53fe-149">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="a53fe-150">帐户配置</span><span class="sxs-lookup"><span data-stu-id="a53fe-150">Account Config</span></span>  <br/> |<span data-ttu-id="a53fe-151">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a53fe-151">Teams admin center</span></span>  <br/> |<span data-ttu-id="a53fe-152">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a53fe-152">Teams admin center</span></span>  <br/> |
|<span data-ttu-id="a53fe-153">访问日志</span><span class="sxs-lookup"><span data-stu-id="a53fe-153">Access logs</span></span>  <br/> |<span data-ttu-id="a53fe-154">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a53fe-154">Teams admin center</span></span>  <br/> |<span data-ttu-id="a53fe-155">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a53fe-155">Teams admin center</span></span> <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="a53fe-156">为 Microsoft Teams 会议室配置组策略</span><span class="sxs-lookup"><span data-stu-id="a53fe-156">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="a53fe-157"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-157"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="a53fe-158">本部分介绍 Microsoft Teams 会议室正常运行所依赖的系统设置。</span><span class="sxs-lookup"><span data-stu-id="a53fe-158">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="a53fe-159">将 Microsoft Teams 会议室加入域时，请确保组策略不会覆盖下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="a53fe-159">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="a53fe-160">设置</span><span class="sxs-lookup"><span data-stu-id="a53fe-160">Setting</span></span>|<span data-ttu-id="a53fe-161">允许</span><span class="sxs-lookup"><span data-stu-id="a53fe-161">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="a53fe-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="a53fe-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="a53fe-163">启用 Microsoft Teams 会议室启动</span><span class="sxs-lookup"><span data-stu-id="a53fe-163">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="a53fe-164">电源管理 - \> 在交流电源上，10 分钟后关闭屏幕</span><span class="sxs-lookup"><span data-stu-id="a53fe-164">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="a53fe-165">电源管理 - \> 在交流电源上，切勿将系统置于睡眠状态</span><span class="sxs-lookup"><span data-stu-id="a53fe-165">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="a53fe-166">允许 Microsoft Teams 会议室关闭附加的显示器并自动唤醒</span><span class="sxs-lookup"><span data-stu-id="a53fe-166">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="a53fe-167">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="a53fe-167">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="a53fe-168">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="a53fe-168">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="a53fe-169">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="a53fe-169">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="a53fe-170">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="a53fe-170">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="a53fe-171">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="a53fe-171">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="a53fe-172">配置文件项 中讨论了使用组 [策略传输文件](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="a53fe-172">Transferring files using Group Policies is discussed in [Configure a File Item](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11)).</span></span>

> [!NOTE]
> <span data-ttu-id="a53fe-173">当 Microsoft Teams 会议室设备与下一版本的 Windows 10 OS 兼容时，设备会通过 Windows 更新自动更新到下一版本。</span><span class="sxs-lookup"><span data-stu-id="a53fe-173">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="a53fe-174">Microsoft Teams 会议室设备不应手动或通过启用 Windows 更新 for Business (WUFB) 组策略"选择要接收的更新的 Windows 准备级别"和"选择何时收到预览版本和功能更新"通过 GPO 手动升级到下一个 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="a53fe-174">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="a53fe-175">已知启用了这些组策略的设备在 Microsoft Teams 会议室应用中遇到 Windows 10 OS 更新问题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-175">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="a53fe-176">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="a53fe-176">Remote Management using PowerShell</span></span>
<span data-ttu-id="a53fe-177"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-177"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="a53fe-178">可以使用 PowerShell 远程执行以下管理操作 (请参阅下表，了解脚本示例) ：</span><span class="sxs-lookup"><span data-stu-id="a53fe-178">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="a53fe-179">获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="a53fe-179">Get attached devices</span></span>
- <span data-ttu-id="a53fe-180">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="a53fe-180">Get app status</span></span>
- <span data-ttu-id="a53fe-181">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="a53fe-181">Get system info</span></span>
- <span data-ttu-id="a53fe-182">重启系统</span><span class="sxs-lookup"><span data-stu-id="a53fe-182">Reboot system</span></span>
- <span data-ttu-id="a53fe-183">检索日志</span><span class="sxs-lookup"><span data-stu-id="a53fe-183">Retrieve logs</span></span>
- <span data-ttu-id="a53fe-184">传输 (需要已加入域的 Microsoft Teams 会议室) </span><span class="sxs-lookup"><span data-stu-id="a53fe-184">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a53fe-185">默认情况下，此功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="a53fe-185">This functionality is off by default.</span></span> <span data-ttu-id="a53fe-186">需要在 Microsoft Teams 会议室系统中为环境启用远程 PowerShell 才能执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="a53fe-186">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="a53fe-187">请参阅 **[Enable-PSRemoting 文档](/powershell/module/microsoft.powershell.core/enable-psremoting)** ，了解如何启用远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a53fe-187">Refer to the documentation on **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="a53fe-188">例如，可以按如下所示启用远程 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="a53fe-188">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="a53fe-189">在 Microsoft Teams 会议室设备上以管理员角色登录。</span><span class="sxs-lookup"><span data-stu-id="a53fe-189">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="a53fe-190">打开提升权限的 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a53fe-190">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="a53fe-191">输入以下命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span><span class="sxs-lookup"><span data-stu-id="a53fe-191">Enter the following command: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span></span>
4. <span data-ttu-id="a53fe-192">打开"本地安全策略"，将"*管理员* 安全组"添加到"**安全设置**""本地策略""用户权限分配  >    >    >  **""从网络访问此计算机"。**</span><span class="sxs-lookup"><span data-stu-id="a53fe-192">Open the Local Security Policy and add the *Administrators* security group to **Security Settings** > **Local Policies** > **User Rights Assignment** > **Access this computer from the network**.</span></span>

<span data-ttu-id="a53fe-193">执行管理操作：</span><span class="sxs-lookup"><span data-stu-id="a53fe-193">To perform a management operation:</span></span>
  
1. <span data-ttu-id="a53fe-194">使用有权在 Microsoft Teams 会议室设备上运行 PowerShell 命令的帐户凭据登录到电脑。</span><span class="sxs-lookup"><span data-stu-id="a53fe-194">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="a53fe-195">在电脑上打开常规 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a53fe-195">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="a53fe-196">复制下表中的命令文本，并将其粘贴到提示符下。</span><span class="sxs-lookup"><span data-stu-id="a53fe-196">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="a53fe-197">将  `<Device fqdn>` 字段替换为适合环境的 FQDN 值。</span><span class="sxs-lookup"><span data-stu-id="a53fe-197">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="a53fe-198">将  *\<path\>*  替换为主文件配置文件或主题SkypeSettings.xml的 (和本地) 。</span><span class="sxs-lookup"><span data-stu-id="a53fe-198">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="a53fe-199">获取附加设备</span><span class="sxs-lookup"><span data-stu-id="a53fe-199">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="a53fe-200">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="a53fe-200">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="a53fe-201">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="a53fe-201">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="a53fe-202">重启系统</span><span class="sxs-lookup"><span data-stu-id="a53fe-202">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="a53fe-203">检索日志</span><span class="sxs-lookup"><span data-stu-id="a53fe-203">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="a53fe-204">推送 XML 配置文件 (或主题图形) </span><span class="sxs-lookup"><span data-stu-id="a53fe-204">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="a53fe-205">软件更新</span><span class="sxs-lookup"><span data-stu-id="a53fe-205">Software updates</span></span>
<span data-ttu-id="a53fe-206"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-206"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="a53fe-207">默认情况下，Microsoft Teams 会议室尝试连接到 Windows 应用商店，获取最新版本的 Microsoft Teams 会议室软件，因此设备需要定期访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="a53fe-207">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="a53fe-208">在联系 Microsoft 解决支持问题之前，请确保 Microsoft Teams 会议室设备已加载该应用的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a53fe-208">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="a53fe-209">默认情况下，Microsoft Teams 会议室连接到 Windows 更新以检索操作系统和 USB 外围设备固件更新，并安装在配置的营业时间之外。</span><span class="sxs-lookup"><span data-stu-id="a53fe-209">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="a53fe-210">你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。</span><span class="sxs-lookup"><span data-stu-id="a53fe-210">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="a53fe-211">如果要手动管理更新，并且无法遵循[Microsoft Store for Business](https://businessstore.microsoft.com/store)分发脱机应用的常规过程，[](/microsoft-store/distribute-offline-apps)可以从部署工具包[ (](https://go.microsoft.com/fwlink/?linkid=851168)获取相应的 APPX 文件和依赖项，其说明中提供了配置 Microsoft [Teams 会议室](console.md)控制台) ，该说明可用于配置管理器。</span><span class="sxs-lookup"><span data-stu-id="a53fe-211">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="a53fe-212">部署工具包发布滞后于应用商店版本，因此可能无法始终匹配最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="a53fe-212">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="a53fe-213">使用 Powershell 进行更新</span><span class="sxs-lookup"><span data-stu-id="a53fe-213">To update using Powershell</span></span>

1. <span data-ttu-id="a53fe-214">将程序包从 [安装 MSI 提取](https://go.microsoft.com/fwlink/?linkid=851168) 到设备可以访问的共享。</span><span class="sxs-lookup"><span data-stu-id="a53fe-214">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="a53fe-215">针对 Microsoft Teams 会议室设备运行以下脚本，并 \<share\> 视情况更改设备共享：</span><span class="sxs-lookup"><span data-stu-id="a53fe-215">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="a53fe-216">管理模式和设备管理</span><span class="sxs-lookup"><span data-stu-id="a53fe-216">Admin mode and device management</span></span>
<span data-ttu-id="a53fe-217"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-217"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="a53fe-218">某些管理功能（如手动安装专用 CA 证书）需要将 Surface Pro 设备置于管理模式。</span><span class="sxs-lookup"><span data-stu-id="a53fe-218">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="a53fe-219">在 Microsoft Teams 会议室应用运行时切换到管理模式并返回</span><span class="sxs-lookup"><span data-stu-id="a53fe-219">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="a53fe-220">挂断任何正在进行的呼叫，然后返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="a53fe-220">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="a53fe-221">选择"齿轮"图标，然后打开菜单 **(选项包括**"设置"、**辅助功能** 和 **"重启设备") 。**</span><span class="sxs-lookup"><span data-stu-id="a53fe-221">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="a53fe-222">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="a53fe-222">Select **Settings**.</span></span>
4. <span data-ttu-id="a53fe-223">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="a53fe-223">Enter the Administrator Password.</span></span> <span data-ttu-id="a53fe-224">将显示“设置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="a53fe-224">The Setup screen will appear.</span></span>  <span data-ttu-id="a53fe-225">如果设备未加入域，则默认 (用户名"Admin") 本地管理帐户。</span><span class="sxs-lookup"><span data-stu-id="a53fe-225">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="a53fe-226">此帐户的默认密码为"sfb"，请尽快更改密码。</span><span class="sxs-lookup"><span data-stu-id="a53fe-226">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="a53fe-227">如果计算机已加入域，可以使用适当的特权域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a53fe-227">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="a53fe-228">在 **左列中选择"Windows** 设置"。</span><span class="sxs-lookup"><span data-stu-id="a53fe-228">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="a53fe-229">选择“**转至管理员登录**”。</span><span class="sxs-lookup"><span data-stu-id="a53fe-229">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="a53fe-230">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="a53fe-230">Enter the Administrator Password.</span></span> <span data-ttu-id="a53fe-231">此时将正常注销应用并带你访问 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="a53fe-231">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="a53fe-232">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="a53fe-232">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="a53fe-233">你将拥有管理设备所需的权限。</span><span class="sxs-lookup"><span data-stu-id="a53fe-233">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="a53fe-234">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="a53fe-234">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="a53fe-235">从管理员帐户注销。</span><span class="sxs-lookup"><span data-stu-id="a53fe-235">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="a53fe-236">返回到 Microsoft Teams 会议室，选择屏幕最左侧的用户帐户图标，然后选择 **"Skype"。**</span><span class="sxs-lookup"><span data-stu-id="a53fe-236">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="a53fe-237">如果未 **列出 Skype** 用户，可能需要选择其他用户并输入 **.\skype** 作为用户名，然后登录。</span><span class="sxs-lookup"><span data-stu-id="a53fe-237">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="a53fe-238">主机现在回到其正常操作模式。以下过程要求将键盘连接到设备（如果尚未连接）。</span><span class="sxs-lookup"><span data-stu-id="a53fe-238">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="a53fe-239">切换到管理模式，在 Microsoft Teams 会议室应用崩溃时切换回</span><span class="sxs-lookup"><span data-stu-id="a53fe-239">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="a53fe-240">快速连续按 Windows 键五次。</span><span class="sxs-lookup"><span data-stu-id="a53fe-240">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="a53fe-241">此时将显示 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="a53fe-241">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="a53fe-242">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="a53fe-242">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="a53fe-243">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="a53fe-243">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="a53fe-244">完成后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="a53fe-244">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a53fe-245">此方法不会注销 Skype 用户或正常终止应用，但如果应用未响应，并且其他方法不可用，你将使用它。</span><span class="sxs-lookup"><span data-stu-id="a53fe-245">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="a53fe-246">主机重启到其正常运行模式，运行 Microsoft Teams 会议室应用。</span><span class="sxs-lookup"><span data-stu-id="a53fe-246">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="a53fe-247">如果键盘已附加，可将其删除，以便执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a53fe-247">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="a53fe-248">故障排除提示</span><span class="sxs-lookup"><span data-stu-id="a53fe-248">Troubleshooting tips</span></span>
   <span data-ttu-id="a53fe-249"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="a53fe-249"><a name="TS"> </a></span></span>

- <span data-ttu-id="a53fe-250">跨域边界发送会议邀请时 (，例如，在两家公司之间) 。</span><span class="sxs-lookup"><span data-stu-id="a53fe-250">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="a53fe-251">在这种情况下，IT 管理员应决定是否允许外部用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="a53fe-251">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="a53fe-252">Microsoft Teams 会议室不支持通过 Exchange 2010 进行 Exchange 自动发现重定向。</span><span class="sxs-lookup"><span data-stu-id="a53fe-252">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="a53fe-253">一般而言，IT 管理员禁用他们不打算使用的任何音频终结点是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="a53fe-253">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="a53fe-254">如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。</span><span class="sxs-lookup"><span data-stu-id="a53fe-254">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="a53fe-255">丢失控制台触摸屏访问权限是已知问题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-255">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="a53fe-256">在这种情况下，有时可以通过重启 Microsoft Teams 会议室系统来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-256">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="a53fe-257">通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-257">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="a53fe-258">在这种情况下，重新启动电脑可以解决本地音频播放问题。</span><span class="sxs-lookup"><span data-stu-id="a53fe-258">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
