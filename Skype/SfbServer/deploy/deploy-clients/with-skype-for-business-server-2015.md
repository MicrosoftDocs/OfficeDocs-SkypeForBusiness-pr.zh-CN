---
title: 将 Skype 会议室系统 v2 与 Skype for Business Server 2015 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读有关如何部署使用 Skype 的 Skype 的空间系统 v2 为业务服务器 2015年本主题。
ms.openlocfilehash: 904835e766283791f52c0dc1d1221a0d7253e3e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>将 Skype 会议室系统 v2 与 Skype for Business Server 2015 一起部署
 
阅读有关如何部署使用 Skype 的 Skype 的空间系统 v2 为业务服务器 2015年本主题。
  
本主题说明如何添加 Skype 的空间系统 v2 的设备帐户，当您具有单目录林内部部署。
  
如果您有一个单林、 内部部署 Exchange 2013 SP1 或更高版本和 Skype 的业务服务器 2015年或更高版本，然后可以使用提供的 Windows PowerShell 脚本来创建设备帐户。 如果您使用的多目录林部署，可以使用等价 cmdlet 将产生相同的结果。 本节中对这些 cmdlet 进行了介绍。
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>将 Skype 会议室系统 v2 与 Skype for Business Server 2015 一起部署

对于业务服务器 2015年部署 Skype 与 Skype 的空间系统 v2 之前，请确保已满足要求。 有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
开始部署 Skype 的空间系统第 2 版之前，请确保您具有正确的权限运行相关联的 cmdlet。
  
1. 从 PC 启动远程 Windows PowerShell 会话，并连接到 Exchange。 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   请注意，$strExchangeServer 您的 Exchange 服务器的完全限定的域名 (FQDN)，$strLyncFQDN 为您的业务服务器 2015年部署 Skype 的 FQDN。
    
2. 之后建立会话，您将创建一个新邮箱和它启用为 RoomMailboxAccount，或者更改现有空间邮箱的设置。 这将允许对 Skype 的空间系统 v2 进行身份验证的帐户。
    
    如果要更改现有的资源邮箱：
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果您正在创建新的资源邮箱：
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以设置各种 Exchange 属性在设备的帐户，以提高人们的会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 如果您决定将不会过期的密码，您可以设置，使用 Windows PowerShell cmdlet 太。 有关详细信息，请参阅“密码管理”。
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. 因此，它将对 Skype 的空间系统 v2 身份验证启用 Active Directory 中的帐户。
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 通过启用业务服务器 2015年池 Skype 上的 Skype 的空间系统 v2 Active Directory 帐户启用业务服务器 2015 Skype 与设备的帐户：
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    该项目需要使用会话初始协议 (SIP) 地址和域控制器。 
    
7. **可选。** 您还可以允许 Skype 的空间系统 v2 和通过为您的帐户启用企业语音接收公用交换的电话网络 (PSTN) 电话呼叫。 企业语音不是 Skype 的空间系统 v2 的必要条件，但如果 Skype 的空间系统第 2 版客户端需要 PSTN 拨号功能，下面介绍了如何启用它：
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a>示例： 房间帐户设置 Exchange 和 Skype 为内部部署的业务服务器 2015

```
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) 
-UserPrincipalName rigel1@contoso.com
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false 
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1

```

## <a name="see-also"></a>另请参阅

#### 

[Skype 的空间规划系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 的空间系统 v2](room-systems-v2.md)
  
[配置控制台，Skype 的空间系统 v2](console.md)
  
[Skype 的机房管理系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

