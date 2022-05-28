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
description: 了解如何管理Microsoft Teams 会议室。
ms.openlocfilehash: df9760694bd8e0c650be25eec7d435efcae02127
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761054"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 会议室维护和操作
 
 
Microsoft Teams 会议室是 Microsoft 的会议解决方案，旨在将会议室转变为丰富的协作体验。 用户将享受其熟悉的Microsoft Teams或Skype for Business界面，IT 管理员将欣赏轻松部署和管理的Windows 10 Teams 会议室应用。 Microsoft Teams 会议室旨在利用现有设备轻松安装，将Microsoft Teams或Skype for Business带入会议室。
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>在Microsoft Teams 会议室上收集日志
<a name="Logs"> </a>

若要在管理中心Teams收集日志，请转到 **Windows上> Teams 会议室Teams设备**。 选择要为其提供日志的设备的显示名称。 在顶部面板中，选择“下载设备日志”。 确认后，日志将在几分钟后准备好在“历史记录”选项卡中下载。

还可以使用 PowerShell 收集日志。 必须调用随Microsoft Teams 会议室应用附带的日志收集脚本。 在[管理员模式](rooms-operations.md)下，启动提升的命令提示符，并发出以下命令：
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

日志将以 ZIP 文件的形式输出至 c:\rigel 中。

### <a name="managing-disk-space"></a>管理磁盘空间
<a name="Space"> </a>

设备上下载的日志可以占用磁盘空间。 如果日志未定期清理，可能会干扰会议室的正常功能。 Teams 会议室在 30 天后删除下载的日志。 IT 管理员可以使用设备注册表设置替代日志清理。

|设置|允许|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |30 天后清理日志。  <br/> |
  
## <a name="front-of-room-display-settings"></a>会议室前显示设置
<a name="Display"> </a>

配置会议室前显示 () 的设置，以支持消费电子控制 (CEC) 或启用电脑模式。
  
如果希望会议室前部显示器在从备用模式唤醒时自动切换到Teams 会议室，则必须满足某些条件。 此功能是可选的，但受Microsoft Teams 会议室软件的支持，前提是基础硬件支持该功能。 用作会议室前显示器的使用者电视需要支持消费电子控制 (CEC) HDMI 功能。  根据所选 (可能不支持 CEC 的停靠或控制台，请参阅制造商支持文档) ，可能需要控制器（例如来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 [Extron 中的 Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) ）才能启用所需的行为。

### <a name="scale-and-resolution"></a>缩放和解析

若要获得Teams 会议室设计体验，会议室前显示器需要满足分辨率和缩放要求。

若要远程设置会议室前台显示的规模和分辨率，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md#set-front-of-room-scale-and-resolution)。

若要在Teams会议室管理员设置中手动设置缩放和解析：

1. 在Teams会议室中，切换到[管理模式](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. 选择“开始”图标。 然后 **设置 >系统>显示**

3. 转到 **“缩放”和“布局**”，然后 **更改文本、应用和其他项的大小**，并将缩放设置为 100%。

4. 将显示分辨率设置为 1080p。 如果有双监视器，请为两个屏幕设置缩放和分辨率。

5. 接下来，选择起始图标并输入 **命令提示符**。 选择 **“以管理员身份运行**”。

6. 运行以下命令：

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. 重启设备。
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 会议室重置 (工厂还原) 
<a name="Reset"> </a>

如果Microsoft Teams 会议室运行状况不佳，执行出厂重置可能会有所帮助。 为此，请使用[Microsoft Teams会议室恢复工具](recovery-tool.md)并按照工厂还原说明操作。

> [!NOTE]
> 存在一个已知问题：如果 **“保留我的文件 - 删除应用和设置**”，但在重置Windows过程中选择了个人文件选项，则Microsoft Teams 会议室可能变得不可用。 *请勿* 使用此选项。
  
## <a name="supported-remote-options"></a>支持的远程选项
<a name="RemoteOptions"> </a>

下表汇总了可能的远程操作和可以用于完成这些操作的方法。
  

|工作组 |未加入域|加入域|
|:-----|:-----|:-----|
|重新启动  <br/> |Teams 管理中心  <br/> 远程桌面  <br/> 远程 PowerShell  <br/> | <br/>远程桌面 (需要进一步配置)   <br/> 远程 PowerShell (需要进一步配置)   <br/> 配置管理器  <br/> |
|更新操作系统  <br/> |Windows 更新  <br/> |Windows 更新  <br/> WSUS  <br/> |
|应用更新  <br/> |Windows 应用商店  <br/> |Windows 应用商店  <br/> 配置管理器  <br/> |
|帐户配置  <br/> |Teams 管理中心  <br/> |Teams 管理中心  <br/> |
|访问日志  <br/> |Teams 管理中心  <br/> PowerShell  <br/> |Teams 管理中心 <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>为Microsoft Teams 会议室配置组策略
<a name="GroupPolicy"> </a>

本部分介绍Microsoft Teams 会议室依赖于其正常运行的系统设置。 

将Teams 会议室加入 Active Directory 域可提供以下优势：

- 通过加入域Teams 会议室可以授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。

- 可以将Windows服务质量配置部署到Teams 会议室。

- 如果使用Skype for Business，则加入Teams 会议室会自动导入组织的专用根证书链。

将Teams 会议室加入域时，需要创建单独的组织单位 (OU) ，以便可以向所有Teams 会议室对象所在的 OU 提供组策略对象 (GPO) 排除项。 禁用所有 GPO 继承，以便不支持组策略设置不应用于Teams 会议室。 在将Teams 会议室加入域之前在 OU 中创建计算机对象，以确保不应用应用于默认计算机 OU 的组策略。

> [!NOTE]
> 即使创建单独的 OU 并阻止继承，某些组策略也可能导致问题（如果未设置替代）。 具有“无替代”集的组策略将使用块策略继承集来击败 OU。

许多组织都有以下 GPO，这会影响Teams 会议室功能。 确保重写或阻止以下内容的继承：

  - 登录会话的超时（自动锁定）
  - 电源管理相关的策略
  - 需要附加身份验证步骤
  - 拒绝访问本地驱动器
  - 提示用户网络连接较慢
  - 登录时启动特定程序
  - 在所有加入域的计算机上创建另一个域用户帐户。
  - 将Windows 更新推送到Teams 会议室

将Microsoft Teams 会议室加入域时，请确保组策略不会覆盖下表中的设置。

|设置|允许|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |启用Microsoft Teams 会议室启动  <br/> |
|电源管理 -\> 在 AC 上，10 分钟后关闭屏幕  <br/> 电源管理 -\> 在 AC 上，从不让系统入睡  <br/> |使Microsoft Teams 会议室能够关闭附加的显示器并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |

> [!NOTE]
> 当Microsoft Teams 会议室与下一版本的Windows 10 OS 兼容时，Teams 会议室通过Windows 更新自动更新到下一版本。 Microsoft Teams 会议室不应手动升级到下一版本的Windows 10，也不应通过启用适用于企业的Windows 更新 (WUFB) 组策略“为要接收的更新选择Windows就绪级别”和通过 GPO 选择“预览版本和功能更新何时收到”。 Teams 会议室启用这些组策略后，WINDOWS 10操作系统更新时会遇到问题。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

可以使用 PowerShell 远程执行以下管理操作 (请参阅下表，了解脚本示例) ：
  
- 获取连接的设备
- 获取应用状态
- 获取系统信息
- 重启系统
- 检索日志
- 传输文件 (需要已加入域的Microsoft Teams 会议室) 
    
> [!NOTE]
> 默认情况下，此功能处于关闭状态。 需要为Microsoft Teams 会议室系统上的环境启用远程 PowerShell 才能执行以下操作。 有关如何启用远程 PowerShell 的信息，请参阅有关 **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** 的文档。
  
例如，可以按如下所示启用远程 PowerShell：
  
1. 在Microsoft Teams 会议室设备上以管理员身份登录。
2. 打开提升的 PowerShell 命令提示符。
3. 输入以下命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 打开本地安全策略，并将 *管理员* 安全组添加到 **安全设置** > **本地策略** > **用户权限分配** > **从网络访问此计算机**。

执行管理操作：
  
1. 使用有权在Microsoft Teams 会议室设备上运行 PowerShell 命令的帐户凭据登录到电脑。
2. 在电脑上打开常规的 PowerShell 命令提示符。
3. 复制下表中的命令文本，并将其粘贴到提示符处。
4. 将字段替换  `<Device fqdn>` 为适合环境的 FQDN 值。
5. 替换  *\<path\>*  为主SkypeSettings.xml配置文件 (或主题映像) 的文件名和本地路径。
    
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

默认情况下，Microsoft Teams 会议室尝试连接到Windows Microsoft Store以获取最新版本的Microsoft Teams 会议室软件。 因此，Teams 会议室需要定期访问 Internet。 在遇到支持问题之前，请确保Microsoft Teams 会议室加载了最新版本的应用。
  
Microsoft Teams 会议室连接到Windows 更新以检索操作系统和外围设备固件更新。 它还连接到Microsoft Store以检索应用程序更新。

如果需要手动管理应用程序更新，但无法按照正常过程[适用于企业的 Microsoft Store](https://businessstore.microsoft.com/store)[分发脱机应用](/microsoft-store/distribute-offline-apps)，则可以获取Teams 会议室更新包，以便在支持的操作系统上执行应用更新。 更新版本可能落后于应用商店版本，并且可能并不总是与最新可用版本匹配。 请参阅[手动更新Microsoft Teams 会议室设备](manual-update.md)以了解详细信息。

## <a name="admin-mode-and-device-management"></a>管理模式和设备管理
<a name="AdminMode"> </a>

某些管理功能（例如手动安装专用 CA 证书）需要将Teams 会议室置于管理员模式。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>切换到管理员模式并在Microsoft Teams 会议室应用运行时返回

1. 挂断任何正在进行的呼叫，并返回到主屏幕。
2. 选择“齿轮”图标，并显示菜单 (**选项设置**、**辅助功能** 和 **重启设备**) 。
3. 选择“**设置**”。
4. 输入管理员密码。 将显示“设置”屏幕。  如果设备未加入域，默认情况下将使用本地管理帐户 (用户名“管理员”) 。 此帐户的默认密码为“sfb”。 尽快更改此密码。 如果计算机已加入域，则可以使用适当的特权域帐户登录。
5. 在左列中选择 **Windows 设置**。
6. 用你的管理凭据登录桌面。 你将拥有管理设备所需的权限。
7. 执行必要的管理任务。
8.  完成后重启计算机。
    
现在，控制台将返回其标准运行模式。 下面的过程要求将键盘连接至设备（如果尚未连接）。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>切换到管理员模式并在Microsoft Teams 会议室应用崩溃时返回

1. 快速连续按 Windows 键五次。 此时将显示 Windows 登录屏幕。 
2. 用你的管理凭据登录桌面。
3. 执行必要的管理任务。
4. 完成后重启计算机。

    > [!NOTE]
    > 此方法不会将Skype用户注销或正常终止应用，但如果应用未响应且其他方法不可用，则使用该应用。 

   控制台重新启动到正常操作模式，运行Microsoft Teams 会议室应用。 如果附加了一个来完成此过程，则可以删除键盘。
   ## <a name="troubleshooting-tips"></a>故障排除提示
   <a name="TS"> </a>

- 例如，在两家公司之间) ，跨域边界发送 (时，可能不会显示会议邀请。 在这种情况下，IT 管理员应决定是否允许外部用户安排会议。 请参阅Exchange PowerShell cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing)，特别是“ProcessExternalMeetingMessages”参数的文章。
- Microsoft Teams 会议室不支持通过 Exchange 2010 Exchange自动发现重定向。
- 通常，IT 管理员最好禁用他们不打算使用的任何音频终结点。
- 如果镜像在会议室预览中显示，IT 管理员可以通过循环使用相机电源或使用相机设置翻转图像方向来更正。
- 丢失控制台触摸屏访问权限是已知问题。 在这种情况下，有时通过重启Teams 会议室来解决此问题。
- 通过有线采集将电脑连接到控制台时丢失本地音频是已知问题。 在这种情况下，重新启动电脑可以解决本地音频播放问题。
