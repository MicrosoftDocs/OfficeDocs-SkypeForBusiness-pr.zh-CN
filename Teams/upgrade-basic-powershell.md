---
title: 基本升级 PowerShell|Microsoft Teams|授予升级互操作策略
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解在租户中未亮起管理员中心时升级到 Microsoft Teams 的权宜之计。
ms.localizationpriority: medium
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606031"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>将用户从 Skype for Business Online 升级到 Microsoft Teams

> [!Note]
> 本文中所述的命令旨在用作 [“升级基本](./upgrade-start-here.md) ”清单的一部分。

升级的技术迁移方面需要通知用户Skype for Business将升级到 Teams，然后将其移动到 **仅限 Teams** 模式。 可以通过Skype for Business远程Windows PowerShell会话或 Microsoft Teams 管理中心来完成这些步骤。

我们正在 [Microsoft Teams 管理中心](manage-teams-skypeforbusiness-admin-center.md)中积极推出升级工具，该工具应会很快在租户上推出。 一旦它可用，你就可以在 [“设置共存和升级设置”](./setting-your-coexistence-and-upgrade-settings.md)中找到有关迁移用户的信息。

如果现在已准备好升级，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升级基本步骤# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 通知Skype for Business用户<br> (如果用户当前处于 **Islands** 模式 (默认) ) ，请使用此命令 | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*例如， (，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business仅 + 通知Skype for Business用户 <br> (如果用户当前处于 **仅Skype for Business模式，请** 使用此命令)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Only | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |