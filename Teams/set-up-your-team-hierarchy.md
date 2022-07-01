---
title: 设置团队目标层次结构
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 了解如何在组织中设置团队层次结构以将内容发布到一大组团队。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 877b081e4964d07a7df0372688eee589bbde8fac
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563780"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

设置团队目标层次结构将允许组织将内容发布到一大组团队。 面向层次结构的团队定义层次结构中的所有团队如何相互关联、用户可以发布任务以及哪些团队用户有权发布到这些团队。 除非为组织设置了团队目标层次结构，否则所有用户将禁用发布功能。 若要设置面向层次结构的团队，需要创建一个定义层次结构的文件，然后将其上传到 Teams 以将其应用到组织。 上传架构后，Teams 中的应用可以使用它。

> [!IMPORTANT]
> 对于初始版本，只有 Tasks 应用支持分层团队。  将团队目标层次结构应用于组织将启用任务应用中 [的任务发布](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 。 在 Microsoft Teams 的其他区域中，不会看到团队层次结构。

下面是一个示例，说明如何在 Teams 的 Tasks 应用中表示层次结构。 创建任务列表后，发布团队的成员可以选择收件人团队，将 (发布) 任务列表发送到。 选择团队时，发布团队可以按层次结构、属性或两者的组合进行筛选。<br>

![任务发布的屏幕截图。](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>术语

导航层次结构时，以下术语非常重要。 Teams 将称为 **节点**。

* **根节点** 是层次结构中最顶层的节点。 在该示例中，零售通信是一个根节点。
* **父节点** 和 **子节点** 是表示两个已连接节点之间的关系的术语。 在该示例中，区域 01 是区域 1 的子节点。
* 多个级别的儿童称为 **后代**。 区 01、商店 01、商店 03、商店 07、区 02 和区 03 都是第 1 区的后代。
* 没有子节点的节点称为 **叶节点**。 它们位于层次结构的底部。
* **收件人团队** 是已选择接收要发布的特定内容集的团队。 它们必须是叶节点。

## <a name="plan-your-hierarchy"></a>规划层次结构

在创建定义层次结构的架构之前，需要执行一些规划，并确定要如何塑造组织。  首要任务之一是确定哪些组织组需要将任务发布到其他组。 层次结构中的每个节点表示工作组或组。

### <a name="permissions-to-publish"></a>发布权限

发布权限取决于用户是否是层次结构中任何团队的成员，以及该团队或团队集与层次结构中其他团队的关系。

> [!NOTE]
> 团队所有者也被授予发布权限。

* 如果用户是至少一个在层次结构中具有后代的团队的成员，则该用户可以发布到这些后代，而无需成为要发布到的所有团队的成员。
* 如果用户是层次结构中至少一个团队的成员，但不是层次结构中具有后代的任何团队的成员，则该用户可以查看并接收其组织发布的内容。
* 如果用户不是层次结构中任何团队的成员，该用户将看不到任何与发布相关的功能。

### <a name="guidelines"></a>指引

* 每个组织只能应用一个层次结构文件。 但是，可以将组织中的不同部分作为一个文件中的节点的不同层次结构一起包含在一起。 例如，Contoso Pharmaceuticals 有一个药房根节点和一个零售根节点。 这两个根节点都有多个后代行，它们之间没有重叠。
* 只有叶节点可以是出版物的收件人。 层次结构中的其他节点有助于选择出版物的收件人。
* 团队只能在层次结构中表示一次。
* 层次结构最多可以包含 15，000 个节点。 我们计划与客户合作，提高大型组织的此限制。

### <a name="example-hierarchy"></a>示例层次结构

例如，在以下层次结构中，召回、通信和 HR 可以将任务发布到层次结构)  (团队的每个底部节点，但东北地区只能将任务发布到纽约商店和波士顿商店团队。 示例层次结构允许召回、通信和人力资源组发布适用于整个公司的任务，例如来自 CEO 的权益信息或消息。 东北地区只能向纽约商店和波士顿商店团队发布人员计划、天气信息等任务。

![团队分层示例。](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>创建层次结构

> [!NOTE]
> 本文的其余部分讨论如何在将任务发布到收件人团队的上下文中设置团队层次结构。 有关任务应用的概述，请参阅 [Teams 中组织的任务管理应用](./manage-tasks-app.md) ，在启用任务发布时将显示该应用。

定义层次结构的架构基于以逗号分隔的值 (CSV) 文件。 该文件必须采用 UTF-8 格式。 CSV 文件中的每个行对应于团队层次结构中的一个节点。 每一行都包含为层次结构中的节点命名的信息，可以选择将其链接到团队，并包含可用于筛选支持它的应用中的团队的属性。

还可以定义 **存储桶**，这些类别是发布团队可用于组织发送给收件人团队的内容的类别，以便他们更轻松地查看、排序和关注相关内容。

### <a name="add-required-columns"></a>添加所需的列

从第一列开始，CSV 文件必须按以下顺序包含以下三列。 节点必须链接到团队才能接收任务。

| 列名   | 必需 | 描述   |
----------------|----------|---------------|
| DisplayName    | 是      | 此字段是节点的名称。 该名称最多可以是 100 个字符，并且仅包含字符 A-Z、a-z 和 0-9。 节点名称必须是唯一的。 |
| ParentName    | 是       | 这是父节点的名称。 此处指定的值必须与父节点的 **DisplayName** 字段中的值完全匹配。 如果要添加多个父节点，请使用分号 (分隔每个父节点名称;) 。 最多可添加 25 个父节点，每个父节点名称最多可长 2500 个字符。 仅当父节点是根节点时，节点才能具有多个父节点。   <br><br>**重要** 请注意，不要创建一个循环，其中层次结构中较高级别的父级引用层次结构中较低的子节点。 不支持此功能。 |
| TeamId        | 是，如果团队发布任务或从父节点接收任务       | 这包含要将节点链接到的团队的 ID。 每个节点必须引用唯一的团队，因此每个 TeamId 值在层次结构文件中只能显示一次。 若要获取要将节点链接到的团队的 ID，请运行以下 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv` 此命令列出组织中的团队，并包含每个团队的名称和 ID。 找到要链接到的团队的名称，然后将 ID 复制到此字段中。|

> [!NOTE]
> 如果节点不是根节点或叶节点，并且不需要团队成员身份来授予相应的发布和报告权限，则可以将 TeamId 留空。 此方法可用于在选择收件人团队或查看完成报表时添加更多粒度，而无需拥有相应的团队。

### <a name="add-attribute-columns"></a>添加属性列

添加三个必需列后，可以添加可选属性列。 这些属性可用于筛选节点，以便可以更轻松地选择要将任务发布到的节点。 有两种方法可以定义属性，具体取决于该属性的值是否相互排斥。

|添加属性的方法|说明 |示例  |
|---|---------|---------|
|如果属性的值是互斥的，则指定的列名称将成为属性的名称。|每行可以包含该属性的一个值，每个属性列最多可以有 50 个唯一值。 每个值最多可以是 100 个字符。 使用团队目标层次结构选择收件人团队时，在属性列中指定的属性值集将显示为该属性的筛选器值。|你希望用户能够按布局筛选商店。 此属性的值是互斥的，因为存储区只能有一个布局。 <br><br>若要添加属性以按布局筛选存储，请添加名为“应用商店”布局的列。 在此示例中，应用商店布局属性的值为 Compact、Standard 和 Large。
|如果需要指示属性的多个值，并且这些值不是互斥的，请对列名称使用 **AttributeName：UniqueValue** 格式。 <br><br>**重要** 请确保使用仅限英语的冒号 (：) 作为属性列分隔符不支持 unicode。 |冒号 (：) 之前的文本字符串将成为属性的名称。 在冒号 (：) 之前包含相同文本字符串的所有列将分组到筛选菜单中的一个部分。 冒号之后的每个字符串都成为该节的值。<br><br>对于该属性，每行的值可以为 0 (零) 或 1。 值为 0 表示该属性不适用于节点，值为 1 表示该属性适用于该节点。|你希望用户能够按部门筛选商店。 存储可以有多个部门，因此此属性的值不会相互排斥。<br><br>在此示例中，我们添加了部门：服装，部门：电子，部门：食品，部门：家庭和花园，部门：体育用品作为属性列。 部门成为属性名称，用户可以按服装、电子、食品、家庭和花园以及体育用品部门进行筛选。|

添加属性列时，请记住以下事项：

* 指定的列名或在冒号 (：) 成为属性名称之前指定的列名。 此值将显示在使用层次结构的 Teams 应用中。
* 层次结构中最多可以有 50 个属性列。
* 列名最多可以是 100 个字符，并且仅包含字符 A-Z、a-z、0-9 和空格。 列名必须是唯一的。

### <a name="add-bucket-columns"></a>添加存储桶列

可以添加存储桶列来创建存储桶，这些存储桶是可将任务组织到其中的分组。 每个存储桶在 CSV 文件中获取自己的列。 创建的存储桶可供发布团队使用。 然后，发布团队可以使用这些存储桶对收件人团队的任务进行分类。 如果团队中尚不存在存储桶，则在发布任务时按需创建存储桶。

通过集中对工作项进行一次分类，发布团队可以为接收任务列表的所有数十、数百或数千个收件人团队预先组织任务列表。 然后，收件人团队可以按存储桶对任务进行排序和筛选，以专注于与其工作最相关的区域。

添加存储桶列时，请注意以下事项：

* 列名称将成为存储桶的名称。 指定的每个存储桶将显示在使用层次结构的 Teams 应用的“存储桶”列表中。
* 建议不要在存储桶名称中包含敏感信息。 此时，发布团队在创建后无法通过发布来删除存储桶。
* 列名称前面必须有一个井号标签 (#) 。 它可以长达 100 个字符，并且仅包含字符 A-Z、a-z 和 0-9。 例如，#Operations和#Frozen商品。
* 层次结构最多可以包含 25 个存储桶列。 我们计划与客户合作，提高大型组织的此限制。

### <a name="example"></a>示例

下面是一个架构 CSV 文件的示例，该文件将创建为支持上图中显示的层次结构。 此架构包含以下内容：

* 命名和`TargetName``ParentName`命名的三个必需列`TeamId`
* 命名的 `Store layout`三个属性列， `Departments:Clothing`以及 `Departments:Foods`
* 命名的 `Fresh Foods`三个存储桶列， `Frozen Foods`以及 `Women's Wear`

该`Store layout`属性的值包括`Compact`和 `Standard``Large`. `Departments`属性列可以设置为值`0` (零) 或 `1`。 上 `Store` 图中未显示布局和 `Departments` 属性。 此处添加这些属性有助于显示如何将属性添加到节点条目。 这三个存储桶列也是如此。

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>应用层次结构

> [!NOTE] 
> 若要执行此步骤，必须从PowerShell 库安装和使用 Teams PowerShell 公共预览模块。 有关如何安装模块的步骤，请参阅安装 Teams PowerShell。

> [!NOTE]
> 政府社区云 (GCC) 客户必须使用 [cmdlet 预览版 2.4.0 预览](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) 版或更高版本，以确保将数据路由到 GCC 环境，而不是公有云环境。

在架构 CSV 文件中定义层次结构后，即可将其上传到 Teams。 为此，请运行以下命令。 必须是全局管理员或 Teams 服务管理员才能执行此步骤。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>更新层次结构

可以上传新层次结构，使用与上面相同的 PowerShell 命令替换旧层次结构。 每次上传新层次结构时，它都会替换以前的层次结构。

### <a name="check-the-status-of-your-hierarchy"></a>检查层次结构的状态

可以运行以下命令来检查层次结构上传的状态。

```powershell
Get-TeamTargetingHierarchyStatus
```

该命令将返回以下字段：

字段|说明
-----|------------
Id | 上传的唯一 ID。
地位 | 上传状态。 值包括 **起始**、 **验证**、 **成功** 和 **失败**
ErrorDetails | 有关上传错误的详细信息。 有关错误详细信息的详细信息，请参阅“故障排除”部分。 如果没有错误，则此字段为空。
LastUpdatedAt | 上次更新文件的时间戳和日期。
LastModifiedBy | 修改文件的最后一个用户的 ID。
FileName | CSV 的文件名。

## <a name="remove-your-hierarchy"></a>删除层次结构

如果想要立即为组织中的所有用户禁用 **“已发布列表”** 选项卡，可以删除层次结构。 用户将无法访问 **“已发布列表** ”选项卡或选项卡上的任何功能。 这包括能够创建新的任务列表来发布、访问草稿列表、发布、取消发布和重复列表以及查看报告。 删除层次结构不会取消发布以前发布的任务。 这些任务仍将可供收件人团队完成。

若要删除层次结构，请运行以下命令。 必须是管理员才能执行此步骤。

```powershell
Remove-TeamTargetingHierarchy
```

确认删除时，状态消息仍将显示以前的架构，尽管尝试再次删除会返回对象为 null 的错误。

## <a name="create-a-sample-hierarchy"></a>创建示例层次结构

### <a name="install-the-teams-powershell-module"></a>安装 Teams PowerShell 模块

> [!IMPORTANT]
> 若要执行此步骤，必须安装并使用 [PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/) 中的 Teams PowerShell 公共预览模块。 有关如何安装模块的步骤，请参阅 [安装 Teams PowerShell](teams-powershell-install.md)。

### <a name="sample-script"></a>示例脚本

以下脚本可用于创建团队并将.csv文件上传到 Microsoft Teams 租户。 如果有现有层次结构，则此脚本将替换它。

#### <a name="create-teams-for-a-simple-hierarchy"></a>为简单的层次结构创建团队

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>使用团队数据 (DisplayName、ParentName、TeamId) 创建逗号分隔输出

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>将输出保存到 **“下载** ”文件夹中的.csv文件

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>上传层次结构

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>疑难解答

### <a name="how-to-view-error-details"></a>如何查看错误详细信息

可以运行以下命令来了解导致错误的原因，并返回错误详细信息。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时收到错误消息

记下错误消息，因为它应包含故障排除信息，以指示无法上传架构的原因。 根据错误消息中的信息查看和编辑架构 CSV 文件，然后重试。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时，会收到“错误：InvalidTeamId”错误消息

尝试上传架构 CSV 文件时，会收到以下错误消息：

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

检查以确保在架构 CSV 文件中为团队使用正确的 TeamId。 TeamId 应与支持团队的 Microsoft 365 组的组 ID 相同。 可以在 Microsoft Teams 管理中心查找团队的组 ID。

1. 在 [Microsoft Teams 管理中心的](https://admin.teams.microsoft.com/)左侧导航中，转到 **Teams** > **管理团队**。
2. 如果表中未显示 **“组 ID** ”列，请选择表右上角的“ **编辑”列** ，然后打开 **组 ID**。
3. 在列表中查找团队，然后找到组 ID。

确保架构 CSV 文件中的 TeamId 与 Microsoft Teams 管理中心中显示的组 ID 匹配。

## <a name="related-topics"></a>相关主题

* [在 Teams 中管理组织的 Tasks 应用](manage-tasks-app.md)
* [Teams PowerShell 概览](teams-powershell-overview.md)
