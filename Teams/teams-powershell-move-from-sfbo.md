---
title: 从 Skype for Business Online 连接器迁移到团队 PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online 连接器迁移到团队 PowerShell 模块以管理团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469661"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>从 Skype for Business Online 连接器迁移到团队 PowerShell 模块

若要从使用 Skype for Business Online 连接器转到团队 PowerShell 模块以管理团队，您需要更新现有 PowerShell 脚本。 本文介绍如何执行此操作。

1. 安装最新的团队 PowerShell 模块。 有关步骤，请参阅 [安装 Microsoft 团队 Powershell](teams-powershell-install.md)。
2. 卸载 Skype For Business Online 连接器。 若要执行此操作，请在 "控制面板" 中，转到 " **程序和功能**"，选择 " **Skype for Business Online，Windows PowerShell 模块**"，然后选择 " **卸载**"。 
3. 在 PowerShell 脚本中，更改 "从" 或 "到" 中引用的模块名称 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 。

    例如，"更改 ```Import-Module -Name SkypeOnlineConnector``` 为" ```Import-Module -Name MicrosoftTeams``` 。

> [!NOTE]
> 管理员应继续使用 [新的 CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) ，并在使用 Skype For business Online cmdlet 之前导入该会话。 

## <a name="related-topics"></a>相关主题

[安装 Microsoft 团队 Powershell](teams-powershell-install.md)

[通过团队 PowerShell 管理团队](teams-powershell-managing-teams.md)

[团队 PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
