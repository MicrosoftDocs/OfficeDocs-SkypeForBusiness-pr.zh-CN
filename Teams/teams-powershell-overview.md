---
title: Microsoft 团队 PowerShell 概述
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 PowerShell 控件管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852153"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft 团队 PowerShell 概述

Microsoft 团队 PowerShell 是一组用于直接从 PowerShell 命令行管理团队的 cmdlet。 在 .NET 标准版中，团队 PowerShell 在 Windows、PowerShell 6 和更高版本上的 PowerShell 5.1 上运行，包括 Azure 云外壳。

在开始使用 PowerShell 之前，你需要 [安装它](teams-powershell-install.md)。 

> [!WARNING]
> PowerShell 7 和团队 PowerShell 存在已知问题。 我们建议在解决问题之前使用 PowerShell 5.1。

## <a name="releases"></a>新闻


在两种版本类型中，团队 PowerShell 在 [PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams) 中可用。

- **(GA) 的常规可用性** ：生产的 cmdlet，每月更新。

- **公共预览版** ：及早访问功能。 更新频率可能比 GA 更频繁。

有关两个版本的功能添加和改进的详细信息，请阅读 [团队 PowerShell 发行说明](teams-powershell-release-notes.md)。


## <a name="manage-teams-with-powershell"></a>通过 PowerShell 管理团队

您将使用团队 PowerShell 模块来完全管理团队：

- [Microsoft 团队 powershell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：团队 powershell 模块包含用于管理团队、聊天和频道的 cmdlet。

> [!NOTE]
> 最新的 [团队 powershell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/) 已与 Skype For Business Online 连接器集成，为团队 PowerShell 管理提供单个模块。

- [Skype for Business Powershell 连接器](https://www.microsoft.com/download/details.aspx?id=39366)： skype For business powershell 连接器现在是团队 PowerShell 模块的一部分。

有关使用这些模块管理团队的完整指南，请参阅使用 [团队 PowerShell 管理团队](teams-powershell-managing-teams.md)。


## <a name="related-topics"></a>相关主题

[安装团队 PowerShell](teams-powershell-install.md)

[通过团队 PowerShell 管理团队](teams-powershell-managing-teams.md)

[团队 PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)
