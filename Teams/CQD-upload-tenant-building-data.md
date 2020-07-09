---
title: 在通话质量仪表板（CQD）中上载租户和生成数据
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何在通话质量仪表板（CQD）中上载租户和生成数据。
ms.openlocfilehash: d8a27ab45a01d1b0eccc28716bee9fa838fb8de5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086011"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>在通话质量仪表板（CQD）中上载租户和生成数据


若要充分利用通话质量仪表板（CQD），我们建议你上载租户并生成数据。 有2种类型的租户数据文件，[生成](#upload-building-data-file)和[终结点](#endpoint-data-file)。

你可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例租户数据模板。 有关生成映射的帮助，请参阅为[CQD 创建构建地图](CQD-building-mapping.md)。

从 "CQD 摘要报告" 仪表板中，从 "CQD**设置**" 菜单（位于 CQD 顶部的齿轮图标）中选择 "**租户数据上传**"。 在此，管理员可以上载其组织的建筑物和终结点信息，例如 IP 地址和地理信息的映射、映射每个无线访问点及其 MAC 地址等。

1. 打开 CQD （从团队管理中心或 at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ），然后选择右上角的齿轮图标，然后从 "**摘要报告**" 页面中选择 "**租户数据上传**"。

   ![在上载数据时出现的对话框的屏幕截图](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果你首次访问 CQD，系统将要求你上载数据。 你可以选择 "**立即上载**" 以快速导航到**租户数据上载**页面。

   ![通知用户上载生成数据的横幅的屏幕截图](media/qerguide-image-buildingdatauploadbanner.png)

3. 在 "**租户数据上载**" 页面上，选择 "**浏览**" 以选择数据文件。

4. 选择数据文件后，指定 "**开始日期**"，（可选）指定结束日期。

5. 选择 "**开始日期**" 后，选择 "**上传**" 将文件上传到 CQD。 <br><br>在上载文件之前，它将经过验证。 如果验证失败，则会显示一条错误消息，要求你更正该文件。 下图显示了当数据文件中的列数不正确时出现的错误。

   ![显示生成数据上载错误的对话框示例](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果验证期间没有出现错误，文件上载将成功。 然后，你可以在 "我的上**传**" 表中看到上载的数据文件，其中显示了当前租户在该页面底部的所有上载文件的完整列表。

> [!NOTE]
> 最多可能需要四个小时才能完成处理生成文件。 <br><br> 如果你已经上载了一个生成文件，但需要添加可能已错过或排除的子网，请通过添加新的子网、删除当前文件并重新上载新编辑的文件来修改原始文件。 CQD 中只能有一个活动的构建数据文件。 


## <a name="upload-building-data-file"></a>上载构建数据文件

CQD 中的第一种类型的租户数据文件是**生成**数据文件。 通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。 你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：
  
- 文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。
- 数据文件不包含表格标题行。 数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。
- 文件中的数据类型只能是 String、Integer 或 Boolean。 对于整数数据类型，值必须是一个数值。 布尔值必须是0或1。
- 如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。 空数据字段只是分配一个空字符串值。
- 每一行必须有14列，每一列必须具有相应的数据类型，并且列必须遵循下表中列出的顺序（逗号或制表符分隔）：

**构建数据文件格式**

| 列名称        | 数据类型 | 示例                   | 指引              |
|--------------------|-----------|---------------------------|-----------------------|
| NetworkIP          | String    | 192.168.1.0               | 必需              |
| NetworkName        | String    | 美国/西雅图/西雅图-海-1 | 必需<sup>1</sup>  |
| NetworkRange       | 数字    | 个                        | 必需              |
| BuildingName       | String    | 西雅图-海-1             | 必需<sup>1</sup>  |
| OwnershipType      | String    | 制定                   | 可选              |
| BuildingType       | String    | 终止            | 可选              |
| BuildingOfficeType | String    | 技术               | 可选              |
| 城市               | String    | 西雅图                   | 推荐           |
| ZipCode            | String    | 98001                     | 推荐           |
| 该国            | String    | 我们                        | 推荐           |
| 省/市/自治区              | String    | WA                        | 推荐           |
| 区域             | String    | MSUS                      | 推荐           |
| InsideCorp<sup>2</sup>         | Bool      | 1             | 必需              |
| ExpressRoute<sup>3</sup>       | Bool      | 0             | 必需              |
| VPN                | Bool      | 0                         | 可选              |

<sup>1</sup>虽然 CQD 不是必需的，但模板配置为显示建筑物和网络名称。

<sup>2</sup>此设置可用于反映子网是否位于企业网络内。 你可以自定义其他用途的用法。

<sup>3</sup>此设置可用于反映网络是否使用 Azure ExpressRoute。 你可以自定义其他用途的用法。  

**示例行：**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 网络范围可用于表示 supernet （具有单个路由前缀的若干子网的组合）。 将检查所有新的生成上载，查找任何重叠区域。 如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。 以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。 某些 VPN 实现不能准确报告子网信息。 建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。 每一行可以有相同的建筑物元数据。 例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。
>
> "VPN" 列是可选的，默认值为0。 如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。  请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。


### <a name="supernetting"></a>Supernetting

你可以使用 supernetting （通常称为无类别的域间路由（CIDR））来代替定义每个子网。 *Supernet*是共享单个路由前缀的若干子网的组合。 你可以使用 supernetted 地址，而不是为每个子网添加条目。 支持 Supernetting，但我们不建议使用它。

例如，Contoso 的市场营销大楼由以下子网组成：

-   10.1.0.0/24-第一层
-   10.1.1.0/24-第二层
-   10.1.2.0/24-第三个楼层
-   10.1.3.0/24-第四个楼层

你可以使用 supernetted 地址（在本例中为 10.1.0.0/22），而不是为每个子网添加条目。

-   Network = 10.1.0。0
-   网络范围 = 22

在实现 supernetting 之前，需要考虑以下几点：

-   Supernetting 只能在具有8位到28位掩码的子网映射中使用。

-   Supernetting 花费的时间更少，但它以减少数据丰富的成本为代价。 假设存在涉及子网10.1.2.0 的质量问题。 如果你已实现 supernetting，你将不知道子网所在的位置或网络的类型（例如，实验）。 如果您已为建筑物和上传的地板位置信息定义了所有子网，您将能够看到这种区别。

-   请务必确保 supernetted 地址正确，并且不会捕获不需要的子网。

-   在数据中查找192.168.0.0 非常常见。 对于许多组织，这表示用户在家中。 对于其他人，这是卫星办公室的 IP 地址方案。 如果你的组织具有使用此配置的办事处，则不要将其包含在你的构建文件中，因为很难通过使用[公共子网](quality-of-experience-review-guide.md#common-subnets)来区分家庭网络和内部网络。 

> [!IMPORTANT]
> 网络范围可用于表示 supernet。 将检查所有新生成数据文件上是否有任何重叠区域。 如果你以前上载了一个生成文件，你应该下载当前文件并再次上载它以识别任何重叠并解决问题。 以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。

### <a name="vpn"></a>VPN

客户端发送给 Microsoft 365 或 Office 365 （CQD 数据来源）的体验质量（QoE）数据，包括 VPN 标志。 CQD 将看到这是第一个 VPN 和第二个 VPN 维度。 但是，此标志依赖于 VPN 供应商向 Windows 报告，VPN 网络适配器已注册为远程访问适配器。 并非所有 VPN 供应商都正确注册远程访问适配器。 因此，你可能无法使用内置的 VPN 查询筛选器。 可通过两种方法在构建信息文件中容纳 VPN 子网：

- 通过在此字段中输入 VPN 子网的 "VPN" 来定义**网络名称**。

  ![使用网络名称显示 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnnetworkname.png)

- 通过在此字段中输入 VPN 子网的 "VPN" 来定义**建筑物名称**。

  ![显示使用建筑物名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnbuildingname.png)

> [!IMPORTANT]
> 某些 VPN 实现不会准确报告子网信息。 如果你的报告中出现这种情况，我们建议在将 vpn 子网添加到构建文件时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络，而不是子网的一个条目。 每一行可以有相同的建筑物元数据。 例如，对于 172.16.18.0/24，而不是一行，您有253行，每个地址对应于从 172.16.18.1/32 到 172.16.18.254/32 的每个地址，包括一行。


> [!NOTE]
> 当基础互联网连接为无线时，misidentify 将网络连接称为有线的 VPN 连接。 在通过 VPN 连接查看高质量时，无法假定已准确识别连接类型。


## <a name="endpoint-data-file"></a>终结点数据文件

另一种类型的 CQD 租户数据文件是**终结点**数据文件。 在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。 你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：

- 文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。
- 数据文件的内容不包含表格标题。 数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。
- 所有六列仅使用字符串数据类型。 允许的最大长度为64个字符。
- 数据字段可以为空，但仍须由制表符或逗号分隔。 空数据字段只是分配一个空字符串值。
- 终结点必须是唯一的，否则上传将失败。 如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。
- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。 它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。
- 每行必须有六列，并且列必须按以下顺序排列：

  **字段顺序：**

终结点、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **示例行：**

`1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  



## <a name="update-a-building-file"></a>更新生成文件

在收集生成和子网信息时，管理员通常会在一段时间内将生成文件上载到多个迭代中，并在新子网可用时添加新的子网和生成信息。 出现这种情况时，你需要重新上载你的构建文件。 此过程类似于上一节中所述的初始上载，还有一些例外，如下部分所述。

> [!Important]
> 一次只能有一个生成文件处于活动状态。 多个生成文件不具有累积性。

## <a name="add-net-new-subnets"></a>添加全新的子网

有时，你需要将新的子网添加到 CQD 中的子网，而不是你的网络拓扑的一部分。 若要添加全新的子网，请在 CQD 中的**租户数据上传**页面执行以下操作：

2.  如果尚未有最新的副本，请下载原始文件。
1.  删除 CQD 中的当前文件。
1.  编辑原始构建文件，并提供在获取网络新子网之前至少一天出现的结束日期。
1.  将新的全新子网附加到原始生成文件。
1.  上载新修改的生成文件，并将开始日期设置为上一个生成文件结束后的一天。

## <a name="add-missing-subnets"></a>添加缺少的子网

在上载托管网络的生成信息后，每个托管网络都应具有一个建筑物关联。 但是，这并不总是这样。通常，缺少几个子网。 若要查找这些缺少的网络，请查看 CQD 中的 "**体验质量报告**" 页面上**缺少的子网报告**。 这将显示包含10个或更多音频流的所有子网，这些流在建筑物数据文件中未定义且标记为外部。 确保此列表中没有托管网络。 如果缺少子网，请使用以下过程更新原始生成数据文件，并将其重新上载到 CQD。

1. 转到 CQD 中的**租户数据上传**页面。
1. 如果尚未有最新的副本，请下载原始文件。
1. 删除 CQD 中的当前文件。
1. 将新子网追加到原始文件。
1. 上载构建文件。 请务必先将开始日期设置为至少八个月，这样 CQD 将处理历史记录数据。


> [!IMPORTANT]
> 你需要将租户 ID 作为**第二租户 id**的查询筛选器添加到此报表，以筛选报表以仅查看你的组织的租户数据。 否则，报表将显示联合子网。

> [!NOTE] 
> 请确保将 "月" 报表筛选器调整为当前月份。 选择 "**编辑**"，然后调整 "**月**" 报表筛选器以保存新的默认月份。


## <a name="related-topics"></a>相关主题

[为 CQD 创建建筑地图](CQD-building-mapping.md)

[改善和监控团队的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
