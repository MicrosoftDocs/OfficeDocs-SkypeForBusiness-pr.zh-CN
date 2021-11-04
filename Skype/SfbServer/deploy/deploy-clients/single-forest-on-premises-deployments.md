---
title: Skype会议室系统单林本地部署
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林Skype部署会议室系统。
ms.openlocfilehash: 8768ecfa8aba01074bee5315580fde79ba9c3afc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759144"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype会议室系统单林本地部署
 
阅读本主题，了解如何在单林Skype部署会议室系统。
  
本节概述了在单个林本地部署中托管的 Skype 会议室Exchange Server和Skype for Business Server上预配会议室系统帐户的步骤。
  
## <a name="single-forest-on-premises-deployments"></a>单个林本地部署

如果会议室已有资源邮箱帐户，可以使用该帐户。 否则，需要新建一个。 可以使用 PowerShell Exchange命令行管理 (或) Exchange 管理控制台命令行管理程序创建新的资源邮箱帐户。 我们建议使用新的邮箱 (旧邮箱，然后为会议室) 重新创建Skype邮箱。 请确保先备份邮箱数据，然后再删除，然后使用 Outlook 客户端将其导出回已创建的邮箱 (请参阅导出或备份邮件、日历、任务和联系人，了解) 。 若要通过删除邮箱来还原丢失的会议，请参阅连接[或还原已删除的邮箱](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
若要使用现有资源邮箱帐户 (例如 LRS-01) 请按照以下步骤操作：
  
1. 运行以下 Exchange Management PowerShell 命令：
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 如果计划创建新邮箱，则对于单个林内部部署组织Exchange运行以下命令：
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上述示例在 Active Directory 中创建了一个已启用的用户帐户，为内部部署组织的会议室创建了Exchange邮箱。 RoomMailboxPassword 参数指定用户帐户的密码。
    
3. 配置帐户以通过接受/拒绝会议自动解决冲突。 Skype会议室系统中配备了会议室Exchange帐户由个人管理，但请注意，在个人接受会议之前，Skype会议室系统主屏幕日历上不会显示。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   有关完整的可用命令集，请参阅 Set-CalendarProcessing。
    
   若要提醒会议组织者将会议设置为联机Skype for Business会议Outlook，请运行以下命令来设置新帐户的邮件提示： 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 使用以下命令配置本地化字符串。 如果组织要求，还可以添加自定义翻译： 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 可选：配置会议接受文本，以便为用户提供有关会议Skype for Business 会议室以及安排和加入会议时预期的信息。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>检查 Active Directory 中的资源邮箱帐户

上面步骤 1 Exchange创建的会议室邮箱帐户可能是 Active Directory 中已禁用的用户对象。 Skype如果帐户在 Active Directory 中已禁用，则会议室系统无法使用 Kerberos/NTLM 身份验证登录或进行身份验证。 会议室Skype客户端必须能够针对 Exchange Web 服务进行身份验证以检索日历设置，并且还必须能够发送包含白板内容的电子邮件。 
  
因此，如果禁用该帐户，则必须通过执行以下操作在 Active Directory 中启用此帐户： 
  
1. 在 Active Directory 中，运行以下命令以启用帐户登录： 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   运行此命令将提示您输入当前密码，然后重新输入密码两次进行确认。
    
2. 设置密码后，运行以下命令以启用帐户： 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>为Skype启用会议室系统Skype for Business

本节概述为会议室帐户启用Skype for Business所需的步骤，这将在会议室Skype配置。 
  
为会议室创建资源邮箱帐户后，使用 Skype for Business Server 命令行管理程序 为会议Skype启用会议室Skype for Business帐户。
  
> [!NOTE]
> 以下过程假定你已启用 Active Directory Skype会议室系统帐户。 
  
1. 运行以下命令以在Skype池上启用会议室Skype for Business Server帐户：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 可选：通过为帐户启用 PSTN 电话呼叫，允许此帐户拨打和接听企业语音。 企业语音会议室系统不需要Skype，但是如果未为 企业语音 启用，Skype 会议室系统客户端将无法提供 PSTN 拨号功能：
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果为 企业语音 会议室Skype帐户启用语音策略，请确保配置适合组织的受限语音策略。 如果Skype for Business 会议室资源，则任何人都可以使用它加入会议（计划或临时）。 加入会议后，该人员可以拨出到任何号码。 在Skype for Business Server中，"从会议拨出"功能使用用户的语音策略，在这种情况下，Skype会议室系统帐户加入会议。 在早期版本的 Lync Server 中，使用组织者的语音策略。 因此，如果早期版本的 Lync Server 的用户安排了会议室并邀请 Skype 会议室系统会议室帐户，则任何人都可以使用 Skype for Business 会议室 加入会议，并可以拨打任何国家/地区或国际电话号码，只要组织者允许拨打这些号码。 
