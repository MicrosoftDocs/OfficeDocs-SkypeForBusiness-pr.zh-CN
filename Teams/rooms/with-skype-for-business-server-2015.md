---
title: 使用Skype for Business Server部署Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题，了解如何使用Skype for Business Server部署Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271677"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用Skype for Business Server部署Microsoft Teams 会议室
  
本主题介绍在进行单林本地部署时如何为Microsoft Teams 会议室添加资源帐户。
  
如果使用 Exchange 2013 SP1 或更高版本以及 2015 或更高版本的单林本地部署 Skype for Business Server，则可以使用提供的Windows PowerShell脚本创建设备帐户。 如果使用的是多林部署，则可以使用生成相同结果的等效 cmdlet。 本节中对这些 cmdlet 进行了介绍。
  
在开始部署Microsoft Teams 会议室之前，请确保拥有运行关联 cmdlet 的适当权限。
  

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

   请注意，$strExchangeServer是 Exchange 服务器的完全限定域名 (FQDN) ，$strLyncFQDN是Skype for Business Server部署的 FQDN。

2. 建立会话后，你将创建一个新的邮箱并将其启用为 RoomMailboxAccount，或者更改现有会议室邮箱的设置。 这将允许帐户对Microsoft Teams 会议室进行身份验证。

    如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 可以在Teams 会议室资源帐户上设置各种 Exchange 属性，以改善用户的会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 在资源帐户上关闭密码过期。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中启用资源帐户，以便对Microsoft Teams 会议室进行身份验证。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 通过在Skype for Business Server池中启用Microsoft Teams 会议室 Active Directory 帐户，启用具有Skype for Business Server的资源帐户：

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    将和`-DomainController``-RegistrarPool`属性更改为适合环境的值。

7. **可选。** 还可以通过为帐户启用企业语音，允许Microsoft Teams 会议室在 PSTN) 电话呼叫 (建立和接收公共交换电话网络。 企业语音不是Microsoft Teams 会议室的要求，但如果要为Microsoft Teams 会议室提供 PSTN 拨号功能，下面介绍如何启用它：

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。 参数值 $true 保持不变。 还需要替换语音策略和拨号计划策略名称。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>示例：Exchange 中的会议室帐户设置和本地Skype for Business Server

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>相关主题

[为Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
