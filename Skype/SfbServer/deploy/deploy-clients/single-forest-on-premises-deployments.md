---
title: Skype 会议室系统单林本地部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: 0eae077662b050ed2accb5869f1423e0a201a0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287951"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 会议室系统单林本地部署
 
阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
  
本部分概述了在单个林本地部署中托管的 Exchange Server 和 Skype for business 服务器上预配 Skype 会议室系统帐户的步骤。
  
## <a name="single-forest-on-premises-deployments"></a>单林本地部署

如果您已有会议室的资源邮箱帐户, 则可以使用该帐户。 否则, 你将需要创建一个新的。 你可以使用 Exchange Management Shell (PowerShell) 或 Exchange 管理控制台创建新的资源邮箱帐户。 我们建议使用新的 (删除旧邮箱和重新创建) Skype 会议室系统资源邮箱。 请确保在删除之前备份邮箱数据, 然后使用 Outlook 客户端将其导出回重新创建的邮箱 (有关详细信息, 请参阅导出或备份邮件、日历、任务和联系人)。 若要还原通过删除邮箱而丢失的会议, 请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
要使用现有资源邮箱帐户（例如 LRS-01），请按照下面的步骤进行操作：
  
1. 运行以下 Exchange 管理 PowerShell 命令：
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 如果你计划创建新邮箱，对于单林本地 Exchange 组织，请运行以下命令：
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上述示例在 Active Directory 中创建启用的用户帐户，并为本地 Exchange 组织中的会议室创建会议室邮箱。RoomMailboxPassword 参数指定用户帐户的密码。
    
3. 请将帐户配置为通过接受/拒绝会议来自动解决冲突。 Skype 会议室系统-在 Exchange 中配备的会议室帐户可以由个人管理, 但请注意, 在个人接受会议之前, 它不会显示在 Skype 会议室系统主屏幕日历中。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   有关一组完整的可用命令，请参阅 Set-CalendarProcessing。
    
   若要提醒会议组织者在 Outlook 中使会议成为联机 Skype for Business 会议, 请运行以下命令以设置新帐户的邮件提醒: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 请使用以下命令配置本地化字符串。 如果你的组织要求，你还可以添加自定义转换： 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 可选: 配置会议接受文本, 向用户提供有关 Skype for Business 会议室的信息, 以及他们安排和加入会议时预期的内容。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>在 Active Directory 中检查资源邮箱帐户

上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。 如果在 Active Directory 中禁用帐户, 则 Skype 会议室系统无法使用 Kerberos/NTLM 身份验证登录或进行身份验证。 Skype 会议室系统客户端必须能够针对 Exchange Web 服务进行身份验证, 以检索日历设置, 并且还必须能够发送带白板内容的电子邮件。 
  
因此，如果帐户被禁用，你必须执行以下操作来在 Active Directory 中启用此帐户： 
  
1. 在 Active Directory 中，运行以下命令来启用帐户登录： 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   运行此命令将提示你输入当前密码，并重新输入密码进行确认。
    
2. 在设置密码后，请运行以下命令来启用帐户： 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>启用 Skype for business 的 Skype 会议室系统帐户

本部分概述了为您的会议室帐户启用 Skype for Business 所需的步骤, 这些步骤将在 Skype 会议室系统上配置。 
  
为会议会议室创建资源邮箱后, 请使用 Skype for business Server Management Shell 启用 skype for business 服务的 Skype 会议室系统帐户。
  
> [!NOTE]
> 以下过程假定你已在 Active Directory 中启用了 Skype 会议室系统帐户。 
  
1. 运行以下命令, 在 Skype for business 服务器池中启用 Skype 会议室系统帐户:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。 Skype 会议室系统不需要企业语音, 但是如果不为企业语音启用企业语音, 则 Skype 会议室系统客户端将无法提供 PSTN 拨号功能:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果为 Skype 会议室系统会议室帐户启用企业语音, 请确保配置适合你的组织的受限语音策略。 如果 Skype for Business 会议室是公共可用资源, 则任何人都可以使用它加入会议, 无论是计划的还是临时的。 在加入会议之后，用户可以拨打任何号码。 在 Skype for Business 服务器中, "通过会议拨出" 功能使用用户的语音策略, 这种情况下用于加入会议的 Skype 会议室系统帐户。 在较早版本的 Lync Server 中，使用的是组织者的语音策略。 因此, 如果早期版本的 Lync Server 的用户安排会议室并邀请 Skype 会议室系统帐户, 任何人都可以使用 Skype for Business 会议室加入会议, 并且可以拨打任何国家/地区或国际电话号码, 只要组织者被允许拨打这些号码。 
  

