---
title: 设置团队目标层次结构
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 了解如何在组织中设置团队层次结构，以便将内容发布到大型团队集。
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc4e7e88e855432f17c7daed9584e20e0e4739f1
ms.sourcegitcommit: fcbbc197e43bcd63bf95cb329df9cb52e06ee356
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2022
ms.locfileid: "68842110"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

设置团队目标层次结构将允许组织将内容发布到一大组团队。 团队目标层次结构定义层次结构中的所有团队彼此之间的关系、哪些用户可以发布任务，以及哪些团队用户有权发布到。 除非为组织设置了团队目标层次结构，否则将禁用所有用户的发布功能。 若要设置团队目标层次结构，需要创建一个定义层次结构的文件，然后将其上传到 Teams 以将其应用于组织。 上传架构后，Teams 中的应用可以使用它。

> [!IMPORTANT]
> 对于初始版本，只有任务应用支持分层团队。  将团队目标层次结构应用于组织将在任务应用中启用 [任务发布](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 。 你不会在 Microsoft Teams 的其他区域中看到团队层次结构。

下面是如何在 Teams 中的“任务”应用中表示层次结构的示例。 创建任务列表后，发布团队的成员可以选择要发送 (发布) 任务列表的收件人团队。 选择团队时，发布团队可以按层次结构、属性或两者的组合进行筛选。<br>

![任务发布的屏幕截图。](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>术语

在导航层次结构时，以下术语非常重要。 Teams 将称为 **节点**。

* **根节点** 是层次结构中最顶层的节点。 在此示例中，零售通信是根节点。
* **父节点** 和 **子节点** 是表示两个已连接节点之间关系的术语。 在此示例中，第 01 区是区域 1 的子节点。
* 多个级别的子级称为 **后代**。 01 区、商店 01、商店 03、商店 07、区 02 和 03 区都是 1 区的后裔。
* 没有子节点的节点称为 **叶节点**。 它们位于层次结构的底部。
* **收件人团队** 是已选择接收要发布的一组特定内容的团队。 它们必须是叶节点。

## <a name="plan-your-hierarchy"></a>规划层次结构

在创建定义层次结构的架构之前，需要进行一些规划，并决定如何塑造组织。  首要任务之一是决定哪些组织组需要将任务发布到其他组。 层次结构中的每个节点都表示一个工作组或组组。

### <a name="permissions-to-publish"></a>发布权限

发布权限取决于用户是层次结构中任何团队的成员，以及该团队或团队集与层次结构中其他团队的关系。

> [!NOTE]
> 团队的所有者还被授予发布权限。

* 如果用户是层次结构中至少有一个具有后代的团队的成员，则该用户可以发布到这些后代，而无需成为要发布到的所有团队的成员。
* 如果用户是层次结构中至少一个团队的成员，但不是层次结构中具有后代的任何团队的成员，则用户可以查看和接收来自其组织的已发布内容。
* 如果用户不是层次结构中任何团队的成员，该用户将不会看到任何与发布相关的功能。

### <a name="guidelines"></a>指引

* 每个组织只能应用一个层次结构文件。 但是，可以将组织的不同部分作为一个文件中节点的不同层次结构包含在一起。 例如，Contoso Pharmaceuticals 具有 Pharmacy 根节点和零售根节点。 两个根节点都有多行后代，并且它们之间没有重叠。
* 只有叶节点可以是出版物的接收者。 层次结构中的其他节点有助于选择出版物的收件人。
* 团队只能在层次结构中表示一次。
* 层次结构最多可包含 15，000 个节点。 我们计划与客户合作，为大型组织提高此限制。

### <a name="example-hierarchy"></a>示例层次结构

例如，在以下层次结构中，召回、通信和 HR 可以将任务发布到层次结构中的每个底层节点 (团队) ，但东北区域只能将任务发布到纽约商店和波士顿商店团队。 示例层次结构允许召回、通信和 HR 组发布适用于整个公司的任务，例如来自 CEO 的权益信息或消息。 东北区域只能向纽约商店和波士顿商店团队发布人员安排、天气信息等任务。

![团队分层示例。](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>创建层次结构

> [!NOTE]
> 本文的其余部分讨论在将任务发布到收件人团队的上下文中设置团队层次结构。 有关“ [任务”应用的概述，请参阅在 Teams 中为组织管理](./manage-tasks-app.md) 任务应用，启用后会显示任务发布。

定义层次结构的架构基于 CSV) 文件的逗号分隔值 (。 该文件必须采用 UTF-8 格式。 CSV 文件中的每一行对应于团队层次结构中的一个节点。 每行都包含用于命名层次结构中节点的信息，可以选择将其链接到团队，并包含可用于在支持该节点的应用中筛选团队的属性。

还可以定义 **存储桶**，这些类别是发布团队可用于组织发送给收件人团队的内容，以便他们更轻松地查看、排序和关注相关内容。

### <a name="add-required-columns"></a>添加所需列

CSV 文件必须包含以下三列（按以下顺序），从第一列开始。 节点必须链接到团队才能接收任务。

| 列名称   | 必需 | 描述   |
----------------|----------|---------------|
| DisplayName    | 是      | 此字段是节点的名称。 名称最多可以包含 100 个字符，并且仅包含 A-Z、a-z 和 0-9 字符。 节点名称必须唯一。 |
| ParentName    | 是       | 这是父节点的名称。 此处指定的值必须与父节点的 **DisplayName** 字段中的值完全匹配。 如果要添加多个父节点，请使用分号 (;) 分隔每个父节点名称。 最多可以添加 25 个父节点，每个父节点名称最多可以包含 2500 个字符。 仅当父节点是根节点时，一个节点才能有多个父节点。   <br><br>**重要** 请注意，不要创建层次结构中较高父级引用层次结构中较低子节点的循环。 不支持此操作。 |
| TeamId        | 是，如果团队发布任务或从父节点接收任务       | 它包含要将节点链接到的团队的 ID。 每个节点必须引用唯一的团队，因此每个 TeamId 值只能在层次结构文件中出现一次。 若要获取要将节点链接到的团队的 ID，请运行以下 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv`。 此命令列出组织中的团队，并包括每个团队的名称和 ID。 找到要链接到的团队的名称，然后将 ID 复制到此字段中。|

> [!NOTE]
> 如果节点不是根节点或叶节点，并且不需要团队成员身份即可授予相应的发布和报告权限，则可以将 TeamId 留空。 此方法可用于在选择收件人团队或查看完成报告时添加更多粒度，而无需相应的团队。

### <a name="add-attribute-columns"></a>添加属性列

添加三个必需列后，可以添加可选属性列。 这些属性可用于筛选节点，以便可以更轻松地选择要将任务发布到的节点。 可通过两种方式定义属性，具体取决于该属性的值是否互斥。

|添加属性的方法|说明 |示例  |
|---|---------|---------|
|如果属性的值是互斥的，则指定的列名称将成为该属性的名称。|每行可以包含该属性的一个值，每个属性列最多可以有 50 个唯一值。 每个值最多可以有 100 个字符。 使用团队目标层次结构选择收件人团队时，在属性列中指定的属性值集将显示为该属性的筛选器值。|你希望用户能够按布局筛选存储区。 此属性的值是互斥的，因为一个商店只能有一个布局。 <br><br>若要添加属性以按布局筛选存储区，请添加名为“应用商店布局”的列。 在此示例中，Microsoft Store 布局属性的值为 Compact、Standard 和 Large。
|如果需要为属性指示多个值，并且这些值不是互斥的，请使用 **AttributeName：UniqueValue** 格式作为列名称。 <br><br>**重要** 请确保使用仅英文冒号 (：) ，因为 unicode 不支持作为属性列分隔符。 |冒号 (：) 前面的文本字符串将成为属性的名称。 在冒号 (：) 之前包含相同文本字符串的所有列将分组到筛选菜单中的某个部分。 冒号后面的每个字符串都将成为该部分的值。<br><br>每行的值为 0 (零) 或 1。 值为 0 表示特性不适用于节点，值为 1 表示属性应用于该节点。|你希望用户能够按部门筛选商店。 一个商店可以有多个部门，因此此属性的值不是互斥的。<br><br>在此示例中，我们添加 Departments：Clothing、Departments：Electronics、Departments：Foods、Departments：Home and Garden、Departments：体育用品作为属性列。 部门成为属性名称，用户可以按服装、电子、食品、家居和花园以及体育用品部门进行筛选。|

添加属性列时，请记住以下几点：

* 指定的列名或列名在冒号 (：) 之前指定的列名将成为属性的名称。 此值将显示在使用层次结构的 Teams 应用中。
* 层次结构中最多可以有 50 个属性列。
* 列名最长可以为 100 个字符，仅包含字符 A-Z、a-z、0-9 和空格。 列名称必须唯一。

### <a name="add-bucket-columns"></a>添加存储桶列

可以添加存储桶列以创建存储桶，这些存储桶是可将任务组织到其中的分组。 每个存储桶在 CSV 文件中获取其自己的列。 创建的存储桶可供发布团队使用。 然后，发布团队可以使用这些存储桶对收件人团队的任务进行分类。 如果团队中尚不存在存储桶，则会在发布任务时按需创建存储桶。

通过集中对工作项进行一次分类，发布团队可以为接收任务列表的所有数十、数百或数千个收件人团队预先组织任务列表。 然后，接收团队可以按存储桶对任务进行排序和筛选，以专注于与其工作最相关的区域。

添加存储桶列时，请注意以下事项：

* 列名称将成为存储桶的名称。 指定的每个存储桶将显示在使用层次结构的 Teams 应用中的“存储桶”列表中。
* 建议不要在存储桶名称中包含敏感信息。 目前，发布团队无法在创建存储桶后通过发布来删除该存储桶。
* 列名称前面必须带有井号标记 (#) 。 它最多可以包含 100 个字符，并且仅包含 A-Z、a-z 和 0-9 字符。 例如，#Operations和#Frozen商品。
* 层次结构最多可以包含 25 个存储桶列。 我们计划与客户合作，提高大型组织的此限制。

### <a name="example"></a>示例

下面是要创建的架构 CSV 文件的示例，该文件支持上图中显示的层次结构。 此架构包含以下项：

* 三个必需的列，名为 `TargetName`、 `ParentName`、 和 `TeamId`
* 名为 、 `Departments:Clothing`和 的三个`Store layout`属性列`Departments:Foods`
* 名为 、 `Frozen Foods`和 的三个`Fresh Foods`存储桶列`Women's Wear`

特性 `Store layout` 具有包含 `Compact`、 `Standard`和 `Large`的值。 属性`Departments`列可以设置为 (零) 或 `1`的值`0`。 上 `Store` 图中未显示布局和 `Departments` 属性。 此处添加了这些属性，以帮助演示如何将属性添加到节点条目。 这三个存储桶列也是如此。

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
> 若要执行此步骤，必须使用 Microsoft Teams PowerShell cmdlet。 应使用 4.6.0 或更高版本的 Microsoft Teams cmdlet。 此要求也适用于政府社区云 (GCC) 客户。

在架构 CSV 文件中定义层次结构后，即可将其上传到 Teams。 为此，请运行以下命令。 你必须是全局管理员或 Teams 服务管理员才能执行此步骤。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>更新层次结构

可以使用上述相同 PowerShell 命令上传新层次结构以替换旧层次结构。 每次上传新层次结构时，都会替换以前的层次结构。

### <a name="check-the-status-of-your-hierarchy"></a>检查层次结构的状态

可以运行以下命令来检查层次结构上传的状态。

```powershell
Get-TeamTargetingHierarchyStatus
```

该命令将返回以下字段：

字段|说明
-----|------------
Id | 上传的唯一 ID。
地位 | 上传状态。 值包括 **Starting**、 **Validating**、 **Successful** 和 **Failed**
ErrorDetails | 出现上传错误的详细信息。 有关错误详细信息的详细信息，请参阅故障排除部分。 如果没有错误，则此字段为空。
LastUpdatedAt | 上次更新文件的时间戳和日期。
LastModifiedBy | 上次修改文件的用户的 ID。
FileName | CSV 的文件名。

## <a name="remove-your-hierarchy"></a>删除层次结构

如果要立即为组织中的所有用户禁用 **“已发布列表** ”选项卡，可以删除层次结构。 用户无权访问“ **已发布列表** ”选项卡或选项卡上的任何功能。 这包括创建新任务列表以发布、访问草稿列表、发布、取消发布和重复列表以及查看报告的功能。 删除层次结构不会取消发布以前发布的任务。 这些任务仍可供收件人团队完成。

若要删除层次结构，请运行以下命令。 你必须是管理员才能执行此步骤。

```powershell
Remove-TeamTargetingHierarchy
```

确认删除时，状态消息仍会显示以前的架构，尽管尝试再次删除会返回一个错误，指出对象为 null。

## <a name="create-a-sample-hierarchy"></a>创建示例层次结构

### <a name="install-the-teams-powershell-module"></a>安装 Teams PowerShell 模块

> [!IMPORTANT]
> 若要执行此步骤，必须从 [PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/)安装并使用 Teams PowerShell 模块。 有关如何安装模块的步骤，请参阅 [安装 Microsoft Teams PowerShell 模块](teams-powershell-install.md)。

### <a name="sample-script"></a>示例脚本

以下脚本可用于创建团队并将.csv文件上传到 Microsoft Teams 租户。 如果有现有层次结构，此脚本将替换它。

#### <a name="create-teams-for-a-simple-hierarchy"></a>为简单层次结构创建团队

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>使用团队数据创建逗号分隔的输出， (DisplayName、ParentName、TeamId) 

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>将输出保存到 **“下载”** 文件夹中的.csv文件

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

可以运行以下命令来了解导致错误的原因并返回错误详细信息。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时收到错误消息

记下错误消息，因为它应包括故障排除信息，以指示无法上传架构的原因。 根据错误消息中的信息查看和编辑架构 CSV 文件，然后重试。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>上传架构 CSV 文件时收到“错误： InvalidTeamId”错误消息

尝试上传架构 CSV 文件时，会收到以下错误消息：

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

检查以确保在架构 CSV 文件中为团队使用正确的 TeamId。 TeamId 应与为团队提供后盾的 Microsoft 365 组的组 ID 相同。 可以在 Microsoft Teams 管理中心中查找团队的组 ID。

1. 在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)的左侧导航栏中，转到 **“Teams** > **管理团队**”。
2. 如果表中未显示 **“组 ID** ”列，请选择表格右上角的“ **编辑列** ”，然后打开 **“组 ID**”。
3. 在列表中查找团队，然后找到组 ID。

确保架构 CSV 文件中的 TeamId 与 Microsoft Teams 管理中心中显示的组 ID 匹配。

## <a name="related-topics"></a>相关主题

* [在 Teams 中管理组织的“任务”应用](manage-tasks-app.md)
* [Teams PowerShell 概览](teams-powershell-overview.md)
