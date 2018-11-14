---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读此主题以获取如何部署与 Office 365 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 39f443acb6a0757539ee69cd5586daed09345e05
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510658"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="4c966-103">将 Skype 会议室系统 v2 与 Office 365 一起部署 </span><span class="sxs-lookup"><span data-stu-id="4c966-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="4c966-104">阅读此主题以获取如何部署与 Office 365，其中的业务和 Exchange Skype 都联机 Skype 会议室系统 v2 的信息。</span><span class="sxs-lookup"><span data-stu-id="4c966-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span> 

<span data-ttu-id="4c966-105">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="4c966-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="4c966-106">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="4c966-107">如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="4c966-108">将 Skype 会议室系统 v2 与 Office 365 一起部署 </span><span class="sxs-lookup"><span data-stu-id="4c966-108">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="4c966-109">部署与 Office 365 的 Skype 会议室系统 v2 之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="4c966-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="4c966-110">有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c966-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="4c966-111">若要启用 for Business 的 Skype，您必须：</span><span class="sxs-lookup"><span data-stu-id="4c966-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="4c966-112">Skype 业务 online （计划 2 中或基于企业的规划） 或更高版本 Office 365 计划中。</span><span class="sxs-lookup"><span data-stu-id="4c966-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="4c966-113">计划需要允许电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="4c966-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="4c966-114">如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="4c966-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="4c966-115">如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。</span><span class="sxs-lookup"><span data-stu-id="4c966-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 

- <span data-ttu-id="4c966-116">您的租户用户必须拥有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4c966-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="4c966-117">Skype 会议室系统 v2 帐户确实需要在最小 Skype 业务 Online (计划 2) 许可证，但它不需要的 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="4c966-117">Your Skype Room Systems v2 account does require at a minumum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="4c966-118">有关详细信息，请参阅[Skype 会议室系统 v2 许可](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="4c966-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="4c966-119">Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4c966-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="4c966-120">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="4c966-120">Add a device account</span></span>

1. <span data-ttu-id="4c966-121">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="4c966-121">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="4c966-122">确保你有合适的权限集来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4c966-122">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="4c966-123">下面是可以在你的环境中使用和修改的一些 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="4c966-123">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="4c966-124">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="4c966-124">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="4c966-125">这将允许对 Skype 会议室系统 v2 进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-125">This will allow the account to authenticate to Skype Room Systems v2.</span></span>

   <span data-ttu-id="4c966-126">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="4c966-126">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  <span data-ttu-id="4c966-127">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="4c966-127">If you're creating a new resource mailbox:</span></span>

   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="4c966-p108">必须设置设备帐户的各个 Exchange 属性，以改进会议体验。你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="4c966-p108">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>

   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="4c966-130">你需要连接至 Azure Active Directory 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="4c966-130">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="4c966-131">要连接至 Azure AD，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4c966-131">To connect to Azure AD, run the following cmdlet:</span></span>

   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="4c966-132">	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c966-132">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="4c966-133">你还可以为会议室设置电话号码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c966-133">You can also set a phone number for the room as follows:</span></span>

   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="4c966-134">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4c966-134">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="4c966-135">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="4c966-135">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4c966-136">您可以使用 Get-msolaccountsku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：</span><span class="sxs-lookup"><span data-stu-id="4c966-136">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="4c966-p111">接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="4c966-p111">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="4c966-139">接下来，您需要启用 for Business 的 Skype 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-139">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="4c966-140">确保你的环境满足 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="4c966-140">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="4c966-141">启动远程 Windows PowerShell 会话，如下所示 （请务必业务 Online PowerShell 组件安装 Skype）：</span><span class="sxs-lookup"><span data-stu-id="4c966-141">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="4c966-142">接下来，您 Skype 会议室系统 v2 帐户启用 Skype 业务服务器通过运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4c966-142">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="4c966-143">本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：</span><span class="sxs-lookup"><span data-stu-id="4c966-143">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="4c966-144">不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-144">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="4c966-145">上面的命令将防止由于这种情况下的帐户设置中的错误。</span><span class="sxs-lookup"><span data-stu-id="4c966-145">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="4c966-146">您已完成上述步骤中 Skype 您 Skype 会议室系统 v2 帐户启用业务联机后，您需要将许可证分配给 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="4c966-146">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="4c966-147">使用 Office 365 管理门户，为业务 Online (计划 2) 或业务 Online (计划 3) 许可证设备 Skype 分配任一 Skype。</span><span class="sxs-lookup"><span data-stu-id="4c966-147">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="4c966-148">向你的帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="4c966-148">Assign a license to your account</span></span>

1. <span data-ttu-id="4c966-149">登录以租户管理员，打开 Office 365 管理门户，并单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c966-149">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="4c966-150">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="4c966-150">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="4c966-151">选择 Skype 会议室系统 v2 帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="4c966-151">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="4c966-152">单击“**许可证**”选项。</span><span class="sxs-lookup"><span data-stu-id="4c966-152">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="4c966-153">在**分配许可证**部分中，您需要选择 Skype 业务 Online (计划 2) 或 Skype 的业务 Online (计划 3)，具体取决于您的授权和决定方面需要企业语音。</span><span class="sxs-lookup"><span data-stu-id="4c966-153">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="4c966-154">您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 云 PBX。</span><span class="sxs-lookup"><span data-stu-id="4c966-154">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="4c966-155">至少需要 CloudPBX 才能进行语音连接。</span><span class="sxs-lookup"><span data-stu-id="4c966-155">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="4c966-156">然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="4c966-156">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="4c966-157">有关详细信息，请参阅[Skype 会议室系统 v2 许可证](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)。</span><span class="sxs-lookup"><span data-stu-id="4c966-157">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="4c966-158">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="4c966-158">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="4c966-159">示例： 会议室帐户安装在 Exchange Online 和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="4c966-159">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

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
> <span data-ttu-id="4c966-160">这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。</span><span class="sxs-lookup"><span data-stu-id="4c966-160">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="4c966-161">此外，还需要使用管理界面来指定电话号码。</span><span class="sxs-lookup"><span data-stu-id="4c966-161">Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 

## <a name="validate"></a><span data-ttu-id="4c966-162">验证</span><span class="sxs-lookup"><span data-stu-id="4c966-162">Validate</span></span>

<span data-ttu-id="4c966-163">进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="4c966-163">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>


## <a name="see-also"></a><span data-ttu-id="4c966-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c966-164">See also</span></span>

[<span data-ttu-id="4c966-165">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="4c966-165">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="4c966-166">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="4c966-166">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="4c966-167">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="4c966-167">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="4c966-168">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="4c966-168">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="4c966-169">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="4c966-169">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="4c966-170">Skype 会议室系统 v2 许可</span><span class="sxs-lookup"><span data-stu-id="4c966-170">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
