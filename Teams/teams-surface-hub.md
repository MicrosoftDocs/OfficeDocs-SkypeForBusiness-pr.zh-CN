---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 配置 Microsoft 团队面中心的管理设置。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab8bb4be2d98c33ad01827f3eb6a3c940bfb6228
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23868218"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>曲面集线器部署的 Microsoft 团队
======================================

为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。 有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/surface-hub/)。

## <a name="set-up-user-accounts"></a>设置用户帐户
 
若要设置可用于与团队面集线器的用户帐户，创建设备帐户与 for Business 的 Skype 像支持。 设备帐户需要具有禁用 （以允许自动登录） 的多因素身份验证 Office 365 中的团队的以下相关服务：  
- Exchange 
- SharePoint 
- Office 应用程序 

## <a name="add-a-device-account"></a>添加设备帐户 

驱动器。 在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange。 确保您具有正确的权限设置为运行相关联的 cmdlet。 下面是可以在你的环境中使用和修改的一些 cmdlet 示例。

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2\。 建立会话后，你将创建新邮箱并将其启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许对团队进行身份验证的帐户。

如果要更改现有的资源邮箱：

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

如果要新建资源邮箱：

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\。 必须设置设备帐户的各个 Exchange 属性，以改进会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\。 你需要连接至 Azure Active Directory 来应用一些帐户设置。 要连接至 Azure AD，请运行以下 cmdlet：

```
Connect-MsolService -Credential $cred
```

5\。 	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示： 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

你还可以为会议室设置电话号码，如下所示：

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\。 设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您可以使用 Get-msolaccountsku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：
 
```
Get-MsolAccountSku
```

接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\。 接下来，您需要为面集线器中启用团队的设备帐户。 确保您的环境符合[Microsoft Surface 中心管理指南](https://docs.microsoft.com/surface-hub/)中定义的要求。

启动远程 Windows PowerShell 会话，如下所示 （请务必业务 Online PowerShell 组件安装 Skype）：

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

接下来，通过运行以下 cmdlet 启用您的团队面集线器帐户：

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> 不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。 上面的命令将防止由于这种情况下的帐户设置中的错误。 

您已完成上述步骤将启用您的团队面集线器帐户后，您需要将许可证分配给面集线器 v2 设备。 使用 Office 365 管理门户，将团队面集线器许可证分配给设备。

### <a name="assign-a-license-to-the-account"></a>将许可证分配给该帐户

1. 以租户管理员身份登录，打开 Office 365 管理中心中，单击管理应用程序。
2. 单击**用户和组**，然后单击**添加用户，重置密码和详细信息**。
3. 选择团队面集线器帐户，然后单击或点击笔图标，表示编辑。
4. 单击**许可证**选项。
5. 在**分配许可证**部分中，您需要选择计划，具体取决于您的授权。
6. 单击“**保存**”完成任务。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>从 Microsoft 存储的表面集线器安装团队 

安装 Microsoft 存储中的图面集线器团队供以下说明。 
 
1. 启动 Microsoft 存储：<br>
   a. 点击**开始** > **所有应用程序** > **设置**。<br> b. 点击**面集线器设备帐户、 管理**。<br>
   c. 在左侧，点击**应用程序和功能**选项卡。<br> d. 在右侧，点击**打开存储**按钮。 
2. 从 Microsoft 存储，搜索*的 Microsoft 团队*。 将显示**图面中心的 Microsoft 团队**。 点击**获取应用程序**按钮以安装。  
3. 安装完成后，重新启动面集线器。 

> [!NOTE]
> 不点击从商店列表页的**启动**。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>使团队默认呼叫和会议应用程序
 
有两种配置的默认呼叫和会议应用程序策略： 

- **选项 1**： 配置通过 USB 键。 
- **选项 2**： 通过如 Intune MDM 配置。
 
### <a name="option-1-configure-via-usb-key"></a>选项 1： 配置通过 USB 键 
 
此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。 选择相应的包的安装，并将其复制到 usb 闪存盘您计划。 要使用的正确.ppkg 文件取决于您想要应用，如下所示的默认应用程序策略： 

|数字  |说明  |
|---------|---------|
|0     | Skype 团队会议可用的启动屏幕上的首选应用程序        |
|1     | 团队 Skype 会议可用的启动屏幕上的首选应用程序        |
|2     | 在开始屏幕 (Skype app 不可用) 团队专用应用程序        |
 
1. 将 usb 闪存盘附加到面集线器设备。 
2. 打开面集线器设备上的**设置**应用程序。 
3. **曲面集线器设备帐户管理**打开。
4. 打开**设备管理**。 
5. 单击**添加或删除设置包**。 
6. 单击**添加包**。
7. 从下拉列表菜单中选择**可移动媒体**选项。 
8. 添加适当的**TeamsRTMMode*.ppkg**包以前复制到 usb 闪存盘。 
9. 重新启动面集线器设备。 
10. 设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>选项 2： 配置通过如 Intune MDM 

使用以下配置通过 Intune 的默认呼叫和会议应用程序策略。

.

|设置   |值    |说明    |
|----------|---------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|数据类型 | 整数 (0-2)   |0-团队会议可用的启动屏幕上的 Skype 首选应用程序<br>1-团队 Skype 会议可用的启动屏幕上的首选应用程序<br>2-团队 （不可用 Skype 应用程序） 在开始屏幕上的专用应用程序 |
|运营| 获取、 设置        |

|设置   |值    |
|----------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|数据类型 | 字符串-团队应用程序包 ID 为**Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe 设置字符串 ！团队** |
|运营| 获取、 设置        |

重新启动面集线器设备。 设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。

