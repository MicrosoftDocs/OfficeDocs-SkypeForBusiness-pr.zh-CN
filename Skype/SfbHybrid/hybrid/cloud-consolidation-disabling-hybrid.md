---
title: 禁用混合以完成云迁移
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
description: 本文包括禁用混合作为 Teams 和 Skype for Business 云整合的一部分的详细步骤。
ms.openlocfilehash: 18bda898563e10dbf964ba149f27202372fbcceb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656698"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>禁用混合配置以完成到云的迁移

本文介绍如何在停用本地 Skype for Business 环境之前禁用混合配置。 这是停止使用本地环境的以下步骤的第 2 步：

- 步骤 1. [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。

- **步骤 2.禁用混合配置。**  (本文) 

- 步骤 3. [将混合应用程序终结点从本地移动到联机](decommission-move-on-prem-endpoints.md)。

- 步骤 4. [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。


## <a name="overview"></a>概述

将所有用户从本地 Skype for Business 升级到 Microsoft 365 中的 Teams Only 后，可以停用本地 Skype for Business 部署。 在停用本地 Skype for Business 部署并删除任何硬件之前，必须通过禁用混合在逻辑上将本地部署与 Microsoft 365 分离。 禁用混合包含以下三个步骤：

1. 将 DNS 记录更新为指向 Microsoft 365。

2. 在 Microsoft 365 (禁用共享 sip 地址空间) 也称为"拆分域"。

3. 在本地禁用与 Microsoft 365 进行通信的能力。

这些步骤在逻辑上将 Skype for Business Server 本地部署与 Microsoft 365 分离，并作为一个单元一起执行。 本文提供了每个步骤的详细信息。 完成后，可以使用下面引用的两种方法之一停用本地 Skype for Business 部署。

> [!Important] 
> 完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD Connect 同步到 Azure AD。 如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。 请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！ 稍后将介绍这两种停用方法的详细信息和权衡。

## <a name="detailed-steps"></a>详细步骤

1. *更新 DNS 以指向 Microsoft 365。* 需要更新内部部署组织的组织外部 DNS，以便 Skype for Business 记录指向 Microsoft 365，而不是本地部署。 具体来说：

    |记录类型|名称|TTL|值|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync。 <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync。 <span>com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync。 <span>com|
    |CNAME| sip|    3600|   sipdir.online.lync。 <span>com|

    此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。 最后，应删除内部网络中 Skype for Business 的所有 DNS 记录。

    > [!Note] 
    > 在极少数情况下，将 DNS 从本地指向组织的 Microsoft 365 可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：
    >
    > - 任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。 此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。
    > 
    > - 没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。 这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。 在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。
    >
    > 如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。


2.  *在 Microsoft 365 组织中禁用共享 sip 地址空间。* 以下命令需要在 Skype for Business Online PowerShell 窗口中完成。

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *在本地禁用与 Microsoft 365 进行通信的能力。* 以下命令需要在内部部署 PowerShell 窗口中完成：

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>将用户从本地迁移到云后管理属性

默认情况下，之前已启用 Skype for Business Server 且随后移动到云的所有用户在本地 Active Directory 中仍配置了 msRTCSIP 属性。 这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 以及可能的电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。 如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory 中进行更改，然后同步到 Azure AD。 但是，一旦删除了 Skype for Business Server 部署，Skype for Business Server 工具将不能用于管理这些属性。

有两个选项可用于处理这种情况：

1. 保留为 Skype for Business 服务器帐户启用的用户，然后使用 Active Directory 工具管理 msRTCSIP 属性。 这可确保迁移用户不会丢失服务，并允许你通过消除 (（例如擦除) ）轻松删除 Skype for Business Server 部署，而无需完全停用。 但是，新授权的用户不会在本地 Active Directory 中填充这些属性，并且需要联机管理。

2.  清除本地 Active Directory 中迁移用户的所有 msRTCSIP 属性，然后使用联机工具管理这些属性。 此方法允许现有用户和新用户采用一致的管理方法，但可能会导致本地停用过程中暂时丢失服务。


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码

即使已取消本地部署，管理员也可以管理之前从本地 Skype for Business Server 移动到云的用户。 如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在本地 Active Directory) 中已有值，则必须在本地 Active Directory 中这样做，让值 (s) 流向 Azure AD。 这不需要本地 Skype for Business Server。 相反，您可以直接在本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下) 所示，或者使用 PowerShell 修改这些属性。 如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：

- 若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。 请注意，如果 `ProxyAddresses` 属性包含 sip 地址，作为最佳做法，还应更新该值。 尽管已填充的 O365 将忽略 中的 sip 地址，但其他本地组件 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 可能会使用。

- 若要修改用户的电话号码，请 `msRTCSIP-Line` *修改（如果已具有值*）。

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
-  如果用户在移动之前最初没有本地值，可以使用 `msRTCSIP-Line` Skype for Business Online PowerShell 模块中 `onpremLineUri` [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) 中的 - 参数修改电话号码。

这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。 如果你习惯混合使用这些方法以及将 msRTCSIP 属性留在本地 Active Directory 中，则只需重新映像本地 Skype for Business 服务器。 但是，如果你希望清除所有 msRTCSIP 属性，并传统卸载 Skype for Business Server，请使用方法 2。


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - 清除 Active Directory 中所有本地用户的 Skype for Business 属性

此选项需要进行额外的工作和正确的规划，因为需要重新预配之前从本地 Skype for Business Server 移动到云的用户。 可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统的用户。 在将电话号码从本地 Active Directory 中管理到云过程中，使用电话系统的用户将遇到电话服务暂时丢失的问题。 **建议先执行涉及少数电话系统的用户的试点，然后开始批量用户操作。** 对于大型部署，可以在不同的时间窗口中以较小的组处理用户。 

> [!NOTE] 
> 对于具有匹配的 sip 地址和 UserPrincipalName 的用户，此过程最简单。 对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。

> [!NOTE]
> 如果为自动助理或呼叫队列配置了本地混合应用程序终结点，请确保在停用 Skype for Business Server 之前，将这些终结点移动到 Microsoft 365。


1. 确认以下本地 Skype for Business PowerShell cmdlet 返回空结果。 空结果意味着没有用户位于本地，并且已移动到 Microsoft 365 或已禁用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据， (LineUri) 、UserPrincipalName 和相关信息来记录用户的当前电话号码：

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据。 建议保留此文件的副本。  请勿在以下步骤中使用此文件处理用户。 

3. 创建一个包含一组用户的文件，以便执行以下步骤。 成功完成第一组用户后，继续处理下一组用户。 在下面的示例中，用户组按字母顺序进行选择，但您可以基于与处理用户匹配的条件筛选用户。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 在继续打开SfbUsers.csv文件并确认已成功导出用户数据之前。 在稍后的步骤中，将需要此 (的 LineUri) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 从 active Directory 中删除与 Skype for Business Server 相关的属性信息，以用于准备更新的一组用户。  此过程有 2 个步骤，如下所示。

   > [!Important] 
   > 运行此步骤后的下一个 AAD 同步周期后，具有电话系统且之前从本地 Skype for Business Server 移动到云的用户将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。 此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   接下来，对于同一组用户，使用本地 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 运行以下本地 Skype for Business PowerShell cmdlet，将 sip 地址值添加回本地 Active Directory 代理Addresses。 这将防止依赖此属性的互操作性问题。 

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

6. 运行 Azure AD 同步

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 等待用户预配完成。 可以通过运行以下 Skype for Business Online PowerShell 命令来监视用户预配进度。 以下 Skype for Business Online PowerShell 命令在进程完成后将返回空结果。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 执行以下 Skype for Business Online PowerShell 命令，为用户分配电话号码并启用电话系统：
     
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
   >  如果 Skype 客户端或第三 (电话上仍有 Skype for Business) ，则还需要将 -HostedVoiceMail 设置为 $true。 如果你的组织仅对启用语音的用户使用 Teams 终结点，则此设置不适用于你的用户。 

9. 确认具有电话系统功能的用户已正确设置。 以下 Skype for Business Online PowerShell 命令在进程完成后将返回空结果。

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

    本地 Skype for Business Server 本地 PowerShell 命令：

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Skype for Business Online PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. 完成方法 2 的所有步骤后，请参阅将混合[](decommission-move-on-prem-endpoints.md)应用程序终结点从本地移动到联机和删除本地 Skype [for Business Server，](decommission-remove-on-prem.md)了解删除 Skype for Business Server 本地部署的其他步骤。


## <a name="see-also"></a>另请参阅

- [Teams 和 Skype for Business 云合并](cloud-consolidation.md)

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

