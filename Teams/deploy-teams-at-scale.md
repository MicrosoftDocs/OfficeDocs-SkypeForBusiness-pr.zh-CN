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
ms.openlocfilehash: feffd8e6f651b4592e789cd24243f01417f1b966
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240729"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>为 Microsoft Teams 中的一线工作人员大规模部署团队

> [!NOTE]
> 此功能目前以公共预览版提供。 如果你想参加，请在 [dscale@microsoft.com](mailto:dscale@microsoft.com) 与我们联系。


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
- 请通过电子邮件保持通知，包括任何)  (完成、状态和错误。 可以选择向最多五个人通知部署的每批团队的状态。 团队所有者和成员在添加到团队时会自动收到通知。

## <a name="how-to-deploy-teams-at-scale"></a>如何大规模部署团队

> [!NOTE]
> 在部署团队之前，请确保所有团队所有者都有 Teams 许可证。

按照以下步骤一次部署大量团队。

### <a name="step-1-prepare-your-csv-files"></a>步骤 1：准备 CSV 文件

需要为部署的每批团队创建两个 CSV 文件：

- **一个 CSV 文件，用于定义要创建的团队**。 从第一列开始，此文件必须按以下顺序包含这些必需的列：

    |列名  |说明  |
    |---------|---------|
    |**团队名称**|团队的名称。|
    |**现有团队 ID**|如果要从现有团队中添加或删除用户，请指定团队的团队 ID。|
    |**知名度**|团队是否为公共 (组织中的任何人都可以加入) 或专用 (用户需要团队所有者的批准才能加入) 。 选项为 **公共** 和 **专用** 选项。|
    |**团队模板 ID**|如果要从预构建或自定义模板创建团队，请指定团队模板 ID。 有关预先生成的团队模板和 ID 的列表，请参阅 [Teams 管理中心中的团队模板入](get-started-with-teams-templates-in-the-admin-console.md) 门。 如果要使用标准默认团队模板，请将此模板留空。|

- **映射要添加到每个团队的用户的 CSV 文件**。 从第一列开始，此文件必须按以下顺序包含这些必需的列：

    |列名  |说明  |
    |---------|---------|
    |**用户全名**|用户的显示名称。|
    |**用户 UPN 或 ID**|用户主体名称 (UPN) 或用户 ID。 例如，averyh@contoso.com。|
    |**团队名称**|团队的名称。|
    |**ActionType**|无论你是在添加还是从团队中删除用户。 选项为 **AddMember** 和 **RemoveMember**。|
    |**所有者或成员**|用户是团队所有者还是团队成员。 选项为 **所有者** 和 **成员**。|

#### <a name="examples"></a>示例

使用以下示例来帮助创建 CSV 文件。 在这里，我们命名了文件、Teams.csv和Users.csv。

**Teams.csv**

|团队名称|现有团队 ID|知名度|团队模板 ID|
|---------|---------|---------|---------|
|Contoso Store 1||公共|com.microsoft.teams.template.retailStore|
|Contoso Store 2||公共|com.microsoft.teams.template.retailStore|
|Contoso Store 3||公共|com.microsoft.teams.template.retailStore|
|Contoso Store 4||公共|com.microsoft.teams.template.retailStore|
|Contoso Store 5||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||公共||
|Contoso Store 8||私人|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||私人|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||私人|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|用户全名 |用户 UPN 或 ID|团队名称|ActionType|所有者或成员|
|---------|---------|---------|---------|---------|
|艾弗里·霍华德|averyh@contoso.com|Contoso Store 1|AddMember|所有者|
|凯西·詹森|caseyj@contoso.com|Contoso Store 2|AddMember|所有者|
|杰西·欧文|jessiei@contoso.com|Contoso Store 3|AddMember|所有者|
|曼吉特·巴蒂亚|manjeetb@contoso.com|Contoso Store 4|AddMember|所有者|
|米凯拉·李|mikaelal@contoso.com|Contoso Store 5|AddMember|所有者|
|摩根·康纳斯|morganc@contoso.com|Contoso Store 6|AddMember|成员|
|奥斯卡·沃德|oscarw@contoso.com|Contoso Store 7|AddMember|成员|
|雷内·佩莱蒂埃|renep@contoso.com|Contoso Store 8|AddMember|成员|
|悉尼马托斯|sydneym@contoso.com|Contoso Store 9|AddMember|成员|
|维奥莱特·马丁内斯|violetm@contoso.com|Contoso Store 10|AddMember|成员|

### <a name="step-2-deploy-your-teams"></a>步骤 2：部署团队

创建 CSV 文件后，即可设置环境并部署团队。

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

1. 运行以下命令部署一批团队。 在此命令中，指定 CSV 文件的路径以及最多 5 个收件人的电子邮件地址，以通知有关此部署的信息。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    例如：

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    收件人将收到有关部署状态的电子邮件通知。 电子邮件包含你提交的批处理的业务流程 ID 以及可能发生的任何错误。

1. 运行以下命令以检查提交的批处理的状态。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>向我们发送反馈

我们重视你的反馈。 可用性，可靠性，性能&mdash;，我们欢迎这一切！

电子邮件 [dscale@microsoft.com](mailto:dscale@microsoft.com) 包含业务流程 ID 和错误文件（如果有）。

## <a name="related-articles"></a>相关文章

- [Teams PowerShell 概览](teams-powershell-overview.md)
