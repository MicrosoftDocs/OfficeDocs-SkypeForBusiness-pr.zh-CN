---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
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
ms.openlocfilehash: 96eb92c45af065b5f09ab9312f79198377067c4a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246155"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="c033c-103">曲面集线器部署的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="c033c-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="c033c-104">为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。</span><span class="sxs-lookup"><span data-stu-id="c033c-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="c033c-105">有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)。</span><span class="sxs-lookup"><span data-stu-id="c033c-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="c033c-106">设置用户帐户</span><span class="sxs-lookup"><span data-stu-id="c033c-106">Set up user accounts</span></span>
 
<span data-ttu-id="c033c-107">若要设置可用于与团队面集线器的用户帐户，创建设备帐户与 for Business 的 Skype 像支持。</span><span class="sxs-lookup"><span data-stu-id="c033c-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="c033c-108">设备帐户需要具有禁用 （以允许自动登录） 的多因素身份验证 Office 365 中的团队的以下相关服务：</span><span class="sxs-lookup"><span data-stu-id="c033c-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="c033c-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="c033c-109">Exchange</span></span> 
- <span data-ttu-id="c033c-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c033c-110">SharePoint</span></span> 
- <span data-ttu-id="c033c-111">Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="c033c-112">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="c033c-112">Add a device account</span></span> 

<span data-ttu-id="c033c-113">驱动器。</span><span class="sxs-lookup"><span data-stu-id="c033c-113">1\.</span></span> <span data-ttu-id="c033c-114">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="c033c-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="c033c-115">确保您具有正确的权限设置为运行相关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c033c-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="c033c-116">下面是可以在你的环境中使用和修改的一些 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="c033c-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="c033c-117">2\。</span><span class="sxs-lookup"><span data-stu-id="c033c-117">2\.</span></span> <span data-ttu-id="c033c-118">建立会话后，你将创建新邮箱并将其启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="c033c-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="c033c-119">这将允许对团队进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="c033c-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="c033c-120">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="c033c-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="c033c-121">如果要新建资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="c033c-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="c033c-122">3\。</span><span class="sxs-lookup"><span data-stu-id="c033c-122">3\.</span></span> <span data-ttu-id="c033c-123">必须设置设备帐户的各个 Exchange 属性，以改进会议体验。</span><span class="sxs-lookup"><span data-stu-id="c033c-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="c033c-124">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c033c-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="c033c-125">4\。</span><span class="sxs-lookup"><span data-stu-id="c033c-125">4\.</span></span> <span data-ttu-id="c033c-126">你需要连接至 Azure Active Directory 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="c033c-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="c033c-127">要连接至 Azure AD，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c033c-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="c033c-128">5\。</span><span class="sxs-lookup"><span data-stu-id="c033c-128">5\.</span></span> <span data-ttu-id="c033c-129">	如果不希望密码过期，请运行带 PasswordNeverExpires 选项的 Set-MsolUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c033c-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="c033c-130">你还可以为会议室设置电话号码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c033c-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="c033c-131">6\。</span><span class="sxs-lookup"><span data-stu-id="c033c-131">6\.</span></span> <span data-ttu-id="c033c-132">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="c033c-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="c033c-133">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="c033c-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="c033c-134">您可以使用 Get-msolaccountsku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：</span><span class="sxs-lookup"><span data-stu-id="c033c-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="c033c-p109">接下来，可以使用 Set-MsolUserLicense cmdlet 添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="c033c-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="c033c-137">7\。</span><span class="sxs-lookup"><span data-stu-id="c033c-137">7\.</span></span> <span data-ttu-id="c033c-138">接下来，您需要为面集线器中启用团队的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="c033c-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="c033c-139">确保您的环境符合[Microsoft Surface 中心管理指南](https://docs.microsoft.com/en-us/surface-hub/)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="c033c-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="c033c-140">启动远程 Windows PowerShell 会话，如下所示 （请务必业务 Online PowerShell 组件安装 Skype）：</span><span class="sxs-lookup"><span data-stu-id="c033c-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="c033c-141">接下来，通过运行以下 cmdlet 启用您的团队面集线器帐户：</span><span class="sxs-lookup"><span data-stu-id="c033c-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="c033c-142">本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：</span><span class="sxs-lookup"><span data-stu-id="c033c-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="c033c-143">不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c033c-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="c033c-144">上面的命令将防止由于这种情况下的帐户设置中的错误。</span><span class="sxs-lookup"><span data-stu-id="c033c-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="c033c-145">您已完成上述步骤将启用您的团队面集线器帐户后，您需要将许可证分配给面集线器 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="c033c-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="c033c-146">使用 Office 365 管理门户，将团队面集线器许可证分配给设备。</span><span class="sxs-lookup"><span data-stu-id="c033c-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="c033c-147">将许可证分配给该帐户</span><span class="sxs-lookup"><span data-stu-id="c033c-147">Assign a license to the account</span></span>

1. <span data-ttu-id="c033c-148">以租户管理员身份登录，打开 Office 365 管理中心中，单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="c033c-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="c033c-149">单击**用户和组**，然后单击**添加用户，重置密码和详细信息**。</span><span class="sxs-lookup"><span data-stu-id="c033c-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="c033c-150">选择团队面集线器帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="c033c-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="c033c-151">单击**许可证**选项。</span><span class="sxs-lookup"><span data-stu-id="c033c-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="c033c-152">在**分配许可证**部分中，您需要选择计划，具体取决于您的授权。</span><span class="sxs-lookup"><span data-stu-id="c033c-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="c033c-153">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="c033c-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="c033c-154">从 Microsoft 存储的表面集线器安装团队</span><span class="sxs-lookup"><span data-stu-id="c033c-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="c033c-155">安装 Microsoft 存储中的图面集线器团队供以下说明。</span><span class="sxs-lookup"><span data-stu-id="c033c-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="c033c-156">启动 Microsoft 存储：</span><span class="sxs-lookup"><span data-stu-id="c033c-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="c033c-157">a.</span><span class="sxs-lookup"><span data-stu-id="c033c-157">a.</span></span> <span data-ttu-id="c033c-158">点击**开始** > **所有应用程序** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="c033c-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="c033c-159">b.</span><span class="sxs-lookup"><span data-stu-id="c033c-159">b.</span></span> <span data-ttu-id="c033c-160">点击**面集线器设备帐户、 管理**。</span><span class="sxs-lookup"><span data-stu-id="c033c-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="c033c-161">c.</span><span class="sxs-lookup"><span data-stu-id="c033c-161">c.</span></span> <span data-ttu-id="c033c-162">在左侧，点击**应用程序和功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c033c-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="c033c-163">d.</span><span class="sxs-lookup"><span data-stu-id="c033c-163">d.</span></span> <span data-ttu-id="c033c-164">在右侧，点击**打开存储**按钮。</span><span class="sxs-lookup"><span data-stu-id="c033c-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="c033c-165">从 Microsoft 存储，搜索*的 Microsoft 团队*。</span><span class="sxs-lookup"><span data-stu-id="c033c-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="c033c-166">将显示**图面中心的 Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="c033c-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="c033c-167">点击**获取应用程序**按钮以安装。</span><span class="sxs-lookup"><span data-stu-id="c033c-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="c033c-168">安装完成后，重新启动面集线器。</span><span class="sxs-lookup"><span data-stu-id="c033c-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="c033c-169">不点击从商店列表页的**启动**。</span><span class="sxs-lookup"><span data-stu-id="c033c-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="c033c-170">使团队默认呼叫和会议应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="c033c-171">有两种配置的默认呼叫和会议应用程序策略：</span><span class="sxs-lookup"><span data-stu-id="c033c-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="c033c-172">**选项 1**： 配置通过 USB 键。</span><span class="sxs-lookup"><span data-stu-id="c033c-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="c033c-173">**选项 2**： 通过如 InTune MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="c033c-173">**Option 2**: Configure via MDM such as InTune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="c033c-174">选项 1： 配置通过 USB 键</span><span class="sxs-lookup"><span data-stu-id="c033c-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="c033c-175">此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。</span><span class="sxs-lookup"><span data-stu-id="c033c-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="c033c-176">选择相应的包的安装，并将其复制到 usb 闪存盘您计划。</span><span class="sxs-lookup"><span data-stu-id="c033c-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="c033c-177">要使用的正确.ppkg 文件取决于您想要应用，如下所示的默认应用程序策略：</span><span class="sxs-lookup"><span data-stu-id="c033c-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="c033c-178">数字</span><span class="sxs-lookup"><span data-stu-id="c033c-178">Number</span></span>  |<span data-ttu-id="c033c-179">说明</span><span class="sxs-lookup"><span data-stu-id="c033c-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c033c-180">0</span><span class="sxs-lookup"><span data-stu-id="c033c-180">0</span></span>     | <span data-ttu-id="c033c-181">Skype 团队会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="c033c-182">1</span><span class="sxs-lookup"><span data-stu-id="c033c-182">1</span></span>     | <span data-ttu-id="c033c-183">团队 Skype 会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="c033c-184">2</span><span class="sxs-lookup"><span data-stu-id="c033c-184">2</span></span>     | <span data-ttu-id="c033c-185">在开始屏幕 (Skype app 不可用) 团队专用应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="c033c-186">将 usb 闪存盘附加到面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="c033c-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="c033c-187">打开面集线器设备上的**设置**应用程序。</span><span class="sxs-lookup"><span data-stu-id="c033c-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="c033c-188">**曲面集线器设备帐户管理**打开。</span><span class="sxs-lookup"><span data-stu-id="c033c-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="c033c-189">打开**设备管理**。</span><span class="sxs-lookup"><span data-stu-id="c033c-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="c033c-190">单击**添加或删除设置包**。</span><span class="sxs-lookup"><span data-stu-id="c033c-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="c033c-191">单击**添加包**。</span><span class="sxs-lookup"><span data-stu-id="c033c-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="c033c-192">从下拉列表菜单中选择**可移动媒体**选项。</span><span class="sxs-lookup"><span data-stu-id="c033c-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="c033c-193">添加适当的**TeamsRTMMode\*.ppkg**包以前复制到 usb 闪存盘。</span><span class="sxs-lookup"><span data-stu-id="c033c-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="c033c-194">重新启动面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="c033c-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="c033c-195">设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。</span><span class="sxs-lookup"><span data-stu-id="c033c-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="c033c-196">选项 2： 配置通过如 InTune MDM</span><span class="sxs-lookup"><span data-stu-id="c033c-196">Option 2: Configure via MDM such as InTune</span></span> 

<span data-ttu-id="c033c-197">使用以下配置通过 InTune 的默认呼叫和会议应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="c033c-197">Use the following to configure the default calling and meetings application policy via InTune.</span></span>

|<span data-ttu-id="c033c-198">设置</span><span class="sxs-lookup"><span data-stu-id="c033c-198">Setting</span></span>   |<span data-ttu-id="c033c-199">值</span><span class="sxs-lookup"><span data-stu-id="c033c-199">Value</span></span>    |<span data-ttu-id="c033c-200">说明</span><span class="sxs-lookup"><span data-stu-id="c033c-200">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="c033c-201">路径</span><span class="sxs-lookup"><span data-stu-id="c033c-201">Path</span></span>      | <span data-ttu-id="c033c-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="c033c-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="c033c-203">数据类型</span><span class="sxs-lookup"><span data-stu-id="c033c-203">Data Type</span></span> | <span data-ttu-id="c033c-204">整数 (0-2)</span><span class="sxs-lookup"><span data-stu-id="c033c-204">integer (0-2)</span></span>   |<span data-ttu-id="c033c-205">0-团队会议可用的启动屏幕上的 Skype 首选应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-205">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="c033c-206">1-团队 Skype 会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-206">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="c033c-207">2-团队 （不可用 Skype 应用程序） 在开始屏幕上的专用应用程序</span><span class="sxs-lookup"><span data-stu-id="c033c-207">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="c033c-208">运营</span><span class="sxs-lookup"><span data-stu-id="c033c-208">Operations</span></span>| <span data-ttu-id="c033c-209">获取、 设置</span><span class="sxs-lookup"><span data-stu-id="c033c-209">Get, Set</span></span>        |

|<span data-ttu-id="c033c-210">设置</span><span class="sxs-lookup"><span data-stu-id="c033c-210">Setting</span></span>   |<span data-ttu-id="c033c-211">值</span><span class="sxs-lookup"><span data-stu-id="c033c-211">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="c033c-212">路径</span><span class="sxs-lookup"><span data-stu-id="c033c-212">Path</span></span>      | <span data-ttu-id="c033c-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="c033c-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="c033c-214">数据类型</span><span class="sxs-lookup"><span data-stu-id="c033c-214">Data Type</span></span> | <span data-ttu-id="c033c-215">字符串-团队应用程序包 ID 为**Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe 设置字符串 ！团队**</span><span class="sxs-lookup"><span data-stu-id="c033c-215">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="c033c-216">运营</span><span class="sxs-lookup"><span data-stu-id="c033c-216">Operations</span></span>| <span data-ttu-id="c033c-217">获取、 设置</span><span class="sxs-lookup"><span data-stu-id="c033c-217">Get, Set</span></span>        |

<span data-ttu-id="c033c-218">重新启动面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="c033c-218">Restart the Surface Hub device.</span></span> <span data-ttu-id="c033c-219">设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。</span><span class="sxs-lookup"><span data-stu-id="c033c-219">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

