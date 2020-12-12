---
title: 使用 Skype for Business Server 部署 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题，了解如何使用 Skype for Business Server 部署 Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662257"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用 Skype for Business Server 部署 Microsoft Teams 会议室
  
本主题介绍在单林本地部署时如何为 Microsoft Teams 会议室添加设备帐户。
  
如果你有使用 Exchange 2013 SP1 或更高版本以及 Skype for Business Server 2015 或更高版本的单林本地部署，可以使用提供的 Windows PowerShell 脚本创建设备帐户。 如果使用多林部署，可以使用将生成相同结果的等效 cmdlet。 本节中对这些 cmdlet 进行了介绍。

  
在开始部署 Microsoft Teams 会议室之前，请确保拥有运行关联 cmdlet 所需的正确权限。
  

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

   请注意$strExchangeServer是 Exchange 服务器的 FQDN (完全限定) ，$strLyncFQDN 是 Skype for Business Server 部署的 FQDN。

2. 建立会话后，您将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户向 Microsoft Teams 会议室进行身份验证。

    如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以在设备帐户上设置各种 Exchange 属性，以改进人员的会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 如果决定让密码永不过期，也可使用 Windows PowerShell cmdlet 进行设置。 有关详细信息，请参阅“密码管理”。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中启用帐户，以便向 Microsoft Teams 会议室进行身份验证。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 通过启用 Skype for Business Server 池上的 Microsoft Teams 会议室 Active Directory 帐户，为 Skype for Business Server 启用设备帐户：

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    该项目需要使用会话初始协议 (SIP) 地址和域控制器。

7. **可选。** 您还可以允许 Microsoft Teams 会议室通过为您的帐户启用 (，在 PSTN) 拨打和接收企业语音电话交换网。 企业语音不是 Microsoft Teams 会议室的一项要求，但如果你需要 Microsoft Teams 会议室客户端的 PSTN 拨号功能，下面将了解如何启用此功能：

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>示例：Exchange 和本地 Skype for Business Server 中的会议室帐户设置

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

## <a name="related-topics"></a>相关主题

[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
