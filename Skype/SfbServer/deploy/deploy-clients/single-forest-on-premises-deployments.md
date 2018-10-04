---
title: Skype 会议室系统单林本地部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: a0c3f76d94e54c616068303a08e4e4254f5f8347
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375299"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="79aa7-103">Skype 会议室系统单林本地部署</span><span class="sxs-lookup"><span data-stu-id="79aa7-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="79aa7-104">阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="79aa7-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="79aa7-105">本节概述了用于设置业务服务器承载的单林在本地部署中的 Exchange Server 和 Skype 上的 Skype 会议室系统帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="79aa7-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="79aa7-106">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="79aa7-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="79aa7-107">如果您已为会议房间资源邮箱帐户，您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="79aa7-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="79aa7-108">否则，您需要创建一个新的成员。</span><span class="sxs-lookup"><span data-stu-id="79aa7-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="79aa7-109">您可以使用 Exchange 命令行管理程序 (PowerShell) 或 Exchange 管理控制台创建新资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="79aa7-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="79aa7-110">我们建议使用新 （删除旧的邮箱并重新创建） 的 Skype 会议室系统资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="79aa7-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="79aa7-111">请确保备份之前删除的邮箱数据，然后将其导出到使用 Outlook 客户端重新创建邮箱 （请参阅 Export 或备份邮件、 日历、 任务和联系人的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="79aa7-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="79aa7-112">若要还原的会议丢失通过删除邮箱，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79aa7-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="79aa7-113">要使用现有资源邮箱帐户（例如 LRS-01），请按照下面的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="79aa7-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="79aa7-114">运行以下 Exchange 管理 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="79aa7-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="79aa7-115">如果你计划创建新邮箱，对于单林本地 Exchange 组织，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="79aa7-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="79aa7-p102">上述示例在 Active Directory 中创建启用的用户帐户，并为本地 Exchange 组织中的会议室创建会议室邮箱。RoomMailboxPassword 参数指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="79aa7-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="79aa7-118">请将帐户配置为通过接受/拒绝会议来自动解决冲突。</span><span class="sxs-lookup"><span data-stu-id="79aa7-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="79aa7-119">Skype 会议室系统配备的会议室中 Exchange 帐户可以管理由个人，但请注意，各接受会议之前，则不显示 Skype 会议室系统主屏幕日历。</span><span class="sxs-lookup"><span data-stu-id="79aa7-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="79aa7-120">有关一组完整的可用命令，请参阅 Set-CalendarProcessing。</span><span class="sxs-lookup"><span data-stu-id="79aa7-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="79aa7-121">提醒使会议的会议组织者在 Outlook 中，业务会议联机 Skype，请运行以下命令以设置新帐户的邮件提示：</span><span class="sxs-lookup"><span data-stu-id="79aa7-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="79aa7-p104">请使用以下命令配置本地化字符串。如果你的组织要求，你还可以添加自定义转换：</span><span class="sxs-lookup"><span data-stu-id="79aa7-p104">Use the following commands to configure localized strings. If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="79aa7-124">可选： 配置会议的用户提供信息的业务会议室，并安排和加入时收获 Skype 验收文本会议。</span><span class="sxs-lookup"><span data-stu-id="79aa7-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="79aa7-125">在 Active Directory 中检查资源邮箱帐户</span><span class="sxs-lookup"><span data-stu-id="79aa7-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="79aa7-126">上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="79aa7-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="79aa7-127">Skype 会议室系统无法登录，或使用 Kerberos/NTLM 身份验证，如果在 Active Directory 中禁用了帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="79aa7-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="79aa7-128">Skype 会议室系统客户端必须能够针对 Exchange Web 服务检索日历设置进行身份验证，并且也必须能够使用白板内容发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="79aa7-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="79aa7-129">因此，如果帐户被禁用，你必须执行以下操作来在 Active Directory 中启用此帐户：</span><span class="sxs-lookup"><span data-stu-id="79aa7-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="79aa7-130">在 Active Directory 中，运行以下命令来启用帐户登录：</span><span class="sxs-lookup"><span data-stu-id="79aa7-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="79aa7-131">运行此命令将提示你输入当前密码，并重新输入密码进行确认。</span><span class="sxs-lookup"><span data-stu-id="79aa7-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="79aa7-132">在设置密码后，请运行以下命令来启用帐户：</span><span class="sxs-lookup"><span data-stu-id="79aa7-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="79aa7-133">启用 Skype 会议室系统的 Skype 帐户 for Business</span><span class="sxs-lookup"><span data-stu-id="79aa7-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="79aa7-134">本节概述了 for Business 的 Skype 启用您会议室帐户，将 Skype 会议室系统上配置所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="79aa7-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="79aa7-135">创建的会议会议室资源邮箱帐户后，使用 Skype 的业务 Server 命令行管理程序启用 Skype 会议室系统帐户的 Skype 业务服务。</span><span class="sxs-lookup"><span data-stu-id="79aa7-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79aa7-136">下面的过程假定您已启用 Active Directory 中的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="79aa7-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="79aa7-137">运行以下命令以启用 Skype 业务服务器池上的 Skype 会议室系统帐户：</span><span class="sxs-lookup"><span data-stu-id="79aa7-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="79aa7-138">可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="79aa7-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="79aa7-139">企业语音，则不需要 Skype 会议室系统，但如果您不启用企业语音的 Skype 会议室 System 客户端不能提供 PSTN 拨号的功能：</span><span class="sxs-lookup"><span data-stu-id="79aa7-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="79aa7-140">如果您的 Skype 会议室系统会议室帐户启用企业语音，请确保配置受限制适用于您的组织的语音策略。</span><span class="sxs-lookup"><span data-stu-id="79aa7-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="79aa7-141">如果业务会议室的 Skype，可公开访问的资源的任何人都可以使用它参加会议，计划或临时。</span><span class="sxs-lookup"><span data-stu-id="79aa7-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="79aa7-142">在加入会议之后，用户可以拨打任何号码。</span><span class="sxs-lookup"><span data-stu-id="79aa7-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="79aa7-143">在业务服务器 Skype，拨出式会议功能从本例 Skype 会议室系统帐户用于加入会议中使用用户的语音的策略。</span><span class="sxs-lookup"><span data-stu-id="79aa7-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="79aa7-144">在较早版本的 Lync Server 中，使用的是组织者的语音策略。</span><span class="sxs-lookup"><span data-stu-id="79aa7-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="79aa7-145">因此，如果的早期版本的 Lync Server 用户安排会议聊天室，并邀请 Skype 会议室系统会议室帐户，则任何人都可以使用的业务会议室 Skype 加入会议并无法拨号任何国家/地区或国际电话数，只要组织者允许拨打这些号码。</span><span class="sxs-lookup"><span data-stu-id="79aa7-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

