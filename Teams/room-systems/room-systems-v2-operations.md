---
title: Microsoft 团队会议室维护和操作
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 阅读本主题，了解 Microsoft 球队会议室的管理、下一代 Skype 会议室系统的管理。
ms.openlocfilehash: 14f4fb23868cc3e4247c700d15851511310db471
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775226"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="e359e-103">Microsoft 团队会议室维护和操作</span><span class="sxs-lookup"><span data-stu-id="e359e-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="e359e-104">阅读本主题，了解 Microsoft 球队会议室的管理、下一代 Skype 会议室系统的管理。</span><span class="sxs-lookup"><span data-stu-id="e359e-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="e359e-105">Microsoft 团队聊天室是 Microsoft 的最新会议解决方案，旨在将会议室转换为丰富、协作的体验。</span><span class="sxs-lookup"><span data-stu-id="e359e-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="e359e-106">用户将享受其熟悉的 Microsoft 团队或 Skype for business 界面，并且 IT 管理员将欣赏轻松部署和管理的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="e359e-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="e359e-107">Microsoft 球队会议室旨在利用 LCD 面板等现有设备进行轻松安装，将 Microsoft 团队或 Skype for business 带入会议室。</span><span class="sxs-lookup"><span data-stu-id="e359e-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="e359e-108">有了其他配置，使用 Microsoft Azure 监视器可进行远程管理，如使用[Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)中所述，使用[azure 监视器、管理部署 microsoft 团队会议室管理](azure-monitor-deploy.md) [带有 Azure 监视器的 Microsoft 团队聊天室设备](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="e359e-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="e359e-109">您也可以[使用 XML 配置文件远程管理 Microsoft 球队聊天室控制台设置](xml-config-file.md)，其中包括应用自定义显示主题。</span><span class="sxs-lookup"><span data-stu-id="e359e-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="e359e-110">在 Microsoft 团队聊天室上收集日志</span><span class="sxs-lookup"><span data-stu-id="e359e-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="e359e-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-111"></span></span>

<span data-ttu-id="e359e-112">若要收集日志，必须调用 Microsoft 团队聊天室应用随附的日志收集脚本。</span><span class="sxs-lookup"><span data-stu-id="e359e-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e359e-113">在管理模式中，启动提升的命令提示符并发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="e359e-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="e359e-114">日志将以 ZIP 文件的形式输出至 c:\rigel 中。</span><span class="sxs-lookup"><span data-stu-id="e359e-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="e359e-115">会议室前端显示屏设置</span><span class="sxs-lookup"><span data-stu-id="e359e-115">Front of Room Display Settings</span></span>
<span data-ttu-id="e359e-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-116"></span></span>

<span data-ttu-id="e359e-117">将会议室前端显示屏配置为扩展模式。</span><span class="sxs-lookup"><span data-stu-id="e359e-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="e359e-118">这样做可确保当你重启屏幕上的电源时，不会在该屏幕上复制控制台 UI。</span><span class="sxs-lookup"><span data-stu-id="e359e-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e359e-p105">用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。</span><span class="sxs-lookup"><span data-stu-id="e359e-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="e359e-121">Microsoft 团队会议室重置（出厂还原）</span><span class="sxs-lookup"><span data-stu-id="e359e-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="e359e-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-122"></span></span>

<span data-ttu-id="e359e-123">如果 Microsoft 团队聊天室运行不好，则执行恢复恢复可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="e359e-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="e359e-124">可在 "**恢复**" 选项卡上的 "设置" 应用中执行此操作。在 "**重置此电脑**" 下，选择 "**开始**"，然后**删除所有内容**。</span><span class="sxs-lookup"><span data-stu-id="e359e-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="e359e-125">按照其余提示重置设备。</span><span class="sxs-lookup"><span data-stu-id="e359e-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e359e-126">如果**保留我的文件-删除应用和设置，但**在 Windows 重置过程中选中了 "保留你的个人文件" 选项，则 Microsoft 团队聊天室可能会变得不可用的已知问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="e359e-127">请勿_使用此_选项。</span><span class="sxs-lookup"><span data-stu-id="e359e-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="e359e-128">支持的远程选项</span><span class="sxs-lookup"><span data-stu-id="e359e-128">Supported Remote Options</span></span>
<span data-ttu-id="e359e-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-129"></span></span>

<span data-ttu-id="e359e-130">下表汇总了可能的远程操作和可以用于完成这些操作的方法。</span><span class="sxs-lookup"><span data-stu-id="e359e-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="e359e-131">\*\*工作组 \*\*</span><span class="sxs-lookup"><span data-stu-id="e359e-131">**Workgroup**</span></span>|<span data-ttu-id="e359e-132">**未加入域**</span><span class="sxs-lookup"><span data-stu-id="e359e-132">**Not domain joined**</span></span>|<span data-ttu-id="e359e-133">**加入域**</span><span class="sxs-lookup"><span data-stu-id="e359e-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e359e-134">重新启动</span><span class="sxs-lookup"><span data-stu-id="e359e-134">Restart</span></span>  <br/> |<span data-ttu-id="e359e-135">远程桌面</span><span class="sxs-lookup"><span data-stu-id="e359e-135">Remote desktop</span></span>  <br/> <span data-ttu-id="e359e-136">远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e359e-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="e359e-137">远程桌面（需要进一步配置）</span><span class="sxs-lookup"><span data-stu-id="e359e-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="e359e-138">远程 Powershell （需要进一步配置）</span><span class="sxs-lookup"><span data-stu-id="e359e-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="e359e-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="e359e-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="e359e-140">更新操作系统</span><span class="sxs-lookup"><span data-stu-id="e359e-140">Update OS</span></span>  <br/> |<span data-ttu-id="e359e-141">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="e359e-141">Windows Update</span></span>  <br/> |<span data-ttu-id="e359e-142">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="e359e-142">Windows Update</span></span>  <br/> <span data-ttu-id="e359e-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="e359e-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="e359e-144">应用更新</span><span class="sxs-lookup"><span data-stu-id="e359e-144">App update</span></span>  <br/> |<span data-ttu-id="e359e-145">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="e359e-145">Windows Store</span></span>  <br/> |<span data-ttu-id="e359e-146">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="e359e-146">Windows Store</span></span>  <br/> <span data-ttu-id="e359e-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="e359e-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="e359e-148">Skype 帐户配置</span><span class="sxs-lookup"><span data-stu-id="e359e-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="e359e-149">当前不支持</span><span class="sxs-lookup"><span data-stu-id="e359e-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="e359e-150">当前不支持</span><span class="sxs-lookup"><span data-stu-id="e359e-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="e359e-151">访问日志</span><span class="sxs-lookup"><span data-stu-id="e359e-151">Access logs</span></span>  <br/> |<span data-ttu-id="e359e-152">当前不支持</span><span class="sxs-lookup"><span data-stu-id="e359e-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="e359e-153">当前不支持</span><span class="sxs-lookup"><span data-stu-id="e359e-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="e359e-154">为 Microsoft 团队聊天室配置组策略</span><span class="sxs-lookup"><span data-stu-id="e359e-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="e359e-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-155"></span></span>

<span data-ttu-id="e359e-156">本部分介绍 Microsoft 团队聊天室依赖于正常工作的系统设置。</span><span class="sxs-lookup"><span data-stu-id="e359e-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="e359e-157">将 Microsoft 团队会议室加入域时，请确保你的组策略不会覆盖下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="e359e-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="e359e-158">**设置**</span><span class="sxs-lookup"><span data-stu-id="e359e-158">**Setting**</span></span>|<span data-ttu-id="e359e-159">**这样**</span><span class="sxs-lookup"><span data-stu-id="e359e-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e359e-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （REG_SZ）1</span><span class="sxs-lookup"><span data-stu-id="e359e-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="e359e-161">支持 Microsoft 团队会议室启动</span><span class="sxs-lookup"><span data-stu-id="e359e-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="e359e-162">电源管理-\>通过交流，10分钟后关闭屏幕</span><span class="sxs-lookup"><span data-stu-id="e359e-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e359e-163">电源管理-\>在交流上，从不将系统置于睡眠状态</span><span class="sxs-lookup"><span data-stu-id="e359e-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e359e-164">使 Microsoft 团队会议室能够关闭附加的显示并自动唤醒</span><span class="sxs-lookup"><span data-stu-id="e359e-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e359e-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="e359e-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e359e-166">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="e359e-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="e359e-167">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="e359e-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="e359e-168">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="e359e-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e359e-169">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="e359e-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e359e-170">在 "[配置文件" 项目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)中讨论了使用组策略传输文件的内容。</span><span class="sxs-lookup"><span data-stu-id="e359e-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="e359e-171">当 Microsoft 团队聊天室设备与下一版本的 Windows 10 操作系统兼容时，设备会通过 Windows 更新自动更新到下一个版本。</span><span class="sxs-lookup"><span data-stu-id="e359e-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="e359e-172">Microsoft 团队会议室不应将设备升级到 Windows 10 的下一版本手动或通过启用 Windows 更新 for Business （WUFB）组策略 "选择要接收的更新的 Windows 准备情况级别" 和 "在预览版本中选择" 和 "功能更新通过 GPO 接收。</span><span class="sxs-lookup"><span data-stu-id="e359e-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="e359e-173">已启用这些组策略的设备已知通过 Microsoft 团队聊天室应用运行 Windows 10 操作系统更新时遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="e359e-174">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="e359e-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="e359e-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-175"></span></span>

<span data-ttu-id="e359e-176">你可以使用 PowerShell 远程执行以下管理操作（请参阅下表中的脚本示例）：</span><span class="sxs-lookup"><span data-stu-id="e359e-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="e359e-177">获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="e359e-177">Get attached devices</span></span>
    
- <span data-ttu-id="e359e-178">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="e359e-178">Get app status</span></span>
    
- <span data-ttu-id="e359e-179">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="e359e-179">Get system info</span></span>
    
- <span data-ttu-id="e359e-180">重启系统</span><span class="sxs-lookup"><span data-stu-id="e359e-180">Reboot system</span></span>
    
- <span data-ttu-id="e359e-181">检索日志</span><span class="sxs-lookup"><span data-stu-id="e359e-181">Retrieve logs</span></span>
    
- <span data-ttu-id="e359e-182">传输文件（需要加入域的 Microsoft 团队聊天室）</span><span class="sxs-lookup"><span data-stu-id="e359e-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="e359e-183">默认情况下，此功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="e359e-183">This functionality is off by default.</span></span> <span data-ttu-id="e359e-184">你需要在 Microsoft 团队聊天室系统上为你的环境启用远程 PowerShell 以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="e359e-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="e359e-185">有关如何启用远程 PowerShell 的信息，请参阅有关**[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 的文档。</span><span class="sxs-lookup"><span data-stu-id="e359e-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="e359e-186">例如，可以按如下所示启用远程 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e359e-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="e359e-187">在 Microsoft 团队聊天室设备上以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="e359e-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="e359e-188">打开提升的 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e359e-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="e359e-189">输入以下命令：Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="e359e-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="e359e-190">执行管理操作：</span><span class="sxs-lookup"><span data-stu-id="e359e-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="e359e-191">使用具有在 Microsoft 团队聊天室设备上运行 PowerShell 命令的权限的帐户凭据登录到电脑。</span><span class="sxs-lookup"><span data-stu-id="e359e-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="e359e-192">在电脑上打开常规 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e359e-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="e359e-193">从下表中复制命令文本，并在出现提示时粘贴它。</span><span class="sxs-lookup"><span data-stu-id="e359e-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="e359e-194">将`<Device fqdn>`具有相应环境的 FQDN 值替换为相应的字段。</span><span class="sxs-lookup"><span data-stu-id="e359e-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="e359e-195">将\* \<路径\> \*替换为 master SkypeSettings 配置文件的文件名和本地路径（或主题图像）。</span><span class="sxs-lookup"><span data-stu-id="e359e-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="e359e-196">获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="e359e-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="e359e-197">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="e359e-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="e359e-198">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="e359e-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="e359e-199">重启系统</span><span class="sxs-lookup"><span data-stu-id="e359e-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="e359e-200">检索日志</span><span class="sxs-lookup"><span data-stu-id="e359e-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="e359e-201">推送 XML 配置文件（或主题图形）</span><span class="sxs-lookup"><span data-stu-id="e359e-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="e359e-202">软件更新</span><span class="sxs-lookup"><span data-stu-id="e359e-202">Software updates</span></span>
<span data-ttu-id="e359e-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-203"></span></span>

<span data-ttu-id="e359e-204">默认情况下，Microsoft 团队聊天室会尝试连接到 Windows 应用商店以获取最新版本的 Microsoft 团队聊天室软件，因此设备将需要常规的 internet 访问权限。</span><span class="sxs-lookup"><span data-stu-id="e359e-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="e359e-205">在与 Microsoft 保持支持问题之前，请确保 Microsoft 团队聊天室设备已加载了最新版本的应用。</span><span class="sxs-lookup"><span data-stu-id="e359e-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="e359e-206">默认情况下，Microsoft 团队聊天室将连接到 Windows 更新以检索操作系统和 USB 外围设备固件更新，并将其安装在已配置的工作时间之外。</span><span class="sxs-lookup"><span data-stu-id="e359e-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="e359e-207">你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。</span><span class="sxs-lookup"><span data-stu-id="e359e-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="e359e-208">如果你希望手动管理更新，并且无法按照[Microsoft Store For Business](https://businessstore.microsoft.com/store) [分发脱机应用](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的常规过程进行操作，可以从[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)获取相应的 APPX 文件和依赖项（从可与 SCCM 一起使用的[配置 Microsoft 团队聊天室控制台](console.md)的说明。</span><span class="sxs-lookup"><span data-stu-id="e359e-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="e359e-209">部署工具包版本滞后于应用商店版本，因此它可能不会始终与最新的可用内部版本匹配。</span><span class="sxs-lookup"><span data-stu-id="e359e-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="e359e-210">使用 Powershell 更新</span><span class="sxs-lookup"><span data-stu-id="e359e-210">To update using Powershell</span></span>

1. <span data-ttu-id="e359e-211">将程序包从安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)解压缩到设备可以访问的共享。</span><span class="sxs-lookup"><span data-stu-id="e359e-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="e359e-212">运行以下针对 Microsoft 团队聊天室设备的脚本，根据需要\<将\>共享更改为设备共享：</span><span class="sxs-lookup"><span data-stu-id="e359e-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="e359e-213">管理模式和设备管理</span><span class="sxs-lookup"><span data-stu-id="e359e-213">Admin mode and device management</span></span>
<span data-ttu-id="e359e-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-214"></span></span>

<span data-ttu-id="e359e-215">某些管理功能（如手动安装专用 CA 证书）要求在 "管理员模式" 下放置 Surface Pro 设备。</span><span class="sxs-lookup"><span data-stu-id="e359e-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="e359e-216">当 Microsoft 团队聊天室应用正在运行时切换到管理员模式并返回回来</span><span class="sxs-lookup"><span data-stu-id="e359e-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="e359e-217">挂起任何正在进行的呼叫，并返回主屏幕。</span><span class="sxs-lookup"><span data-stu-id="e359e-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="e359e-218">选择齿轮图标并弹出菜单（选项为 "**设置**"、"**辅助功能**" 和 "**重启设备**"）。</span><span class="sxs-lookup"><span data-stu-id="e359e-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="e359e-219">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="e359e-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="e359e-220">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="e359e-220">Enter the Administrator Password.</span></span> <span data-ttu-id="e359e-221">将显示“设置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="e359e-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e359e-222">如果设备未加入域，将默认使用本地管理帐户（用户名 "Admin"）。</span><span class="sxs-lookup"><span data-stu-id="e359e-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="e359e-223">此帐户的默认密码为“sfb”，但出于安全考虑，建议贵组织尽快更改此密码。</span><span class="sxs-lookup"><span data-stu-id="e359e-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="e359e-224">如果计算机已加入域，则可以使用适当权限的域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e359e-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="e359e-225">在左侧列中选择 " **Windows 设置**"。</span><span class="sxs-lookup"><span data-stu-id="e359e-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="e359e-226">选择“**转至管理员登录**”。</span><span class="sxs-lookup"><span data-stu-id="e359e-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="e359e-227">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="e359e-227">Enter the Administrator Password.</span></span> <span data-ttu-id="e359e-228">此时将正常注销应用并带你访问 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="e359e-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="e359e-229">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="e359e-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="e359e-230">你将拥有管理设备所需的权限。</span><span class="sxs-lookup"><span data-stu-id="e359e-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="e359e-231">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="e359e-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="e359e-232">从管理员帐户注销。</span><span class="sxs-lookup"><span data-stu-id="e359e-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="e359e-233">通过选择屏幕最左侧的用户帐户图标，然后选择 " **Skype**"，返回到 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="e359e-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="e359e-234">如果未列出**Skype**用户，您可能需要选择 "**其他用户**" 并输入 " **.\skype** " 作为用户名，然后登录。</span><span class="sxs-lookup"><span data-stu-id="e359e-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="e359e-235">控制台现在恢复正常操作模式。以下过程要求你将键盘附加到设备（如果尚未连接）。</span><span class="sxs-lookup"><span data-stu-id="e359e-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="e359e-236">当 Microsoft 团队聊天室应用崩溃时切换到管理员模式并返回回来</span><span class="sxs-lookup"><span data-stu-id="e359e-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="e359e-237">快速连续按 Windows 键五次。</span><span class="sxs-lookup"><span data-stu-id="e359e-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="e359e-238">此时将显示 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="e359e-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="e359e-239">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="e359e-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e359e-240">此方法不会将 Skype 用户注销或正常终止应用，但如果应用未响应且其他方法不可用，则可以使用它。</span><span class="sxs-lookup"><span data-stu-id="e359e-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="e359e-241">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="e359e-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="e359e-242">完成后，重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e359e-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="e359e-243">控制台将重启到其正常操作模式，运行 Microsoft 团队聊天室应用。</span><span class="sxs-lookup"><span data-stu-id="e359e-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e359e-244">如果已附加键盘，则可以将其删除，以允许执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e359e-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="e359e-245">故障排除提示</span><span class="sxs-lookup"><span data-stu-id="e359e-245">Troubleshooting tips</span></span>
   <span data-ttu-id="e359e-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="e359e-246"></span></span>

- <span data-ttu-id="e359e-247">通过域边界（例如，两家公司之间）发送会议邀请时，可能不会显示会议邀请。</span><span class="sxs-lookup"><span data-stu-id="e359e-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="e359e-248">在这种情况下，IT 管理员应决定是否允许外部用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="e359e-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="e359e-249">Microsoft 团队聊天室不支持通过 Exchange 2010 的 Exchange 自动发现重定向。</span><span class="sxs-lookup"><span data-stu-id="e359e-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="e359e-250">一般情况下，IT 管理员禁用不打算使用的任何音频终结点是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="e359e-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="e359e-251">如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。</span><span class="sxs-lookup"><span data-stu-id="e359e-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="e359e-252">丢失控制台触摸屏访问权限是已知问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="e359e-253">在这种情况下，有时会通过重新启动 Microsoft 团队聊天室系统来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="e359e-254">通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="e359e-255">在这种情况下，重新启动电脑可以解决本地音频播放问题。</span><span class="sxs-lookup"><span data-stu-id="e359e-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
