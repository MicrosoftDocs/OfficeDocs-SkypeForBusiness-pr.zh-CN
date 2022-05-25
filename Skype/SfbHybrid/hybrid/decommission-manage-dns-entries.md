---
title: 在解除本地环境授权时管理 DNS 条目
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关在解除本地Skype for Business环境授权时如何管理 DNS 条目的说明。
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671878"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>更新 DNS 条目，使组织仅Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

以前在本地部署 Skype for Business Server 或 Lync Server 的组织可能仍具有指向本地Skype for Business部署的 DNS 条目。 如果组织包含本地Skype for Business用户，则需要这些记录。 但是，一旦你的组织不再拥有任何本地Skype for Business或 Lync Server 用户，本地部署就不再需要这些原始记录，并且 **这些 DNS 条目必须更新为指向Microsoft 365 (，或者在某些情况下**，在从本地迁移到仅Teams时删除) 。 *Microsoft 无法代表你更新这些 DNS 记录。*

尝试向整个租户授予 TeamsOnly 时，Teams将检查 DNS 以确定下面列出的这些 DNS 记录中是否有任何存在于组织中每个Microsoft 365已验证域中。 如果找到任何记录，并且它们指向Microsoft 365以外的其他记录，则尝试将租户共存模式更改为 TeamsOnly 将按设计失败。 这可防止具有本地用户的混合组织错误地将 TeamsOnly 模式应用到租户，因为这样做会破坏组织中所有本地Skype for Business用户的联合身份验证， (是使用Teams还是Skype for Business) 。

## <a name="how-to-identify-stale-dns-records"></a>如何识别过时的 DNS 记录

若要识别阻止组织成为所有仅Teams的任何 DNS 记录，可以使用Teams管理中心将共存模式更改为 TeamsOnly。 转到 **Teams** >  **Teams升级设置**。 任何阻止组织成为Teams的 DNS 记录都将包含在错误消息中。  如果未找到 DNS 记录，则组织的共存模式将更改为 TeamsOnly。

或者，可以使用 Teams PowerShell 执行相同的操作，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>要更新的 DNS 记录

如果组织不再在本地Skype for Business Server或 Lync Server 中托管任何用户，则必须执行以下操作：

- 将下面的Skype for Business DNS 记录列表更新为指向Microsoft 365 (，而不是本地部署) 。 如果有多个 SIP 域，则必须针对Microsoft 365已验证域的每个 SIP 域执行此操作。

- 如果不再使用 SIP 域，请删除Skype for Business DNS 记录。

在找到以下任何记录的每个域中，按如下所示更新这些记录：

|记录类型|名称|TTL|优先级|粗细|端口|值|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|不适用|不适用|不适用|webdir.online.lync.com|
|CNAME|sip|3600|不适用|不适用|不适用|sipdir.online.lync.com|

此外，如果存在，可以删除会议或对话 (的 CNAME 记录) 。 最后，应删除内部网络中Skype for Business的任何 DNS 记录。

> [!NOTE]
> 在极少数情况下，将 DNS 从本地指向组织Microsoft 365可能会导致与其他一些组织联合身份验证停止工作，直到其他组织更新其联合身份验证配置：
>
> - 使用较旧的直接联合身份验证模型 (（也称为允许的合作伙伴服务器) ）的任何联合组织都需要更新其允许的域条目，以便其组织删除代理 FQDN。 此旧版联合身份验证模型不基于 DNS SRV 记录，因此，一旦组织移到云中，此类配置将过时。
>
> - 没有为 sipfed.online.lync 启用托管提供程序的任何联合组织。<span>com 需要更新其配置才能启用此功能。 仅当联合组织纯粹在本地且从未与任何混合或联机租户联合时，才可能出现这种情况。 在这种情况下，与这些组织联合在启用其托管提供程序之前将不起作用。
>
> 如果你怀疑你的任何联合合作伙伴可能正在使用直接联合身份验证，或者没有与任何在线或混合组织联合，我们建议你在准备完成迁移到云时向他们发送有关此信息的通信。
