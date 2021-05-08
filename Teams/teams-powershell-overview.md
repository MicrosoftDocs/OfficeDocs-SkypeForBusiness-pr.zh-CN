---
title: Microsoft TeamsPowerShell 概述
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
description: 了解如何使用 PowerShell 控件管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768351"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft TeamsPowerShell 概述

Microsoft TeamsPowerShell 是一组 cmdlet，用于Teams PowerShell 命令行管理数据。 PowerShell 以 .NET Standard 编写Teams适用于 Windows、PowerShell 6.x 和更高版本的所有平台上的 PowerShell 5.1，包括 Azure Cloud Shell。

在开始使用 PowerShell 之前，需要 [安装它](teams-powershell-install.md)。 

> [!WARNING]
> PowerShell 7 和 PowerShell Teams问题。 我们建议使用 PowerShell 5.1，直到问题得到解决。

## <a name="releases"></a>发布


TeamsPowerShell 在[PowerShell 库中提供两](https://www.powershellgallery.com/packages/MicrosoftTeams)种发布类型。

- **常规可用性 (GA) ：** 生产就绪型 cmdlet，每月更新一次。

- **公共预览** 版：提前访问功能。 更新频率可能高于 GA。

有关两个版本中的功能添加和改进的详细信息，请阅读[powerShell](teams-powershell-release-notes.md)Teams说明 。


## <a name="manage-teams-with-powershell"></a>使用 PowerShell Teams管理资源

将使用 PowerShell 模块Teams完全管理Teams：

- [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：Teams PowerShell 模块包含用于管理团队、聊天和频道的 cmdlet。

> [!NOTE]
> PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本 2.0 或更高版本包括所有 Skype for Business Online Connector cmdlet，为 PowerShell 管理提供Teams模块。

- [Skype for Business PowerShell 连接器](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)：Skype for Business PowerShell 连接器现在是 PowerShell 模块Teams的一部分。

有关使用这些模块管理Teams的完整指南，请参阅使用 powerShell Teams [Teams管理应用程序](teams-powershell-managing-teams.md)。


## <a name="related-topics"></a>相关主题

[安装 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[TeamsPowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)

[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)
