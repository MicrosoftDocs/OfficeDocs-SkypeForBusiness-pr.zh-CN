---
title: Skype 会议室系统单林本地部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: 5fd9ab3f2a2e581f2f1675bea0f663b95cfa3eb5
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699712"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 会议室系统单林本地部署
 
阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
  
本节概述了用于设置业务服务器承载的单林在本地部署中的 Exchange Server 和 Skype 上的 Skype 会议室系统帐户的步骤。
  
## <a name="single-forest-on-premises-deployments"></a>单林本地部署

如果您已为会议房间资源邮箱帐户，您可以使用它。 否则，您需要创建一个新的成员。 您可以使用 Exchange 命令行管理程序 (PowerShell) 或 Exchange 管理控制台创建新资源邮箱帐户。 我们建议使用新 （删除旧的邮箱并重新创建） 的 Skype 会议室系统资源邮箱。 请确保备份之前删除的邮箱数据，然后将其导出到使用 Outlook 客户端重新创建邮箱 （请参阅 Export 或备份邮件、 日历、 任务和联系人的详细信息）。 要通过删除邮箱来还原丢失的会议，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
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
    
3. 请将帐户配置为通过接受/拒绝会议来自动解决冲突。 Skype 会议室系统配备的会议室中 Exchange 帐户可以管理由个人，但请注意，各接受会议之前，则不显示 Skype 会议室系统主屏幕日历。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   有关一组完整的可用命令，请参阅 Set-CalendarProcessing。
    
   提醒使会议的会议组织者在 Outlook 中，业务会议联机 Skype，请运行以下命令以设置新帐户的邮件提示： 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 请使用以下命令配置本地化字符串。 如果你的组织要求，你还可以添加自定义转换： 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 可选： 配置会议的用户提供信息的业务会议室，并安排和加入时收获 Skype 验收文本会议。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>在 Active Directory 中检查资源邮箱帐户

上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。 Skype 会议室系统无法登录，或使用 Kerberos/NTLM 身份验证，如果在 Active Directory 中禁用了帐户进行身份验证。 Skype 会议室系统客户端必须能够针对 Exchange Web 服务检索日历设置进行身份验证，并且也必须能够使用白板内容发送电子邮件。 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>启用 Skype 会议室系统的 Skype 帐户 for Business

本节概述了 for Business 的 Skype 启用您会议室帐户，将 Skype 会议室系统上配置所需的步骤。 
  
创建的会议会议室资源邮箱帐户后，使用 Skype 的业务 Server 命令行管理程序启用 Skype 会议室系统帐户的 Skype 业务服务。
  
> [!NOTE]
> 下面的过程假定您已启用 Active Directory 中的 Skype 会议室系统帐户。 
  
1. 运行以下命令以启用 Skype 业务服务器池上的 Skype 会议室系统帐户：
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。 企业语音，则不需要 Skype 会议室系统，但如果您不启用企业语音的 Skype 会议室 System 客户端不能提供 PSTN 拨号的功能：
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果您的 Skype 会议室系统会议室帐户启用企业语音，请确保配置受限制适用于您的组织的语音策略。 如果业务会议室的 Skype，可公开访问的资源的任何人都可以使用它参加会议，计划或临时。 在加入会议之后，用户可以拨打任何号码。 在业务服务器 Skype，拨出式会议功能从本例 Skype 会议室系统帐户用于加入会议中使用用户的语音的策略。 在较早版本的 Lync Server 中，使用的是组织者的语音策略。 因此，如果的早期版本的 Lync Server 用户安排会议聊天室，并邀请 Skype 会议室系统会议室帐户，则任何人都可以使用的业务会议室 Skype 加入会议并无法拨号任何国家/地区或国际电话数，只要组织者允许拨打这些号码。 
  

