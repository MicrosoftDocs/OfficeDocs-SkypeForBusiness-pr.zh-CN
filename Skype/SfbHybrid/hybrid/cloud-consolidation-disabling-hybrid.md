---
title: 禁用混合以完成仅Teams迁移
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
description: 本文包括禁用混合功能的详细步骤，作为云解决方案和Teams Skype for Business。
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420837"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>禁用混合配置以完成仅Teams迁移 

本文介绍如何在停用本地部署环境之前禁用Skype for Business配置。 这是停止使用本地环境的以下步骤的第 2 步：

- 步骤 1. [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。

- **步骤 2.禁用混合配置。**  (本文) 

- 步骤 3. [将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。

- 步骤 4. [删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。

> [!NOTE]
> 步骤 2 和步骤 3 应在同一维护窗口中完成，因为任何现有的混合应用程序终结点在步骤 2 和步骤 3 完成之间将不可发现。

## <a name="overview"></a>概述

在将所有用户从本地Skype for Business升级到Teams仅在 Microsoft 365 中，可以停用内部部署Skype for Business部署。 在停用内部部署部署Skype for Business删除任何硬件之前，必须通过禁用混合在逻辑上将本地部署与Microsoft 365分开。 禁用混合包括以下四个步骤：

1. 将 DNS 记录更新为指向 Microsoft 365。

2. 将组织的共存模式更改为"仅Teams"。

3. 在组织 (禁用共享 sip 地址) 也称为"拆分Microsoft 365空间。

4. 在本地禁用与用户通信Microsoft 365。

这些步骤在逻辑上将本地部署的 Skype for Business Server 与 Microsoft 365，并确保你的组织完全Teams Only。 本文提供了每个步骤的详细信息。 完成后，可以使用下面引用的两种方法Skype for Business停用内部部署部署。

> [!Important] 
> 完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD 连接同步到 Azure AD。 如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。 请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！ 稍后将介绍这两种停用方法的详细信息和权衡。

## <a name="detailed-steps"></a>详细步骤

1. *更新 DNS 以指向Microsoft 365。* 需要更新内部部署组织的组织外部 DNS，以便Skype for Business记录指向Microsoft 365部署。。 具体来说：

    |记录类型|名称|TTL|优先级|粗细|端口|值|
    |---|---|---|---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync。 <span>com|
    |SRV|_sip._tls|3600|100|1|443|sipdir.online.lync。 <span>com|
    |CNAME| lyncdiscover|   3600| | | |webdir.online.lync。 <span>com|
    |CNAME| sip|    3600| | | | sipdir.online.lync。 <span>com|

    此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。 最后，应删除Skype for Business网络的任何 DNS 记录。

    > [!Note] 
    > 在极少数情况下，将组织的 DNS 从本地指向Microsoft 365可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：
    >
    > - 任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。 此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。
    > 
    > - 没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。 这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。 在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。
    >
    > 如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。

2.  *将组织的共存模式更改为"仅Teams"。* 这可确保将组织的任何新用户始终创建为仅Teams用户。 此外，尝试将租户模式更改为 Teams Only 将自动检查是否存在步骤 1 中可能遗漏的任何本地 DNS 记录，并识别输出中的这些记录。  在更新组织的所有 DNS 记录Teams仅租户模式不会成功。 若要将租户模式更改为 Teams请仅从 PowerShell 窗口Teams以下命令。

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
或者，可以使用 Teams 管理中心将租户共存模式更改为 TeamsOnly，在"组织范围的设置"->"Teams升级"下。    
    
3.  *在组织中禁用共享 sip Microsoft 365空间。* 以下命令需要从 PowerShell 窗口Teams完成。

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  *在本地禁用与用户通信Microsoft 365。* 以下命令需要在内部部署 PowerShell 窗口中完成：

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>将用户从本地迁移到云后管理属性

默认情况下，之前已启用 Skype for Business Server随后移动到云的所有用户仍在本地 Active Directory 中配置 msRTCSIP 属性。 这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 以及可能的电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。 如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory 中进行更改，然后同步到 Azure AD。 但是，Skype for Business Server部署后，Skype for Business Server工具将不能管理这些属性。

有两个选项可用于处理这种情况：

1. 将启用的用户保留为 Skype for Business 帐户，然后使用 Active Directory 工具管理 msRTCSIP 属性。 这可确保迁移用户不会丢失服务，并允许你通过消除 (（例如擦除) 服务器）轻松删除 Skype for Business Server 部署，而无需完全停用。 但是，新授权的用户不会在本地 Active Directory 中填充这些属性，并且需要联机管理。

2.  清除本地 Active Directory 中迁移用户的所有 msRTCSIP 属性，然后使用联机工具管理这些属性。 此方法允许现有用户和新用户采用一致的管理方法，但可能会导致本地停用过程中暂时丢失服务。


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码

管理员可管理以前从本地部署Skype for Business Server移动到云的用户，即使内部部署已停用。 如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在本地 Active Directory) 中已有值，则必须在本地 Active Directory 中这样做，让值 (s) 流向 Azure AD。 这不需要本地Skype for Business Server。 相反，您可以直接在本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下) 所示，或者使用 PowerShell 修改这些属性。 如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：

- 若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。

    > [!NOTE]
    > 如果 `ProxyAddresses` 属性包含 sip 地址，则作为最佳实践更新该值。 尽管已填充的 O365 将忽略 中的 sip 地址，但其他本地组件 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 可能会使用。

- 若要修改用户的电话号码，请 `msRTCSIP-Line` *修改（如果已具有值*）。

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
-  如果用户在移动之前最初没有本地值，您可以使用 `msRTCSIP-Line` Skype for Business Online PowerShell 模块中 `onpremLineUri` [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps)中的 - 参数修改电话号码。

这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。 如果你习惯混合使用这些方法，并习惯将 msRTCSIP 属性留在本地 Active Directory 中，则只需重新映像本地 Skype for Business 服务器。 但是，如果你希望清除所有 msRTCSIP 属性，并执行传统卸载Skype for Business Server，请使用方法 2。


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - Skype for Business Active Directory 中所有本地用户的属性

此选项需要进行额外的工作并进行适当的规划，因为以前从本地Skype for Business Server移动到云的用户需要重新预配。 可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统。 在将电话系统 Active Directory 中管理到云中时，拥有此号码的用户将遇到电话服务暂时丢失的问题。 **建议在启动批量用户操作之前执行涉及少量用户电话系统试点。** 对于大型部署，可以在不同的时间窗口中以较小的组处理用户。 

> [!NOTE] 
> 对于具有匹配的 sip 地址和 UserPrincipalName 的用户，此过程最简单。 对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。

> [!NOTE]
> 如果为自动助理或呼叫队列配置了本地混合应用程序终结点，请确保在停用 Microsoft 365 之前，Skype for Business Server。


1. 确认以下本地 Skype for Business PowerShell cmdlet 返回空结果。 空结果意味着没有用户位于本地，并且已移动到Microsoft 365或已禁用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据 (LineUri) 、UserPrincipalName 和相关信息，记录用户的当前电话号码：

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

4. 从 active Directory 中删除Skype for Business Server准备更新的一组用户的属性信息。  此过程有 2 个步骤，如下所示。

   > [!Important] 
   > 在运行此步骤后的下一个 AAD Sync 周期后，具有 电话系统 的用户（以前从本地 Skype for Business Server 移动到云）将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。 此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。

 
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

5. 运行以下内部部署 Active Directory 模块Windows PowerShell cmdlet 将 sip 地址值添加回本地 Active Directory 代理Addresses。 这将防止依赖此属性的互操作性问题。 

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

7. 等待用户预配完成。 可以通过运行以下命令来监视用户预配Skype for Business Online PowerShell 命令。 以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 执行以下 Skype for Business Online PowerShell 命令来分配电话号码并允许用户电话系统：
     
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
   >  如果仍有Skype for Business终结点 (客户端Skype第三方) ，则还需要将 -HostedVoiceMail 设置为 $true。 如果您的组织仅对启用Teams使用语音终结点，则此设置不适用于您的用户。 

9. 确认具有电话系统功能的用户已正确设置。 以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。

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
    Skype for Business联机 PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. 完成方法 2 的所有步骤后，请参阅将混合[](decommission-move-on-prem-endpoints.md)应用程序终结点从本地移动到联机和删除本地[Skype for Business Server，](decommission-remove-on-prem.md)了解删除本地 Skype for Business Server 部署的其他步骤。


## <a name="see-also"></a>另请参阅

- [云解决方案Teams Skype for Business](cloud-consolidation.md)

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

