---
title: 确定在停用后如何管理属性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文介绍如何在停用本地环境后管理属性。
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458979"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="bffe6-103">确定在停用后如何管理属性</span><span class="sxs-lookup"><span data-stu-id="bffe6-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="bffe6-104">默认情况下，之前已启用 Skype for Business Server随后移动到云的所有用户仍在本地 Active Directory 中配置 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="bffe6-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="bffe6-105">这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 以及可能的电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bffe6-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="bffe6-106">如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory 中进行更改，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bffe6-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="bffe6-107">但是，Skype for Business Server部署后，Skype for Business Server工具将不能管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="bffe6-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="bffe6-108">有两个选项可用于处理这种情况：</span><span class="sxs-lookup"><span data-stu-id="bffe6-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="bffe6-109">将启用的用户保留为 Skype for Business 帐户，然后使用 Active Directory 工具管理 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="bffe6-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="bffe6-110">这可确保迁移用户不会丢失服务，并允许你通过消除 (（例如擦除) 服务器）轻松删除 Skype for Business Server 部署，而无需完全停用。</span><span class="sxs-lookup"><span data-stu-id="bffe6-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="bffe6-111">但是，新授权的用户不会在本地 Active Directory 中填充这些属性，并且需要联机管理。</span><span class="sxs-lookup"><span data-stu-id="bffe6-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="bffe6-112">清除本地 Active Directory 中迁移用户的所有 msRTCSIP 属性，然后使用联机工具管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="bffe6-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="bffe6-113">此方法允许现有用户和新用户采用一致的管理方法，但可能会导致本地停用过程中暂时丢失服务。</span><span class="sxs-lookup"><span data-stu-id="bffe6-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="bffe6-114">方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码</span><span class="sxs-lookup"><span data-stu-id="bffe6-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="bffe6-115">管理员可管理以前从本地部署Skype for Business Server移动到云的用户，即使内部部署已停用。</span><span class="sxs-lookup"><span data-stu-id="bffe6-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="bffe6-116">如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在本地 Active Directory) 中已有值，则必须在本地 Active Directory 中这样做，让值 (s) 流向 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bffe6-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="bffe6-117">这不需要本地Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="bffe6-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="bffe6-118">相反，您可以直接在本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下) 所示，或者使用 PowerShell 修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="bffe6-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="bffe6-119">如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：</span><span class="sxs-lookup"><span data-stu-id="bffe6-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="bffe6-120">若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="bffe6-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bffe6-121">如果 `ProxyAddresses` 属性包含 sip 地址，则作为最佳实践更新该值。</span><span class="sxs-lookup"><span data-stu-id="bffe6-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="bffe6-122">尽管已填充的 O365 将忽略 中的 sip 地址，但其他本地组件 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 可能会使用。</span><span class="sxs-lookup"><span data-stu-id="bffe6-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="bffe6-123">若要修改用户的电话号码，请 `msRTCSIP-Line` *修改（如果已具有值*）。</span><span class="sxs-lookup"><span data-stu-id="bffe6-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="bffe6-125">如果用户在移动之前最初没有本地值，您可以使用 `msRTCSIP-Line` Skype for Business Online PowerShell 模块中 `onpremLineUri` [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps)中的 - 参数修改电话号码。</span><span class="sxs-lookup"><span data-stu-id="bffe6-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="bffe6-126">这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="bffe6-127">如果你习惯混合使用这些方法，并习惯将 msRTCSIP 属性留在本地 Active Directory 中，则只需重新映像本地 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="bffe6-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="bffe6-128">但是，如果你希望清除所有 msRTCSIP 属性，并执行传统卸载Skype for Business Server，请使用方法 2。</span><span class="sxs-lookup"><span data-stu-id="bffe6-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="bffe6-129">方法 2 - Skype for Business Active Directory 中所有本地用户的自定义属性</span><span class="sxs-lookup"><span data-stu-id="bffe6-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="bffe6-130">此选项需要进行额外的工作并进行适当的规划，因为以前从本地Skype for Business Server移动到云的用户需要重新预配。</span><span class="sxs-lookup"><span data-stu-id="bffe6-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="bffe6-131">可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统。</span><span class="sxs-lookup"><span data-stu-id="bffe6-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="bffe6-132">在将电话系统 Active Directory 中管理到云中时，拥有此号码的用户将遇到电话服务暂时丢失的问题。</span><span class="sxs-lookup"><span data-stu-id="bffe6-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="bffe6-133">**建议在启动批量用户操作之前执行涉及少量用户电话系统试点。**</span><span class="sxs-lookup"><span data-stu-id="bffe6-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="bffe6-134">对于大型部署，可以在不同的时间窗口中以较小的组处理用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="bffe6-135">对于具有匹配的 sip 地址和 UserPrincipalName 的用户，此过程最简单。</span><span class="sxs-lookup"><span data-stu-id="bffe6-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="bffe6-136">对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。</span><span class="sxs-lookup"><span data-stu-id="bffe6-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="bffe6-137">如果为自动助理或呼叫队列配置了本地混合应用程序终结点，请确保在停用 Microsoft 365 之前，Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="bffe6-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="bffe6-138">确认以下本地 Skype for Business PowerShell cmdlet 返回空结果。</span><span class="sxs-lookup"><span data-stu-id="bffe6-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="bffe6-139">空结果意味着没有用户位于本地，并且已移动到Microsoft 365或已禁用：</span><span class="sxs-lookup"><span data-stu-id="bffe6-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="bffe6-140">通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据 (LineUri) 、UserPrincipalName 和相关信息，记录用户的当前电话号码：</span><span class="sxs-lookup"><span data-stu-id="bffe6-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="bffe6-141">在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据。</span><span class="sxs-lookup"><span data-stu-id="bffe6-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="bffe6-142">建议保留此文件的副本。</span><span class="sxs-lookup"><span data-stu-id="bffe6-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="bffe6-143">请勿在以下步骤中使用此文件处理用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="bffe6-144">创建一个包含一组用户的文件，以便执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bffe6-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="bffe6-145">成功完成第一组用户后，继续处理下一组用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="bffe6-146">在下面的示例中，用户组按字母顺序进行选择，但您可以基于与处理用户匹配的条件筛选用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="bffe6-147">在继续打开SfbUsers.csv文件并确认已成功导出用户数据之前。</span><span class="sxs-lookup"><span data-stu-id="bffe6-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="bffe6-148">在稍后的步骤中，将需要此 (的 LineUri) 、UserPrincipalName、SamAccountName 和 SipAddress。</span><span class="sxs-lookup"><span data-stu-id="bffe6-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="bffe6-149">从 active Directory 中删除Skype for Business Server准备更新的一组用户的属性信息。</span><span class="sxs-lookup"><span data-stu-id="bffe6-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="bffe6-150">此过程有 2 个步骤，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bffe6-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="bffe6-151">在运行此步骤后的下一个 AAD Sync 周期后，具有 电话系统 的用户（以前从本地 Skype for Business Server 移动到云）将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。</span><span class="sxs-lookup"><span data-stu-id="bffe6-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="bffe6-152">此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。</span><span class="sxs-lookup"><span data-stu-id="bffe6-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="bffe6-153">接下来，对于同一组用户，使用本地 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：</span><span class="sxs-lookup"><span data-stu-id="bffe6-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="bffe6-154">运行以下内部部署 Active Directory 模块Windows PowerShell cmdlet 将 sip 地址值添加回本地 Active Directory 代理Addresses。</span><span class="sxs-lookup"><span data-stu-id="bffe6-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="bffe6-155">这将防止依赖此属性的互操作性问题。</span><span class="sxs-lookup"><span data-stu-id="bffe6-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="bffe6-156">运行Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="bffe6-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="bffe6-157">等待用户预配完成。</span><span class="sxs-lookup"><span data-stu-id="bffe6-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="bffe6-158">可以通过运行以下命令来监视用户预配Skype for Business Online PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="bffe6-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="bffe6-159">以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。</span><span class="sxs-lookup"><span data-stu-id="bffe6-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="bffe6-160">执行以下 Skype for Business Online PowerShell 命令来分配电话号码并允许用户电话系统：</span><span class="sxs-lookup"><span data-stu-id="bffe6-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="bffe6-161">如果仍有Skype for Business终结点 (客户端Skype第三方) ，则还需要将 -HostedVoiceMail 设置为 $true。</span><span class="sxs-lookup"><span data-stu-id="bffe6-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="bffe6-162">如果您的组织仅对启用Teams使用语音终结点，则此设置不适用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="bffe6-163">确认具有电话系统功能的用户已正确设置。</span><span class="sxs-lookup"><span data-stu-id="bffe6-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="bffe6-164">以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。</span><span class="sxs-lookup"><span data-stu-id="bffe6-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="bffe6-165">重复步骤 3 至 9，直到处理所有用户。</span><span class="sxs-lookup"><span data-stu-id="bffe6-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="bffe6-166">通过运行以下两个 PowerShell 命令，确认所有用户都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="bffe6-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="bffe6-167">本地 Skype for Business Server PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="bffe6-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="bffe6-168">Skype for Business联机 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="bffe6-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="bffe6-169">完成方法 2 的所有步骤后，请参阅将混合[](decommission-move-on-prem-endpoints.md)应用程序终结点从本地移动到联机和删除本地[Skype for Business Server，](decommission-remove-on-prem.md)了解删除本地 Skype for Business Server 部署的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="bffe6-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="bffe6-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bffe6-170">See also</span></span>

- [<span data-ttu-id="bffe6-171">云解决方案Teams Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bffe6-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="bffe6-172">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="bffe6-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

