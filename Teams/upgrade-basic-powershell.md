---
title: 基本升级 PowerShell |Microsoft Teams |授予升级互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解在管理中心未在租户中亮起时用于升级到 Microsoft Teams 的停止服务。
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809092"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>将用户从 Skype for Business Online 升级到 Microsoft Teams

> [!Note]
> 本文中所述的命令旨在用作升级基本清单 [的一](https://aka.ms/UpgradeBasic) 部分。

升级的技术迁移方面需要通知用户 Skype for Business 将升级到 Teams，然后将其移动到仅 **Teams** 模式。 这些步骤可以通过 Skype for Business 远程Windows PowerShell或 Microsoft Teams 管理中心完成。

我们正在 Microsoft [Teams](manage-teams-skypeforbusiness-admin-center.md)管理中心中积极推出升级工具，你的租户中很快就会提供该工具。 一旦可用，就可以在"设置共存和升级设置"中查找有关迁移 [用户的信息](https://aka.ms/SkypeToTeams-SetCoexistence)。

如果现在已准备好升级，可以使用下表中列出的 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升级基本步骤# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 群岛 + 通知 Skype for Business 用户<br> (用户当前处于群岛模式或默认 (，) 此命令 | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 仅 Skype for Business + 通知 Skype for Business 用户 <br> (用户当前处于 **仅 Skype for Business** 模式，请使用)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | 仅 Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
