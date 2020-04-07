---
title: Microsoft 团队会议室维护和操作
ms.author: v-lanac
author: lanachin
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
description: 阅读本主题，了解 Microsoft 球队会议室的管理、下一代 Skype 会议室系统的管理。
ms.openlocfilehash: 1fecf852c11e7ab89e0cdc7dc6caf615182e7d5f
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157756"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft 团队会议室维护和操作 
 
阅读本主题，了解 Microsoft 球队会议室的管理、下一代 Skype 会议室系统的管理。
  
Microsoft 团队聊天室是 Microsoft 的最新会议解决方案，旨在将会议室转换为丰富、协作的体验。 用户将享受其熟悉的 Microsoft 团队或 Skype for business 界面，并且 IT 管理员将欣赏轻松部署和管理的 Windows 10 Skype 会议应用。 Microsoft 球队会议室旨在利用 LCD 面板等现有设备进行轻松安装，将 Microsoft 团队或 Skype for business 带入会议室。
  
有了其他配置，使用 Microsoft Azure 监视器可以进行远程管理，如使用[Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)中所述，使用 azure 监视器[部署 microsoft 团队聊天室管理](azure-monitor-deploy.md)，[使用 Azure 监视器管理 microsoft 团队聊天室设备](azure-monitor-deploy.md)。 您也可以[使用 XML 配置文件远程管理 Microsoft 球队聊天室控制台设置](xml-config-file.md)，其中包括应用自定义显示主题。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>在 Microsoft 团队聊天室上收集日志
<a name="Logs"> </a>

若要收集日志，必须调用 Microsoft 团队聊天室应用随附的日志收集脚本。 在 "管理员模式" 下，启动提升的 PowerShell 提示，然后发出以下命令：
  
```PowerShell
c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1 -ExecutionPolicy unrestricted
```

日志将以 ZIP 文件的形式输出至 c:\rigel 中。
  
## <a name="front-of-room-display-settings"></a>会议室前端显示屏设置
<a name="Display"> </a>

将会议室前端显示屏配置为扩展模式。 这样做可确保当你重启屏幕上的电源时，不会在该屏幕上复制控制台 UI。
  
> [!NOTE]
> 如果你希望在从待机模式唤醒源时自动切换到活动视频源（如 MTR 控制台），则必须满足某些条件。 此功能是可选的，但 Microsoft 团队工作室软件支持此功能，但提供的基础硬件支持此功能。 在室内显示时使用的消费者电视需要支持 HDMI 的 "消费者电子设备控制" （CEC）功能。  根据所选的坞站或控制台（可能不支持 CEC，请参阅制造商支持文档），可能需要从 Extron Crestron 或[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad)中的控制器（如[HD RX-201-C](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) ）来启用所需的行为。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft 团队会议室重置（出厂还原）
<a name="Reset"> </a>

如果 Microsoft 团队聊天室运行不好，则执行恢复恢复可能会有所帮助。 若要执行此操作，请使用[Microsoft 团队房间恢复工具](recovery-tool.md)，并按照出厂还原说明进行操作。

> [!NOTE]
> 如果**保留我的文件-删除应用和设置，但**在 Windows 重置过程中选中了 "保留你的个人文件" 选项，则 Microsoft 团队聊天室可能会变得不可用的已知问题。 请勿*使用此*选项。
  
## <a name="supported-remote-options"></a>支持的远程选项
<a name="RemoteOptions"> </a>

下表汇总了可能的远程操作和可以用于完成这些操作的方法。
  

|工作组 |未加入域|加入域|
|:-----|:-----|:-----|
|重新启动  <br/> |远程桌面  <br/> 远程 PowerShell  <br/> |远程桌面（需要进一步配置）  <br/> 远程 Powershell （需要进一步配置）  <br/> 配置管理器  <br/> |
|更新操作系统  <br/> |Windows 更新  <br/> |Windows 更新  <br/> WSUS  <br/> |
|应用更新  <br/> |Windows 应用商店  <br/> |Windows 应用商店  <br/> 配置管理器  <br/> |
|Skype 帐户配置  <br/> |当前不支持  <br/> |当前不支持  <br/> |
|访问日志  <br/> |当前不支持  <br/> |当前不支持  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>为 Microsoft 团队聊天室配置组策略
<a name="GroupPolicy"> </a>

本部分介绍 Microsoft 团队聊天室依赖于正常工作的系统设置。 将 Microsoft 团队会议室加入域时，请确保你的组策略不会覆盖下表中的设置。
  

|设置|这样|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （REG_SZ）1  <br/> |支持 Microsoft 团队会议室启动  <br/> |
|电源管理-\>通过交流，10分钟后关闭屏幕  <br/> 电源管理-\>在交流上，从不将系统置于睡眠状态  <br/> |使 Microsoft 团队会议室能够关闭附加的显示并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
在 "[配置文件" 项目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)中讨论了使用组策略传输文件的内容。

> [!NOTE]
> 当 Microsoft 团队聊天室设备与下一版本的 Windows 10 操作系统兼容时，设备会通过 Windows 更新自动更新到下一个版本。 Microsoft 团队会议室不应将设备升级到 Windows 10 的下一版本手动或通过启用 Windows 更新 for Business （WUFB）组策略 "选择要接收的更新的 Windows 准备情况级别" 和 "通过 GPO 选择何时接收预览版和功能更新"。 已启用这些组策略的设备已知通过 Microsoft 团队聊天室应用运行 Windows 10 操作系统更新时遇到的问题。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

你可以使用 PowerShell 远程执行以下管理操作（请参阅下表中的脚本示例）：
  
- 获取连接的设备
- 获取应用状态
- 获取系统信息
- 重启系统
- 检索日志
- 传输文件（需要加入域的 Microsoft 团队聊天室）
    
> [!NOTE]
> 默认情况下，此功能处于关闭状态。 你需要在 Microsoft 团队聊天室系统上为你的环境启用远程 PowerShell 以执行以下操作。 有关如何启用远程 PowerShell 的信息，请参阅有关**[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 的文档。
  
例如，可以按如下所示启用远程 PowerShell：
  
1. 在 Microsoft 团队聊天室设备上以管理员身份登录。
2. 打开提升的 PowerShell 命令提示符。
3. 输入以下命令：Enable-PSRemoting -force

执行管理操作：
  
1. 使用具有在 Microsoft 团队聊天室设备上运行 PowerShell 命令的权限的帐户凭据登录到电脑。
2. 在电脑上打开常规 PowerShell 命令提示符。
3. 从下表中复制命令文本，并在出现提示时粘贴它。
4. 将`<Device fqdn>`具有相应环境的 FQDN 值替换为相应的字段。
5. 将* \<路径\> *替换为 master SkypeSettings 配置文件的文件名和本地路径（或主题图像）。
    
获取连接的设备
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

获取应用状态
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

获取系统信息
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

重启系统
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

检索日志
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

推送 XML 配置文件（或主题图形）
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>软件更新
<a name="SWupdate"> </a>

默认情况下，Microsoft 团队聊天室会尝试连接到 Windows 应用商店以获取最新版本的 Microsoft 团队聊天室软件，因此设备将需要常规的 internet 访问权限。 在与 Microsoft 保持支持问题之前，请确保 Microsoft 团队聊天室设备已加载了最新版本的应用。
  
默认情况下，Microsoft 团队聊天室将连接到 Windows 更新以检索操作系统和 USB 外围设备固件更新，并将其安装在已配置的工作时间之外。 你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。
  
如果你希望手动管理更新，并且无法按照[Microsoft Store For Business](https://businessstore.microsoft.com/store) [分发脱机应用](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的常规过程进行操作，你可以从[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)获取相应的 APPX 文件和依赖项（从[配置 Microsoft 团队聊天室控制台](console.md)的说明），可与 Configuration Manager 配合使用。 部署工具包版本滞后于应用商店版本，因此它可能不会始终与最新的可用内部版本匹配。
  
### <a name="to-update-using-powershell"></a>使用 Powershell 更新

1. 将程序包从安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)解压缩到设备可以访问的共享。
2. 运行以下针对 Microsoft 团队聊天室设备的脚本，根据需要\<将\>共享更改为设备共享：
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理模式和设备管理
<a name="AdminMode"> </a>

某些管理功能（如手动安装专用 CA 证书）要求在 "管理员模式" 下放置 Surface Pro 设备。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>当 Microsoft 团队聊天室应用正在运行时切换到管理员模式并返回回来

1. 挂起任何正在进行的呼叫，并返回主屏幕。
2. 选择齿轮图标并弹出菜单（选项为 "**设置**"、"**辅助功能**" 和 "**重启设备**"）。
3. 选择“**设置**”。
4. 输入管理员密码。 将显示“设置”屏幕。  如果设备未加入域，将默认使用本地管理帐户（用户名 "Admin"）。 此帐户的默认密码为 "sfb"，请尽快更改密码。 如果计算机已加入域，则可以使用适当权限的域帐户登录。 
5. 在左侧列中选择 " **Windows 设置**"。
6. 选择“**转至管理员登录**”。
7. 输入管理员密码。 此时将正常注销应用并带你访问 Windows 登录屏幕。 
8. 用你的管理凭据登录桌面。 你将拥有管理设备所需的权限。
9. 执行必要的管理任务。
10. 从管理员帐户注销。
11. 通过选择屏幕最左侧的用户帐户图标，然后选择 " **Skype**"，返回到 Microsoft 团队聊天室。
    
    如果未列出**Skype**用户，您可能需要选择 "**其他用户**" 并输入 " **.\skype** " 作为用户名，然后登录。
    
控制台现在恢复正常操作模式。以下过程要求你将键盘附加到设备（如果尚未连接）。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>当 Microsoft 团队聊天室应用崩溃时切换到管理员模式并返回回来

1. 快速连续按 Windows 键五次。 此时将显示 Windows 登录屏幕。 
2. 用你的管理凭据登录桌面。
3. 执行必要的管理任务。
4. 完成后，重新启动计算机。

    > [!NOTE]
    > 此方法不会将 Skype 用户注销或正常终止应用，但如果应用未响应且其他方法不可用，则可以使用它。 

   控制台将重启到其正常操作模式，运行 Microsoft 团队聊天室应用。 如果已附加键盘，则可以将其删除，以允许执行此过程。
   ## <a name="troubleshooting-tips"></a>故障排除提示
   <a name="TS"> </a>

- 通过域边界（例如，两家公司之间）发送会议邀请时，可能不会显示会议邀请。 在这种情况下，IT 管理员应决定是否允许外部用户安排会议。
- Microsoft 团队聊天室不支持通过 Exchange 2010 的 Exchange 自动发现重定向。
- 一般情况下，IT 管理员禁用不打算使用的任何音频终结点是一种很好的做法。
- 如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。
- 丢失控制台触摸屏访问权限是已知问题。 在这种情况下，有时会通过重新启动 Microsoft 团队聊天室系统来解决该问题。
- 通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。 在这种情况下，重新启动电脑可以解决本地音频播放问题。
    
