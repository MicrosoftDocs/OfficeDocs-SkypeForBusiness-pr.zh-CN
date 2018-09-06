---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读此主题以获取如何部署与 Office 365 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: c623d689f876cfe36c7c8308a7f62526be217ec1
ms.sourcegitcommit: a9556a51f7f970fc05ab0acc9998401db3c1aa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2018
ms.locfileid: "22601967"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>将 Skype 会议室系统 v2 与 Office 365 一起部署 
 
阅读此主题以获取如何部署与 Office 365，其中的业务和 Exchange Skype 都联机 Skype 会议室系统 v2 的信息。 

设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。 Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。 如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>将 Skype 会议室系统 v2 与 Office 365 一起部署 

部署与 Office 365 的 Skype 会议室系统 v2 之前，请确保已满足的要求。 有关详细信息，请参阅[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
若要启用 for Business 的 Skype，您必须：
  
- Skype 业务 online （计划 2 中或基于企业的规划） 或更高版本 Office 365 计划中。 计划需要允许电话拨入式会议功能。
    
- 如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。  如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。 
    
- 您的租户用户必须拥有 Exchange 邮箱。
    
- Skype 会议室系统 v2 帐户确实需要在最小 Skype 业务 Online (计划 2) 许可证，但它不需要的 Exchange Online 的许可证。

Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。

### <a name="add-a-device-account"></a>添加设备帐户

1. 在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange。 确保你有合适的权限集来运行相关 cmdlet。 下面是可以在你的环境中使用和修改的一些 cmdlet 示例。
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. 后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。 这将允许对 Skype 会议室系统 v2 进行身份验证的帐户。
    
  如果要更改现有的资源邮箱：
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  如果您正在创建新的资源邮箱：
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 必须设置设备帐户的各个 Exchange 属性，以改进会议体验。你可以看到需要在 Exchange 属性部分设置的属性。
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. 你需要连接至 Azure Active Directory 来应用一些帐户设置。 要连接至 Azure AD，请运行以下 cmdlet：
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示： 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   你还可以为会议室设置电话号码，如下所示：
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. 设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您可以使用 Get-msolaccountsku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：
    
   ```
   Get-MsolAccountSku
   ```

   接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. 接下来，您需要启用 for Business 的 Skype 的设备帐户。 确保您的环境符合[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。
    
   启动远程 Windows PowerShell 会话，如下所示 （请务必业务 Online PowerShell 组件安装 Skype）：
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   接下来，您 Skype 会议室系统 v2 帐户启用 Skype 业务服务器通过运行以下 cmdlet:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。 上面的命令将防止由于这种情况下的帐户设置中的错误。 
  
您已完成上述步骤中 Skype 您 Skype 会议室系统 v2 帐户启用业务联机后，您需要将许可证分配给 Skype 会议室系统 v2 设备。 使用 Office 365 管理门户，为业务 Online (计划 2) 或业务 Online (计划 3) 许可证设备 Skype 分配任一 Skype。
  
### <a name="assign-a-license-to-your-account"></a>向你的帐户分配许可证

1. 登录以租户管理员，打开 Office 365 管理门户，并单击管理应用程序。
    
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
    
3. 选择 Skype 会议室系统 v2 帐户，然后单击或点击笔图标，表示编辑。
    
4. 单击“**许可证**”选项。
    
5. 在**分配许可证**部分中，您需要选择 Skype 业务 Online (计划 2) 或 Skype 的业务 Online (计划 3)，具体取决于您的授权和决定方面需要企业语音。 您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 云 PBX。 至少需要 CloudPBX 才能进行语音连接。 然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。
    
6. 单击“**保存**”完成任务。
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>示例： 会议室帐户安装在 Exchange Online 和 Skype 业务 online

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> 这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。此外，还需要使用管理界面来指定电话号码。 
  
## <a name="validate"></a>验证

进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。


## <a name="see-also"></a>另请参阅

[配置帐户 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)

[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

