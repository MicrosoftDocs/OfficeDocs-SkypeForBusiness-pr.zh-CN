---
title: Microsoft 团队聊天室的维护和操作
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: 阅读本主题可了解有关 Microsoft 团队聊天室，管理下一代 Skype 会议室系统。
ms.openlocfilehash: efaf2a1bae7980855501b826d6a2ee902f0f56b2
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362659"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="2efcc-103">Microsoft 团队聊天室的维护和操作</span><span class="sxs-lookup"><span data-stu-id="2efcc-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="2efcc-104">阅读本主题可了解有关 Microsoft 团队聊天室，管理下一代 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="2efcc-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="2efcc-105">Microsoft 团队聊天室是 Microsoft 的最新的会议解决方案设计您的会议室转换为丰富的协作体验。</span><span class="sxs-lookup"><span data-stu-id="2efcc-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="2efcc-106">用户将享受其熟悉的 Microsoft 团队或业务接口和 IT 管理员的 Skype 将抽易于部署和管理 Windows 10 Skype 会议应用程序。</span><span class="sxs-lookup"><span data-stu-id="2efcc-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="2efcc-107">Microsoft 团队聊天室旨在利用现有的设备，如 LCD 面板为了简化安装将 Microsoft 团队或 Skype for Business 导入您的会议室。</span><span class="sxs-lookup"><span data-stu-id="2efcc-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="2efcc-108">其他配置远程管理是可以[使用 Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)、[部署 Microsoft 团队聊天室管理使用 Azure 监视器](azure-monitor-deploy.md)，[管理中所述使用 Microsoft Azure 监视器使用 Azure 监视器的 Microsoft 团队聊天室设备](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="2efcc-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="2efcc-109">您还可以[管理 Microsoft 团队聊天室控制台远程设置的 XML 配置文件](xml-config-file.md)，其中包括应用自定义显示主题。</span><span class="sxs-lookup"><span data-stu-id="2efcc-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="2efcc-110">Microsoft 团队聊天室上收集日志</span><span class="sxs-lookup"><span data-stu-id="2efcc-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="2efcc-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-111"></span></span>

<span data-ttu-id="2efcc-112">收集日志，必须调用附带的 Microsoft 团队聊天室应用程序日志收集脚本。</span><span class="sxs-lookup"><span data-stu-id="2efcc-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="2efcc-113">在管理模式中，启动提升的命令提示符并发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="2efcc-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="2efcc-114">日志将以 ZIP 文件的形式输出至 c:\rigel 中。</span><span class="sxs-lookup"><span data-stu-id="2efcc-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="2efcc-115">会议室前端显示屏设置</span><span class="sxs-lookup"><span data-stu-id="2efcc-115">Front of Room Display Settings</span></span>
<span data-ttu-id="2efcc-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-116"></span></span>

<span data-ttu-id="2efcc-117">将会议室前端显示屏配置为扩展模式。</span><span class="sxs-lookup"><span data-stu-id="2efcc-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="2efcc-118">这样可以确保的 UI 不重复该显示屏时显示周期电源控制台。</span><span class="sxs-lookup"><span data-stu-id="2efcc-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2efcc-p105">用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。</span><span class="sxs-lookup"><span data-stu-id="2efcc-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="2efcc-121">Microsoft 团队聊天室重置 （出厂还原）</span><span class="sxs-lookup"><span data-stu-id="2efcc-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="2efcc-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-122"></span></span>

<span data-ttu-id="2efcc-123">如果 Microsoft 团队聊天室也未运行，可以帮助执行出厂重置。</span><span class="sxs-lookup"><span data-stu-id="2efcc-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="2efcc-124">这可**重置此 PC**下方的**恢复**选项卡上的设置应用程序中，选择**开始**，然后**删除所有内容**。</span><span class="sxs-lookup"><span data-stu-id="2efcc-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="2efcc-125">按照剩余提示重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="2efcc-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2efcc-126">是一个已知的问题 Microsoft 团队聊天室可以成为 Windows 重置的过程中选择**保存我的文件的删除应用程序和设置，但您的个人文件**选项的情况下无法使用。</span><span class="sxs-lookup"><span data-stu-id="2efcc-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="2efcc-127">执行_不_使用此选项。</span><span class="sxs-lookup"><span data-stu-id="2efcc-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="2efcc-128">支持的远程选项</span><span class="sxs-lookup"><span data-stu-id="2efcc-128">Supported Remote Options</span></span>
<span data-ttu-id="2efcc-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-129"></span></span>

<span data-ttu-id="2efcc-130">下表汇总了可能的远程操作和可以用于完成这些操作的方法。</span><span class="sxs-lookup"><span data-stu-id="2efcc-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="2efcc-131">\*\*工作组 \*\*</span><span class="sxs-lookup"><span data-stu-id="2efcc-131">**Workgroup**</span></span>|<span data-ttu-id="2efcc-132">**未加入域**</span><span class="sxs-lookup"><span data-stu-id="2efcc-132">**Not domain joined**</span></span>|<span data-ttu-id="2efcc-133">**加入域**</span><span class="sxs-lookup"><span data-stu-id="2efcc-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2efcc-134">重新启动</span><span class="sxs-lookup"><span data-stu-id="2efcc-134">Restart</span></span>  <br/> |<span data-ttu-id="2efcc-135">远程桌面</span><span class="sxs-lookup"><span data-stu-id="2efcc-135">Remote desktop</span></span>  <br/> <span data-ttu-id="2efcc-136">远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2efcc-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="2efcc-137">远程桌面 （需要进一步的配置）</span><span class="sxs-lookup"><span data-stu-id="2efcc-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="2efcc-138">远程 Powershell （需要进一步的配置）</span><span class="sxs-lookup"><span data-stu-id="2efcc-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="2efcc-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="2efcc-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="2efcc-140">更新操作系统</span><span class="sxs-lookup"><span data-stu-id="2efcc-140">Update OS</span></span>  <br/> |<span data-ttu-id="2efcc-141">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="2efcc-141">Windows Update</span></span>  <br/> |<span data-ttu-id="2efcc-142">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="2efcc-142">Windows Update</span></span>  <br/> <span data-ttu-id="2efcc-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="2efcc-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="2efcc-144">应用更新</span><span class="sxs-lookup"><span data-stu-id="2efcc-144">App update</span></span>  <br/> |<span data-ttu-id="2efcc-145">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="2efcc-145">Windows Store</span></span>  <br/> |<span data-ttu-id="2efcc-146">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="2efcc-146">Windows Store</span></span>  <br/> <span data-ttu-id="2efcc-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="2efcc-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="2efcc-148">Skype 帐户配置</span><span class="sxs-lookup"><span data-stu-id="2efcc-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="2efcc-149">当前不支持</span><span class="sxs-lookup"><span data-stu-id="2efcc-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="2efcc-150">当前不支持</span><span class="sxs-lookup"><span data-stu-id="2efcc-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="2efcc-151">访问日志</span><span class="sxs-lookup"><span data-stu-id="2efcc-151">Access logs</span></span>  <br/> |<span data-ttu-id="2efcc-152">当前不支持</span><span class="sxs-lookup"><span data-stu-id="2efcc-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="2efcc-153">当前不支持</span><span class="sxs-lookup"><span data-stu-id="2efcc-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="2efcc-154">为 Microsoft 团队房间配置组策略</span><span class="sxs-lookup"><span data-stu-id="2efcc-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="2efcc-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-155"></span></span>

<span data-ttu-id="2efcc-156">本节介绍 Microsoft 团队聊天室取决于能够正常工作的系统设置。</span><span class="sxs-lookup"><span data-stu-id="2efcc-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="2efcc-157">时加入域的 Microsoft 团队聊天室，确保您的组策略不会覆盖下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="2efcc-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="2efcc-158">**设置**</span><span class="sxs-lookup"><span data-stu-id="2efcc-158">**Setting**</span></span>|<span data-ttu-id="2efcc-159">**允许**</span><span class="sxs-lookup"><span data-stu-id="2efcc-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2efcc-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="2efcc-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="2efcc-161">启用 Microsoft 团队聊天室启动</span><span class="sxs-lookup"><span data-stu-id="2efcc-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="2efcc-162">电源管理-\>上交流，关闭屏幕 10 分钟后</span><span class="sxs-lookup"><span data-stu-id="2efcc-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="2efcc-163">电源管理-\>上交流，从不提供系统进入休眠模式</span><span class="sxs-lookup"><span data-stu-id="2efcc-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="2efcc-164">启用 Microsoft 团队聊天室附加显示关闭并自动唤醒</span><span class="sxs-lookup"><span data-stu-id="2efcc-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="2efcc-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="2efcc-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="2efcc-166">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="2efcc-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="2efcc-167">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="2efcc-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="2efcc-168">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="2efcc-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="2efcc-169">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="2efcc-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="2efcc-170">使用组策略的文件传输将在[配置文件项](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)讨论。</span><span class="sxs-lookup"><span data-stu-id="2efcc-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="2efcc-171">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="2efcc-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="2efcc-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-172"></span></span>

<span data-ttu-id="2efcc-173">您可以使用 PowerShell 远程执行以下管理操作 （参阅下表中的脚本示例）：</span><span class="sxs-lookup"><span data-stu-id="2efcc-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="2efcc-174">获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="2efcc-174">Get attached devices</span></span>
    
- <span data-ttu-id="2efcc-175">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="2efcc-175">Get app status</span></span>
    
- <span data-ttu-id="2efcc-176">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="2efcc-176">Get system info</span></span>
    
- <span data-ttu-id="2efcc-177">重启系统</span><span class="sxs-lookup"><span data-stu-id="2efcc-177">Reboot system</span></span>
    
- <span data-ttu-id="2efcc-178">检索日志</span><span class="sxs-lookup"><span data-stu-id="2efcc-178">Retrieve logs</span></span>
    
- <span data-ttu-id="2efcc-179">传输文件 （需要加入域的 Microsoft 团队聊天室）</span><span class="sxs-lookup"><span data-stu-id="2efcc-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="2efcc-180">默认情况下，此功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="2efcc-180">This functionality is off by default.</span></span> <span data-ttu-id="2efcc-181">您需要启用 Microsoft 团队聊天室系统环境的远程 PowerShell，可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="2efcc-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="2efcc-182">请参阅有关如何启用远程 PowerShell **[Enable-psremoting](https://technet.microsoft.com/library/hh849694.aspx)** 的文档。</span><span class="sxs-lookup"><span data-stu-id="2efcc-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="2efcc-183">例如，可以按如下所示启用远程 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="2efcc-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="2efcc-184">以管理员身份登录的 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="2efcc-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="2efcc-185">打开提升的 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2efcc-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="2efcc-186">输入以下命令：Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="2efcc-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="2efcc-187">执行管理操作：</span><span class="sxs-lookup"><span data-stu-id="2efcc-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="2efcc-188">登录到有权的 Microsoft 团队聊天室设备上运行 PowerShell 命令的帐户凭据的 PC。</span><span class="sxs-lookup"><span data-stu-id="2efcc-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="2efcc-189">打开常规 PowerShell 命令提示符 PC 上。</span><span class="sxs-lookup"><span data-stu-id="2efcc-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="2efcc-190">从下表中复制的命令文本，并将其粘贴在提示符处。</span><span class="sxs-lookup"><span data-stu-id="2efcc-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="2efcc-191">替换`<Device fqdn>`具有 FQDN 值的字段适合于您的环境。</span><span class="sxs-lookup"><span data-stu-id="2efcc-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="2efcc-192">替换*\<路径\>* 用文件名和母版页 SkypeSettings.xml 配置文件 （或主题图像） 的本地路径。</span><span class="sxs-lookup"><span data-stu-id="2efcc-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="2efcc-193">若要获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="2efcc-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="2efcc-194">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="2efcc-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="2efcc-195">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="2efcc-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="2efcc-196">重启系统</span><span class="sxs-lookup"><span data-stu-id="2efcc-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="2efcc-197">检索日志</span><span class="sxs-lookup"><span data-stu-id="2efcc-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="2efcc-198">推送 XML 配置文件 （或主题图形）</span><span class="sxs-lookup"><span data-stu-id="2efcc-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="2efcc-199">软件更新</span><span class="sxs-lookup"><span data-stu-id="2efcc-199">Software updates</span></span>
<span data-ttu-id="2efcc-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-200"></span></span>

<span data-ttu-id="2efcc-201">默认情况下，Microsoft 团队聊天室尝试连接到 Windows 应用商店获取最新版本的 Microsoft 团队聊天室软件，因此设备需要正则 internet 访问。</span><span class="sxs-lookup"><span data-stu-id="2efcc-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="2efcc-202">之前与 Microsoft 联系支持问题，请确保 Microsoft 团队聊天室设备将加载包含应用程序的最新版本。</span><span class="sxs-lookup"><span data-stu-id="2efcc-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="2efcc-203">默认情况下，Microsoft 团队聊天室连接到 Windows Update 以检索操作系统和 USB 外围设备固件更新，并安装它们非配置工作时间发出。</span><span class="sxs-lookup"><span data-stu-id="2efcc-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="2efcc-204">你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。</span><span class="sxs-lookup"><span data-stu-id="2efcc-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="2efcc-205">如果您想要手动管理更新，并且无法按照[Microsoft Store for Business](https://businessstore.microsoft.com/store)到[分发脱机应用程序](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的常规过程，您可以获取的相应约文件和从[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)（从相关性要[配置的 Microsoft 团队聊天室控制台](console.md)的说明） 可用于 SCCM。</span><span class="sxs-lookup"><span data-stu-id="2efcc-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="2efcc-206">部署套件版本低于存储版本中，因此不可能总是匹配的最新的生成。</span><span class="sxs-lookup"><span data-stu-id="2efcc-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="2efcc-207">使用 Powershell 进行更新</span><span class="sxs-lookup"><span data-stu-id="2efcc-207">To update using Powershell</span></span>

1. <span data-ttu-id="2efcc-208">从安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)到共享设备可以访问提取程序包。</span><span class="sxs-lookup"><span data-stu-id="2efcc-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="2efcc-209">运行以下脚本面向 Microsoft 团队聊天室设备，更改\<共享\>到设备共享根据：</span><span class="sxs-lookup"><span data-stu-id="2efcc-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="2efcc-210">管理模式和设备管理</span><span class="sxs-lookup"><span data-stu-id="2efcc-210">Admin mode and device management</span></span>
<span data-ttu-id="2efcc-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-211"></span></span>

<span data-ttu-id="2efcc-212">一些管理功能，如手动安装将私有 CA 证书，需要管理员模式中发出 Surface Pro 设备。</span><span class="sxs-lookup"><span data-stu-id="2efcc-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="2efcc-213">切换到管理员模式和 Microsoft 团队聊天室应用程序运行时回报</span><span class="sxs-lookup"><span data-stu-id="2efcc-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="2efcc-214">挂断任何正在进行的呼叫，并返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="2efcc-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="2efcc-215">选择齿轮图标和弹出菜单 （选项是**设置**、**辅助功能**，和**重新启动设备**）。</span><span class="sxs-lookup"><span data-stu-id="2efcc-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="2efcc-216">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="2efcc-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="2efcc-217">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="2efcc-217">Enter the Administrator Password.</span></span> <span data-ttu-id="2efcc-218">将显示“设置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="2efcc-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2efcc-219">如果设备不加入域的将默认情况下使用本地管理帐户 （用户名"Admin"）。</span><span class="sxs-lookup"><span data-stu-id="2efcc-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="2efcc-220">此帐户的默认密码为“sfb”，但出于安全考虑，建议贵组织尽快更改此密码。</span><span class="sxs-lookup"><span data-stu-id="2efcc-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="2efcc-221">如果计算机已加入域，您可以使用相应特权的域帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="2efcc-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="2efcc-222">左侧列中，选择**Windows 设置**。</span><span class="sxs-lookup"><span data-stu-id="2efcc-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="2efcc-223">选择“**转至管理员登录**”。</span><span class="sxs-lookup"><span data-stu-id="2efcc-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="2efcc-224">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="2efcc-224">Enter the Administrator Password.</span></span> <span data-ttu-id="2efcc-225">此时将正常注销应用并带你访问 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="2efcc-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="2efcc-226">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="2efcc-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="2efcc-227">您必须所需的权限来管理设备。</span><span class="sxs-lookup"><span data-stu-id="2efcc-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="2efcc-228">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="2efcc-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="2efcc-229">从管理员帐户注销。</span><span class="sxs-lookup"><span data-stu-id="2efcc-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="2efcc-230">通过选择最左侧的屏幕上的用户帐户图标，然后选择**Skype**返回到 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="2efcc-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="2efcc-231">如果未列出的**Skype**用户，您可能需要选择**其他用户**，然后输入 **。 \skype**作为用户名和登录。</span><span class="sxs-lookup"><span data-stu-id="2efcc-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="2efcc-232">控制台现返回处于正常操作模式。下面的过程，需要将键盘附加到该设备，如果尚未附加。</span><span class="sxs-lookup"><span data-stu-id="2efcc-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="2efcc-233">切换到管理员模式和 Microsoft 团队聊天室应用程序崩溃时回报</span><span class="sxs-lookup"><span data-stu-id="2efcc-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="2efcc-234">快速连续按 Windows 键五次。</span><span class="sxs-lookup"><span data-stu-id="2efcc-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="2efcc-235">此时将显示 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="2efcc-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="2efcc-236">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="2efcc-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2efcc-237">此方法不会注销 Skype 用户或正常终止应用程序，但如果应用程序未响应并没有可用的其他方法，需要使用它。</span><span class="sxs-lookup"><span data-stu-id="2efcc-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="2efcc-238">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="2efcc-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="2efcc-239">完成后，重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="2efcc-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="2efcc-240">控制台重新启动到其正常操作模式，运行 Microsoft 团队聊天室应用程序。</span><span class="sxs-lookup"><span data-stu-id="2efcc-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="2efcc-241">您可以删除键盘，如果它已连接以允许您执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2efcc-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="2efcc-242">故障排除提示</span><span class="sxs-lookup"><span data-stu-id="2efcc-242">Troubleshooting tips</span></span>
   <span data-ttu-id="2efcc-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="2efcc-243"></span></span>

- <span data-ttu-id="2efcc-244">跨域边界 （例如，两个公司） 之间发送时，可能不出现会议邀请。</span><span class="sxs-lookup"><span data-stu-id="2efcc-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="2efcc-245">在这种情况下，IT 管理员应决定是否允许外部用户可以安排会议。</span><span class="sxs-lookup"><span data-stu-id="2efcc-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="2efcc-246">Microsoft 团队聊天室不支持 Exchange 2010 通过 Exchange AutoDiscover 重定向。</span><span class="sxs-lookup"><span data-stu-id="2efcc-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="2efcc-247">一般情况下，最好 IT 管理员可以禁用他们不想要使用的任何音频终结点。</span><span class="sxs-lookup"><span data-stu-id="2efcc-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="2efcc-248">如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。</span><span class="sxs-lookup"><span data-stu-id="2efcc-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="2efcc-249">丢失控制台触摸屏访问权限是已知问题。</span><span class="sxs-lookup"><span data-stu-id="2efcc-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="2efcc-250">在这种情况下，通过重新启动 Microsoft 团队聊天室系统有时解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2efcc-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="2efcc-251">通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。</span><span class="sxs-lookup"><span data-stu-id="2efcc-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="2efcc-252">在这种情况下，重新启动电脑可以解决本地音频播放问题。</span><span class="sxs-lookup"><span data-stu-id="2efcc-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
