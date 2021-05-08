---
title: 使用 PowerShell Microsoft Teams协作栏创建Microsoft Teams资源帐户
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 请阅读本主题，了解如何为用户部署协作Microsoft Teams。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115600"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="4f266-103">使用 PowerShell Microsoft 365资源帐户</span><span class="sxs-lookup"><span data-stu-id="4f266-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="4f266-104">请阅读本主题，了解如何使用 PowerShell 为协作栏创建Microsoft Teams帐户。</span><span class="sxs-lookup"><span data-stu-id="4f266-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="4f266-105">创建资源帐户的最简单方法是使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="4f266-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="4f266-106">[请参阅此文章了解如何执行此操作](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="4f266-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="4f266-107">要求</span><span class="sxs-lookup"><span data-stu-id="4f266-107">Requirements</span></span>

<span data-ttu-id="4f266-108">使用 Microsoft Teams 会议室 部署Office 365，请确保满足要求。</span><span class="sxs-lookup"><span data-stu-id="4f266-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="4f266-109">有关详细信息，请参阅为用户[部署协作Microsoft Teams。](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="4f266-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="4f266-110">如果需要协作栏的 PSTN 功能，则需要电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="4f266-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="4f266-111">你的资源帐户必须具有Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="4f266-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="4f266-112">由于这些是资源帐户，Exchange许可证。</span><span class="sxs-lookup"><span data-stu-id="4f266-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="4f266-113">我们建议对资源帐户使用会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="4f266-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="4f266-114">添加资源帐户</span><span class="sxs-lookup"><span data-stu-id="4f266-114">Add a resource account</span></span>

1. <span data-ttu-id="4f266-115">连接 PowerShell Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="4f266-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="4f266-116">有关说明，请参阅 连接[Exchange Online PowerShell。](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="4f266-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="4f266-117">在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="4f266-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="4f266-118">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4f266-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4f266-119">此示例使用以下设置创建新的会议室邮箱：</span><span class="sxs-lookup"><span data-stu-id="4f266-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="4f266-120">名称：Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="4f266-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="4f266-121">别名：HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="4f266-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="4f266-122">帐户：huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4f266-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="4f266-123">帐户密码：P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="4f266-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="4f266-124">若要修改现有会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4f266-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4f266-125">此示例为别名为 HuddleRoom02 的现有会议室邮箱启用帐户，将密码808P@$$W 0rd。</span><span class="sxs-lookup"><span data-stu-id="4f266-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="4f266-126">请注意，帐户 HuddleRoom02@contoso.onmicrosoft.com 现有别名值。</span><span class="sxs-lookup"><span data-stu-id="4f266-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="4f266-127">有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="4f266-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="4f266-128">在 Exchange Online PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="4f266-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4f266-129">AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="4f266-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4f266-130">AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="4f266-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4f266-131">DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) </span><span class="sxs-lookup"><span data-stu-id="4f266-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4f266-132">DeleteSubject：$false (保留传入会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="4f266-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4f266-133">RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) </span><span class="sxs-lookup"><span data-stu-id="4f266-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4f266-134">AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) </span><span class="sxs-lookup"><span data-stu-id="4f266-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4f266-135">AdditionalResponse："此聊天室有一个协作栏用于Microsoft Teams！"</span><span class="sxs-lookup"><span data-stu-id="4f266-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="4f266-136"> (要添加到会议请求的其他文本。) </span><span class="sxs-lookup"><span data-stu-id="4f266-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4f266-137">此示例在名为 Huddle-Room-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="4f266-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="4f266-138">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="4f266-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="4f266-139">连接运行 powershell cmdlet，通过 MS Online PowerShell 创建 Active `Connect-MsolService -Credential $cred` Directory 设置。</span><span class="sxs-lookup"><span data-stu-id="4f266-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="4f266-140">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="4f266-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4f266-141">[Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="4f266-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="4f266-142">使用以下语法 huddleroom01@contoso.onmicrosoft.com 密码，使密码永不过期：</span><span class="sxs-lookup"><span data-stu-id="4f266-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="4f266-143">资源帐户需要具有有效的 Office 365 许可证，最好是 会议室 SKU。</span><span class="sxs-lookup"><span data-stu-id="4f266-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="4f266-144">还需要为设备帐户分配使用位置 ，这决定了帐户可以使用哪些许可证 SKUS。</span><span class="sxs-lookup"><span data-stu-id="4f266-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4f266-145">可以使用 检索 `Get-MsolAccountSku` 租户的可用 SKUS Office 365列表。</span><span class="sxs-lookup"><span data-stu-id="4f266-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="4f266-146">可以使用 Set-MsolUserLicense 分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4f266-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="4f266-147">有关详细说明，请参阅[使用 PowerShell 向用户帐户Office 365许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4f266-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="4f266-148">使用 PowerShell 为Microsoft Teams栏配置帐户</span><span class="sxs-lookup"><span data-stu-id="4f266-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="4f266-149">为 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f266-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="4f266-150">适用于 Microsoft Teams 许可的协作栏</span><span class="sxs-lookup"><span data-stu-id="4f266-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)