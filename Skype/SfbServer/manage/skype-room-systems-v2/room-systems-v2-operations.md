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
ms.openlocfilehash: 907abcbe07e52369aefa5065a359f0a3769b20c5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013041"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft 团队聊天室的维护和操作 
 
阅读本主题可了解有关 Microsoft 团队聊天室，管理下一代 Skype 会议室系统。
  
Microsoft 团队聊天室是 Microsoft 的最新设计用来转换为业务体验丰富的、 协作 Skype 您会议室的会议解决方案。 用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。 Microsoft 团队聊天室旨在利用现有的设备，如 LCD 面板为了简化安装将 Skype for Business 导入您的会议室。
  
其他配置远程管理是可以[使用 Azure 监视器规划 Microsoft 团队聊天室管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md)、[部署 Microsoft 团队聊天室管理使用 Azure 监视器](../../deploy/deploy-clients/azure-monitor.md)，[管理中所述使用 Microsoft Azure 监视器使用 Azure 监视器的 Microsoft 团队聊天室设备](azure-monitor.md)。 您还可以[管理 Microsoft 团队聊天室控制台远程设置的 XML 配置文件](xml-config-file.md)，其中包括应用自定义显示主题。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft 团队聊天室上收集日志
<a name="Logs"> </a>

收集日志，必须调用附带的 Microsoft 团队聊天室应用程序日志收集脚本。 在管理模式中，启动提升的命令提示符并发出以下命令：
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

日志将以 ZIP 文件的形式输出至 c:\rigel 中。
  
## <a name="front-of-room-display-settings"></a>会议室前端显示屏设置
<a name="Display"> </a>

将会议室前端显示屏配置为扩展模式。 这样可以确保的 UI 不重复该显示屏时显示周期电源控制台。
  
> [!NOTE]
> 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft 团队聊天室重置 （出厂还原）
<a name="Reset"> </a>

如果 Microsoft 团队聊天室也未运行，可以帮助执行出厂重置。 这可**重置此 PC**下方的**恢复**选项卡上的设置应用程序中，选择**开始**，然后**删除所有内容**。 按照剩余提示重新启动设备。
  
> [!NOTE]
> 是一个已知的问题 Microsoft 团队聊天室可以成为 Windows 重置的过程中选择**保存我的文件的删除应用程序和设置，但您的个人文件**选项的情况下无法使用。 执行_不_使用此选项。
  
## <a name="supported-remote-options"></a>支持的远程选项
<a name="RemoteOptions"> </a>

下表汇总了可能的远程操作和可以用于完成这些操作的方法。
  

|**工作组 **|**未加入域**|**加入域**|
|:-----|:-----|:-----|
|重新启动  <br/> |远程桌面  <br/> 远程 PowerShell  <br/> |远程桌面 （需要进一步的配置）  <br/> 远程 Powershell （需要进一步的配置）  <br/> SCCM  <br/> |
|更新操作系统  <br/> |Windows 更新  <br/> |Windows 更新  <br/> WSUS  <br/> |
|应用更新  <br/> |Windows 应用商店  <br/> |Windows 应用商店  <br/> SCCM  <br/> |
|Skype 帐户配置  <br/> |当前不支持  <br/> |当前不支持  <br/> |
|访问日志  <br/> |当前不支持  <br/> |当前不支持  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>为 Microsoft 团队房间配置组策略
<a name="GroupPolicy"> </a>

本节介绍 Microsoft 团队聊天室取决于能够正常工作的系统设置。 时加入域的 Microsoft 团队聊天室，确保您的组策略不会覆盖下表中的设置。
  

|**设置**|**允许**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |启用 Microsoft 团队聊天室启动  <br/> |
|电源管理-\>上交流，关闭屏幕 10 分钟后  <br/> 电源管理-\>上交流，从不提供系统进入休眠模式  <br/> |启用 Microsoft 团队聊天室附加显示关闭并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
使用组策略的文件传输将在[配置文件项](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)讨论。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

您可以使用 PowerShell 远程执行以下管理操作 （参阅下表中的脚本示例）：
  
- 获取连接的设备
    
- 获取应用状态
    
- 获取系统信息
    
- 重启系统
    
- 检索日志
    
- 传输文件 （需要加入域的 Microsoft 团队聊天室）
    
> [!NOTE]
> 默认情况下，此功能处于关闭状态。 您需要启用 Microsoft 团队聊天室系统环境的远程 PowerShell，可以执行以下操作。 请参阅有关如何启用远程 PowerShell **[Enable-psremoting](https://technet.microsoft.com/library/hh849694.aspx)** 的文档。
  
例如，可以按如下所示启用远程 PowerShell：
  
1. 以管理员身份登录的 Microsoft 团队聊天室设备。
    
2. 打开提升的 PowerShell 命令提示符。
    
3. 输入以下命令：Enable-PSRemoting -force
    
执行管理操作：
  
1. 登录到有权的 Microsoft 团队聊天室设备上运行 PowerShell 命令的帐户凭据的 PC。
    
2. 打开常规 PowerShell 命令提示符 PC 上。
    
3. 从下表中复制的命令文本，并将其粘贴在提示符处。
    
4. 替换`<Device fqdn>`具有 FQDN 值的字段适合于您的环境。
    
5. 替换*\<路径\>* 用文件名和母版页 SkypeSettings.xml 配置文件 （或主题图像） 的本地路径。
    
若要获取连接的设备
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

获取应用状态
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

获取系统信息
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

重启系统
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

检索日志
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

推送 XML 配置文件 （或主题图形）
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>软件更新
<a name="SWupdate"> </a>

默认情况下，Microsoft 团队聊天室尝试连接到 Windows 应用商店获取最新版本的 Microsoft 团队聊天室软件，因此设备需要正则 internet 访问。 之前与 Microsoft 联系支持问题，请确保 Microsoft 团队聊天室设备将加载包含应用程序的最新版本。
  
默认情况下，Microsoft 团队聊天室连接到 Windows Update 以检索操作系统和 USB 外围设备固件更新，并安装它们非配置工作时间发出。 你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。
  
如果您想要手动管理更新，并且无法按照[Microsoft Store for Business](https://businessstore.microsoft.com/store)到[分发脱机应用程序](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的常规过程，您可以获取的相应约文件和从[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)（从相关性要[配置的 Microsoft 团队聊天室控制台](../../deploy/deploy-clients/console.md)的说明） 可用于 SCCM。 部署套件版本低于存储版本中，因此不可能总是匹配的最新的生成。
  
### <a name="to-update-using-powershell"></a>使用 Powershell 进行更新

1. 从安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)到共享设备可以访问提取程序包。
    
2. 运行以下脚本面向 Microsoft 团队聊天室设备，更改\<共享\>到设备共享根据：
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理模式和设备管理
<a name="AdminMode"> </a>

一些管理功能，如手动安装将私有 CA 证书，需要管理员模式中发出 Surface Pro 设备。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>切换到管理员模式和 Microsoft 团队聊天室应用程序运行时回报

1. 挂断任何正在进行的呼叫，并返回到主屏幕。
    
2. 选择齿轮图标和弹出菜单 （选项是**设置**、**辅助功能**，和**重新启动设备**）。
    
3. 选择“**设置**”。
    
4. 输入管理员密码。 将显示“设置”屏幕。
    
    > [!NOTE]
    > 如果设备不加入域的将默认情况下使用本地管理帐户 （用户名"Admin"）。 此帐户的默认密码为“sfb”，但出于安全考虑，建议贵组织尽快更改此密码。 如果计算机已加入域，您可以使用相应特权的域帐户进行登录。 
  
5. 左侧列中，选择**Windows 设置**。
    
6. 选择“**转至管理员登录**”。
    
7. 输入管理员密码。 此时将正常注销应用并带你访问 Windows 登录屏幕。 
    
8. 用你的管理凭据登录桌面。 您必须所需的权限来管理设备。
    
9. 执行必要的管理任务。
    
10. 从管理员帐户注销。
    
11. 通过选择最左侧的屏幕上的用户帐户图标，然后选择**Skype**返回到 Microsoft 团队聊天室。
    
    如果未列出的**Skype**用户，您可能需要选择**其他用户**，然后输入 **。 \skype**作为用户名和登录。
    
控制台现返回处于正常操作模式。下面的过程，需要将键盘附加到该设备，如果尚未附加。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>切换到管理员模式和 Microsoft 团队聊天室应用程序崩溃时回报

1. 快速连续按 Windows 键五次。 此时将显示 Windows 登录屏幕。 
    
2. 用你的管理凭据登录桌面。
    
    > [!NOTE]
    > 此方法不会注销 Skype 用户或正常终止应用程序，但如果应用程序未响应并没有可用的其他方法，需要使用它。 
  
3. 执行必要的管理任务。
    
4. 完成后，重新启动计算机。
    
   控制台重新启动到其正常操作模式，运行 Microsoft 团队聊天室应用程序。 您可以删除键盘，如果它已连接以允许您执行此过程。
   ## <a name="troubleshooting-tips"></a>故障排除提示
   <a name="TS"> </a>

- 跨域边界 （例如，两个公司） 之间发送时，可能不出现会议邀请。 在这种情况下，IT 管理员应决定是否允许外部用户可以安排会议。
    
- Microsoft 团队聊天室不支持 Exchange 2010 通过 Exchange AutoDiscover 重定向。
    
- 一般情况下，最好 IT 管理员可以禁用他们不想要使用的任何音频终结点。
    
- 如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。
    
- 丢失控制台触摸屏访问权限是已知问题。 在这种情况下，通过重新启动 Microsoft 团队聊天室系统有时解决此问题。
    
- 通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。 在这种情况下，重新启动电脑可以解决本地音频播放问题。
    
