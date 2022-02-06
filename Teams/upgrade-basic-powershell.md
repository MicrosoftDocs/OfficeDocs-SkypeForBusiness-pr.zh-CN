---
title: 基本升级 PowerShell|Microsoft Teams|授予升级互操作策略
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解在管理中心尚未在租户中亮起时Microsoft Teams升级到 windows 的 stopgap。
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
---

# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>将用户从 Skype for Business Online 升级到 Microsoft Teams

> [!Note]
> 本文中所述的命令旨在用作升级基本清单 [的一](./upgrade-start-here.md) 部分。

升级的技术迁移方面需要通知用户，Skype for Business将升级到 Teams，然后将他们移动到Teams **模式**。 这些步骤可以通过远程Skype for Business会话Windows PowerShell或Microsoft Teams管理中心完成。

我们正在管理中心内积极推出升级Microsoft Teams工具，该工具[](manage-teams-skypeforbusiness-admin-center.md)应该很快就会在你的租户上推出。 一旦可用，就可以在设置共存和升级设置中查找有关迁移 [用户的信息](./setting-your-coexistence-and-upgrade-settings.md)。

如果现在已准备好升级，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升级基本步骤# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 群岛 + 通知Skype for Business用户<br> (用户当前处于群岛模式或默认值) #A3 时 (此命令 | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business仅 + 通知Skype for Business用户 <br> (如果用户当前处于仅Skype for Business **模式，** 请使用)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Only | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |