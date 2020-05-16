---
title: 为使用 PowerShell 的 Microsoft 团队创建协作栏的 Microsoft 团队资源帐户
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
description: 阅读本主题，了解有关如何为 Microsoft 团队部署协作栏的信息。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268015"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="c0621-103">使用 PowerShell 创建 Microsoft 365 资源帐户</span><span class="sxs-lookup"><span data-stu-id="c0621-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="c0621-104">阅读本主题，了解有关如何使用 PowerShell 为 Microsoft 团队创建协作栏的资源帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="c0621-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="c0621-105">创建资源帐户最简单的方法是使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="c0621-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="c0621-106">[有关如何执行此操作的详情，请参阅这篇文章](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="c0621-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="c0621-107">要求</span><span class="sxs-lookup"><span data-stu-id="c0621-107">Requirements</span></span>

<span data-ttu-id="c0621-108">在使用 Office 365 部署 Microsoft 团队聊天室之前，请确保满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="c0621-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="c0621-109">有关详细信息，请参阅[为 Microsoft 团队部署协作栏](collab-bar-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="c0621-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="c0621-110">如果你需要协作栏的 PSTN 功能，您将需要电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="c0621-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="c0621-111">您的资源帐户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c0621-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="c0621-112">由于这些资源帐户是资源帐户，因此不需要任何 Exchange 许可证。</span><span class="sxs-lookup"><span data-stu-id="c0621-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="c0621-113">我们建议为资源帐户使用会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="c0621-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="c0621-114">添加资源帐户</span><span class="sxs-lookup"><span data-stu-id="c0621-114">Add a resource account</span></span>

1. <span data-ttu-id="c0621-115">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c0621-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="c0621-116">有关说明，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="c0621-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="c0621-117">在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="c0621-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="c0621-118">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c0621-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c0621-119">此示例使用以下设置创建新的会议室邮箱：</span><span class="sxs-lookup"><span data-stu-id="c0621-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="c0621-120">名称： Huddle-01</span><span class="sxs-lookup"><span data-stu-id="c0621-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="c0621-121">别名： HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="c0621-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="c0621-122">帐户： huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c0621-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="c0621-123">帐户密码： P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="c0621-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="c0621-124">若要修改现有的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="c0621-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c0621-125">此示例启用具有 alias 值 HuddleRoom02 的现有聊天室邮箱的帐户，并将密码设置为 808P@ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="c0621-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="c0621-126">请注意，由于现有的别名值，该帐户将 HuddleRoom02@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c0621-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="c0621-127">有关详细的语法和参数信息，请参阅[新邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c0621-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="c0621-128">在 Exchange Online PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="c0621-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="c0621-129">AutomateProcessing： AutoAccept （会议组织者直接收到会议室保留决定，无需人工干预：闲 = 接受; 忙 = 拒绝。）</span><span class="sxs-lookup"><span data-stu-id="c0621-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="c0621-130">AddOrganizerToSubject： $false （会议组织者未添加到会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="c0621-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="c0621-131">DeleteComments： $false （保留收到的会议请求的邮件正文中的任何文本。）</span><span class="sxs-lookup"><span data-stu-id="c0621-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c0621-132">DeleteSubject： $false （请保留收到的会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="c0621-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c0621-133">RemovePrivateProperty： $false （确保由会议组织者在原始会议请求中发送的私人标志保持指定。）</span><span class="sxs-lookup"><span data-stu-id="c0621-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="c0621-134">AddAdditionalResponse： $true （由 AdditionalResponse 参数指定的文本将添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="c0621-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="c0621-135">AdditionalResponse： "此聊天室有一个适用于 Microsoft 团队的协作栏！"</span><span class="sxs-lookup"><span data-stu-id="c0621-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="c0621-136">（要添加到会议请求的其他文本。）</span><span class="sxs-lookup"><span data-stu-id="c0621-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="c0621-137">此示例在名为 Huddle-01 的聊天室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="c0621-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="c0621-138">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="c0621-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="c0621-139">通过运行 PowerShell cmdlet 连接到 MS Online PowerShell 以进行 Active Directory 设置 `Connect-MsolService -Credential $cred` 。</span><span class="sxs-lookup"><span data-stu-id="c0621-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="c0621-140">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="c0621-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="c0621-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。</span><span class="sxs-lookup"><span data-stu-id="c0621-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="c0621-142">使用以下语法将 huddleroom01@contoso.onmicrosoft.com 的密码设置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="c0621-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="c0621-143">资源帐户需要拥有有效的 Office 365 许可证，最好是会议室 SKU。</span><span class="sxs-lookup"><span data-stu-id="c0621-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="c0621-144">你还需要为设备帐户分配一个使用位置，这决定了你的帐户可以使用哪些许可证 Sku。</span><span class="sxs-lookup"><span data-stu-id="c0621-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="c0621-145">你可以使用 `Get-MsolAccountSku` 来检索 Office 365 租户的可用 sku 列表。</span><span class="sxs-lookup"><span data-stu-id="c0621-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="c0621-146">你可以使用 MsolUserLicense 分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c0621-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="c0621-147">有关详细说明，请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c0621-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="c0621-148">使用 PowerShell 为 Microsoft 团队配置协作栏的帐户</span><span class="sxs-lookup"><span data-stu-id="c0621-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="c0621-149">为 Microsoft 团队部署协作栏</span><span class="sxs-lookup"><span data-stu-id="c0621-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="c0621-150">Microsoft 团队许可的协作栏</span><span class="sxs-lookup"><span data-stu-id="c0621-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


