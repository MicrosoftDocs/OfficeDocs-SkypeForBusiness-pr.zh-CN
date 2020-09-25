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
description: 此附录包括将混合禁用作为团队和 Skype for Business 的云整合的一部分的详细步骤。
ms.openlocfilehash: f852a3fb44408c6601be8c6bd4f07946419cea71
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269656"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>禁用混合以完成云迁移

将所有用户从本地移动到云后，可取消本地 Skype for Business 部署。 除删除任何硬件之外，关键步骤是在逻辑上将该本地部署与 Microsoft 365 或 Office 365 分开，方法是禁用混合。 禁用混合的步骤包括三个步骤：

1. 更新 DNS 记录以指向 Microsoft 365 或 Office 365。

2. 在 Microsoft 365 或 Office 365 组织中禁用拆分域。

3. 禁用内部部署中与 Microsoft 365 或 Office 365 通信的功能。

这些步骤应作为一个单元一起完成。 下面提供了详细信息。 此外，在本地部署断开连接后，将提供准则来管理迁移用户的电话号码。

完成这些步骤后，将不再使用本地 Skype for Business 服务器，并且可以重新映像这些服务器。

> [!Important] 
>应继续让 Active Directory 同步中的 msRTCSIP 属性通过 Azure AD 连接到 Azure AD。  请勿清除这些属性中的任何一个，除非由支持定向。  请勿在本地环境中运行 Disable-Get-csuser。 如果需要修改用户的 SIP 地址，请在本地 Active Directory 中执行此操作，并通过 Azure AD Connect 将此更改同步到 Azure AD，如下所述。 同样，如果需要更改电话号码，并且用户已在本地定义了用户的 LineURI，则应在本地 Active Directory 中进行修改。
>从本地迁移后清除本地 msRTCSIP 属性可能会导致用户的服务丢失！

> [!Note] 
> 在极少数情况下，将 DNS 从指向 Microsoft 365 或 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合身份验证配置：<ul><li>
任何使用旧直接联盟模型的联合组织 (也称为 "允许的伙伴服务器) " 将需要更新其组织的允许的域条目，以删除代理 FQDN。 此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。 </li><li>没有已启用 sipfed.online.lync.com> <span> 的托管提供程序的任何联合组织。com 将需要更新其配置才能启用。 只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下，这种情况才可行。 在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</li></ul>如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关此的通信。

1.  *更新 DNS 以指向 Microsoft 365 或 Office 365。*
组织的内部部署组织的外部 DNS 需要更新，以便 Skype for Business 记录指向 Microsoft 365 或 Office 365 而不是本地部署。 具体来说：

    |记录类型|名称|TTL|值|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync.com>。 <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync.com>。 <span>com|
    |CNAME| lyncdiscover|   3600|   webdir。 <span>com|
    |CNAME| sip|    3600|   sipdir.online.lync.com>。 <span>com|
    |CNAME| 法规|   3600|   webdir。 <span>com|
    |CNAME| 入  |3600|  webdir。 <span>com|

    此外，如果存在) 可以删除 (，则用于满足或拨入的 CNAME 记录。 最后，应删除内部网络中 Skype for Business 的任何 DNS 记录。

    > [!Note] 
    > 在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：
    >
    > - 任何使用旧直接联盟模型的联合组织 (也称为 "允许的伙伴服务器) " 将需要更新其组织的允许的域条目，以删除代理 FQDN。 此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。
    > 
    > - 没有已启用 sipfed.online.lync.com> <span> 的托管提供程序的任何联合组织。com 将需要更新其配置才能启用。 仅当联合组织完全在本地，且从未与任何混合或联机租户联合时，这种情况才可行。 在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。
    >
    > 如果您怀疑任何联盟伙伴可能正在使用直接联盟，或者未与任何 online 或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关这方面的通信。


2.  *在 Microsoft 365 或 Office 365 组织中禁用共享 SIP 地址空间。*
下面的命令需要从 Skype for business Online PowerShell 窗口中执行。

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *在本地中禁用与 Microsoft 365 或 Office 365 通信的功能。*  
需要从内部部署 PowerShell 窗口中执行以下命令：

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>管理从本地迁移的用户的 sip 地址和电话号码

管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。 如果要对用户的 SIP 地址或用户的线路 URI 进行更改 (并且 SIP 地址或线路 URI 已在内部部署 Active Directory) 中定义，则必须在本地 Active Directory 中执行此操作，并允许值 (s) 流到 Azure AD。 这不需要本地 Skype for Business Server。 相反，您可以使用 Active Directory 用户和计算机 MMC 管理单元或使用 PowerShell，直接在内部部署 Active Directory 中修改这些属性。 如果使用的是 MMC 管理单元，请打开用户的 "属性" 页，单击 "属性编辑器" 选项卡，然后找到要修改的相应属性：

- 若要修改用户的 SIP 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。 此外，如果该 `ProxyAddresses` 属性包含 sip 值，请更新该 sip 值以匹配的新值 `msRTCSIP-PrimaryUserAddress` 。 如果不包含 SIP 值，则可以将其保留为空。

- 若要修改用户的电话号码，请修改（ `msRTCSIP-Line` *如果它已有值*）。

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
如果用户最初没有 `LineURI` 在移动前的本地值，则可以使用 `onpremLineUri` Skype For Business Online PowerShell 模块中的 [get-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 中的-参数修改 LineURI。


## <a name="see-also"></a>另请参阅

[针对团队和 Skype for Business 的云整合](cloud-consolidation.md)
