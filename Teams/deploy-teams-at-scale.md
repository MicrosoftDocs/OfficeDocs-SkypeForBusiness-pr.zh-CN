---
title: 为 Microsoft Teams 中的一线工作人员大规模部署团队
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何为组织中的一线工作人员大规模部署团队。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947223"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>为 Microsoft Teams 中的一线工作人员大规模部署团队

> [!NOTE]
> 此功能目前以专用预览版提供。 若要参加专用预览版，请在 [dscale@microsoft.com](mailto:dscale@microsoft.com) 与我们联系。

## <a name="overview"></a>概述
 
你的组织可能有很多团队可用于推动一线员工之间的沟通和协作，这些团队分布在不同的商店、地点和角色中。 目前，没有简单的解决方案可以大规模部署、设置和管理这些团队和用户。

我们正在构建一个解决方案，使管理员能够大规模部署和管理团队。

下面概述了目前可用于一次创建和管理大量团队的功能，以及我们近期的规划。

||今天可用 |2022 年晚些时候  |
|---------|---------|---------|
|**每个批次可以创建的团队数**|最多 100 个 |最多 500 个|
|**可以为每个团队添加的用户数**|最多 25 个|最多 25 个|

大规模部署团队可以：

- 使用预生成的模板或自己的自定义模板创建团队。
- 将用户作为所有者或成员添加到团队。
- 通过从现有团队中添加或删除用户来大规模管理团队。
- 请通过电子邮件保持通知，包括任何)  (完成、状态和错误。 团队所有者和成员将收到通知。

## <a name="how-to-deploy-teams-at-scale"></a>如何大规模部署团队

> [!NOTE]
> 在部署团队之前，请确保所有团队所有者都有 Teams 许可证。

按照以下步骤一次部署大量团队。

```New-CsBatchTeamsDeployment```使用该 cmdlet 提交一批要创建的团队。 将为每个批次生成业务流程 ID。 然后，可以使用 ```Get-CsBatchTeamsDeployment``` cmdlet 跟踪每个批处理的进度和状态。

1. 安装 PowerShell 版本 7 或更高版本。 有关分步指南，请参阅在 [Windows 上安装 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。
1. 在管理员模式下运行 PowerShell。
1. 运行以下命令，卸载以前安装的任何 Teams PowerShell 模块。

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    如果收到错误消息，则已设置。 转到下一步。
1. 下载并安装 [最新版本的 Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。

1. 运行以下命令以连接到 Teams。

    ```powershell
    Connect-MicrosoftTeams
    ```

    出现提示时，请使用管理员凭据登录。

1. 运行以下命令以获取 Teams PowerShell 模块中的命令列表。

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    验证是否```New-CsBatchTeamsDeployment```已列出。```Get-CsBatchTeamsDeployment```

1. 运行以下命令部署一批团队。 最多可以在 **UsersToNotify** 参数中输入五个电子邮件地址。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. 运行以下命令以检查提交的批处理的状态。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>向我们发送反馈

我们重视你的反馈。 可用性，可靠性，性能&mdash;，我们欢迎这一切！

电子邮件 [dscale@microsoft.com](mailto:dscale@microsoft.com) 包含业务流程 ID 和错误文件（如果有）。

## <a name="related-articles"></a>相关文章

- [Teams PowerShell 概览](teams-powershell-overview.md)
