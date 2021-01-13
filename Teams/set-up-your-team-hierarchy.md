---
title: 设置团队目标层次结构
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: 了解如何在组织中设置团队层次结构，以将内容发布到大量团队。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099ee82e5890e81b6fc89a5ffc1842d936e6ad1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806152"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

> **此功能目前以个人预览版提供。**

若要创建组织可用于将内容发布到大量团队的团队层次结构，需要设置团队目标架构。 架构定义层次结构中所有团队之间的关联方式，以及可用于筛选团队的属性。 创建架构后，将其上传到 Teams，层次结构将应用于整个组织。 上传架构后，Teams 客户端中的应用可以使用它。 

> [!IMPORTANT]
> 浏览团队或频道时，不会看到团队层次结构。 若要查看团队的层次结构，你需要使用支持它的应用。 对于初始版本，只有"任务"应用支持分层团队。 本文的其余部分讨论如何在将任务发布到收件人团队的上下文中设置团队层次结构。 在设置团队目标层次结构之前，请参阅"在 [Teams](manage-tasks-app.md) 中为组织管理任务"应用，了解任务发布概述。

下面是在 Teams 的"任务"应用中如何表示层次结构的示例。 创建任务列表后，发布团队成员可以选择收件人团队 (将) 发布到任务列表。 选择团队时，发布团队可以按层次结构、属性或两者的组合进行筛选。<br>

![任务发布屏幕截图](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>规划层次结构

创建定义层次结构的架构之前，需要执行一些规划，并决定要如何塑造组织。 这包括确定哪些组织组需要将任务发布到其他组。 层次结构中的每个节点代表一个工作组或组组。 层次结构底部的节点 (没有) 的节点是可接收任务的团队，而父 () 节点是有权向下发布任务的组织组。 团队在层次结构中只能表示一次。

例如，在下面的层次结构中，"召回率"、零售通信和 HR 可以将任务发布到层次结构中的每个底部节点 (团队) ，而"北部区域"只能将任务发布到纽约应用商店和波士顿商店团队。 此层次结构允许召回、零售通信和 HR 组发布适用于整个公司的任务，例如 CEO 的权益信息或消息。 美国东部区域只能向纽约应用商店和波士顿商店团队发布任务，例如人员日程安排、天气信息等。

![团队分层示例](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>创建层次结构

定义层次结构的架构基于 CSV 文件上的逗号 () 值。 CSV 文件的每一行对应于团队层次结构中的一个节点。 每一行都包含在层次结构中为节点命名的信息，可以选择性地将节点链接到团队，以及可用于筛选支持它的应用中的团队的属性。

还可以定义存储桶，这些类别是发布团队可用于组织发送给收件人团队的内容，以便他们更轻松地查看、排序和关注相关内容。

### <a name="add-required-columns"></a>添加所需的列

CSV 文件必须包含以下三列，顺序如下，从第一列开始。 节点必须链接到团队，它接收任务。 在个人预览期间，我们支持 2，000 个节点。 在启动时，我们希望默认支持至少 15，000 个节点。 我们计划与客户合作，提高较大组织的此限制。

| 列名称   | 是否必需 | 描述   |
----------------|----------|---------------|
| TargetName    | 是      | 这是节点的名称。 名称最多包含 100 个字符，并且仅包含 A-Z、a-z 和 0-9 字符。 节点名称必须唯一。 |
| ParentName    | 是       | 这是父节点的名称。 此处指定的值必须与父节点的 TargetName 字段中的值完全匹配。 如果要添加多个父节点，请用分号分隔每个父节点 (;) 。 可以添加最多 25 个父节点，每个父节点名称最多包含 2500 个字符。 只有当父节点是根节点时，一个节点才能具有多个父节点。   <br><br>**重要** 请注意不要创建循环，其中层次结构中较高级别的父级引用层次结构中较低级别的子节点。 不支持此操作。 |
| TeamId        | 是，如果团队发布任务或从父节点接收任务       | 这包含要链接到节点的团队的 ID。 如果节点位于层次结构的底部，如果希望用户能够从该节点发布，或者希望用户能够看到该节点及其后代的报告，则必须将节点链接到该团队。 例如，如果西部区域办公室的经理想要查看属于该区域中的节点的任务完成报告。<br><br>如果只想添加节点以对层次结构中的其他节点进行分组，则不需要将该节点链接到团队，可以将此字段留空。 只能将每个节点链接到一个团队。<br>若要获取想要将节点链接到的团队的 ID，请运行以下 PowerShell 命令 `Get-Team | Export-Csv TeamList.csv` ： 这会列出你组织的团队，并包括每个团队的名称和 ID。 找到要链接到的团队的名称，然后将 ID 复制到此字段中。|

### <a name="add-attribute-columns"></a>添加属性列

添加三个必需列后，可以添加可选属性列。 这些属性可用于筛选节点，以便更轻松地选择要将任务发布到的节点。 有两种方法可定义属性，具体取决于该属性的值是否互斥。

|添加属性的方法|描述 |示例  |
|---|---------|---------|
|如果属性的值互斥，则指定的列名称将成为属性的名称。|每行可以包含该属性的一个值，每个值最多包含 100 个字符。 在属性列中指定的属性值集将在使用层次结构的 Teams 应用中显示为该属性的可用筛选器值。 每个属性列最多包含 50 个唯一值。 |您希望用户能够按布局筛选存储。 此属性的值互斥，因为商店只能有一个布局。 <br><br>若要添加属性以按布局筛选应用商店，请添加名为"应用商店布局"的列。 此示例中，应用商店布局属性的值为"压缩"、"标准"和"大"。
|如果需要指示属性的多个值，并且值不是互斥的，请对列名称使用 **AttributeName：UniqueValue** 格式。 |冒号为 (：) 之前的文本字符串将成为属性的名称。 在冒号 (：) 之前包含相同文本字符串的所有列将组合到筛选菜单中的一个分区中。 冒号后的每个字符串将成为该节的值。<br><br>对于该属性，每一行的值 (0) 或 1。 值为 0 表示该属性不适用于节点，值为 1 表示该属性适用于该节点。|希望用户能够按部门筛选存储。 一个存储可以有多个部门，因此此属性的值不是互斥的。<br><br>本示例将 Departments：Clothing、Departments：Electronics、Departments：Foods、Departments：Home and Garden、Departments：Electronics 商品添加为属性列。 部门成为属性名称，用户可以按服装、电子、食品、住宅和住宅以及运动用品部门进行筛选。|

添加属性列时，请记住以下事项：

- 指定的列名称或在冒号 (：) 之前指定的列名称将成为属性的名称。 此值将显示在使用层次结构的 Teams 应用中。
- 列名最多包含 100 个字符，并且仅包含 A-Z、a-z 和 0-9 字符以及空格。 列名称必须唯一。
- 在发布时，我们计划允许 50 个属性列。

### <a name="add-bucket-columns"></a>添加存储桶列

可以添加存储桶列以创建存储桶，这些存储桶是可组织任务的分组。 每个存储桶在 CSV 文件中都有其自己的列。 创建的存储桶可供发布团队使用。 然后，发布团队可以使用这些存储桶对收件人团队的任务进行分类。 如果团队中不存在存储桶，则发布任务时，会按需创建存储桶。

通过集中对工作进行分类，发布团队可以预先组织接收任务列表的所有数十、数百或数千个收件人团队的任务列表。 然后，收件人团队可以按存储桶对任务进行排序和筛选，以专注于与工作最相关的区域。

添加存储桶列时，请注意以下事项：

- 列名称将成为存储桶的名称。 指定的每个存储桶将显示在使用层次结构的 Teams 应用中的存储桶列表中。 建议不要在存储桶名称中包括敏感信息。 目前，发布团队无法通过创建存储桶后通过发布来删除存储桶。
- 列名称前面必须带有井号标签 (#) 。 它最多包含 100 个字符，并且仅包含 A-Z、a-z 和 0-9 字符。 例如，#Operations#Frozen商品。
- 在发布时，我们希望支持 25 个存储桶列。 我们计划与客户合作，提高较大组织的此限制。

### <a name="example"></a>示例

下面是一个架构 CSV 文件示例，该文件将创建以支持上图所示的层次结构。 此架构包含以下内容：

- 名为 、、和 `TargetName` 的三 `ParentName` 个必需列 `TeamId`
- 名为 、、和的 `Store layout` `Departments:Clothing` 三个属性列 `Departments:Foods`
- 三个名为 `Fresh Foods` "， "的存储桶 `Frozen Foods` 列， `Womenswear`

该属性 `Store layout` 的值包括 `Compact` ， `Standard` 和 `Large` 。 属性 `Departments` 列可以设置为零或 `0` (值 `1`) 值。 上面的 `Store` `Departments` 图像中未显示布局和属性。 它们已添加到此处，以帮助显示如何将属性添加到节点条目。 这三个存储桶列也是如此。


| TargetName             | ParentName                      | TeamId                       | 应用商店布局|Departments：Clothing|Departments：食品|#Fresh食品|#Frozen食品|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| 召回                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| 通讯         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| 人力资源                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| 东部区域办公室   |                         |                                      |||||||
| 西部区域办公室   |                         |                                      |||||||
| "美国东部"区域        | 东部区域办公室    |                                      |||||||
| 东南亚区域        | 东部区域办公室    |                                      |||||||
| 纽约应用商店         | "美国东部"区域         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |大型|1|1||||
| 波士顿商店           | "美国东部"区域         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| 迈阿密商店            | 东南亚区域         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |紧凑|0|1||||
| 新州应用商店      | 东南亚区域         | 6be960b8-72af-4561-a343-9ac4711874eb |紧凑|0|1||||
| 西雅图商店          | 西部区域办公室    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| 洛杉矶商店      | 西部区域办公室    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |大型|1|1||||

## <a name="apply-your-hierarchy"></a>应用层次结构

> [!IMPORTANT]
> 若要执行此步骤，必须从 PowerShell 库安装和使用 Teams PowerShell 公共 [预览版模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)。 有关安装模块的步骤，请参阅"[安装 Teams PowerShell"。](teams-powershell-install.md)

在架构 CSV 文件中定义层次结构后，即可将其上传到 Teams。 为此，请运行以下命令。 只有全局管理员或 Teams 服务管理员才能执行此步骤。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>删除层次结构

> [!IMPORTANT]
> 若要执行此步骤，必须从 PowerShell 库安装和使用 Teams PowerShell 公共 [预览版模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)。 有关安装模块的步骤，请参阅"[安装 Teams PowerShell"。](teams-powershell-install.md)

如果要立即禁用组织中所有用户的"已发布列表"选项卡，可以删除层次结构。 用户无法访问"已发布列表 **"选项卡或** 选项卡上的任何功能。 这包括创建新任务列表以发布、访问草稿列表、发布、取消发布和重复列表以及查看报告的能力。 删除层次结构不会取消发布以前发布的任务。 这些任务仍可供收件人团队完成。 

若要删除层次结构，请运行以下命令。 只有管理员才能执行此步骤。 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>疑难解答

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时收到错误消息

记下错误消息，因为它应包括故障排除信息，以指示无法上传架构的原因。 根据错误消息中的信息查看和编辑架构 CSV 文件，然后重试。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时，收到"错误： InvalidTeamId"错误消息

尝试上传架构 CSV 文件时，收到以下错误消息：

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

检查以确保在架构 CSV 文件中为团队使用正确的 TeamId。 TeamId 应该与支持团队的 Microsoft 365 组的组 ID 相同。 可以在 Microsoft Teams 管理中心中查找团队的组 ID。 

1. 在 [Microsoft Teams](https://admin.teams.microsoft.com/)管理中心的左侧导航栏中，转到 **"Teams**  >  **管理团队"。**
2. 如果表中未显示"组 **ID"** 列，请选择表右上角的"编辑列"，然后打开"组 **ID"。**
3. 在列表中找到团队，然后找到组 ID。

确保架构 CSV 文件中 TeamId 与 Microsoft Teams 管理中心中显示的组 ID 匹配。 

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理"任务"应用](manage-tasks-app.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
