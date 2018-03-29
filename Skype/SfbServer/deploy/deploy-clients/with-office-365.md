---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读有关如何部署使用 Office 365 的 Skype 的空间系统 v2 本主题。
ms.openlocfilehash: b05afbf973e814c5adf7b8a8490aefa0cbb04886
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>将 Skype 会议室系统 v2 与 Office 365 一起部署 
 
阅读有关如何部署使用 Office 365 的 Skype 的空间系统 v2 本主题。
  
本主题介绍如何添加 Skype 的空间系统 v2 的设备帐户，当您拥有 Office 365 提供联机部署。
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>将 Skype 会议室系统 v2 与 Office 365 一起部署 

部署与 Office 365 的 Skype 的空间系统 v2 之前，请确保已满足要求。 有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
若要启用业务的 Skype，您必须：
  
- Skype 的在线业务 (计划 2) 或更高版本在您 Office 365 的计划。 该计划需要支持会议功能。
    
- 如果您需要企业语音 （PSTN 电话服务） 对 Skype 的空间系统 v2 使用电话服务提供程序需要 Skype 业务联机 (计划 3)。
    
- 租户用户必须具有 Exchange 邮箱。
    
- Skype 的空间系统 v2 帐户需要 Skype 的在线业务 (计划 2) 或 Skype 的在线业务 (计划 3) 许可证，但它不需要 Exchange Online 的许可证。
    
### <a name="add-a-device-account"></a>添加设备帐户

1. 在计算机上启动远程 Windows PowerShell 会话，并连接到 Exchange。 确保你有合适的权限集来运行相关 cmdlet。 下面是可以在你的环境中使用和修改的一些 cmdlet 示例。
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. 之后建立会话，您将创建一个新邮箱和它启用为 RoomMailboxAccount，或者更改现有空间邮箱的设置。 这将允许对 Skype 的空间系统 v2 进行身份验证的帐户。
    
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
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. 设备的帐户需要有一个有效的 Office 365 提供许可证，或交换和业务的 Skype 不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 可以使用 Get MsolAccountSku，如下所示为 Office 365 租户检索可用 Sku 列表：
    
   ```
   Get-MsolAccountSku
   ```

   接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. 接下来，您需要启用设备的帐户与 Skype 的业务。 请确保您的环境符合[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。
    
   启动远程 Windows PowerShell 会话，如下所示 （请务必安装 Skype 业务在线 PowerShell 组件）：
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   接下来，让 Skype 的空间系统 v2 帐户 Skype 业务服务器通过运行以下 cmdlet:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   新的用户帐户在安装过程中，从获取 RegistrarPool 信息，如本示例所示：
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 不可能在组织中现有的用户帐户相同的注册器池上创建新的用户帐户。 上面的命令将会阻止这种情况由于开户中的错误。 
  
完成上述步骤启用联机业务 Skype Skype 的空间系统 v2 帐户后，您需要向 Skype 的空间系统 v2 设备分派许可证。 使用 Office 365 管理门户，在线业务 (计划 2) 或 Skype 业务联机 (计划 3) 许可证的设备分配任一 Skype。
  
### <a name="assign-a-license-to-your-account"></a>向你的帐户分配许可证

1. 登录作为租户管理员，打开 Office 365 管理门户网站，并在管理应用程序上单击。
    
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
    
3. 选择 Skype 的空间系统 v2 帐户，然后单击或点击笔图标，表示编辑。
    
4. 单击“**许可证**”选项。
    
5. 在**分配许可证**部分中，您需要选择 Skype 业务联机 (计划 2) 或 Skype 业务联机 (计划 3)，具体取决于您的授权和决定方面需要企业语音。 您必须使用计划 3 许可证，如果您想要使用 Skype 的空间系统 v2 云 PBX。 至少需要 CloudPBX 才能进行语音连接。 然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。
    
6. 单击“**保存**”完成任务。
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>示例： 房间帐户设置在 Exchange 联机和 Skype 的在线业务

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
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 的空间规划系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 的空间系统 v2](room-systems-v2.md)
  
[配置控制台，Skype 的空间系统 v2](console.md)
  
[Skype 的机房管理系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

