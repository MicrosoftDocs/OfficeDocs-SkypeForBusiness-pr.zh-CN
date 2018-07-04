---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 配置 Microsoft 团队面中心的管理设置。
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192177"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>曲面集线器部署的 Microsoft 团队
======================================

为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。 有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)。

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

7\。 接下来，您需要为面集线器中启用团队的设备帐户。 确保您的环境符合[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)中定义的要求。

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

这些说明包括当前安装的 Microsoft 存储中的图面集线器团队解决方法。 
 
1. 启动 Windows 应用商店：<br>
   a. 点击**开始** > **所有应用程序** > **设置**。<br> b. 点击**面集线器设备帐户、 管理**。<br>
   c. 在左侧，点击**应用程序和功能**选项卡。<br> d. 在右侧，点击**打开存储**按钮。 
2. 从 Microsoft 存储，搜索*的 Microsoft 团队*。 将显示**图面集线器 （预览） 的 Microsoft 团队**。 点击**获取应用程序**按钮以安装。  
3. 安装完成后，重新启动面集线器。 
4. 曲面集线器重新启动后，您应该能够从**开始**菜单启动团队应用程序并从日历加入会议。 

## <a name="make-teams-the-default-vtc-application"></a>使团队默认 VTC 应用程序

最多为默认 VTC 应用程序，而不是 for Business 的 Skype，均可以设置团队。 移动设备管理 (MDM) 策略需要应用于面集线器设备。 
 
有两种配置 MDM 策略： 

- 如果您已配置的策略，则将其添加通过设备管理应用程序。 
- 如果您没有配置的远程策略，我们将拖放到 usb 闪存盘上可以加载的设置的包文件。

### <a name="device-management-configuration"></a>设备管理配置

下面是添加配置从管理中心 MDM 颁发机构 MDM 策略的示例。 如果您位于企业网络时，您可以使用以下说明原义，包括用户帐户。 
 
1. 在**设备管理**部分中，点击**+**。<br>
   将打开**连接工作或学校**对话框。 
2. 输入的策略电子邮件地址和密码提示时。<br>
   **注意：** 在已输入您的设备管理帐户后不自动刷新 UI OS 没有 bug。 您需要关闭并重新打开设置，以便查看列出的帐户。 
3. 它将执行几分钟，以便同步 MDM 策略设置。如果您想要强制进行同步，点击**MDM 帐户**按钮，，，然后点击**信息**按钮。 此操作将显示信息窗口，然后点击**同步**。 
4. 若要验证已您的需要您可以检查注册表。 您应看到**HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**下的两个键。 <br><br>
   **VtcAppMeetingHandlingMode** DWORD 值指示团队是默认应用程序。 可识别以下值。 <br><br>
    |数字 | 值   |
    |-------|---------|
    |0      | SkypePreferred            |
    |1      | VtcPreferred （工作组）      |
    |2      | VtcExclusive （仅适用于工作组） |

    **VtcCallAppPackageId**是已安装的团队包的名称。 如果这不会显示，请确保您已安装工作组包，并重新同步。 
 
### <a name="configure-mdm-via-usb-key"></a>配置 MDM 通过 USB 键 
 
此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。 选择相应的包的安装，并将其复制到 usb 闪存盘您计划。 要使用的正确.ppkg 文件取决于已安装了从存储区，团队包和您想要应用 （Skype 独占、 首选的 Skype 团队首选，团队独占） 的策略。 
 
1. 将 usb 闪存盘附加到面集线器设备。 
2. 打开面集线器设备上的**设置**应用程序。 
3. **曲面集线器设备帐户管理**打开。
4. 打开**设备管理**。 
5. 单击**添加或删除设置包**。 
6. 单击**添加包**。
7. 从下拉列表菜单中选择**可移动媒体**选项。 
8. 添加**Allowbuildspreview.ppkg**，，然后选择您要添加的图面集线器程序包。 
9. 重新启动面集线器设备。 

> [!NOTE]
> 如果您的设备或组织的设备不是当前的一部分 Windows 内幕计划和中介绍的一般数据保护法规 (GDPR) 的国家/地区 （或您已手动更改为基本的遥测设置），则您必须重新检查是否具有允许完全遥测之前加入内幕计划。 GDPR 更改在欧盟为基本设置遥测面集线器设备的默认行为。