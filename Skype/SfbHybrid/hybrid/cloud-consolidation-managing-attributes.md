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
description: 本文介绍如何在解除本地环境授权后管理属性。
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249014"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>决定如何在解除授权后管理属性

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


默认情况下，启用了Skype for Business Server然后迁移到云的所有用户在本地 Active Directory中仍配置了 msRTCSIP 属性。 

这些属性（尤其是 msRTCSIP-PrimaryUserAddress)  (sip 地址和电话号码 (msRTCSIP-Line) ）继续同步到Azure AD。 如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory中进行这些更改，然后同步到Azure AD。 但是，删除Skype for Business Server部署后，将无法使用Skype for Business Server工具来管理这些属性。

有两个选项可用于处理这种情况：

1. 使已为Skype for Business服务器帐户启用的用户保持Skype for Business，并使用 Active Directory 工具管理 msRTCSIP 属性。 此方法可确保迁移用户不会丢失服务，并通过消除 (（例如，擦除) 服务器，而无需完全停用）来删除Skype for Business Server部署。 但是，新许可的用户不会在本地 Active Directory中填充这些属性，需要联机管理。

2.  清除本地 Active Directory中已迁移用户的所有 msRTCSIP 属性，并使用联机工具管理这些属性。 此方法允许对现有用户和新用户采用一致的管理方法。 但是，在本地停用过程中，这可能会导致服务暂时丢失。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - 管理 Active Directory 中用户的 sip 地址和电话号码

管理员可以管理从本地Skype for Business Server迁移到云的用户，即使本地部署已解除授权。 

如果要更改用户的 sip 地址或用户的电话号码 (，并且 sip 地址或电话号码已在本地 Active Directory) 中具有值，则必须在本地 Active Directory中进行更改，并让值 () 流至Azure AD。 此方法不需要本地Skype for Business Server。 相反，可以直接在本地 Active Directory中使用 Active Directory 用户和计算机 MMC 管理单元 (（如下) 所示）或使用 PowerShell 来修改这些属性。 如果使用的是 MMC 管理单元，请打开用户的属性页，单击“属性编辑器”选项卡，并找到要修改的相应属性：

- 若要修改用户的 sip 地址，请修改 。`msRTCSIP-PrimaryUserAddress`

    > [!NOTE]
    > 如果该 `ProxyAddresses` 属性包含一个 sip 地址，则还会将该值更新为最佳做法。 虽然 O365 忽略 sip 地址（ `ProxyAddresses` 如果 `msRTCSIP-PrimaryUserAddress` 填充），但其他本地组件可能会使用它。

- 若要修改用户的电话号码，请修改`msRTCSIP-Line`*其是否已具有值*。

  ![Active Directory 用户和计算机工具。](../media/disable-hybrid-1.png)


- 如果用户在移动前最初没有本地值`msRTCSIP-Line`，则可以使用 `-PhoneNumber` Teams PowerShell 模块中的 [Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment) 中的参数修改电话号码。

禁用混合后创建的新用户不需要执行这些步骤，并且可以直接在云中管理这些用户。 如果你愿意使用这些方法的组合，并且在本地 Active Directory中保留 msRTCSIP 属性，则可以重新映像本地Skype for Business服务器。 但是，如果想要清除所有 msRTCSIP 属性并执行传统的Skype for Business Server卸载，请使用方法 2。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - 清除 Active Directory 中所有本地用户的Skype for Business属性

此选项需要更多精力和适当的规划，因为必须重新预配从本地Skype for Business Server迁移到云的用户。 这些用户可以分为两个不同的类别：没有电话系统的用户和具有电话系统的用户。 拥有电话系统的用户在将电话号码从本地 Active Directory管理过渡到云时，将暂时丢失电话服务。 **建议在开始批量用户操作之前，先执行涉及少量具有电话系统的用户的试点。** 对于大型部署，可以在不同的时间窗口中以较小的组处理用户。 

> [!NOTE] 
> 对于具有匹配的 sip 地址和 UserPrincipalName 的用户而言，此过程最简单。 对于具有在这两个属性中具有非匹配值的用户的组织，必须按照下面所述格格外小心，才能顺利过渡。

> [!NOTE]
> 如果已为自动助理或呼叫队列配置了本地混合应用程序终结点，请务必在解除Skype for Business Server之前将这些终结点移动到Microsoft 365。 有关详细信息，请参阅 [在解除本地环境授权之前迁移混合应用程序终结点](decommission-move-on-prem-endpoints.md)。  


1. 确认以下本地Skype for Business PowerShell cmdlet 返回空结果。 空结果意味着没有用户在本地驻留，并且已移动到Microsoft 365或已禁用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据，记录用户当前手机号码 (LineUri) 、UserPrincipalName 和相关信息：

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据之前。 建议保留此文件的副本。  请勿在以下步骤中使用此文件来处理用户。 

3. 创建一个文件，其中包含一组要在以下步骤中使用的用户。 第一组用户成功完成后，继续下一组用户。 在下面的示例中，按字母顺序选择用户组。 可以根据与处理用户方式匹配的条件对用户进行筛选。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUsers.csv文件并确认用户数据已成功导出之前。 稍后的步骤中，需要此文件中的 LineUri (电话号码) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 从 Active Directory 中删除与Skype for Business Server相关的属性信息，以便你已准备好更新的用户集。  此过程有两个步骤，如下所示。

   > [!Important] 
   > 运行此步骤后的下一个AAD Sync周期后，在步骤 8 成功完成并在步骤 9 中确认之前，已从本地Skype for Business Server迁移到云的电话系统用户将失去拨打和接听呼叫的能力。 此外，请确保已根据步骤 2 保存用户的电话号码和相关信息，因为该步骤需要该信息。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   接下来，对于同一组用户，使用 本地 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 若要将 sip 地址值添加回本地 Active Directory proxyAddresses，请为Windows PowerShell cmdlet 运行以下本地 Active Directory模块。 此操作将防止依赖此属性的互操作性问题。 

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

7. 等待用户预配完成。 可以通过运行以下 Teams PowerShell 命令来监视用户预配进度。 以下Teams PowerShell 命令会在进程完成后立即返回空结果。

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. 若要分配电话号码并为用户启用电话系统，请执行以下 Teams PowerShell 命令：


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
   >  如果) Skype客户端或第三方电话 (仍有Skype for Business终结点，则还需要将 -HostedVoiceMail 设置为$true。 如果组织仅对启用语音的用户使用Teams终结点，则此设置不适用于用户。 

9. 确认已正确预配具有电话系统功能的用户。 以下Teams PowerShell 命令会在进程完成后立即返回空结果。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. 重复步骤 3 到 9，直到处理所有用户。

11. 运行以下两个 PowerShell 命令，确认所有用户都已成功处理。

    本地Skype for Business Server本地 PowerShell 命令：

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. 在方法 2 中完成所有步骤后，请参阅[将混合应用程序终结点从本地移动到联机](decommission-move-on-prem-endpoints.md)，[并删除本地Skype for Business Server](decommission-remove-on-prem.md)，以获取删除本地部署Skype for Business Server的其他步骤。


## <a name="see-also"></a>另请参阅

- [适用于Teams和Skype for Business的云合并](cloud-consolidation.md)

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

