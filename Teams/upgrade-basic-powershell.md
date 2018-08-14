---
title: 升级基本 PowerShell 命令的 Microsoft 团队
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 如果在您的租户亮起尚未 Admin Center 升级到团队的应急
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001716"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>您的用户从升级 Skype 业务 online 到 Microsoft 团队

> [!Note]
> 本文中介绍的命令旨在用作[基本升级](https://aka.ms/UpgradeBasic)的清单的一部分。

升级的技术迁移方面伴有将升级到团队，然后将它们移动到**团队仅**模式 for Business 的 Skype 通知用户。 业务远程 Windows PowerShell 会话或通过 Microsoft 团队和业务管理中心的 Skype，可以通过 Skype 完成这些步骤。 
 
我们主动推出升级中[的 Microsoft 团队和业务管理中心的 Skype](manage-teams-skypeforbusiness-admin-center.md)、 工具和应立即在您的租户上可用。 只要可用它，您可以找到有关迁移用户[设置您共存并升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)的信息。 
 
如果您已经准备立即升级，您可以使用下表中列出的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。 
 
 |升级的基本步骤 # | 模式 | PowerShell 命令 |
|-------|--------|------|
| [5](upgrade-basic.md#step-5) |群岛 + 业务用户通知 Skype<br>（如果用户当前正在**群岛**模式 （默认），则使用此命令） | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>_(例如，$SipAddress = 'TestUser@contoso.com)_<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5)  | Skype for Business 仅 + 业务用户通知 Skype <br>（如果用户当前正在**for Business 仅 Skype**模式，则使用此命令） | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | 仅团队 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


