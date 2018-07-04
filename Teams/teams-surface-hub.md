---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 配置 Microsoft 团队面中心的管理设置。
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192177"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="8d9ff-103">曲面集线器部署的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="8d9ff-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="8d9ff-104">为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="8d9ff-105">有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="8d9ff-106">设置用户帐户</span><span class="sxs-lookup"><span data-stu-id="8d9ff-106">Set up user accounts</span></span>
 
<span data-ttu-id="8d9ff-107">若要设置可用于与团队面集线器的用户帐户，创建设备帐户与 for Business 的 Skype 像支持。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="8d9ff-108">设备帐户需要具有禁用 （以允许自动登录） 的多因素身份验证 Office 365 中的团队的以下相关服务：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="8d9ff-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="8d9ff-109">Exchange</span></span> 
- <span data-ttu-id="8d9ff-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d9ff-110">SharePoint</span></span> 
- <span data-ttu-id="8d9ff-111">Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="8d9ff-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="8d9ff-112">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="8d9ff-112">Add a device account</span></span> 

<span data-ttu-id="8d9ff-113">驱动器。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-113">1\.</span></span> <span data-ttu-id="8d9ff-114">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="8d9ff-115">确保您具有正确的权限设置为运行相关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="8d9ff-116">下面是可以在你的环境中使用和修改的一些 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="8d9ff-117">2\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-117">2\.</span></span> <span data-ttu-id="8d9ff-118">建立会话后，你将创建新邮箱并将其启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="8d9ff-119">这将允许对团队进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="8d9ff-120">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="8d9ff-121">如果要新建资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="8d9ff-122">3\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-122">3\.</span></span> <span data-ttu-id="8d9ff-123">必须设置设备帐户的各个 Exchange 属性，以改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="8d9ff-124">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="8d9ff-125">4\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-125">4\.</span></span> <span data-ttu-id="8d9ff-126">你需要连接至 Azure Active Directory 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="8d9ff-127">要连接至 Azure AD，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="8d9ff-128">5\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-128">5\.</span></span> <span data-ttu-id="8d9ff-129">	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="8d9ff-130">你还可以为会议室设置电话号码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="8d9ff-131">6\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-131">6\.</span></span> <span data-ttu-id="8d9ff-132">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="8d9ff-133">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="8d9ff-134">您可以使用 Get-msolaccountsku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="8d9ff-p109">接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="8d9ff-137">7\。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-137">7\.</span></span> <span data-ttu-id="8d9ff-138">接下来，您需要为面集线器中启用团队的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="8d9ff-139">确保您的环境符合[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="8d9ff-140">启动远程 Windows PowerShell 会话，如下所示 （请务必业务 Online PowerShell 组件安装 Skype）：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="8d9ff-141">接下来，通过运行以下 cmdlet 启用您的团队面集线器帐户：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="8d9ff-142">本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="8d9ff-143">不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="8d9ff-144">上面的命令将防止由于这种情况下的帐户设置中的错误。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="8d9ff-145">您已完成上述步骤将启用您的团队面集线器帐户后，您需要将许可证分配给面集线器 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="8d9ff-146">使用 Office 365 管理门户，将团队面集线器许可证分配给设备。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="8d9ff-147">将许可证分配给该帐户</span><span class="sxs-lookup"><span data-stu-id="8d9ff-147">Assign a license to the account</span></span>

1. <span data-ttu-id="8d9ff-148">以租户管理员身份登录，打开 Office 365 管理中心中，单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="8d9ff-149">单击**用户和组**，然后单击**添加用户，重置密码和详细信息**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="8d9ff-150">选择团队面集线器帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="8d9ff-151">单击**许可证**选项。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="8d9ff-152">在**分配许可证**部分中，您需要选择计划，具体取决于您的授权。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="8d9ff-153">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="8d9ff-154">从 Microsoft 存储的表面集线器安装团队</span><span class="sxs-lookup"><span data-stu-id="8d9ff-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="8d9ff-155">这些说明包括当前安装的 Microsoft 存储中的图面集线器团队解决方法。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="8d9ff-156">启动 Windows 应用商店：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="8d9ff-157">a.</span><span class="sxs-lookup"><span data-stu-id="8d9ff-157">a.</span></span> <span data-ttu-id="8d9ff-158">点击**开始** > **所有应用程序** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="8d9ff-159">b.</span><span class="sxs-lookup"><span data-stu-id="8d9ff-159">b.</span></span> <span data-ttu-id="8d9ff-160">点击**面集线器设备帐户、 管理**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="8d9ff-161">c.</span><span class="sxs-lookup"><span data-stu-id="8d9ff-161">c.</span></span> <span data-ttu-id="8d9ff-162">在左侧，点击**应用程序和功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="8d9ff-163">d.</span><span class="sxs-lookup"><span data-stu-id="8d9ff-163">d.</span></span> <span data-ttu-id="8d9ff-164">在右侧，点击**打开存储**按钮。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="8d9ff-165">从 Microsoft 存储，搜索*的 Microsoft 团队*。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="8d9ff-166">将显示**图面集线器 （预览） 的 Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="8d9ff-167">点击**获取应用程序**按钮以安装。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="8d9ff-168">安装完成后，重新启动面集线器。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="8d9ff-169">曲面集线器重新启动后，您应该能够从**开始**菜单启动团队应用程序并从日历加入会议。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="8d9ff-170">使团队默认 VTC 应用程序</span><span class="sxs-lookup"><span data-stu-id="8d9ff-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="8d9ff-171">最多为默认 VTC 应用程序，而不是 for Business 的 Skype，均可以设置团队。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="8d9ff-172">移动设备管理 (MDM) 策略需要应用于面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="8d9ff-173">有两种配置 MDM 策略：</span><span class="sxs-lookup"><span data-stu-id="8d9ff-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="8d9ff-174">如果您已配置的策略，则将其添加通过设备管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="8d9ff-175">如果您没有配置的远程策略，我们将拖放到 usb 闪存盘上可以加载的设置的包文件。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="8d9ff-176">设备管理配置</span><span class="sxs-lookup"><span data-stu-id="8d9ff-176">Device management configuration</span></span>

<span data-ttu-id="8d9ff-177">下面是添加配置从管理中心 MDM 颁发机构 MDM 策略的示例。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="8d9ff-178">如果您位于企业网络时，您可以使用以下说明原义，包括用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="8d9ff-179">在**设备管理**部分中，点击**+**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="8d9ff-180">将打开**连接工作或学校**对话框。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="8d9ff-181">输入的策略电子邮件地址和密码提示时。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="8d9ff-182">**注意：** 在已输入您的设备管理帐户后不自动刷新 UI OS 没有 bug。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="8d9ff-183">您需要关闭并重新打开设置，以便查看列出的帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="8d9ff-184">它将执行几分钟，以便同步 MDM 策略设置。如果您想要强制进行同步，点击**MDM 帐户**按钮，，，然后点击**信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="8d9ff-185">此操作将显示信息窗口，然后点击**同步**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="8d9ff-186">若要验证已您的需要您可以检查注册表。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="8d9ff-187">您应看到**HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**下的两个键。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="8d9ff-188">**VtcAppMeetingHandlingMode** DWORD 值指示团队是默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="8d9ff-189">可识别以下值。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="8d9ff-190">数字</span><span class="sxs-lookup"><span data-stu-id="8d9ff-190">Number</span></span> | <span data-ttu-id="8d9ff-191">值</span><span class="sxs-lookup"><span data-stu-id="8d9ff-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="8d9ff-192">0</span><span class="sxs-lookup"><span data-stu-id="8d9ff-192">0</span></span>      | <span data-ttu-id="8d9ff-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="8d9ff-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="8d9ff-194">1</span><span class="sxs-lookup"><span data-stu-id="8d9ff-194">1</span></span>      | <span data-ttu-id="8d9ff-195">VtcPreferred （工作组）</span><span class="sxs-lookup"><span data-stu-id="8d9ff-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="8d9ff-196">2</span><span class="sxs-lookup"><span data-stu-id="8d9ff-196">2</span></span>      | <span data-ttu-id="8d9ff-197">VtcExclusive （仅适用于工作组）</span><span class="sxs-lookup"><span data-stu-id="8d9ff-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="8d9ff-198">**VtcCallAppPackageId**是已安装的团队包的名称。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="8d9ff-199">如果这不会显示，请确保您已安装工作组包，并重新同步。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="8d9ff-200">配置 MDM 通过 USB 键</span><span class="sxs-lookup"><span data-stu-id="8d9ff-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="8d9ff-201">此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="8d9ff-202">选择相应的包的安装，并将其复制到 usb 闪存盘您计划。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="8d9ff-203">要使用的正确.ppkg 文件取决于已安装了从存储区，团队包和您想要应用 （Skype 独占、 首选的 Skype 团队首选，团队独占） 的策略。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="8d9ff-204">将 usb 闪存盘附加到面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="8d9ff-205">打开面集线器设备上的**设置**应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="8d9ff-206">**曲面集线器设备帐户管理**打开。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="8d9ff-207">打开**设备管理**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="8d9ff-208">单击**添加或删除设置包**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="8d9ff-209">单击**添加包**。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="8d9ff-210">从下拉列表菜单中选择**可移动媒体**选项。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="8d9ff-211">添加**Allowbuildspreview.ppkg**，，然后选择您要添加的图面集线器程序包。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="8d9ff-212">重新启动面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d9ff-213">如果您的设备或组织的设备不是当前的一部分 Windows 内幕计划和中介绍的一般数据保护法规 (GDPR) 的国家/地区 （或您已手动更改为基本的遥测设置），则您必须重新检查是否具有允许完全遥测之前加入内幕计划。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="8d9ff-214">GDPR 更改在欧盟为基本设置遥测面集线器设备的默认行为。</span><span class="sxs-lookup"><span data-stu-id="8d9ff-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>