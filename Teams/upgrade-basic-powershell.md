---
title: 基本升级 PowerShell|Microsoft Teams|授予升级互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解在管理中心尚未在租户中亮起时Microsoft Teams升级到租户的 stopgap。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd4c3cab1795ffcffe1cfd3ed1229f19e3ec80a243497ab13790e009878f9f35
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300748"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>将用户从 Skype for Business Online 升级到 Microsoft Teams

> [!Note]
> 本文中所述的命令旨在用作升级基本清单 [的一](./upgrade-start-here.md) 部分。

升级的技术迁移方面需要通知用户，Skype for Business将升级到 Teams，然后将他们移动到Teams **模式**。 这些步骤可以通过远程Skype for Business会话Windows PowerShell或Microsoft Teams中心完成。

我们正在管理中心中积极推出升级Microsoft Teams[工具](manage-teams-skypeforbusiness-admin-center.md)，该工具应该很快就会在你的租户上推出。 一旦可用，就可以在设置共存和升级设置 中查找有关迁移 [用户的信息](./setting-your-coexistence-and-upgrade-settings.md)。

如果现在已准备好升级，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升级基本步骤# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 群岛 + 通知Skype for Business用户<br> (如果用户当前处于"群岛"模式或默认 (，请使用) )  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business仅 + 通知Skype for Business用户 <br> (如果用户当前处于仅Skype for Business模式，请使用)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Only | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |