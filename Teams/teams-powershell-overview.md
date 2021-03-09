---
title: Microsoft Teams PowerShell 概述
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
description: 了解如何使用 PowerShell 控件管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569018"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell 概述

Microsoft Teams PowerShell 是一组 cmdlet，用于直接从 PowerShell 命令行管理 Teams。 Teams PowerShell 以 .NET Standard 编写，适用于 Windows、PowerShell 6.x 和更高版本的所有平台上的 PowerShell 5.1，包括 Azure Cloud Shell。

在开始使用 PowerShell 之前，需要 [安装它](teams-powershell-install.md)。 

> [!WARNING]
> PowerShell 7 和 Teams PowerShell 存在已知问题。 我们建议使用 PowerShell 5.1，直到问题得到解决。

## <a name="releases"></a>发布


Teams PowerShell 在 [PowerShell 库中提供两](https://www.powershellgallery.com/packages/MicrosoftTeams) 种发布类型。

- **常规 (GA) ：** 生产就绪的 cmdlet，每月更新一次。

- **公共预览** 版：提前访问功能。 更新频率可能高于 GA。

有关两个版本中的功能添加和改进的详细信息，请阅读 [Teams PowerShell 发行说明](teams-powershell-release-notes.md)。


## <a name="manage-teams-with-powershell"></a>使用 PowerShell 管理 Teams

你将使用 Teams PowerShell 模块来完全管理 Teams：

- [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：Teams PowerShell 模块包含用于管理团队、聊天和频道的 cmdlet。

> [!NOTE]
> [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)1.1.6 或更高版本与 Skype for Business Online 连接器集成，为 Teams PowerShell 管理提供单个模块。

- [Skype for Business PowerShell 连接器：Skype](https://www.microsoft.com/download/details.aspx?id=39366)for Business PowerShell 连接器现在是 Teams PowerShell 模块的一部分。

有关使用这些模块管理 Teams 的完整指南，请参阅"使用[Teams PowerShell 管理 Teams"。](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>相关主题

[安装 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)
