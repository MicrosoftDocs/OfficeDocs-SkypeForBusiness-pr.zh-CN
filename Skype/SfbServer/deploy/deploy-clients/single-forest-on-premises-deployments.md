---
title: Skype 会议室系统单林本地部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: b998c0b1e139951297eca8a963536dd59dcd4b39
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 会议室系统单林本地部署
 
阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
  
本节概述了单目录林内部部署中承载的业务服务器配置 Exchange Server 和 Skype 上的 Skype 的空间系统帐户的步骤。
  
## <a name="single-forest-on-premises-deployments"></a>单林本地部署

如果已对会议文件室资源邮箱帐户，您可以使用它。 否则，您将需要创建一个新。 您可以使用 Exchange 管理外壳程序 (PowerShell) 或 Exchange 管理控制台来创建新的资源邮箱帐户。 我们建议使用新 （旧邮箱删除和重新创建） Skype 的空间系统的资源邮箱。 请确保在删除之前备份邮箱数据，然后将其导出到使用 Outlook 客户端重新创建邮箱 （请参阅导出或备份邮件、 日历、 任务和联系人的详细信息）。 要还原丢失通过删除该邮箱的会议，请参阅[连接或恢复已删除的邮箱](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)。 
  
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
    
3. 请将帐户配置为通过接受/拒绝会议来自动解决冲突。 Skype 室系统配备的会议室中 Exchange 帐户可以由个人，但请注意，个人接受会议之前它不会在 Skype 的空间系统主屏幕日历上。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   有关一组完整的可用命令，请参阅 Set-CalendarProcessing。
    
   要提醒会议组织者，使会议在线商务会议在 Outlook 中，Skype 运行以下命令以设置新帐户 MailTip: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 请使用以下命令配置本地化字符串。如果你的组织要求，你还可以添加自定义转换： 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 可选： 配置会议接受文本，为用户提供有关业务的会议室，和预期行为时他们计划和加入 Skype 的信息会议。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>在 Active Directory 中检查资源邮箱帐户

上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。 Skype 的空间系统不能登录或使用 Kerberos/NTLM 身份验证，如果在 Active Directory 中禁用了该帐户进行身份验证。 Skype 的空间系统客户端必须能够验证 Exchange Web 服务来检索日历设置，还必须能够将电子邮件发送与白板的内容。 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>启用 Skype 的空间系统的业务占 Skype

本节概述了会议房间帐户，将 Skype 的空间系统配置为启用 Skype 业务所需的步骤。 
  
创建资源邮箱的会议房间帐户后，使用业务服务器管理外壳的 Skype 业务服务让 Skype Skype 的空间系统帐户。
  
> [!NOTE]
> 下面的过程假定您已启用 Active Directory 中的 Skype 的空间系统帐户。 
  
1. 运行以下命令来启用业务服务器池 Skype 上的 Skype 的空间系统帐户：
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。 企业语音不是必需的 Skype 的空间系统，但如果企业语音为不启用它，Skype 的空间系统客户端将无法提供 PSTN 拨号功能：
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> 如果 Skype 的空间系统会议室帐户启用企业语音，请确保配置受限的语音策略适用于您的组织。 为业务会议房间 Skype 是否公开可用的资源，任何人都可以使用它加入计划或特别会议。 在加入会议之后，用户可以拨打任何号码。 在 Skype 业务服务器，从会议功能拨出使用 Skype 的空间系统帐户，参加会议的这种情况下使用语音策略的用户。 在较早版本的 Lync Server 中，使用的是组织者的语音策略。 因此，如果 Lync Server 的早期版本的用户安排会议室和邀请 Skype 的空间系统帐户，则任何人都可以使用业务会议室内的 Skype 参加会议并无法拨打任何国家/地区或国际电话号，只要组织者允许拨打这些号码。 
  

