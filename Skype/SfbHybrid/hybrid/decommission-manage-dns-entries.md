---
title: 在停用本地环境时管理 DNS 条目
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关如何在停用本地部署环境时管理 DNS Skype for Business说明。
ms.openlocfilehash: a5321aa187a88505b3973c3e5418f4a88e1e6f69
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486242"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>更新 DNS 条目，使组织能够"仅Teams"

以前具有本地部署的 Skype for Business Server 或 Lync Server 的组织可能仍具有指向本地部署部署Skype for Business条目。 如果组织包括本地用户，则这些记录Skype for Business要求。 但是，一旦组织不再具有任何本地 Skype for Business 或 Lync Server 用户，本地部署不再需要这些原始记录，并且这些 DNS 条目必须更新为指向 Microsoft 365 (，或者在某些情况下，作为从本地迁移到 Teams Only 的一部分删除 **) 。** *Microsoft 无法代表你更新这些 DNS 记录。*

尝试将 TeamsOnly 授予整个租户时，Teams将检查 DNS 以确定下面列出的任何 DNS 记录是否存在于组织的每个 Microsoft 365 验证域中。 如果找到任何记录，并且它们指向 Microsoft 365，尝试将租户共存模式更改为 TeamsOnly 将按设计失败。 这样可以防止具有本地用户的混合组织错误地将 TeamsOnly 模式应用到租户，因为这样做会破坏组织中所有本地 Skype for Business 用户的联盟 (无论使用 Teams 还是 Skype for Business) 。


## <a name="how-to-identify-stale-dns-records"></a>如何识别过时的 DNS 记录

若要确定任何阻止组织成为仅Teams DNS 记录，可以使用 Teams 管理中心将共存模式更改为 TeamsOnly。 转到"**组织范围的设置Teams**  ->  **升级"。** 任何阻止组织成为Teams仅 DNS 记录都将包含在错误消息中。  如果未找到 DNS 记录，组织的共存模式将更改为 TeamsOnly。   

或者，可以使用 Teams PowerShell 执行相同的操作，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>要更新的 DNS 记录

如果您的组织不再有任何用户托管在本地 Skype for Business Server Lync Server 中，则必须执行以下操作：

- 将Skype for Business DNS 记录列表更新为指向Microsoft 365 (而不是本地部署) 。 如果您具有多个 SIP 域，则必须为已验证的每个 SIP 域Microsoft 365 SIP 域。

- 如果Skype for Business SIP 域，请删除 DNS 记录。 

在找到以下任一记录的每个域中，按如下方式更新这些记录：

| 记录类型 | 名称 | TTL | 优先级 | 粗细 | 端口 | 值 |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  不适用 |   不适用 |   不适用 |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    不适用 |   不适用  | 不适用 |    sipdir.online.lync.com |
|||||||

此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。 最后，应删除Skype for Business网络的任何 DNS 记录。

> [!Note] 
> 在极少数情况下，将组织的 DNS 从本地指向Microsoft 365可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：
>
> - 任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。 此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。
> 
> - 没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。 这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。 在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。
>
> 如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。
  




