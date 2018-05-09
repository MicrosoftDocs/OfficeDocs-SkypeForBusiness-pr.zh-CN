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
description: 阅读此主题以了解有关的 Skype 会议室系统 v2，管理下一代 Skype 会议室系统。
ms.openlocfilehash: 48069f7e5e63df752fe94cb557796e9f2080c917
ms.sourcegitcommit: 0d649ac15d8b50e497b05531b724bc9a171a2953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="manage-skype-room-systems-v2"></a>管理 Skype 会议室系统 v2
 
阅读此主题以了解有关的 Skype 会议室系统 v2，管理下一代 Skype 会议室系统。
  
Skype 会议室系统 v2 是 Microsoft 的最新设计用来转换为业务体验丰富的、 协作 Skype 您会议室的会议解决方案。 用户将获得熟悉的 Skype for Business 界面，IT 管理员将体验部署和管理都很轻松的 Windows 10 Skype 会议应用。 Skype 会议室系统 v2 旨在利用现有的设备，如 LCD 面板为了简化安装将 Skype for Business 导入您的会议室。
  
其他配置远程管理是可以[使用 OMS 的规划 Skype 会议室系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[使用 OMS 的部署 Skype 会议室系统 v2 管理](../../deploy/deploy-clients/with-oms.md)和[管理中所述使用 Microsoft 操作管理套件 (OMS)OMS Skype 会议室系统 v2 设备](oms.md)。 您还可以[远程使用 XML 配置文件的管理 Skype 会议室系统 v2 控制台设置](xml-config-file.md)，其中包括应用自定义显示主题。 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>收集 Skype 会议室系统 v2 的日志
<a name="Logs"> </a>

收集日志，必须调用附带 Skype 会议室系统 v2 应用程序日志收集脚本。 在管理模式中，启动提升的命令提示符并发出以下命令：
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

日志将以 ZIP 文件的形式输出至 c:\rigel 中。
  
## <a name="front-of-room-display-settings"></a>会议室前端显示屏设置
<a name="Display"> </a>

将会议室前端显示屏配置为扩展模式。 这样做可确保在对显示屏进行电源重启时，控制台 UI 不会重复出现在显示屏上。
  
> [!NOTE]
> 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Skype 会议室系统 v2 重置（恢复出厂设置）
<a name="Reset"> </a>

如果 Skype 会议室系统 v2 还没有运行，可帮助执行出厂重置。 这从下方的"重置 PC"标头"恢复"选项卡可设置应用程序中，选择"开始"后跟"删除所有内容。" 根据需要按照其余提示操作以重置设备。
  
> [!NOTE]
> 是一个已知的问题其中 Skype 会议室系统 v2 可能会重置 Windows 过程中选择了"将文件保存-删除应用程序和设置，但保留您的个人文件"选项的情况下无法使用。 **请勿**使用此选项。
  
## <a name="supported-remote-options"></a>支持的远程选项
<a name="RemoteOptions"> </a>

下表汇总了可能的远程操作和可以用于完成这些操作的方法。
  

|**工作组**|**未加入域**|**加入域**|
|:-----|:-----|:-----|
|重新启动  <br/> |远程桌面  <br/> 远程 PowerShell  <br/> |远程桌面 （需要进一步的配置）  <br/> 远程 Powershell （需要进一步的配置）  <br/> SCCM  <br/> |
|更新操作系统  <br/> |Windows 更新  <br/> |Windows 更新  <br/> WSUS  <br/> |
|应用更新  <br/> |Windows 应用商店  <br/> |Windows 应用商店  <br/> SCCM  <br/> |
|Skype 帐户配置  <br/> |当前不支持  <br/> |当前不支持  <br/> |
|访问日志  <br/> |当前不支持  <br/> |当前不支持  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>为 Skype 会议室系统 v2 配置组策略
<a name="GroupPolicy"> </a>

本节介绍 Skype 会议室系统 v2 取决于能够正常工作的系统设置。 当 Skype 会议室系统 v2 加入域，请确保您的组策略不会替代以下设置：
  

|**设置**|**允许**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |允许 Skype 会议室系统 v2 启动  <br/> |
|电源管理-\>上交流，关闭屏幕 10 分钟后  <br/> 电源管理-\>上交流，从不提供系统进入休眠模式  <br/> |允许 Skype 会议室系统 v2 附加显示关闭并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
使用组策略的文件传输将在[配置文件项](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)讨论。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

可以使用 PowerShell 远程执行以下管理操作（请参阅下表了解脚本示例）：
  
- 获取连接的设备
    
- 获取应用状态
    
- 获取系统信息
    
- 重启系统
    
- 检索日志
    
- 传输文件 （需要加入域的 Skype 会议室系统 v2）
    
> [!NOTE]
> 默认情况下，此功能处于关闭状态。 您需要启用 Skype 会议室系统 v2 系统环境的远程 PowerShell，可以执行以下操作。 请参阅**[Enable-psremoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** 有关如何启用远程 PowerShell 的信息的文档。
  
例如，可以按如下所示启用远程 PowerShell：
  
1. 登录以管理员身份 Skype 会议室系统 v2 设备上。
    
2. 启动提升的 PowerShell 命令提示符。
    
3. 输入以下命令： Enable-psremoting-强制
    
执行管理操作：
  
1. 登录到有权 Skype 会议室系统 v2 设备上运行 PowerShell 命令的帐户凭据的 PC。
    
2. 在你的电脑上启动常规 PowerShell 命令提示窗口。
    
3. 将下表中的命令文本复制并粘贴到提示窗口中。
    
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

推送 XML 配置文件或主题图片
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>软件更新
<a name="SWupdate"> </a>

默认情况下，Skype 会议室系统 v2 将尝试连接到 Windows 应用商店获取 Skype 会议室系统 v2 软件的最新版本，以便设备需要正则 internet 访问。 确保 Skype 会议室系统 v2 设备将加载包含应用程序的最新版本之前联系 Microsoft 支持问题。
  
默认情况下 Skype 会议室系统 v2 将连接到 Windows Update 检索操作系统以及 USB 外围固件更新和非配置工作时间发出安装它们。 你可以通过登录管理员帐户并运行“设置”应用来配置办公时间。
  
如果您想要手动管理更新，并且无法按照[Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store)到[分发脱机应用程序](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)的常规过程，您可以获取的相应约文件和从[部署工具包](https://go.microsoft.com/fwlink/?linkid=851168)（从相关性要[配置的 Skype 会议室系统 v2 控制台](../../deploy/deploy-clients/console.md)的说明） 可用于 SCCM。 部署工具包版本落后于应用商店版本，因此可能无法总是与可用的最新内部版本匹配。
  
### <a name="to-update-using-powershell"></a>使用 Powershell 进行更新

1. 到设备访问共享从安装[MSI](https://go.microsoft.com/fwlink/?linkid=851168)提取程序包。
    
2. 运行以下脚本面向 Skype 会议室系统 v2 设备，更改\<共享\>到设备共享根据：
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>管理模式和设备管理
<a name="AdminMode"> </a>

有些管理功能（如手动安装私有 CA 证书）需要将 Surface 4 设备置于管理模式。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>切换到管理员模式和 Skype 会议室系统 v2 应用程序运行时回报

1. 挂起任何正在进行的通话并返回主屏幕。
    
2. 单击齿轮图标和弹出菜单 （选项是**设置**、**辅助功能**，和**重新启动设备**）。
    
3. 选择“**设置**”。
    
4. 输入管理员密码。 将显示“设置”屏幕。
    
    > [!NOTE]
    > 如果设备未加入域，默认情况下将使用本地管理帐户（用户名“Admin”）。此帐户的默认密码为“sfb”，但出于安全考虑，建议贵组织尽快更改此密码。如果计算机已加入域，则可用具有相应权限的域帐户登录。 
  
5. 单击左侧列中的“**Windows 设置**”。
    
6. 选择“**转至管理员登录**”。
    
7. 输入管理员密码。 此时将正常注销应用并带你访问 Windows 登录屏幕。 
    
8. 用你的管理凭据登录桌面。你将拥有管理设备所需的权限。
    
9. 执行必要的管理任务。
    
10. 从管理员帐户注销。
    
11. 返回到 Skype 会议室系统 v2 通过选择在最左边的屏幕上的用户帐户图标并选择**Skype**。
    
    如果未列出的**Skype**用户，您可能需要选择**其他用户**，然后输入**。 \skype**作为用户名和登录。
    
 控制台现返回处于正常操作模式。下面的过程，需要将键盘附加到该设备，如果尚未附加。 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>切换到管理员模式和 Skype 会议室系统 v2 应用程序崩溃时回报

1. 快速连续按 Windows 键五次。此时将显示 Windows 登录屏幕。 
    
2. 用你的管理凭据登录桌面。
    
    > [!NOTE]
    > 此方法不会注销 Skype 用户或正常终止应用，但如果应用不响应并且其他方法不可用，则只能使用此方法。 
  
3. 执行必要的管理任务。
    
4. 完成后重新启动机器。
    
 控制台重新启动到其正常操作模式，运行 Skype 会议室系统 v2 应用程序。 如果你已连接键盘，则可移除键盘以执行此过程。
## <a name="troubleshooting-tips"></a>故障排除提示
<a name="TS"> </a>

- 跨域边界（例如，两个公司之间）发送的会议邀请可能不会显示。 在这种情况下，IT 管理员应该决定是否允许外部用户安排会议。
    
- Skype 会议室系统 v2 不支持 Exchange 2010 通过 Exchange AutoDiscover 重定向。
    
- 通常，比较好的做法是 IT 管理员禁用不打算使用的任何音频端点。
    
- 如果会议室预览中显示镜像图像，IT 管理员可以通过关闭并重新打开摄像头电源或使用摄像头远程控件翻转图像方向来进行更正。
    
- 丢失控制台触摸屏访问权限是已知问题。 在这种情况下，通过重新启动 Skype 会议室系统 v2 系统有时解决此问题。
    
- 通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。 在这种情况下，重新启动电脑可以解决本地音频播放问题。
    
## <a name="see-also"></a>另请参阅
<a name="TS"> </a>

#### 

[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](../../deploy/deploy-clients/console.md)
  
[使用 XML 配置文件远程管理 Skype 会议室系统 v2 控制台设置](xml-config-file.md)

