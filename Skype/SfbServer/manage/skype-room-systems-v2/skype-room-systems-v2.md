---
title: 管理 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: 阅读本主题，以了解有关管理的 Skype 的空间系统 v2 Skype 的空间系统的下一代。
ms.openlocfilehash: 5ef699bed1a77fc48f59ba4c5f8eb78ccc286ef7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2"></a><span data-ttu-id="ed6e2-103">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="ed6e2-103">Manage Skype Room Systems v2</span></span>
 
<span data-ttu-id="ed6e2-104">阅读本主题，以了解有关管理的 Skype 的空间系统 v2 Skype 的空间系统的下一代。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="ed6e2-105">Skype 的空间系统 v2 是 Microsoft 的最新会议解决方案，旨在转换为业务经验丰富、 协作 Skype 的会议室内。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="ed6e2-106">用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="ed6e2-107">Skype 的空间系统 v2 旨在利用现有的设备，如液晶屏，以方便的安装 Skype 业务置于您的会议室。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="ed6e2-108">与其他配置，远程管理是可能使用 Microsoft 操作管理套件 (OMS)，所述[计划 Skype 的空间系统 OMS v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[部署 Skype 的空间系统 v2 管理与 OMS](../../deploy/deploy-clients/with-oms.md)和[管理Skype 的空间系统 OMS 的 v2 设备](oms.md)。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-108">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](oms.md).</span></span> <span data-ttu-id="ed6e2-109">您还可以[远程使用 XML 配置文件的 Skype 的空间系统 v2 管理控制台设置](xml-config-file.md)，其中包括应用自定义显示主题。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="ed6e2-110">收集 Skype 会议室系统 v2 的日志</span><span class="sxs-lookup"><span data-stu-id="ed6e2-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="ed6e2-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-111"></span></span>

<span data-ttu-id="ed6e2-112">收集日志，您必须调用日志收集脚本附带 Skype 的空间系统 v2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="ed6e2-113">在管理模式中，启动提升的命令提示符并发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="ed6e2-114">日志将以 ZIP 文件的形式输出至 c:\rigel 中。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="ed6e2-115">会议室前端显示屏设置</span><span class="sxs-lookup"><span data-stu-id="ed6e2-115">Front of Room Display Settings</span></span>
<span data-ttu-id="ed6e2-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-116"></span></span>

<span data-ttu-id="ed6e2-117">将会议室前端显示屏配置为扩展模式。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="ed6e2-118">这样做可确保在对显示屏进行电源重启时，控制台 UI 不会重复出现在显示屏上。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-118">Doing so will ensure that the console UI is not duplicated on that display when power cycling the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed6e2-119">用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="ed6e2-120">并非所有电视都支持此功能。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="ed6e2-121">Skype 会议室系统 v2 重置（恢复出厂设置）</span><span class="sxs-lookup"><span data-stu-id="ed6e2-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="ed6e2-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-122"></span></span>

<span data-ttu-id="ed6e2-123">如果 Skype 的空间系统 v2 没有很好地运行，可以帮助执行出厂重置。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-123">If Skype Room Systems v2 isn't running well, performing a factory reset may help.</span></span> <span data-ttu-id="ed6e2-124">这从"重置此 PC"标题下的"恢复"选项卡可以设置应用程序中，选择"开始"跟"删除内容"。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-124">This can be done in the Settings app from the "Recovery" tab. Beneath the "Reset this PC" header, select "Get started" followed by "Remove everything."</span></span> <span data-ttu-id="ed6e2-125">根据需要按照其余提示操作以重置设备。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-125">Follow the remaining prompts as desired to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed6e2-126">是一个已知的问题，Skype 的空间系统 v2 会窗口重置过程中选择了"保持我的文件-删除应用程序和设置，但保留您的个人文件"选项的情况下不可用。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-126">There is a known issue where the Skype Room Systems v2 can become unusable if the "Keep my files - Removes Apps and settings, but keeps your personal files" option is selected during the Windows Reset process.</span></span> <span data-ttu-id="ed6e2-127">**请勿**使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-127">**Do not** use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="ed6e2-128">支持的远程选项</span><span class="sxs-lookup"><span data-stu-id="ed6e2-128">Supported Remote Options</span></span>
<span data-ttu-id="ed6e2-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-129"></span></span>

<span data-ttu-id="ed6e2-130">下表汇总了可能的远程操作和可以用于完成这些操作的方法。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="ed6e2-131">**工作组**</span><span class="sxs-lookup"><span data-stu-id="ed6e2-131">**Workgroup**</span></span>|<span data-ttu-id="ed6e2-132">**不加入域**</span><span class="sxs-lookup"><span data-stu-id="ed6e2-132">**Not domain joined**</span></span>|<span data-ttu-id="ed6e2-133">**加入域**</span><span class="sxs-lookup"><span data-stu-id="ed6e2-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed6e2-134">重新启动</span><span class="sxs-lookup"><span data-stu-id="ed6e2-134">Restart</span></span>  <br/> |<span data-ttu-id="ed6e2-135">远程桌面</span><span class="sxs-lookup"><span data-stu-id="ed6e2-135">Remote desktop</span></span>  <br/> <span data-ttu-id="ed6e2-136">远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed6e2-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="ed6e2-137">远程桌面 （需要进一步配置）</span><span class="sxs-lookup"><span data-stu-id="ed6e2-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="ed6e2-138">远程 Powershell （需要进一步配置）</span><span class="sxs-lookup"><span data-stu-id="ed6e2-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="ed6e2-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="ed6e2-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="ed6e2-140">更新操作系统</span><span class="sxs-lookup"><span data-stu-id="ed6e2-140">Update OS</span></span>  <br/> |<span data-ttu-id="ed6e2-141">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="ed6e2-141">Windows Update</span></span>  <br/> |<span data-ttu-id="ed6e2-142">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="ed6e2-142">Windows Update</span></span>  <br/> <span data-ttu-id="ed6e2-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="ed6e2-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="ed6e2-144">应用更新</span><span class="sxs-lookup"><span data-stu-id="ed6e2-144">App update</span></span>  <br/> |<span data-ttu-id="ed6e2-145">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="ed6e2-145">Windows Store</span></span>  <br/> |<span data-ttu-id="ed6e2-146">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="ed6e2-146">Windows Store</span></span>  <br/> <span data-ttu-id="ed6e2-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="ed6e2-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="ed6e2-148">Skype 帐户配置</span><span class="sxs-lookup"><span data-stu-id="ed6e2-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="ed6e2-149">当前不支持</span><span class="sxs-lookup"><span data-stu-id="ed6e2-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="ed6e2-150">当前不支持</span><span class="sxs-lookup"><span data-stu-id="ed6e2-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="ed6e2-151">访问日志</span><span class="sxs-lookup"><span data-stu-id="ed6e2-151">Access logs</span></span>  <br/> |<span data-ttu-id="ed6e2-152">当前不支持</span><span class="sxs-lookup"><span data-stu-id="ed6e2-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="ed6e2-153">当前不支持</span><span class="sxs-lookup"><span data-stu-id="ed6e2-153">Not currently supported</span></span>  <br/> |
||||
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="ed6e2-154">为 Skype 会议室系统 v2 配置组策略</span><span class="sxs-lookup"><span data-stu-id="ed6e2-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="ed6e2-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-155"></span></span>

<span data-ttu-id="ed6e2-156">本部分介绍 Skype 的空间系统 v2 取决于正常的系统设置。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="ed6e2-157">当 Skype 的空间系统 v2 加入到域时，请确保您的组策略不重写下列设置：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-157">When joining Skype Room Systems v2 to a domain, please ensure that your group policy does not override the following settings:</span></span>
  

|<span data-ttu-id="ed6e2-158">**设置**</span><span class="sxs-lookup"><span data-stu-id="ed6e2-158">**Setting**</span></span>|<span data-ttu-id="ed6e2-159">**允许**</span><span class="sxs-lookup"><span data-stu-id="ed6e2-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed6e2-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="ed6e2-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="ed6e2-161">使启动的 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="ed6e2-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="ed6e2-162">电源管理-\>上交流，关闭屏幕后 10 分钟</span><span class="sxs-lookup"><span data-stu-id="ed6e2-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="ed6e2-163">电源管理-\>上交流，永远不会使系统进入休眠模式</span><span class="sxs-lookup"><span data-stu-id="ed6e2-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="ed6e2-164">让 Skype 的空间系统 v2 关闭附加的显示功能和自动唤醒</span><span class="sxs-lookup"><span data-stu-id="ed6e2-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="ed6e2-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="ed6e2-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="ed6e2-166">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="ed6e2-167">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="ed6e2-168">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="ed6e2-169">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="ed6e2-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="ed6e2-170">使用组策略的文件传输将讨论[配置文件项](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="ed6e2-171">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="ed6e2-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="ed6e2-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-172"></span></span>

<span data-ttu-id="ed6e2-173">可以使用 PowerShell 远程执行以下管理操作（请参阅下表了解脚本示例）：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-173">You can perform the following management operations remotely using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="ed6e2-174">获取连接的设备</span><span class="sxs-lookup"><span data-stu-id="ed6e2-174">Get attached devices</span></span>
    
- <span data-ttu-id="ed6e2-175">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="ed6e2-175">Get app status</span></span>
    
- <span data-ttu-id="ed6e2-176">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="ed6e2-176">Get system info</span></span>
    
- <span data-ttu-id="ed6e2-177">重启系统</span><span class="sxs-lookup"><span data-stu-id="ed6e2-177">Reboot system</span></span>
    
- <span data-ttu-id="ed6e2-178">检索日志</span><span class="sxs-lookup"><span data-stu-id="ed6e2-178">Retrieve logs</span></span>
    
- <span data-ttu-id="ed6e2-179">传输文件 （需要加入域的 Skype 的空间系统第 2 版）</span><span class="sxs-lookup"><span data-stu-id="ed6e2-179">Transfer files (requires a domain joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="ed6e2-180">默认情况下，此功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-180">This functionality is off by default.</span></span> <span data-ttu-id="ed6e2-181">您需要启用远程 PowerShell Skype 的空间系统 v2 系统环境，可以执行下面的操作。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="ed6e2-182">请参阅有关如何启用远程 PowerShell 的文档上**[启用 PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** 。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** for information on how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="ed6e2-183">例如，可以按如下所示启用远程 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="ed6e2-184">以管理员身份登录 Skype 的空间系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="ed6e2-185">启动提升的 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-185">Launch an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="ed6e2-186">输入下面的命令： 启用 PSRemoting-强制</span><span class="sxs-lookup"><span data-stu-id="ed6e2-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="ed6e2-187">执行管理操作：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="ed6e2-188">登录到使用拥有 Skype 的空间系统 v2 设备上运行 PowerShell 命令的权限的帐户凭据 PC。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-188">Sign into a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="ed6e2-189">在你的电脑上启动常规 PowerShell 命令提示窗口。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-189">Launch a regular PowerShell command prompt on your PC.</span></span>
    
3. <span data-ttu-id="ed6e2-190">将下表中的命令文本复制并粘贴到提示窗口中。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-190">Copy the command text from the table below and paste it into the prompt.</span></span>
    
4. <span data-ttu-id="ed6e2-191">更换`<Device fqdn>`字段的 FQDN 值适合于您的环境。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="ed6e2-192">更换*\<路径\>*文件的名称和主 SkypeSettings.xml 配置文件 （或主题图像） 的本地路径。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="ed6e2-193">若要获取附加设备</span><span class="sxs-lookup"><span data-stu-id="ed6e2-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="ed6e2-194">获取应用状态</span><span class="sxs-lookup"><span data-stu-id="ed6e2-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="ed6e2-195">获取系统信息</span><span class="sxs-lookup"><span data-stu-id="ed6e2-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="ed6e2-196">重启系统</span><span class="sxs-lookup"><span data-stu-id="ed6e2-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="ed6e2-197">检索日志</span><span class="sxs-lookup"><span data-stu-id="ed6e2-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="ed6e2-198">推送 XML 配置文件或主题图片</span><span class="sxs-lookup"><span data-stu-id="ed6e2-198">Push an XML configuration file or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="ed6e2-199">软件更新</span><span class="sxs-lookup"><span data-stu-id="ed6e2-199">Software updates</span></span>
<span data-ttu-id="ed6e2-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-200"></span></span>

<span data-ttu-id="ed6e2-201">默认情况下，Skype 的空间系统 v2 将尝试连接到 Windows 应用商店要获得 Skype 的空间系统 v2 软件最新版本，以便设备需要定期访问 internet。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-201">By default, Skype Room Systems v2 will attempt to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="ed6e2-202">请确保 Skype 的空间系统 v2 设备加载最新版本的应用程序中，使用联系 Microsoft 支持问题之前。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-202">Be sure the Skype Room Systems v2 device is loaded with the latest version of the app, before contacting Microsoft with support issues.</span></span>
  
<span data-ttu-id="ed6e2-203">默认情况下，Skype 的空间系统 v2 将连接到 Windows 更新检索操作系统以及 USB 外围固件更新和配置工作时间之外来安装它们。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-203">By default, Skype Room Systems v2 will connect to Windows Update to retrieve OS as well as USB peripheral firmware updates and install them outside of configured business hours.</span></span> <span data-ttu-id="ed6e2-204">你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="ed6e2-205">如果您想手动管理更新，无法按照[Microsoft](https://businessstore.microsoft.com/en-us/store)商店的业务[分布脱机应用程序](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)的正常过程，可以获得的相应 APPX 文件和[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)（从依赖项对[Skype 的空间系统 v2 控制台配置](../../deploy/deploy-clients/console.md)说明） 可以使用 SCCM。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) to [Distribute offline apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="ed6e2-206">部署工具包版本落后于应用商店版本，因此可能无法总是与可用的最新内部版本匹配。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-206">The deployment kit release lags behind the store release, so it may not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="ed6e2-207">使用 Powershell 进行更新</span><span class="sxs-lookup"><span data-stu-id="ed6e2-207">To update using Powershell</span></span>

1. <span data-ttu-id="ed6e2-208">到一个设备可以访问共享提取安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)软件包。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a device accessible share.</span></span>
    
2. <span data-ttu-id="ed6e2-209">运行以下脚本目标 Skype 的空间系统 v2 设备、 更改\<共享\>到设备共享酌情：</span><span class="sxs-lookup"><span data-stu-id="ed6e2-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="ed6e2-210">管理模式和设备管理</span><span class="sxs-lookup"><span data-stu-id="ed6e2-210">Admin mode and device management</span></span>
<span data-ttu-id="ed6e2-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-211"></span></span>

<span data-ttu-id="ed6e2-212">有些管理功能（如手动安装私有 CA 证书）需要将 Surface 4 设备置于管理模式。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-212">Some management functions, like manually installing a private CA certificate, require placing the Surface 4 device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="ed6e2-213">切换到管理员模式和 Skype 的空间系统 v2 应用程序正在运行时，返回</span><span class="sxs-lookup"><span data-stu-id="ed6e2-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="ed6e2-214">挂起任何正在进行的通话并返回主屏幕。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-214">Hang up any ongoing calls and return to the home screen.</span></span>
    
2. <span data-ttu-id="ed6e2-215">单击设备图标和弹出菜单 （选项是**设置**、**可访问性**，以及**重新启动设备**）。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-215">Click on the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="ed6e2-216">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="ed6e2-217">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-217">Enter the Administrator Password.</span></span> <span data-ttu-id="ed6e2-218">将显示“设置”屏幕。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed6e2-p115">如果设备未加入域，默认情况下将使用本地管理帐户（用户名“Admin”）。此帐户的默认密码为“sfb”，但出于安全考虑，建议贵组织尽快更改此密码。如果计算机已加入域，则可用具有相应权限的域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-p115">If the device is not domain joined, the local administrative account (username "Admin") will be used by default. The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible. If the machine is domain joined, you can sign in with an appropriately-privileged domain account.</span></span> 
  
5. <span data-ttu-id="ed6e2-222">单击左侧列中的“**Windows 设置**”。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-222">Click on **Windows Settings** on the left column.</span></span>
    
6. <span data-ttu-id="ed6e2-223">选择“**转至管理员登录**”。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="ed6e2-224">输入管理员密码。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-224">Enter the Administrator Password.</span></span> <span data-ttu-id="ed6e2-225">此时将正常注销应用并带你访问 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="ed6e2-p117">用你的管理凭据登录桌面。你将拥有管理设备所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-p117">Log in to the desktop with your administrative credentials. You will have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="ed6e2-228">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="ed6e2-229">从管理员帐户注销。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="ed6e2-230">通过选择屏幕最左侧的用户帐户图标返回到 Skype 的空间系统 v2 并选择**Skype**。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left of the screen and select **Skype**.</span></span>
    
    <span data-ttu-id="ed6e2-231">如果未列出的**Skype**用户，可能需要选择**其他用户**，输入**。 \skype**作为用户名和登录。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-231">If the **Skype** user is not listed, you may have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
 <span data-ttu-id="ed6e2-232">控制台是现在回到其正常操作模式。下列步骤要求您将键盘连接到设备，如果尚未附加。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="ed6e2-233">切换到管理员模式和 Skype 的空间系统 v2 应用程序崩溃时</span><span class="sxs-lookup"><span data-stu-id="ed6e2-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="ed6e2-p118">快速连续按 Windows 键五次。此时将显示 Windows 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-p118">Press the Windows key five times in rapid succession. This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="ed6e2-236">用你的管理凭据登录桌面。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-236">Log into the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed6e2-237">此方法不会注销 Skype 用户或正常终止应用，但如果应用不响应并且其他方法不可用，则只能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-237">This method does not log the Skype user off or gracefully terminate the app, but you would only use it if the app was not responding and the other method was not available.</span></span> 
  
3. <span data-ttu-id="ed6e2-238">执行必要的管理任务。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="ed6e2-239">完成后重新启动机器。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-239">Restart the machine when you are finished.</span></span>
    
 <span data-ttu-id="ed6e2-240">控制台重新启动进入运行 Skype 的空间系统 v2 应用程序的正常操作模式。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="ed6e2-241">如果你已连接键盘，则可移除键盘以执行此过程。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-241">You may remove the keyboard if it was attached to allow you to perform this procedure.</span></span>
## <a name="troubleshooting-tips"></a><span data-ttu-id="ed6e2-242">故障排除提示</span><span class="sxs-lookup"><span data-stu-id="ed6e2-242">Troubleshooting tips</span></span>
<span data-ttu-id="ed6e2-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-243"></span></span>

- <span data-ttu-id="ed6e2-244">跨域边界（例如，两个公司之间）发送的会议邀请可能不会显示。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-244">Meeting invitations may not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="ed6e2-245">在这种情况下，IT 管理员应该决定是否允许外部用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-245">In such cases, IT admins should decide whether or not to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="ed6e2-246">Skype 的空间系统第 2 版不支持通过 Exchange 2010 的 Exchange 自动发现重定向。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-246">Skype Room Systems v2 does not support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="ed6e2-247">通常，比较好的做法是 IT 管理员禁用不打算使用的任何音频端点。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-247">In general, it is a good practice for IT admins to disable any audio endpoints not intended for use.</span></span>
    
- <span data-ttu-id="ed6e2-248">如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="ed6e2-249">丢失控制台触摸屏访问权限是已知问题。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="ed6e2-250">在这种情况下，有时通过 Skype 的空间系统 v2 系统重新启动解决此问题。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="ed6e2-251">通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="ed6e2-252">在这种情况下，重新启动电脑可以解决本地音频播放问题。</span><span class="sxs-lookup"><span data-stu-id="ed6e2-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ed6e2-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed6e2-253">See also</span></span>
<span data-ttu-id="ed6e2-254"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="ed6e2-254"></span></span>

#### 

[<span data-ttu-id="ed6e2-255">Skype 的空间规划系统 v2</span><span class="sxs-lookup"><span data-stu-id="ed6e2-255">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="ed6e2-256">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="ed6e2-256">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="ed6e2-257">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="ed6e2-257">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="ed6e2-258">使用 XML 配置文件的远程管理 Skype 的空间系统 v2 控制台设置</span><span class="sxs-lookup"><span data-stu-id="ed6e2-258">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

