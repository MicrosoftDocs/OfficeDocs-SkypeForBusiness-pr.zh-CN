---
title: 基本升级 PowerShell |Microsoft 团队 |授权升级互操作策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 如果管理中心未在你的租户中亮起，则为升级到团队的 Stopgap
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20864b6b0a4be8cf9a0a88c6f3ce63c18687f2af
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837232"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>将用户从 Skype for Business Online 升级到 Microsoft 团队

> [!Note]
> 本文中介绍的命令旨在用作 "[升级基本](https://aka.ms/UpgradeBasic)" 清单中的一部分。

升级的技术迁移方面必然会通知用户，Skype for Business 将升级到团队，然后将其移动到 "**仅团队**" 模式。 可通过 Skype for Business 远程 Windows PowerShell 会话或通过 Microsoft 团队管理中心完成这些步骤。

我们正在积极推出[Microsoft 团队管理中心](manage-teams-skypeforbusiness-admin-center.md)的升级工具，它应该在你的租户上立即可用。 一旦可用，你就可以在[设置你的共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)中找到有关迁移用户的信息。

如果你已准备好立即升级，则可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。

| 升级基本步骤# | 众 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 群岛 + 通知 Skype for Business 用户<br>（如果用户当前处于 "**孤岛**" 模式下，请使用此命令（默认）） | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*（例如，$SipAddress = "TestUser@contoso.com"）* |
| [5](upgrade-basic.md#step-5) | 仅 skype for business + 通知 Skype for business 用户 <br>（如果用户当前位于**Skype for** business 模式中，请使用此命令） | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | 仅限团队 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
