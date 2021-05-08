---
title: 在本地Microsoft Teams 会议室部署Exchange部署
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
description: 请阅读本主题，了解如何在本地Microsoft Teams 会议室混合环境中部署Exchange部署。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117350"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="f50ee-103">使用 Exchange on premises 部署 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="f50ee-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="f50ee-104">阅读本主题，了解如何在本地或 Microsoft Teams 会议室 Online Exchange混合Microsoft Teams部署Skype for Business部署。</span><span class="sxs-lookup"><span data-stu-id="f50ee-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="f50ee-105">如果组织混合了一些服务，其中一些托管在本地，一些联机托管，则配置将取决于每个服务的托管位置。</span><span class="sxs-lookup"><span data-stu-id="f50ee-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="f50ee-106">本主题介绍在本地托管的Microsoft Teams 会议室的Exchange混合部署。</span><span class="sxs-lookup"><span data-stu-id="f50ee-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="f50ee-107">由于此类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。</span><span class="sxs-lookup"><span data-stu-id="f50ee-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="f50ee-108">以下过程适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="f50ee-108">The following process will work for many configurations.</span></span> <span data-ttu-id="f50ee-109">如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="f50ee-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="f50ee-110">Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助你将其转换为兼容的Microsoft Teams 会议室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f50ee-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="f50ee-111">如果愿意，可以按照以下步骤配置设备Microsoft Teams 会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="f50ee-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f50ee-112">要求</span><span class="sxs-lookup"><span data-stu-id="f50ee-112">Requirements</span></span>

<span data-ttu-id="f50ee-113">在本地使用 Microsoft Teams 会议室部署Exchange之前，请确保满足要求。</span><span class="sxs-lookup"><span data-stu-id="f50ee-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="f50ee-114">有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f50ee-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="f50ee-115">如果要在本地使用 Microsoft Teams 会议室部署Exchange，则你将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f50ee-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="f50ee-116">此帐户将同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f50ee-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f50ee-117">你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f50ee-117">You will need to:</span></span>
  
- <span data-ttu-id="f50ee-118">创建一个帐户并将该帐户与 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="f50ee-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="f50ee-119">启用远程邮箱并设置属性。</span><span class="sxs-lookup"><span data-stu-id="f50ee-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="f50ee-120">分配Microsoft 365或Office 365许可证。</span><span class="sxs-lookup"><span data-stu-id="f50ee-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="f50ee-121">使用设备帐户启用Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="f50ee-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="f50ee-122">要启用设备帐户，你的环境需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="f50ee-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="f50ee-123">你需要在计划或Skype for Business计划 (计划 2) 或更高版本Microsoft 365 Office 365计划。</span><span class="sxs-lookup"><span data-stu-id="f50ee-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="f50ee-124">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="f50ee-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="f50ee-125">如果需要使用企业语音 (服务提供商) PSTN 电话Microsoft Teams 会议室，则需要Skype for Business Online (计划 3) 。</span><span class="sxs-lookup"><span data-stu-id="f50ee-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="f50ee-126">使用 Microsoft Teams 或 Skype for Business Online 配置会议室帐户时，应在将帐户启用为会议室帐户之前分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="f50ee-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="f50ee-127">租户用户必须具有Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="f50ee-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="f50ee-128">你的 Microsoft Teams 会议室 帐户需要 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，但它不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="f50ee-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="f50ee-129">向Skype for Business Server帐户分配Microsoft Teams 会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="f50ee-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="f50ee-130">创建一个帐户并与 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="f50ee-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="f50ee-131">在 **"Active Directory** 用户和计算机"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的文件夹或组织单位，单击"新建"，然后单击"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="f50ee-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="f50ee-p107">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f50ee-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="f50ee-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="f50ee-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f50ee-137">选择 **"密码永不过期**"是Skype for Business Server Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="f50ee-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="f50ee-138">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="f50ee-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="f50ee-139">如果是这样，则需要为每个设备帐户创建Microsoft Teams 会议室异常。</span><span class="sxs-lookup"><span data-stu-id="f50ee-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="f50ee-140">创建该帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="f50ee-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="f50ee-141">完成后，转到管理中心中的"用户"Microsoft 365，验证在之前步骤中创建的帐户已合并到联机状态。</span><span class="sxs-lookup"><span data-stu-id="f50ee-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="f50ee-142">启用远程邮箱并设置属性</span><span class="sxs-lookup"><span data-stu-id="f50ee-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="f50ee-143">[打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或者[使用远程 PowerShell Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f50ee-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="f50ee-144">在 Exchange PowerShell 中，通过运行以下 (为帐户创建邮箱，) 启用该帐户：</span><span class="sxs-lookup"><span data-stu-id="f50ee-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="f50ee-145">有关详细的语法和参数信息，请参阅[Enable-Mailbox。](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f50ee-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="f50ee-146">在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="f50ee-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="f50ee-147">AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="f50ee-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="f50ee-148">AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="f50ee-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="f50ee-149">DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) </span><span class="sxs-lookup"><span data-stu-id="f50ee-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f50ee-150">DeleteSubject：$false (保留传入会议请求的主题。) </span><span class="sxs-lookup"><span data-stu-id="f50ee-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f50ee-151">RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) </span><span class="sxs-lookup"><span data-stu-id="f50ee-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="f50ee-152">AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) </span><span class="sxs-lookup"><span data-stu-id="f50ee-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="f50ee-153">AdditionalResponse："这是一个Skype 会议房间！"</span><span class="sxs-lookup"><span data-stu-id="f50ee-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="f50ee-154"> (要添加到会议请求的其他文本。) </span><span class="sxs-lookup"><span data-stu-id="f50ee-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="f50ee-155">此示例在名为 Project-Rigel-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="f50ee-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="f50ee-156">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="f50ee-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="f50ee-157">分配Microsoft 365或Office 365许可证</span><span class="sxs-lookup"><span data-stu-id="f50ee-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="f50ee-158">连接Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="f50ee-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="f50ee-159">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="f50ee-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="f50ee-160">[Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="f50ee-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="f50ee-161">设备帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams无效。</span><span class="sxs-lookup"><span data-stu-id="f50ee-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="f50ee-162">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="f50ee-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="f50ee-163">可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="f50ee-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="f50ee-164">以检索可用 SKUS 的列表。</span><span class="sxs-lookup"><span data-stu-id="f50ee-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="f50ee-165">接下来，可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="f50ee-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="f50ee-166">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f50ee-166">cmdlet.</span></span> <span data-ttu-id="f50ee-167">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="f50ee-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="f50ee-168">有关详细说明，请参阅[使用 PowerShell 向用户帐户Office 365许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f50ee-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="f50ee-169">启用设备帐户</span><span class="sxs-lookup"><span data-stu-id="f50ee-169">Enable the device account</span></span>

<span data-ttu-id="f50ee-170">Skype for Business联机 PowerShell 用于管理服务 Microsoft Teams Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="f50ee-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="f50ee-171">从电脑Windows PowerShell远程会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f50ee-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="f50ee-172">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="f50ee-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="f50ee-173">如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="f50ee-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="f50ee-174">获取帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="f50ee-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="f50ee-175">**可选。**</span><span class="sxs-lookup"><span data-stu-id="f50ee-175">**Optional.**</span></span> <span data-ttu-id="f50ee-176">如果要向帐户分配电话号码，此时应执行该操作。</span><span class="sxs-lookup"><span data-stu-id="f50ee-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="f50ee-177">如果要分配直接路由电话号码：</span><span class="sxs-lookup"><span data-stu-id="f50ee-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="f50ee-178">如果要分配 Microsoft 提供的电话号码，请使用以下 cmdlet，在向用户预配呼叫计划许可证后：</span><span class="sxs-lookup"><span data-stu-id="f50ee-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="f50ee-179">若要启用Microsoft Teams 会议室帐户，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="f50ee-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="f50ee-180">如果不确定要用于环境中 RegistrarPool 参数的值，可以使用以下命令从现有用户获取该值：</span><span class="sxs-lookup"><span data-stu-id="f50ee-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="f50ee-181">向帐户分配Microsoft Teams 会议室许可证</span><span class="sxs-lookup"><span data-stu-id="f50ee-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="f50ee-182">以租户管理员登录，打开Microsoft 365管理中心，然后单击"管理"应用。</span><span class="sxs-lookup"><span data-stu-id="f50ee-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="f50ee-183">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="f50ee-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="f50ee-184">单击Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="f50ee-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="f50ee-185">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="f50ee-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="f50ee-186">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="f50ee-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="f50ee-187">如果要在应用程序上使用计划 3 许可证，企业语音计划Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="f50ee-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="f50ee-188">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f50ee-188">Click **Save**.</span></span>

<span data-ttu-id="f50ee-189">若要进行验证，应该可以使用任何客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="f50ee-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f50ee-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="f50ee-190">Related topics</span></span>

[<span data-ttu-id="f50ee-191">配置帐户Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="f50ee-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="f50ee-192">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="f50ee-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="f50ee-193">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="f50ee-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="f50ee-194">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="f50ee-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f50ee-195">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="f50ee-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)