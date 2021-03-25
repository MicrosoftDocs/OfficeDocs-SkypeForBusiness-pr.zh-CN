---
title: 使用 Exchange 本地部署 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 阅读本主题，了解如何使用本地 Exchange 在混合环境中部署 Microsoft Teams 会议室。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117350"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="4aa35-103">使用 Exchange on premises 部署 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="4aa35-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="4aa35-104">阅读本主题，了解如何使用本地 Exchange 和 Microsoft Teams 或 Skype for Business Online 在混合环境中部署 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="4aa35-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="4aa35-105">如果组织混合了一些服务，其中一些托管在本地，一些联机托管，则配置将取决于每个服务的托管位置。</span><span class="sxs-lookup"><span data-stu-id="4aa35-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="4aa35-106">本主题介绍在本地托管 Exchange 的 Microsoft Teams 会议室的混合部署。</span><span class="sxs-lookup"><span data-stu-id="4aa35-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="4aa35-107">由于此类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。</span><span class="sxs-lookup"><span data-stu-id="4aa35-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="4aa35-108">以下过程适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="4aa35-108">The following process will work for many configurations.</span></span> <span data-ttu-id="4aa35-109">如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="4aa35-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="4aa35-110">Microsoft [ 提供了SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此脚本可帮助创建新用户帐户或验证现有资源帐户，以帮助将其转换为兼容的 Microsoft Teams 会议室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4aa35-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="4aa35-111">如果愿意，可以按照以下步骤配置 Microsoft Teams 会议室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="4aa35-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4aa35-112">要求</span><span class="sxs-lookup"><span data-stu-id="4aa35-112">Requirements</span></span>

<span data-ttu-id="4aa35-113">在本地部署具有 Exchange 的 Microsoft Teams 会议室之前，请确保满足要求。</span><span class="sxs-lookup"><span data-stu-id="4aa35-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="4aa35-114">有关详细信息，请参阅 [Microsoft Teams 会议室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa35-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="4aa35-115">如果要使用 Exchange 在本地部署 Microsoft Teams 会议室，你将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4aa35-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="4aa35-116">此帐户将同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4aa35-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="4aa35-117">你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4aa35-117">You will need to:</span></span>
  
- <span data-ttu-id="4aa35-118">创建一个帐户并将该帐户与 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="4aa35-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="4aa35-119">启用远程邮箱并设置属性。</span><span class="sxs-lookup"><span data-stu-id="4aa35-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="4aa35-120">分配 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="4aa35-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="4aa35-121">使用 Skype for Business Server 启用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="4aa35-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="4aa35-122">要启用设备帐户，你的环境需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="4aa35-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="4aa35-123">你需要在 Microsoft 365 或 Office 365 计划中 (Skype for Business Online) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4aa35-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="4aa35-124">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="4aa35-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="4aa35-125">如果需要使用 microsoft Teams 企业语音 (电话服务提供商) PSTN 电话服务，则需要 Skype for Business Online (计划 3) 。</span><span class="sxs-lookup"><span data-stu-id="4aa35-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="4aa35-126">使用 Microsoft Teams 或 Skype for Business Online 配置会议室帐户时，应在将帐户启用为会议室帐户之前分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="4aa35-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="4aa35-127">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4aa35-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="4aa35-128">你的 Microsoft Teams 会议室帐户需要 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，但它不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="4aa35-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="4aa35-129">将 Skype for Business Server 许可证分配给 Microsoft Teams 会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="4aa35-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="4aa35-130">创建一个帐户并与 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="4aa35-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="4aa35-131">在 **"Active Directory 用户** 和计算机"工具中，右键单击要创建 Microsoft Teams 会议室帐户的文件夹或组织单位，单击 **"新建**"，然后单击"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="4aa35-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="4aa35-p107">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4aa35-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="4aa35-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="4aa35-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4aa35-137">对于 Microsoft Teams **会议室中的** Skype for Business Server，选择"密码永不过期"是一项要求。</span><span class="sxs-lookup"><span data-stu-id="4aa35-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="4aa35-138">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="4aa35-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="4aa35-139">如果是这样，则需要为每个 Microsoft Teams 会议室设备帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="4aa35-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="4aa35-140">创建该帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="4aa35-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="4aa35-141">完成后，转到 Microsoft 365 管理中心的用户页面，验证在之前步骤中创建的帐户已合并到联机状态。</span><span class="sxs-lookup"><span data-stu-id="4aa35-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="4aa35-142">启用远程邮箱并设置属性</span><span class="sxs-lookup"><span data-stu-id="4aa35-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="4aa35-143">[打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)[，或者使用远程 PowerShell 连接到 Exchange 服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4aa35-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="4aa35-144">在 Exchange PowerShell 中，通过运行以下 (为帐户创建邮箱，) 启用该帐户：</span><span class="sxs-lookup"><span data-stu-id="4aa35-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="4aa35-145">有关详细的语法和参数信息，请参阅[Enable-Mailbox。](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="4aa35-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="4aa35-146">在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="4aa35-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4aa35-147">AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="4aa35-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4aa35-148">AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="4aa35-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4aa35-149">DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) </span><span class="sxs-lookup"><span data-stu-id="4aa35-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4aa35-150">DeleteSubject：$false (保留传入会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="4aa35-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4aa35-151">RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) </span><span class="sxs-lookup"><span data-stu-id="4aa35-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4aa35-152">AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) </span><span class="sxs-lookup"><span data-stu-id="4aa35-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4aa35-153">AdditionalResponse："这是 Skype 会议室！"</span><span class="sxs-lookup"><span data-stu-id="4aa35-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="4aa35-154"> (要添加到会议请求的其他文本。) </span><span class="sxs-lookup"><span data-stu-id="4aa35-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4aa35-155">此示例在名为 Project-Rigel-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="4aa35-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="4aa35-156">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="4aa35-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="4aa35-157">分配 Microsoft 365 或 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="4aa35-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="4aa35-158">连接到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="4aa35-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="4aa35-159">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="4aa35-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4aa35-160">[不支持 Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="4aa35-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="4aa35-161">设备帐户需要具有有效的 Microsoft 365 或 Office 365 许可证，否则 Exchange 和 Microsoft Teams 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4aa35-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="4aa35-162">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="4aa35-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4aa35-163">可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="4aa35-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="4aa35-164">以检索可用 SKUS 的列表。</span><span class="sxs-lookup"><span data-stu-id="4aa35-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="4aa35-165">接下来，可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="4aa35-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="4aa35-166">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4aa35-166">cmdlet.</span></span> <span data-ttu-id="4aa35-167">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="4aa35-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="4aa35-168">有关详细说明，请参阅 [使用 Office 365 PowerShell 向用户帐户分配许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4aa35-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="4aa35-169">启用设备帐户</span><span class="sxs-lookup"><span data-stu-id="4aa35-169">Enable the device account</span></span>

<span data-ttu-id="4aa35-170">Skype for Business Online PowerShell 用于管理 Microsoft Teams 和 Skype for Business Online 的服务。</span><span class="sxs-lookup"><span data-stu-id="4aa35-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="4aa35-171">从电脑Windows PowerShell远程会话会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4aa35-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="4aa35-172">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="4aa35-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="4aa35-173">如果你使用的是最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则不需要安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="4aa35-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="4aa35-174">获取帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="4aa35-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="4aa35-175">**可选。**</span><span class="sxs-lookup"><span data-stu-id="4aa35-175">**Optional.**</span></span> <span data-ttu-id="4aa35-176">如果要向帐户分配电话号码，此时应执行该操作。</span><span class="sxs-lookup"><span data-stu-id="4aa35-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="4aa35-177">如果要分配直接路由电话号码：</span><span class="sxs-lookup"><span data-stu-id="4aa35-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="4aa35-178">如果要分配 Microsoft 提供的电话号码，请使用以下 cmdlet，在向用户预配呼叫计划许可证后：</span><span class="sxs-lookup"><span data-stu-id="4aa35-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="4aa35-179">若要启用 Microsoft Teams 会议室帐户，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="4aa35-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="4aa35-180">如果不确定要用于环境中 RegistrarPool 参数的值，可以使用以下命令从现有用户获取该值：</span><span class="sxs-lookup"><span data-stu-id="4aa35-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="4aa35-181">向 Microsoft Teams 会议室帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="4aa35-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="4aa35-182">以租户管理员登录，打开 Microsoft 365 管理中心，并单击"管理"应用。</span><span class="sxs-lookup"><span data-stu-id="4aa35-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="4aa35-183">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="4aa35-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4aa35-184">单击 Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="4aa35-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="4aa35-185">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="4aa35-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="4aa35-186">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="4aa35-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="4aa35-187">如果要在 Microsoft Teams 会议室中企业语音计划 3 许可证。</span><span class="sxs-lookup"><span data-stu-id="4aa35-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="4aa35-188">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4aa35-188">Click **Save**.</span></span>

<span data-ttu-id="4aa35-189">若要进行验证，应该可以使用任何客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="4aa35-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4aa35-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="4aa35-190">Related topics</span></span>

[<span data-ttu-id="4aa35-191">配置 Microsoft Teams 会议室的帐户</span><span class="sxs-lookup"><span data-stu-id="4aa35-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="4aa35-192">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="4aa35-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4aa35-193">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="4aa35-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="4aa35-194">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="4aa35-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4aa35-195">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="4aa35-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)