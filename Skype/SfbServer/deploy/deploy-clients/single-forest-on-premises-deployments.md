---
title: Skype 会议室系统单林本地部署
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120321"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 会议室系统单林本地部署
 
阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
  
本部分概述了在单个林本地部署中托管的 Exchange Server 和 Skype for Business Server 上设置 Skype 会议室系统帐户的步骤。
  
## <a name="single-forest-on-premises-deployments"></a>单个林本地部署

如果会议室已有资源邮箱帐户，可以使用该帐户。 否则，需要新建一个。 可以使用 Exchange 命令行管理程序 (PowerShell) 或 Exchange 管理控制台 创建新的资源邮箱帐户。 我们建议使用新的 (删除旧邮箱，并重新创建) Skype 会议室系统的资源邮箱。 请确保先备份邮箱数据，然后再删除，然后使用 Outlook 客户端 (将其导出回已创建的邮箱) 请参阅导出或备份邮件、日历、任务和联系人。 若要通过删除邮箱来还原丢失的会议，请参阅 [连接或还原已删除的邮箱](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
若要使用现有资源邮箱帐户 (例如 LRS-01) 请按照以下步骤操作：
  
1. 运行以下 Exchange 管理 PowerShell 命令：
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 如果计划创建新邮箱，则对单个林本地 Exchange 组织运行以下命令：
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上述示例在 Active Directory 中创建了一个已启用的用户帐户，并在本地 Exchange 组织中为会议室创建了会议室邮箱。 RoomMailboxPassword 参数指定用户帐户的密码。
    
3. 配置帐户以通过接受/拒绝会议自动解决冲突。 Exchange 中配备了 Skype 会议室系统的会议室帐户由个人管理，但请注意，在个人接受会议之前，该帐户不会显示在 Skype 会议室系统主屏幕日历上。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   有关完整的可用命令集，请参阅 Set-CalendarProcessing。
    
   若要提醒会议组织者在 Outlook 中使会议成为联机 Skype for Business 会议，请运行以下命令来设置新帐户的邮件提示： 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 使用以下命令配置本地化字符串。 如果组织要求，还可以添加自定义翻译： 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 可选：配置会议接受文本，以便为用户提供有关 Skype for Business 会议室的信息，以及他们安排和加入会议时预期的内容。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>检查 Active Directory 中的资源邮箱帐户

由 Exchange 在以上步骤 1 中创建的会议室邮箱帐户可能是 Active Directory 中已禁用的用户对象。 如果在 Active Directory 中禁用帐户，Skype 会议室系统无法使用 Kerberos/NTLM 身份验证登录或进行身份验证。 Skype 会议室系统客户端必须能够针对 Exchange Web 服务进行身份验证以检索日历设置，并且还必须能够发送包含白板内容的电子邮件。 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>为 Skype for Business 启用 Skype 会议室系统帐户

本部分概述了为会议室帐户启用 Skype for Business 所需的步骤，这将在 Skype 会议室系统上配置。 
  
为会议室创建资源邮箱帐户后，使用 Skype for Business Server 命令行管理程序 为 Skype for Business 服务启用 Skype 会议室系统帐户。
  
> [!NOTE]
> 以下过程假定你已启用 Active Directory 中的 Skype 会议室系统帐户。 
  
1. 运行以下命令以在 Skype for Business Server 池上启用 Skype 会议室系统帐户：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 可选：通过为帐户启用 PSTN 电话呼叫，允许此帐户拨打和接听企业语音。 企业语音不需要 Skype 会议室系统，但是如果未为 企业语音 启用该功能，Skype 会议室系统客户端将无法提供 PSTN 拨号功能：
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果为 Skype 会议室企业语音帐户启用语音策略，请确保配置适合你的组织的受限语音策略。 如果 Skype for Business 会议室是公开可用的资源，则任何人都可以使用它加入会议（计划或临时）。 加入会议后，该人员可以拨出到任何号码。 在 Skype for Business Server 中，从会议拨出功能使用用户的语音策略，在这种情况下，将使用 Skype 会议室系统帐户加入会议。 在早期版本的 Lync Server 中，使用组织者的语音策略。 因此，如果早期版本的 Lync Server 的用户安排了会议室并邀请 Skype 会议室系统会议室帐户，则任何人都可以使用 Skype for Business 会议室加入会议，并可以拨打任何国家/地区或国际电话号码，只要组织者允许拨打这些号码。 
