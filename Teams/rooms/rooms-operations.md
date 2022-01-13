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
ms.localizationpriority: medium
description: 阅读本主题，了解如何管理Microsoft Teams 会议室。
ms.openlocfilehash: 2238712b269475891074016c1099a33c56004595
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015042"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 会议室维护和操作
 
阅读本主题，了解如何管理Microsoft Teams 会议室。
  
Microsoft Teams 会议室是 Microsoft 的会议解决方案，旨在将会议室转换为丰富的协作体验。 用户将喜欢其熟悉的Microsoft Teams或Skype for Business界面，IT 管理员将非常欣赏轻松部署和管理的 Windows 10 Teams 会议室 应用。 Microsoft Teams 会议室旨在利用现有设备轻松安装，Microsoft Teams Skype for Business会议室。
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>在 Microsoft Teams 会议室 上收集日志
<a name="Logs"> </a>

若要在管理中心Teams日志，请转到Teams **上> Teams 会议室设备Windows。** 选择显示名称其日志的设备组。 在顶部面板中，选择"下载设备日志"。 确认后，几分钟后即可在"历史记录"选项卡中下载日志。

也可使用 PowerShell 收集日志。 必须调用随应用一起Microsoft Teams 会议室脚本。 在 [管理模式下](rooms-operations.md)，启动提升的命令提示符，并发出以下命令：
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

日志将以 ZIP 文件的形式输出至 c:\rigel 中。
  
## <a name="front-of-room-display-settings"></a>会议室前端显示屏设置
<a name="Display"> </a>

配置"会议室前"屏幕 (的设置) CEC (或) "电脑模式"。
  
如果希望房间前显示器在从备用模式Teams 会议室自动切换到屏幕，则必须满足某些条件。 此功能是可选的，但受 Microsoft Teams 会议室的支持，但基础硬件支持该功能。 用作房间前显示器的消费者电视需要支持 HDMI 的使用者 (CEC) 功能。  根据所选的扩展坞或主机 (可能不支持 CEC，请参阅制造商支持文档) ，需要来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Extron 的 [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 等控制器才能实现所需行为。
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 会议室重置 (恢复出厂) 
<a name="Reset"> </a>

如果Microsoft Teams 会议室运行不佳，执行恢复出厂设置可能会有所帮助。 为此，请使用"Microsoft Teams[恢复工具](recovery-tool.md)并按照工厂还原说明进行操作。

> [!NOTE]
> 存在一个已知问题 **，Microsoft Teams 会议室"** 保留我的文件 - 删除应用和设置，但保留个人文件"选项在"重置"过程中Windows不可用。 *请不要* 使用此选项。
  
## <a name="supported-remote-options"></a>支持的远程选项
<a name="RemoteOptions"> </a>

下表汇总了可能的远程操作和可以用于完成这些操作的方法。
  

|工作组 |未加入域|加入域|
|:-----|:-----|:-----|
|重新启动  <br/> |Teams管理中心  <br/> 远程桌面  <br/> 远程 PowerShell  <br/> | <br/>远程桌面 (需要进一步配置)   <br/> 远程 PowerShell (需要进一步配置)   <br/> 配置管理器  <br/> |
|更新操作系统  <br/> |Windows 更新  <br/> |Windows 更新  <br/> WSUS  <br/> |
|应用更新  <br/> |Windows 应用商店  <br/> |Windows 应用商店  <br/> 配置管理器  <br/> |
|帐户配置  <br/> |Teams管理中心  <br/> |Teams管理中心  <br/> |
|访问日志  <br/> |Teams管理中心  <br/> PowerShell  <br/> |Teams管理中心 <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>为用户配置组Microsoft Teams 会议室
<a name="GroupPolicy"> </a>

本部分介绍系统设置Microsoft Teams 会议室正常运行所依赖的系统设置。 

将Teams 会议室 Active Directory 域提供以下优势：

- 通过域加入Teams 会议室可授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。

- 可以将Windows服务质量配置部署到Teams 会议室。

- 如果使用 Skype for Business，则加入域Teams 会议室自动导入组织的专用根证书链。

将 Teams 会议室 加入域时，需要创建单独的组织单位 (OU) ，以便可以将组策略对象 (GPO) 排除项提供到所有 Teams 会议室 对象所在的 OU。 禁用所有 GPO 继承，以便不支持的组策略设置不会应用到Teams 会议室。 在将域加入域Teams 会议室 OU 中的计算机对象，以确保未应用应用于默认计算机 OU 的组策略。

> [!NOTE]
> 即使创建了单独的 OU 和块继承，也有一些组策略在设置了"无重写"时可能会导致问题。 设置了"无重写"的组策略会优先于设置了阻止策略继承的 OU。

许多组织具有以下 GPO，这会影响Teams 会议室功能。 确保重写或阻止以下代码的继承：

  - 登录会话的超时（自动锁定）
  - 电源管理相关的策略
  - 需要附加身份验证步骤
  - 拒绝访问本地驱动器
  - 提示用户网络连接较慢
  - 登录时启动特定程序
  - 在所有加入域的计算机上创建另一个域用户帐户。
  - 将Windows更新推送到Teams 会议室

将Microsoft Teams 会议室域时，请确保组策略不会覆盖下表中的设置。

|设置|允许|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |允许Microsoft Teams 会议室启动  <br/> |
|电源管理 - \> 在交流电源上，10 分钟后关闭屏幕  <br/> 电源管理 - \> 在交流电源上，切勿将系统置于睡眠状态  <br/> |允许Microsoft Teams 会议室关闭附加的显示器并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |

> [!NOTE]
> 如果Microsoft Teams 会议室与下一版本的 Windows 10 OS 兼容，Teams 会议室更新自动更新到下一Windows版本。 Microsoft Teams 会议室 不应手动或通过启用 Windows Update for Business (WUFB) 组策略手动升级到下一个 Windows 10 版本"，而应该通过 GPO 启用"选择要接收的更新的 Windows 就绪状态级别"和"选择何时收到预览版本和功能更新"。 Teams 会议室启用这些组策略后，已知在更新 OS Windows 10时遇到问题。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

可以使用 PowerShell 远程执行以下管理操作 (请参阅下表，了解脚本示例) ：
  
- 获取连接的设备
- 获取应用状态
- 获取系统信息
- 重启系统
- 检索日志
- 传输 (需要已加入域的文件Microsoft Teams 会议室) 
    
> [!NOTE]
> 默认情况下，此功能处于关闭状态。 若要执行以下操作，需要在 Microsoft Teams 会议室 上为环境启用远程 PowerShell。 请参阅 **[Enable-PSRemoting 文档](/powershell/module/microsoft.powershell.core/enable-psremoting)** ，了解如何启用远程 PowerShell。
  
例如，可以按如下所示启用远程 PowerShell：
  
1. 在设备上以管理员Microsoft Teams 会议室登录。
2. 打开提升权限的 PowerShell 命令提示符。
3. 输入以下命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 打开"本地安全策略"，*将"管理员* 安全组"添加到"安全设置策略""用户权限分配"从网络  >    >    >  **访问此计算机**。

执行管理操作：
  
1. 使用有权在设备上运行 PowerShell 命令的帐户凭据登录到Microsoft Teams 会议室电脑。
2. 在电脑上打开常规 PowerShell 命令提示符。
3. 复制下表中的命令文本，并将其粘贴到提示符下。
4. 将  `<Device fqdn>` 字段替换为适合环境的 FQDN 值。
5. 将  *\<path\>*  替换为主文件夹配置文件SkypeSettings.xml或主题 (的本地) 。
    
获取附加设备
  
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

推送 XML 配置文件 (或主题图形) 
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>软件更新
<a name="SWupdate"> </a>

默认情况下，Microsoft Teams 会议室尝试连接到 Windows Store，获取最新版本的 Microsoft Teams 会议室 软件。 因此，Teams 会议室需要定期 Internet 访问。 在联系 Microsoft 解决支持问题之前，Microsoft Teams 会议室加载最新版本的应用。
  
Microsoft Teams 会议室连接到 Windows Update 以检索操作系统和外围设备固件更新。 Teams会议室配置为从本地时间凌晨 2：00 开始安装它们。
  
如果由于访问 Windows 应用商店方面的限制而必须手动管理更新，并且因此无法遵循[适用于企业的 Microsoft Store](https://businessstore.microsoft.com/store) [ (](https://go.microsoft.com/fwlink/?linkid=851168)分发脱机应用的常规过程，则可以通过配置[](/microsoft-store/distribute-offline-apps)[Microsoft Teams 会议室配置](console.md)) 的主机主机。 部署工具包发布滞后于应用商店版本，因此可能无法始终匹配最新的可用版本。
  
### <a name="to-update-using-powershell"></a>使用 PowerShell 进行更新

1. 将程序包从 [安装 MSI 提取](https://go.microsoft.com/fwlink/?linkid=851168) 到设备可以访问的共享。
2. 针对以下设备运行Microsoft Teams 会议室脚本， \<share\> 并适当地更改到设备共享：
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>管理模式和设备管理
<a name="AdminMode"> </a>

某些管理功能（例如手动安装专用 CA 证书）需要将Teams 会议室管理模式。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>切换到管理模式，在应用运行时Microsoft Teams 会议室后退

1. 挂断任何正在进行的呼叫，然后返回到主屏幕。
2. 选择"齿轮"图标并弹出菜单， (选项包括设置、辅助功能 **和****重启设备) 。** 
3. 选择“**设置**”。
4. 输入管理员密码。 将显示“设置”屏幕。  如果设备未加入域，则默认 (用户名"Admin") 本地管理帐户。 此帐户的默认密码为"sfb"。 请尽快更改此密码。 如果计算机已加入域，可以使用适当的特权域帐户登录。
5. 选择 **Windows 设置** 列中的"列"。
6. 用你的管理凭据登录桌面。 你将拥有管理设备所需的权限。
7. 执行必要的管理任务。
8.  完成后重启计算机。
    
现在，控制台将返回其标准运行模式。 下面的过程要求将键盘连接至设备（如果尚未连接）。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>切换到管理模式，在应用Microsoft Teams 会议室时返回

1. 快速连续按 Windows 键五次。此时将显示 Windows 登录屏幕。 
2. 用你的管理凭据登录桌面。
3. 执行必要的管理任务。
4. 完成后重启计算机。

    > [!NOTE]
    > 此方法不会记录用户Skype或正常终止应用，但是，如果应用未响应，并且其他方法不可用，你将使用它。 

   主机重启到其正常运行模式，运行 Microsoft Teams 会议室 应用。 如果附加了键盘以完成此过程，可以删除键盘。
   ## <a name="troubleshooting-tips"></a>故障排除提示
   <a name="TS"> </a>

- 跨域边界发送会议邀请时 (，例如，在两家公司之间) 。 在这种情况下，IT 管理员应决定是否允许外部用户安排会议。 请参阅有关 PowerShell cmdlet [set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing)Exchange，特别是"ProcessExternalMeetingMessages"参数的文章。
- Microsoft Teams 会议室不支持通过 Exchange 2010 自动发现Exchange重定向。
- 一般而言，IT 管理员禁用他们不打算使用的任何音频终结点是一种很好的做法。
- 如果会议室预览中显示镜像，IT 管理员可以通过循环相机电源或使用相机设置翻转图像方向进行更正。
- 丢失控制台触摸屏访问权限是已知问题。 在这种情况下，此问题有时可以通过重启Teams 会议室。
- 通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。 在这种情况下，重新启动电脑可以解决本地音频播放问题。
