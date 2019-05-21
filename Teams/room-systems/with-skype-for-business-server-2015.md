---
title: 通过 Skype for Business 服务器部署 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题, 了解如何通过 Skype for Business 服务器部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: a0e476738cb1ff68020b87624cbcdbabb220c248
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288441"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>通过 Skype for Business 服务器部署 Microsoft 团队聊天室
  
本主题介绍了如何在具有单个林内部部署的情况下为 Microsoft 团队聊天室添加设备帐户。
  
如果你有一个具有 Exchange 2013 SP1 或更高版本以及 Skype for business Server 2015 或更高版本的单林、内部部署, 则可以使用所提供的 Windows PowerShell 脚本创建设备帐户。 如果你使用的是多目录林部署, 则可以使用将产生相同结果的等效 cmdlet。 本节中对这些 cmdlet 进行了介绍。

  
开始部署 Microsoft 团队聊天室之前, 请确保你拥有运行关联 cmdlet 的相应权限。
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   请注意, $strExchangeServer 是 Exchange server 的完全限定的域名 (FQDN), 并且 $strLyncFQDN 是 Skype for Business Server 部署的 FQDN。

2. 建立会话后, 你将创建一个新邮箱并将其作为 RoomMailboxAccount 启用, 或更改现有会议室邮箱的设置。 这将允许帐户对 Microsoft 团队聊天室进行身份验证。

    如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果要创建新的资源邮箱, 请执行以下操作:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 你可以在设备帐户上设置各种 Exchange 属性来改善人员的会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 如果您决定让密码永不过期, 则可以使用 Windows PowerShell cmdlet 设置该密码。 有关详细信息，请参阅“密码管理”。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中启用帐户, 以便它将对 Microsoft 团队聊天室进行身份验证。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 通过在 Skype for business 服务器池上启用 Microsoft 团队聊天室 Active Directory 帐户, 通过 Skype for business 服务器启用设备帐户:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    该项目需要使用会话初始协议 (SIP) 地址和域控制器。

7. **可选。** 你还可以允许 Microsoft 团队聊天室通过为你的帐户启用企业语音来拨打和接收公共交换电话网络 (PSTN) 电话呼叫。 企业语音不是 Microsoft 团队聊天室的必要条件, 但如果你希望 Microsoft 团队聊天室客户端的 PSTN 拨号功能, 请按以下方法启用它:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>示例: Exchange 和 Skype for business Server 内部部署中的房间帐户设置

``` Powershell
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

[为 Microsoft 团队聊天室配置帐户](room-systems-v2-configure-accounts.md)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 团队聊天室](room-systems-v2.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
