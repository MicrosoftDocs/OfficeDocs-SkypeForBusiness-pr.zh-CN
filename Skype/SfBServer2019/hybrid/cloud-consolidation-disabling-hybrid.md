---
title: 禁用混合完成迁移到云中
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附录中包括用于云整合个团队和 Skype for Business 的一部分禁用混合的详细的步骤。
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247624"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>禁用混合完成迁移到云中

具有到云从本地移动所有用户后，您可以停用业务部署本地 Skype。 删除所有的硬件，除了关键步骤是逻辑分隔禁用混合从 Office 365 的内部部署。 禁用混合包含的三个步骤：

1. 更新 DNS 记录以指向 Office 365。
2. 禁用 Office 365 租户中的拆分域。
3. 禁用上 prem 中的功能与 Office 365 进行通信。


应该作为一个整体一起执行这些步骤。 下面提供了详细信息。

> [!Note] 
> 在极少数情况下，从将在本地指向 Office 365 组织更改 DNS 都可能导致联合身份验证与其他组织停止工作，直到其他组织的更新其联合身份验证配置：<ul><li>
使用旧直接联盟模式 （也称为允许的伙伴服务器） 的任何联盟的组织需要更新为其组织要删除的代理 FQDN 其允许的域条目。 此旧联盟模型不基于 DNS SRV 记录，以便您的组织将移动到云之后，这样的配置将成为过期。 </li><li>没有 sipfed.online.lync 启用宿主提供商任何联盟的组织。<span>com 将需要更新其配置，以启用的。 如果联盟的组织仅在本地并且从不具有与任何混合或 online 租户联盟，这种情况下才可能。 在这种情况下，它们使其承载服务提供商之前，将无法工作与这些组织建立联盟。</li></ul>如果您怀疑您的联盟任何的伙伴可能正在使用直接联盟或具有 online 与任何联盟或混合的组织，我们建议您将它们发送有关此通信准备完成迁移到云中。

1.  *更新 DNS 以指向 Office 365。*
需要进行更新，以便业务记录的 Skype 指向 Office 365 而不是内部部署组织的内部部署组织的外部 DNS。 特别是：

    |记录类型|名称|TTL|值|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync。<span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync。<span>com|
    |CNAME| sip|    3600|   sipdir.online.lync。<span>com|
    |CNAME| 满足|   3600|   webdir.online.lync。<span>com|
    |CNAME| dialin  |3600|  webdir.online.lync。<span>com|

2.  *禁用 Office 365 租户中的共享的 SIP 地址空间。*
下面的命令需要从业务 Online PowerShell 窗口 Skype 完成。

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *禁用上 prem 中的功能与 Office 365 进行通信。*  
下面的命令需要完成从本地 PowerShell 窗口。  如果以前业务 Online 会话导入 Skype，启动新的 Skype 业务 PowerShell 会话。

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>另请参阅

[云整合个团队和 Skype for Business](cloud-consolidation.md)