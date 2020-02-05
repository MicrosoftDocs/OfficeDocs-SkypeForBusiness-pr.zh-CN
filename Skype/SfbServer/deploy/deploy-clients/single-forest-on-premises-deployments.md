---
title: Skype 会议室系统单林本地部署
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 47cbd43709dda35d728bf8324362bec075dc74b1
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768695"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="203e0-103">Skype 会议室系统单林本地部署</span><span class="sxs-lookup"><span data-stu-id="203e0-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="203e0-104">阅读本主题，了解如何在单林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="203e0-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="203e0-105">本部分概述了在单个林本地部署中托管的 Exchange Server 和 Skype for business 服务器上预配 Skype 会议室系统帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="203e0-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="203e0-106">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="203e0-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="203e0-107">如果您已有会议室的资源邮箱帐户，则可以使用该帐户。</span><span class="sxs-lookup"><span data-stu-id="203e0-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="203e0-108">否则，你将需要创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="203e0-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="203e0-109">你可以使用 Exchange Management Shell （PowerShell）或 Exchange 管理控制台创建新的资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="203e0-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="203e0-110">我们建议使用新的（删除旧邮箱和重新创建） Skype 会议室系统资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="203e0-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="203e0-111">请确保在删除之前备份邮箱数据，然后使用 Outlook 客户端将其导出回重新创建的邮箱（有关详细信息，请参阅导出或备份邮件、日历、任务和联系人）。</span><span class="sxs-lookup"><span data-stu-id="203e0-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="203e0-112">若要还原通过删除邮箱而丢失的会议，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="203e0-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="203e0-113">要使用现有资源邮箱帐户（例如 LRS-01），请按照下面的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="203e0-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="203e0-114">运行以下 Exchange 管理 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="203e0-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="203e0-115">如果你计划创建新邮箱，对于单林本地 Exchange 组织，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="203e0-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="203e0-p102">上述示例在 Active Directory 中创建启用的用户帐户，并为本地 Exchange 组织中的会议室创建会议室邮箱。RoomMailboxPassword 参数指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="203e0-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="203e0-118">请将帐户配置为通过接受/拒绝会议来自动解决冲突。</span><span class="sxs-lookup"><span data-stu-id="203e0-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="203e0-119">Skype 会议室系统-在 Exchange 中配备的会议室帐户可以由个人管理，但请注意，在个人接受会议之前，它不会显示在 Skype 会议室系统主屏幕日历中。</span><span class="sxs-lookup"><span data-stu-id="203e0-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="203e0-120">有关一组完整的可用命令，请参阅 Set-CalendarProcessing。</span><span class="sxs-lookup"><span data-stu-id="203e0-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="203e0-121">若要提醒会议组织者在 Outlook 中使会议成为联机 Skype for Business 会议，请运行以下命令以设置新帐户的邮件提醒：</span><span class="sxs-lookup"><span data-stu-id="203e0-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="203e0-122">请使用以下命令配置本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="203e0-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="203e0-123">如果你的组织要求，你还可以添加自定义转换：</span><span class="sxs-lookup"><span data-stu-id="203e0-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="203e0-124">可选：配置会议接受文本，向用户提供有关 Skype for Business 会议室的信息，以及他们安排和加入会议时预期的内容。</span><span class="sxs-lookup"><span data-stu-id="203e0-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="203e0-125">在 Active Directory 中检查资源邮箱帐户</span><span class="sxs-lookup"><span data-stu-id="203e0-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="203e0-126">上述步骤 1 中由 Exchange 中创建的会议室邮箱帐户可能是 Active Directory 中被禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="203e0-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="203e0-127">如果在 Active Directory 中禁用帐户，则 Skype 会议室系统无法使用 Kerberos/NTLM 身份验证登录或进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="203e0-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="203e0-128">Skype 会议室系统客户端必须能够针对 Exchange Web 服务进行身份验证，以检索日历设置，并且还必须能够发送带白板内容的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="203e0-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="203e0-129">因此，如果帐户被禁用，你必须执行以下操作来在 Active Directory 中启用此帐户：</span><span class="sxs-lookup"><span data-stu-id="203e0-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="203e0-130">在 Active Directory 中，运行以下命令来启用帐户登录：</span><span class="sxs-lookup"><span data-stu-id="203e0-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="203e0-131">运行此命令将提示你输入当前密码，并重新输入密码进行确认。</span><span class="sxs-lookup"><span data-stu-id="203e0-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="203e0-132">在设置密码后，请运行以下命令来启用帐户：</span><span class="sxs-lookup"><span data-stu-id="203e0-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="203e0-133">启用 Skype for business 的 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="203e0-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="203e0-134">本部分概述了为您的会议室帐户启用 Skype for Business 所需的步骤，这些步骤将在 Skype 会议室系统上配置。</span><span class="sxs-lookup"><span data-stu-id="203e0-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="203e0-135">为会议会议室创建资源邮箱后，请使用 Skype for business Server Management Shell 启用 skype for business 服务的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="203e0-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="203e0-136">以下过程假定你已在 Active Directory 中启用了 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="203e0-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="203e0-137">运行以下命令，在 Skype for business 服务器池中启用 Skype 会议室系统帐户：</span><span class="sxs-lookup"><span data-stu-id="203e0-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="203e0-138">可选：通过为帐户启用企业语音来允许此帐户拨打和接听 PSTN 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="203e0-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="203e0-139">Skype 会议室系统不需要企业语音，但是如果不为企业语音启用企业语音，则 Skype 会议室系统客户端将无法提供 PSTN 拨号功能：</span><span class="sxs-lookup"><span data-stu-id="203e0-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="203e0-140">如果为 Skype 会议室系统会议室帐户启用企业语音，请确保配置适合你的组织的受限语音策略。</span><span class="sxs-lookup"><span data-stu-id="203e0-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="203e0-141">如果 Skype for Business 会议室是公共可用资源，则任何人都可以使用它加入会议，无论是计划的还是临时的。</span><span class="sxs-lookup"><span data-stu-id="203e0-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="203e0-142">在加入会议之后，用户可以拨打任何号码。</span><span class="sxs-lookup"><span data-stu-id="203e0-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="203e0-143">在 Skype for Business 服务器中，"通过会议拨出" 功能使用用户的语音策略，这种情况下用于加入会议的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="203e0-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="203e0-144">在较早版本的 Lync Server 中，使用的是组织者的语音策略。</span><span class="sxs-lookup"><span data-stu-id="203e0-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="203e0-145">因此，如果早期版本的 Lync Server 的用户安排会议室并邀请 Skype 会议室系统帐户，任何人都可以使用 Skype for Business 会议室加入会议，并且可以拨打任何国家/地区或国际电话号码，只要组织者被允许拨打这些号码。</span><span class="sxs-lookup"><span data-stu-id="203e0-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

