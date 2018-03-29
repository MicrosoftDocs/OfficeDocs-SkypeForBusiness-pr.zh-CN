---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读有关如何部署使用 Office 365 的 Skype 的空间系统 v2 本主题。
ms.openlocfilehash: b05afbf973e814c5adf7b8a8490aefa0cbb04886
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="e2381-103">将 Skype 会议室系统 v2 与 Office 365 一起部署 </span><span class="sxs-lookup"><span data-stu-id="e2381-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="e2381-104">阅读有关如何部署使用 Office 365 的 Skype 的空间系统 v2 本主题。</span><span class="sxs-lookup"><span data-stu-id="e2381-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365.</span></span>
  
<span data-ttu-id="e2381-105">本主题介绍如何添加 Skype 的空间系统 v2 的设备帐户，当您拥有 Office 365 提供联机部署。</span><span class="sxs-lookup"><span data-stu-id="e2381-105">This topic describes how to add a device account for Skype Room Systems v2 when you have an Office 365 online deployment.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="e2381-106">将 Skype 会议室系统 v2 与 Office 365 一起部署 </span><span class="sxs-lookup"><span data-stu-id="e2381-106">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="e2381-107">部署与 Office 365 的 Skype 的空间系统 v2 之前，请确保已满足要求。</span><span class="sxs-lookup"><span data-stu-id="e2381-107">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="e2381-108">有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2381-108">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="e2381-109">若要启用业务的 Skype，您必须：</span><span class="sxs-lookup"><span data-stu-id="e2381-109">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="e2381-110">Skype 的在线业务 (计划 2) 或更高版本在您 Office 365 的计划。</span><span class="sxs-lookup"><span data-stu-id="e2381-110">Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="e2381-111">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="e2381-111">The plan needs to support conferencing capability.</span></span>
    
- <span data-ttu-id="e2381-112">如果您需要企业语音 （PSTN 电话服务） 对 Skype 的空间系统 v2 使用电话服务提供程序需要 Skype 业务联机 (计划 3)。</span><span class="sxs-lookup"><span data-stu-id="e2381-112">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
- <span data-ttu-id="e2381-113">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="e2381-113">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="e2381-114">Skype 的空间系统 v2 帐户需要 Skype 的在线业务 (计划 2) 或 Skype 的在线业务 (计划 3) 许可证，但它不需要 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="e2381-114">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
### <a name="add-a-device-account"></a><span data-ttu-id="e2381-115">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="e2381-115">Add a device account</span></span>

1. <span data-ttu-id="e2381-116">在计算机上启动远程 Windows PowerShell 会话，并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e2381-116">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="e2381-117">确保你有合适的权限集来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2381-117">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="e2381-118">下面是可以在你的环境中使用和修改的一些 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="e2381-118">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="e2381-119">之后建立会话，您将创建一个新邮箱和它启用为 RoomMailboxAccount，或者更改现有空间邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="e2381-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e2381-120">这将允许对 Skype 的空间系统 v2 进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="e2381-120">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="e2381-121">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="e2381-121">If you are changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  <span data-ttu-id="e2381-122">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="e2381-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e2381-p105">必须设置设备帐户的各个 Exchange 属性，以改进会议体验。你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="e2381-p105">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="e2381-125">你需要连接至 Azure Active Directory 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="e2381-125">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="e2381-126">要连接至 Azure AD，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e2381-126">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="e2381-127">	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e2381-127">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="e2381-128">你还可以为会议室设置电话号码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e2381-128">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="e2381-129">设备的帐户需要有一个有效的 Office 365 提供许可证，或交换和业务的 Skype 不起作用。</span><span class="sxs-lookup"><span data-stu-id="e2381-129">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="e2381-130">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="e2381-130">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e2381-131">可以使用 Get MsolAccountSku，如下所示为 Office 365 租户检索可用 Sku 列表：</span><span class="sxs-lookup"><span data-stu-id="e2381-131">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="e2381-p108">接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="e2381-p108">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="e2381-134">接下来，您需要启用设备的帐户与 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="e2381-134">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="e2381-135">请确保您的环境符合[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="e2381-135">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="e2381-136">启动远程 Windows PowerShell 会话，如下所示 （请务必安装 Skype 业务在线 PowerShell 组件）：</span><span class="sxs-lookup"><span data-stu-id="e2381-136">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="e2381-137">接下来，让 Skype 的空间系统 v2 帐户 Skype 业务服务器通过运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e2381-137">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="e2381-138">新的用户帐户在安装过程中，从获取 RegistrarPool 信息，如本示例所示：</span><span class="sxs-lookup"><span data-stu-id="e2381-138">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="e2381-139">不可能在组织中现有的用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e2381-139">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="e2381-140">上面的命令将会阻止这种情况由于开户中的错误。</span><span class="sxs-lookup"><span data-stu-id="e2381-140">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="e2381-141">完成上述步骤启用联机业务 Skype Skype 的空间系统 v2 帐户后，您需要向 Skype 的空间系统 v2 设备分派许可证。</span><span class="sxs-lookup"><span data-stu-id="e2381-141">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="e2381-142">使用 Office 365 管理门户，在线业务 (计划 2) 或 Skype 业务联机 (计划 3) 许可证的设备分配任一 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2381-142">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="e2381-143">向你的帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="e2381-143">Assign a license to your account</span></span>

1. <span data-ttu-id="e2381-144">登录作为租户管理员，打开 Office 365 管理门户网站，并在管理应用程序上单击。</span><span class="sxs-lookup"><span data-stu-id="e2381-144">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="e2381-145">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="e2381-145">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="e2381-146">选择 Skype 的空间系统 v2 帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="e2381-146">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="e2381-147">单击“**许可证**”选项。</span><span class="sxs-lookup"><span data-stu-id="e2381-147">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="e2381-148">在**分配许可证**部分中，您需要选择 Skype 业务联机 (计划 2) 或 Skype 业务联机 (计划 3)，具体取决于您的授权和决定方面需要企业语音。</span><span class="sxs-lookup"><span data-stu-id="e2381-148">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="e2381-149">您必须使用计划 3 许可证，如果您想要使用 Skype 的空间系统 v2 云 PBX。</span><span class="sxs-lookup"><span data-stu-id="e2381-149">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="e2381-150">至少需要 CloudPBX 才能进行语音连接。</span><span class="sxs-lookup"><span data-stu-id="e2381-150">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="e2381-151">然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e2381-151">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="e2381-152">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="e2381-152">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="e2381-153">示例： 房间帐户设置在 Exchange 联机和 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="e2381-153">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> <span data-ttu-id="e2381-p113">这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。此外，还需要使用管理界面来指定电话号码。</span><span class="sxs-lookup"><span data-stu-id="e2381-p113">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e2381-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2381-156">See also</span></span>

#### 

[<span data-ttu-id="e2381-157">Skype 的空间规划系统 v2</span><span class="sxs-lookup"><span data-stu-id="e2381-157">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e2381-158">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="e2381-158">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e2381-159">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="e2381-159">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="e2381-160">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="e2381-160">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

