---
title: 决定如何在解除授权后管理属性
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
ms.localizationpriority: medium
description: 本文介绍如何在停用本地环境后管理属性。
ms.openlocfilehash: 2186a3e3c3c1858a9ae071932d5bf4f6d2c72c1c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592897"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>决定如何在解除授权后管理属性

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


默认情况下，所有启用了 Skype for Business Server 然后移至云的用户仍在你的 本地 Active Directory 中配置 msRTCSIP 属性。 

这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 和电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。 如果需要更改任何 msRTCSIP 属性，则必须在 本地 Active Directory 中进行更改，然后同步到Azure AD。 但是，Skype for Business Server部署后，Skype for Business Server工具将不能管理这些属性。

有两个选项可用于处理这种情况：

1. 将启用的用户保留为Skype for Business帐户，然后使用 Active Directory 工具管理 msRTCSIP 属性。 此方法可确保迁移的用户不会丢失服务，并允许你通过消除 (（例如，在服务器中擦除) ）来删除 Skype for Business Server 部署，而无需完全停用。 但是，新授权的用户不会在你的网站中填充本地 Active Directory并且需要在线管理。

2.  清除迁移用户的所有 msRTCSIP 属性本地 Active Directory联机工具管理这些属性。 此方法允许现有用户和新用户采用一致的管理方法。 但是，它可能会导致本地停用过程中暂时丢失服务。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码

管理员可以管理从本地部署移动到Skype for Business Server的用户，即使在停止使用本地部署之后。 

如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在 本地 Active Directory) 中已有值，则必须在 本地 Active Directory 中进行更改，让 () 的值流向 Azure AD。 此方法不需要本地部署Skype for Business Server。 相反，你可以直接在 本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下所示) PowerShell。 如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：

- 若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress`。

    > [!NOTE]
    > 如果属性 `ProxyAddresses` 包含 sip 地址，则作为最佳实践更新该值。 尽管已填充的 `ProxyAddresses` O365 `msRTCSIP-PrimaryUserAddress` 将忽略 中的 sip 地址，但其他本地组件可能会使用。

- 若要修改用户的电话号码， `msRTCSIP-Line`请 *修改（如果已具有值*）。

  ![Active Directory 用户和计算机工具。](../media/disable-hybrid-1.png)


- 如果用户在`msRTCSIP-Line``-PhoneNumber`移动之前最初没有本地值，您可以使用 Teams PowerShell 模块[中 Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment) 中的 参数修改电话号码。

这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。 如果你习惯混合使用这些方法，并习惯将 msRTCSIP 属性留在 本地 Active Directory 中，你可以重新映像本地 Skype for Business 服务器。 但是，如果你希望清除所有 msRTCSIP 属性，并执行传统卸载Skype for Business Server，请使用方法 2。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - Skype for Business Active Directory 中所有本地用户的自定义属性

此选项需要更多的工作量和正确的规划，因为必须从本地部署Skype for Business Server移动到云的用户必须重新预配。 可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统。 在将电话系统 本地 Active Directory托管到云中时，具有 电话系统 的用户将遇到电话服务暂时丢失的问题。 **建议在启动批量用户操作之前执行涉及少量具有 电话系统 用户的试点。** 对于大型部署，可以在不同的时间窗口中以较小的组处理用户。 

> [!NOTE] 
> 对于具有匹配的 sip 地址和 UserPrincipalName 的用户，此过程最简单。 对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。

> [!NOTE]
> 如果为自动助理或呼叫队列配置了内部部署混合应用程序终结点，请确保先将这些终结点移动到 Microsoft 365，然后再Skype for Business Server。 有关详细信息，请参阅 [在停用本地环境之前迁移混合应用程序终结点](decommission-move-on-prem-endpoints.md)。  


1. 确认以下本地Skype for Business PowerShell cmdlet 返回空结果。 空结果意味着没有用户位于本地，并且已移动到Microsoft 365或已禁用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据 (LineUri) 、UserPrincipalName 和相关信息，记录用户的当前电话号码：

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据。 建议保留此文件的副本。  请勿在以下步骤中使用此文件处理用户。 

3. 创建一个包含一组用户的文件，以便执行以下步骤。 成功完成第一组用户后，继续处理下一组用户。 在下面的示例中，按字母顺序选择用户组。 您可以根据与用户处理方法相匹配的条件来筛选用户。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUsers.csv文件并确认已成功导出用户数据之前。 在稍后的步骤中，你需要从此文件 (LineUri) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 从 active Directory Skype for Business Server准备更新的一组用户的属性信息。  此过程有两个步骤，如下所示。

   > [!Important] 
   > 运行此步骤AAD Sync下一个 AAD Sync 周期后，从本地 Skype for Business Server 移动到云的 电话系统 用户将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。 此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   接下来，对于同一组用户，使用 PowerShell 清除 msRTCSIP-DeploymentLocator 本地 Active Directory值：

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 若要将 sip 地址值添加回 本地 Active Directory proxyAddresses，请运行以下 本地 Active Directory Module for Windows PowerShell cmdlet。 此操作将防止依赖此属性的互操作性问题。 

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

6. 运行Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 等待用户预配完成。 可以通过运行以下 PowerShell 命令来监视Teams进度。 下面的 powerShell Teams在进程完成后将返回空结果。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (UserValidationErrors -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 若要分配电话号码并允许用户电话系统，请执行以下Teams PowerShell 命令：


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  如果仍有 Skype for Business 终结点 (客户端Skype第三方) ，则还需要将 -HostedVoiceMail 设置为 $true。 如果组织仅将 Teams终结点用于启用语音的用户，则此设置不适用于您的用户。 

9. 确认具有电话系统功能的用户已正确设置。 下面的 powerShell Teams在进程完成后将返回空结果。

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

10. 重复步骤 3 至 9，直到处理所有用户。

11. 通过运行以下两个 PowerShell 命令，确认所有用户都已成功处理。

    本地 Skype for Business Server PowerShell 命令：

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. 完成方法 2 的所有步骤后，请参阅将混合应用程序终结点从[](decommission-move-on-prem-endpoints.md)本地移动到联机和删除本地 [Skype for Business Server](decommission-remove-on-prem.md)，了解删除本地部署Skype for Business Server的步骤。


## <a name="see-also"></a>另请参阅

- [云解决方案Teams Skype for Business](cloud-consolidation.md)

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

