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
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="5e7be-103">Skype 会议室系统单林本地部署</span><span class="sxs-lookup"><span data-stu-id="5e7be-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="5e7be-104">阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="5e7be-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="5e7be-105">本节概述了单目录林内部部署中承载的业务服务器配置 Exchange Server 和 Skype 上的 Skype 的空间系统帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="5e7be-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="5e7be-106">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="5e7be-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="5e7be-107">如果已对会议文件室资源邮箱帐户，您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="5e7be-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="5e7be-108">否则，您将需要创建一个新。</span><span class="sxs-lookup"><span data-stu-id="5e7be-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="5e7be-109">您可以使用 Exchange 管理外壳程序 (PowerShell) 或 Exchange 管理控制台来创建新的资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="5e7be-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="5e7be-110">我们建议使用新 （旧邮箱删除和重新创建） Skype 的空间系统的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e7be-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="5e7be-111">请确保在删除之前备份邮箱数据，然后将其导出到使用 Outlook 客户端重新创建邮箱 （请参阅导出或备份邮件、 日历、 任务和联系人的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="5e7be-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="5e7be-112">要还原丢失通过删除该邮箱的会议，请参阅[连接或恢复已删除的邮箱](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5e7be-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="5e7be-113">要使用现有资源邮箱帐户（例如 LRS-01），请按照下面的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="5e7be-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="5e7be-114">运行以下 Exchange 管理 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="5e7be-114">Run the following Exchange Management PowerShell command:</span></span>
    
  ```
  Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

2. <span data-ttu-id="5e7be-115">如果你计划创建新邮箱，对于单林本地 Exchange 组织，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5e7be-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
  ```
  New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

  <span data-ttu-id="5e7be-p102">上述示例在 Active Directory 中创建启用的用户帐户，并为本地 Exchange 组织中的会议室创建会议室邮箱。RoomMailboxPassword 参数指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="5e7be-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="5e7be-118">请将帐户配置为通过接受/拒绝会议来自动解决冲突。</span><span class="sxs-lookup"><span data-stu-id="5e7be-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="5e7be-119">Skype 室系统配备的会议室中 Exchange 帐户可以由个人，但请注意，个人接受会议之前它不会在 Skype 的空间系统主屏幕日历上。</span><span class="sxs-lookup"><span data-stu-id="5e7be-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="5e7be-120">有关一组完整的可用命令，请参阅 Set-CalendarProcessing。</span><span class="sxs-lookup"><span data-stu-id="5e7be-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="5e7be-121">要提醒会议组织者，使会议在线商务会议在 Outlook 中，Skype 运行以下命令以设置新帐户 MailTip:</span><span class="sxs-lookup"><span data-stu-id="5e7be-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="5e7be-p104">请使用以下命令配置本地化字符串。如果你的组织要求，你还可以添加自定义转换：</span><span class="sxs-lookup"><span data-stu-id="5e7be-p104">Use the following commands to configure localized strings. If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="5e7be-124">可选： 配置会议接受文本，为用户提供有关业务的会议室，和预期行为时他们计划和加入 Skype 的信息会议。</span><span class="sxs-lookup"><span data-stu-id="5e7be-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="5e7be-125">在 Active Directory 中检查资源邮箱帐户</span><span class="sxs-lookup"><span data-stu-id="5e7be-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="5e7be-126">上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="5e7be-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="5e7be-127">Skype 的空间系统不能登录或使用 Kerberos/NTLM 身份验证，如果在 Active Directory 中禁用了该帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e7be-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="5e7be-128">Skype 的空间系统客户端必须能够验证 Exchange Web 服务来检索日历设置，还必须能够将电子邮件发送与白板的内容。</span><span class="sxs-lookup"><span data-stu-id="5e7be-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="5e7be-129">因此，如果帐户被禁用，你必须执行以下操作来在 Active Directory 中启用此帐户：</span><span class="sxs-lookup"><span data-stu-id="5e7be-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="5e7be-130">在 Active Directory 中，运行以下命令来启用帐户登录：</span><span class="sxs-lookup"><span data-stu-id="5e7be-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="5e7be-131">运行此命令将提示你输入当前密码，并重新输入密码进行确认。</span><span class="sxs-lookup"><span data-stu-id="5e7be-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="5e7be-132">在设置密码后，请运行以下命令来启用帐户：</span><span class="sxs-lookup"><span data-stu-id="5e7be-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="5e7be-133">启用 Skype 的空间系统的业务占 Skype</span><span class="sxs-lookup"><span data-stu-id="5e7be-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="5e7be-134">本节概述了会议房间帐户，将 Skype 的空间系统配置为启用 Skype 业务所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="5e7be-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="5e7be-135">创建资源邮箱的会议房间帐户后，使用业务服务器管理外壳的 Skype 业务服务让 Skype Skype 的空间系统帐户。</span><span class="sxs-lookup"><span data-stu-id="5e7be-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e7be-136">下面的过程假定您已启用 Active Directory 中的 Skype 的空间系统帐户。</span><span class="sxs-lookup"><span data-stu-id="5e7be-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="5e7be-137">运行以下命令来启用业务服务器池 Skype 上的 Skype 的空间系统帐户：</span><span class="sxs-lookup"><span data-stu-id="5e7be-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="5e7be-138">可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="5e7be-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="5e7be-139">企业语音不是必需的 Skype 的空间系统，但如果企业语音为不启用它，Skype 的空间系统客户端将无法提供 PSTN 拨号功能：</span><span class="sxs-lookup"><span data-stu-id="5e7be-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> <span data-ttu-id="5e7be-140">如果 Skype 的空间系统会议室帐户启用企业语音，请确保配置受限的语音策略适用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="5e7be-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="5e7be-141">为业务会议房间 Skype 是否公开可用的资源，任何人都可以使用它加入计划或特别会议。</span><span class="sxs-lookup"><span data-stu-id="5e7be-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="5e7be-142">在加入会议之后，用户可以拨打任何号码。</span><span class="sxs-lookup"><span data-stu-id="5e7be-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="5e7be-143">在 Skype 业务服务器，从会议功能拨出使用 Skype 的空间系统帐户，参加会议的这种情况下使用语音策略的用户。</span><span class="sxs-lookup"><span data-stu-id="5e7be-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="5e7be-144">在较早版本的 Lync Server 中，使用的是组织者的语音策略。</span><span class="sxs-lookup"><span data-stu-id="5e7be-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="5e7be-145">因此，如果 Lync Server 的早期版本的用户安排会议室和邀请 Skype 的空间系统帐户，则任何人都可以使用业务会议室内的 Skype 参加会议并无法拨打任何国家/地区或国际电话号，只要组织者允许拨打这些号码。</span><span class="sxs-lookup"><span data-stu-id="5e7be-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

