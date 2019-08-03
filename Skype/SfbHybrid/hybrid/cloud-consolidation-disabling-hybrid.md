---
title: 禁用混合以完成到云的迁移
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附录包括将混合禁用作为团队和 Skype for Business 的云整合的一部分的详细步骤。
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160454"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>禁用混合以完成到云的迁移

将所有用户从本地迁移到云后, 您可以停止本地 Skype for Business 部署。 除删除任何硬件之外, 关键步骤是在逻辑上将该本地部署与 Office 365 进行逻辑分离, 方法是禁用混合。 禁用混合的步骤包括三个步骤:

1. 更新 DNS 记录以指向 Office 365。
2. 在 Office 365 租户中禁用拆分域。
3. 禁用本地中与 Office 365 通信的功能。


这些步骤应作为一个单元一起完成。 下面提供了详细信息。

> [!Note] 
> 在极少数情况下, 将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作, 直到其他组织更新其联合配置:<ul><li>
任何使用旧直接联盟模型 (也称为 "允许的伙伴服务器") 的联合组织都需要更新其组织的允许的域条目, 以删除代理 FQDN。 此旧版联合模型不基于 DNS SRV 记录, 因此一旦您的组织移动到云, 这样的配置就会过期。 </li><li>没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。 只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下, 这种情况才可行。 在这种情况下, 与这些组织的联盟在启用其承载提供程序之前将不起作用。</li></ul>如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合, 我们建议您在准备完成到云的迁移时向其发送有关此的通信。

1.  *更新 DNS 以指向 Office 365。*
组织的内部部署组织的外部 DNS 需要更新, 以便 Skype for Business 记录指向 Office 365 而不是本地部署。 具体来说：

    |记录类型|名称|TTL|值|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync.com>。<span>com|
    |SRV|_sip。。|3600|100 1 443 sipdir.online.lync.com>。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir。<span>com|
    |CNAME| sip|    3600|   sipdir.online.lync.com>。<span>com|
    |CNAME| 法规|   3600|   webdir。<span>com|
    |CNAME| 入  |3600|  webdir。<span>com|

2.  *在 Office 365 租户中禁用共享 SIP 地址空间。*
下面的命令需要从 Skype for business Online PowerShell 窗口中执行。

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *禁用本地中与 Office 365 通信的功能。*  
需要从内部部署 PowerShell 窗口执行以下命令。  如果您之前已导入 Skype for business Online 会话, 请启动新的 Skype for Business PowerShell 会话。

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>另请参阅

[针对团队和 Skype for Business 的云整合](cloud-consolidation.md)