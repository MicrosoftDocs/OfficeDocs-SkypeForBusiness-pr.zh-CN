---
title: 使用 Microsoft Teams 会议室 部署Skype for Business Server
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Skype for Business Server。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 702eb2128dd37980fd3fc76548638102d45d7af9
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355617"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用 Microsoft Teams 会议室 部署Skype for Business Server
  
本主题介绍如何在具有单林本地部署Microsoft Teams 会议室添加资源帐户。
  
如果具有具有 Exchange 2013 SP1 或更高版本以及 Skype for Business Server 2015 或更高版本的单林本地部署，可以使用提供的 Windows PowerShell 脚本创建设备帐户。 如果使用多林部署，可以使用将生成相同结果的等效 cmdlet。 本节中对这些 cmdlet 进行了介绍。
  
在开始部署Microsoft Teams 会议室，请确保拥有运行关联的 cmdlet 所需的正确权限。
  

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

   请注意$strExchangeServer是 Exchange 服务器的 FQDN (FQDN) ，$strLyncFQDN 是 Skype for Business Server 部署的 FQDN。

2. 建立会话后，将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户通过身份验证Microsoft Teams 会议室。

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

3. 可以在资源Exchange设置各种Teams 会议室属性，以改进用户的会议体验。 你可以看到需要在 Exchange 属性部分设置的属性。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 关闭资源帐户的密码过期。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中启用资源帐户，以便它向 Microsoft Teams 会议室。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 通过启用 Skype for Business Server 池上的 Microsoft Teams 会议室 Active Directory 帐户，启用具有 Skype for Business Server 的资源帐户：

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    将 `-DomainController` 和 `-RegistrarPool` 属性更改为适合环境的值。

7. **可选。** 您还可以允许Microsoft Teams 会议室启用 PSTN (呼叫公用电话交换) 呼叫，企业语音呼叫。 企业语音不是用户Microsoft Teams 会议室，但如果您希望 PSTN 拨号功能Microsoft Teams 会议室，下面将了解如何启用它：

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。 参数值 $true 保持不变。 还需要替换语音策略和拨号计划策略名称。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>示例：本地Exchange Skype for Business Server会议室帐户设置

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

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
