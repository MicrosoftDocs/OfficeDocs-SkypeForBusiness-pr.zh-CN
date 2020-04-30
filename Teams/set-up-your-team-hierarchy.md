---
title: 设置团队目标层次结构
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: 了解如何在组织中设置团队层次结构，以将内容发布到大型团队组。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 581d67f0083ea8b0e91615a96685f10f4cd64785
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940900"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

> **此功能当前处于私人预览版中。**

若要创建可供你的组织用于将内容发布到大量团队的团队的层次结构，你需要设置团队目标架构。 该架构定义层次结构中的所有团队如何相互关联以及可用于筛选团队的属性。 创建架构后，将其上载到团队，并在整个组织中应用层次结构。 上载架构后，团队客户端中的应用可以使用它。 

> [!IMPORTANT]
> 在浏览团队或频道时，您将看不到团队的层次结构。 若要查看团队的层次结构，你需要使用支持它的应用。 对于初始版本，只有 "任务" 应用支持分层团队。 本文的其余部分介绍了如何在向收件人团队发布任务的上下文中设置团队层次结构。 在设置团队目标层次结构之前，请参阅[管理团队中组织的 "任务" 应用](manage-tasks-app.md)，了解有关任务发布的概述。

下面是在团队的 "任务" 应用中如何表示层次结构的示例。 创建任务列表后，发布团队的成员可以选择要向其发送（发布）任务列表的收件人团队。 选择团队时，发布团队可以按层次结构、属性或二者的组合进行筛选。<br>

![任务发布的屏幕截图](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>规划层次结构

在创建定义层次结构的架构之前，需要执行一些规划并确定如何对组织进行整形。 这包括确定哪些组织组需要将任务发布到其他组。 层次结构中的每个节点表示一个工作组或组组。 层次结构底部的节点（没有子元素的节点）是可以接收任务的团队，而其他节点（父）是具有向下发布任务的权限的组织组。 团队只能在层次结构中表示一次。

例如，在以下层次结构、召回、零售通信和 HR 中，可以将任务发布到层次结构中的每个底部节点（team），而东北区域只能将任务发布到纽约商店和波士顿商店团队。 此层次结构允许撤回、零售通信和人力资源组发布适用于整个公司的任务，例如来自 CEO 的福利信息或消息。 北美区域可将任务（如人员计划、天气信息等）发布到纽约商店和波士顿商店团队。

![团队分层示例](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>创建层次结构

定义层次结构的架构基于逗号分隔值（CSV）文件。 CSV 文件中的每一行对应团队层次结构中的一个节点。 每行都包含用于对层次结构中的节点进行命名的信息，可选择将其链接到团队，并包括可用于在支持它的应用中筛选团队的属性。

你还可以定义存储桶，发布团队可使用这些类别来组织发送给收件人团队的内容，以便更轻松地查看、排序和关注相关内容。

### <a name="add-required-columns"></a>添加所需的列

CSV 文件必须包含以下三列，顺序从第一列开始。 必须将节点链接到团队才能接收任务。 在私人预览版中，我们支持500节点。 在启动时，我们有望默认支持至少2000节点。 我们计划与客户协作，为大型组织提高此限额。

| 列名称   | 是否必需 | 描述   |
----------------|----------|---------------|
| TargetName    | 是      | 这是节点的名称。 该名称最多可包含100个字符，并且仅包含字符 a-z、A-z 和0-9。 节点名称必须是唯一的。 |
| ParentName    | 是       | 这是父节点的名称。 此处指定的值必须与父节点的 TargetName 字段中的值完全匹配。 如果要添加多个父节点，请使用分号（;) 分隔每个父节点名称。 最多可添加25个父节点，每个父节点名称最多可以为2500个字符。 只有当父节点为根节点时，节点才可以有多个父节点。   <br><br>**重要提示**请注意不要创建一个循环，层次结构中的父节点将在层次结构中较低的位置引用该子节点。 这不受支持。 |
| TeamID        | 是，如果团队从父节点发布任务或接收任务       | 这包含要将节点链接到的团队的 ID。 如果你希望用户能够从该节点发布，或者希望用户能够查看该节点及其后代的报告，则必须将该节点链接到团队（如果你的层次结构位于该节点的底部）。 例如，如果您的经理针对西部地区，则 Office 希望查看属于该区域的节点的任务完成报告。<br><br>如果只想添加节点以对层次结构中的其他节点进行分组，则无需将该节点链接到团队，并且可以将此字段保留为空。 您只能将每个节点链接到一个团队。<br>若要获取要将节点链接到的团队的 ID，请运行以下 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv`。 这将列出组织中的团队并包括每个团队的名称和 ID。 找到要链接到的团队的名称，然后将该 ID 复制到此字段中。|

### <a name="add-attribute-columns"></a>添加属性列

添加所需的三个列后，您可以添加可选的属性列。 这些属性可用于筛选节点，以便你可以更轻松地选择要将任务发布到的节点。 可通过两种方法来定义属性，具体取决于该属性的值是否互相排斥。

|添加属性的方法|说明 |示例  |
|---|---------|---------|
|如果某个属性的值是互斥的，则你指定的列名称将成为该属性的名称。|每一行可以包含该属性的一个值，每个值最多可包含100个字符。 在 "属性" 列中指定的属性值集将在使用层次结构的团队应用中显示为该属性的可用筛选值。 每个属性列最多可以有50个唯一值。 |希望用户能够按布局筛选存储。 此属性的值是相互排斥的，因为一个应用商店只能有一个布局。 <br><br>若要添加属性以按布局筛选存储，请添加一个名为 "Store layout" 的列。 在此示例中，应用商店布局属性的值为 Compact、Standard 和大型。
|如果需要为一个属性指示多个值，并且值不是互相排斥的，请对列名称使用**AttributeName： UniqueValue**格式。 |冒号前的文本字符串（:)成为属性的名称。 冒号前包含相同文本字符串的所有列（:)在 "筛选" 菜单中组合到一个分区中。 冒号后面的每个字符串都将成为该节的值。<br><br>对于该属性，每一行都可以具有值0（零）或1。 值为0意味着属性不应用于节点，值1表示属性应用于该节点。|希望用户能够按部门筛选存储。 一个商店可以有多个部门，因此此属性的值不是互相排斥的。<br><br>在此示例中，我们添加了部门：衣服，部门：电子产品，部门：食品，部门：家庭和花园，部门：体育用品作为属性列。 "部门" 将成为属性名称，并且用户可以通过衣服、电子设备、食品、家庭和花园以及体育用品部门进行筛选。|

添加属性列时，请记住以下几点：

- 你指定的列名或在冒号前指定的列名称（:)成为属性的名称。 此值将显示在使用层次结构的团队应用中。
- 列名称最多可包含100个字符，并且仅包含字符 A-z、a-z 和0-9 以及空格。 列名称必须是唯一的。
- 在启动时，我们计划允许50属性列。

### <a name="add-bucket-columns"></a>添加存储桶列

你可以添加存储桶列以创建存储桶，这些存储桶可以分组到哪些任务可以组织。 每个存储桶在 CSV 文件中获取自己的列。 您创建的存储桶将提供给发布团队。 然后，发布团队可以使用这些存储桶对收件人团队的任务进行分类。 如果团队中尚未存在存储桶，则会在发布任务时按需创建存储桶。

通过集中工作一次，发布团队可以为接收任务列表的十个、上百个或数千个收件人团队预组织任务列表。 然后，收件人团队可以按存储桶对任务进行排序和筛选，以重点关注与其工作最相关的区域。

添加存储桶列时，请注意以下事项：

- "列名称" 将成为存储桶的名称。 你指定的每个存储桶都将显示在使用该层次结构的团队应用中的存储桶列表中。 我们建议您不要在存储桶名称中包含敏感信息。 此时，发布团队无法在创建存储桶后通过发布将其删除。
- 列名称前面必须有井号（#）。 其长度最多可为100个字符，并且仅包含字符 a-z、A-z 和0-9。 例如，#Operations 和 #Frozen 商品。
- 在启动时，我们希望支持25个存储桶列。 我们计划与客户协作以增加较大组织的此限额。

### <a name="example"></a>示例

下面是一个架构 CSV 文件的示例，将创建该文件以支持上面的图像中所示的层次结构。 此架构包含以下内容：

- 名为`TargetName`、 `ParentName`和的三个必需列`TeamID`
- 名为`Store layout`、 `Departments:Clothing`和的三个属性列`Departments:Foods`
- 名为`Fresh Foods`、 `Frozen Foods`和的三个 bucket 列`Womenswear`

该`Store layout`属性具有值，其中`Compact`包括`Standard`、和`Large`。 可以`Departments`将属性列设置为值`0` （零）或。 `1` `Store`布局和`Departments`属性未显示在上述图像中。 此处添加它们是为了帮助演示如何将属性添加到节点条目。 这一点同样适用于三个存储桶列。


| TargetName             | ParentName                      | TeamID                       | 应用商店布局|部门：衣服|部门：食品|#Fresh 食品|#Frozen 食品|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| 取回                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| 通讯         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| 人力资源                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| 东亚地区 Office   |                         |                                      |||||||
| 西亚地区办事处   |                         |                                      |||||||
| 东北地区        | 东亚地区 Office    |                                      |||||||
| 东南地区        | 东亚地区 Office    |                                      |||||||
| 纽约商店         | 东北地区         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |大|1|1||||
| 波士顿商店           | 东北地区         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| 迈阿密商店            | 东南地区         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |机身|0|1||||
| 新奥尔良商店      | 东南地区         | 6be960b8-72af-4561-a343-9ac4711874eb |机身|0|1||||
| 西雅图商店          | 西亚地区办事处    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| 洛杉矶商店      | 西亚地区办事处    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |大|1|1||||

## <a name="apply-your-hierarchy"></a>应用层次结构

> [!IMPORTANT]
> 若要执行此步骤，必须从 PowerShell 测试库安装并使用团队 PowerShell 模块的最新版本。 有关如何执行此操作的步骤，请参阅[从 PowerShell 测试库中安装最新团队 PowerShell 模块](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。

在架构 CSV 文件中定义层次结构后，即可将其上载到团队。 若要执行此操作，请运行以下命令。 只有管理员才能执行此步骤。 

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>删除层次结构

> [!IMPORTANT]
> 若要执行此步骤，必须从 PowerShell 测试库安装并使用团队 PowerShell 模块的最新版本。 有关如何执行此操作的步骤，请参阅[从 PowerShell 测试库中安装最新团队 PowerShell 模块](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。

如果要为组织中的所有用户立即禁用 "**已发布的列表**" 选项卡，您可以删除您的层次结构。 用户无法访问 "**已发布的列表**" 选项卡或选项卡上的任何功能。 这包括创建新任务列表以发布、访问草稿列表、发布、取消发布和重复列表以及查看报表的功能。 删除层次结构不会取消发布以前发布的任务。 这些任务将仍可供收件人团队完成。 

若要删除层次结构，请运行以下命令。 只有管理员才能执行此步骤。 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>团队 Powershell 模块

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>从 PowerShell 测试库安装最新团队 PowerShell 模块

团队 PowerShell 模块（当前[1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)）的最新公开可用版本不支持团队层次结构管理。 通过以下步骤，从 PowerShell 测试库中安装团队层次结构支持的最新版本的团队 PowerShell 模块。

> [!NOTE]
> 不要使用来自公共 PowerShell 库的模块版本并排从 PowerShell 测试库中安装团队 PowerShell 模块。 按照以下步骤，首先从公共 PowerShell 库中卸载团队 PowerShell 模块，然后从 PowerShell 测试库中安装最新版本的模块。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从公共 PowerShell 库中卸载团队 PowerShell 模块：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 关闭所有现有 PowerShell 会话。
5. 再次启动 Windows PowerShell 模块，然后运行以下内容以将 PowerShell 测试库注册为受信任的来源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 运行以下内容从 PowerShell 测试库安装最新的团队 PowerShell 模块：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>从 PowerShell 测试库更新到团队 PowerShell 模块的最新版本

如果已从 PowerShell 测试库中安装了团队 PowerShell 模块，请使用以下步骤更新到最新版本。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从 PowerShell 测试库更新当前安装的团队 PowerShell 模块版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>故障排除

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>上载架构文件时收到错误消息

记下该错误消息，因为它应包含疑难解答信息，以指示无法上载架构的原因。 根据错误消息中的信息查看和编辑你的架构 CSV 文件，然后重试。

## <a name="related-topics"></a>相关主题

- [管理团队中组织的 "任务" 应用](manage-tasks-app.md)
