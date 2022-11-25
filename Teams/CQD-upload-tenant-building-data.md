---
title: 在通话质量仪表板 (CQD) 上传租户和生成数据
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何在通话质量仪表板 (CQD) 上传租户和生成数据。
ms.openlocfilehash: d999098a2d920c8709ae1878ac94648451c00f0b
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163222"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>在通话质量仪表板 (CQD) 上传租户和生成数据


若要充分利用通话质量仪表板 (CQD) ，建议上传租户并生成数据。 有 2 种类型的租户数据文件： [生成](#upload-building-data-file) 和 [终结点](#endpoint-data-file)。

可以 [在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例租户数据模板。 有关构建映射的帮助，请阅读 [为 CQD 创建构建图](CQD-building-mapping.md)。

在“CQD 摘要报表”仪表板中，从“CQD **设置”** 菜单中选择“**租户数据上传**”， (CQD) 顶部的齿轮图标。 在此处，管理员可以上传其组织的生成和终结点信息，例如 IP 地址和地理信息的映射、映射每个无线接入点及其 MAC 地址等。

1. 从 Teams 管理中心或 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 打开 CQD (，然后选择右上角的齿轮图标，并从 **“摘要报告**”页中选择“**租户数据上传**”。

   ![上传数据时显示的对话框的屏幕截图。](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果这是你第一次访问 CQD，系统会要求你上传建筑数据。 可以选择“ **立即上传** ”以快速导航到 **“租户数据上传** ”页。

   ![通知用户上传生成数据的横幅的屏幕截图。](media/qerguide-image-buildingdatauploadbanner.png)

3. 在“ **租户数据上传** ”页上，选择“ **浏览** ”以选择数据文件。

4. 选择数据文件后，指定 **开始日期** ，还可以指定结束日期。

5. 选择“ **开始日期**”后，选择“ **上传** ”，将文件上传到 CQD。 <br><br>在上传文件之前，会对其进行验证。 如果验证失败，将显示一条错误消息，要求更正文件。 下图显示了数据文件中的列数不正确时发生的错误。

   ![显示生成数据上传错误的对话框示例。](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果在验证过程中未发生错误，文件上传将成功。 然后，可以在 **“我的上传** ”表中看到上传的数据文件，该表显示该页面底部当前租户的所有已上载文件的完整列表。

> [!NOTE]
> 完成处理生成文件最多可能需要 4 小时。 <br><br> 如果已上传生成文件，并且需要添加可能已错过或排除的子网，请通过添加新子网来修改原始文件，删除当前文件，然后重新上传新编辑的文件。 CQD 中只能有一个活动生成数据文件。 


## <a name="upload-building-data-file"></a>上传生成数据文件

CQD 中的第一种类型的租户数据文件是 **Building** 数据文件。 “子网”列是通过展开“Network+NetworkRange”列，然后将“子网”列联接到呼叫记录的“第一个子网”或“第二个子网”列来派生的，以显示“建筑物”、“城市”、“国家/地区”或“区域”信息。 上传的数据文件的格式必须满足以下条件才能在上传前通过验证检查：
  
- 该文件必须是 .tsv 文件， (列由 TAB) 分隔，或者.csv文件 (列用逗号) 分隔。

- 数据文件不包含表标题行。 数据文件的第一行应是真实的数据，而不是像“网络”这样的标题标签。

- 文件中的数据类型只能为字符串、整数或布尔值。 对于 Integer 数据类型，该值必须是数值。 布尔值必须为 0 或 1。

- 如果列使用 String 数据类型，则数据字段可以为空，但仍必须用制表符或逗号分隔。 空数据字段只分配一个空的 String 值。

- 每个租户数据文件有 1，000，000 个扩展行限制。

- 每行必须有 15 列，每列必须具有适当的数据类型，并且列必须按下表中列出的顺序 (逗号或制表符分隔) ：

  **生成数据文件格式**
  
  | 列名称        | 数据类型 | 示例                   | 指引              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | 必需              |
  | NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | 必需<sup>1</sup>  |
  | NetworkRange       | 数字    | 26                        | 必需              |
  | BuildingName       | String    | SEATTLE-SEA-1             | 必需<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | 可选<sup>4</sup>  |
  | BuildingType       | String    | IT 终止            | 可选<sup>4</sup>  |
  | BuildingOfficeType | String    | 工程               | 可选<sup>4</sup>  |
  | 城市               | String    | 西雅图                   | 推荐           |
  | ZipCode            | String    | 98001                     | 推荐           |
  | 国家            | String    | 我们                        | 推荐           |
  | 省/市/自治区              | String    | WA                        | 推荐           |
  | 区域             | String    | MSUS                      | 推荐           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | 必需              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | 必需              |
  | VPN                | Bool      | 0                         | 可选              |

  <sup>1</sup> 虽然 CQD 不要求模板，但模板配置为显示“生成”和“网络名称”。

  <sup>2</sup> 此设置可用于反映子网是否在公司网络内。 可以出于其他目的自定义使用情况。

  <sup>3</sup> 此设置可用于反映网络是否使用 Azure ExpressRoute。 可以出于其他目的自定义使用情况。  
  
  <sup>4</sup> 虽然这些可选列的命名是为了建议你可能需要使用哪些值来填充它们，但你可以自定义用法以用于其他目的。 例如：网络优先级 - `Tier 1, Tier 2, Tier 3` 

  **示例行：**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 网络范围可用于表示) 具有单个路由前缀的多个子网的超网 (组合。 将检查所有新的生成上传是否存在任何重叠范围。 如果之前已上传生成文件，则应下载当前文件并重新上传，以识别任何重叠并修复问题，然后再再次上传。 以前上传的文件中的任何重叠都可能导致在报表中错误地将子网映射到建筑物。 某些 VPN 实现不会准确报告子网信息。 
>
> VPN 列是可选的，默认为 0。 如果 VPN 列的值设置为 1，则由该行表示的子网将完全展开，以匹配子网中的所有 IP 地址。 请谨慎使用此方法，并且仅对 VPN 子网使用，因为完全扩展这些子网将对涉及生成数据的查询的查询时间产生负面影响。 如果子网的扩展导致超出扩展行限制 1，000，000，则不会接受生成文件。


### <a name="supernetting"></a>Supernetting

可以使用超级网络（通常称为无类Inter-Domain路由 (CIDR）) 来代替定义每个子网。 *超级网络* 是共享单个路由前缀的多个子网的组合。 可以使用超网地址，而不是为每个子网添加条目。 支持超网络，但我们不建议使用它。

例如，Contoso 的营销构建由以下子网组成：

-   10.1.0.0/24 - 一楼
-   10.1.1.0/24- 二楼
-   10.1.2.0/24-三楼
-   10.1.3.0/24 - 四楼

可以使用超网地址（在此示例中为 10.1.0.0/22），而不是为每个子网添加条目。

-   网络 = 10.1.0.0
-   网络范围 = 22

以下是在实现超网之前需要考虑的一些事项：

-   超网络只能在具有 8 位到 28 位掩码的子网映射中使用。

-   超网络预先花费的时间更少，但代价是降低数据的丰富性。 假设子网 10.1.2.0 存在质量问题。 如果实现了超网络，则不知道子网在生成中的哪个位置，也不知道子网 (的网络类型，例如实验室) 。 如果为建筑物定义了所有子网并上传了楼层位置信息，则可以看到该区别。

-   请务必确保超网地址正确且不会捕获不需要的子网。

-   在数据中找到 192.168.0.0 是很常见的。 对于许多组织，这表示用户在家中。 对于其他人，这是附属办公室的 IP 地址方案。 如果你的组织确实有使用此配置的办公室，请不要将其包含在生成文件中，因为很难通过使用 [通用子网](quality-of-experience-review-guide.md#common-subnets)来区分家庭网络和内部网络。 

> [!IMPORTANT]
> 网络范围可用于表示超级网络。 将检查所有新的生成数据文件上传是否存在任何重叠范围。 如果之前已上传生成文件，则应下载当前文件并再次上传，以识别任何重叠并修复问题。 以前上传的文件中的任何重叠都可能导致在报表中错误地将子网映射到建筑物。

### <a name="vpn"></a>VPN

客户端发送到 Microsoft 365 或 Office 365（CQD 数据的来源）的体验质量 (QoE) 数据包括 VPN 标志。 CQD 会将此视为第一个 VPN 和第二个 VPN 维度。 但是，此标志依赖于 VPN 供应商向 Windows 报告注册的 VPN 网络适配器是远程访问适配器。 并非所有 VPN 供应商都正确注册远程访问适配器。 因此，可能无法使用内置 VPN 查询筛选器。 使用上面讨论的 VPN 列准确标记和标识 VPN 子网。 最好是标记 VPN 网络，以便在报表中轻松识别。 下面是有关如何标记 VPN 子网的两个示例：

- 通过在此字段中为 VPN 子网输入“VPN”来定义 **网络名称** 。

  ![显示使用网络名称的 VPN 的 QCD 报表屏幕截图。](media/qerguide-image-vpnnetworkname.png)

- 通过在此字段中为 VPN 子网输入“VPN”来定义 **建筑物名称** 。

  ![显示使用生成名称的 VPN 的 QCD 报表屏幕截图。](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> 已知当基础连接为无线时，VPN 连接错误地将网络连接类型视为有线连接。 通过 VPN 连接查看质量时，无法假设已准确识别连接类型。

## <a name="endpoint-data-file"></a>终结点数据文件

另一种类型的 CQD 租户数据文件是 **终结点** 数据文件。 这些列值用于调用记录的“第一个客户端终结点名称”或“第二个客户端终结点名称”列中，以显示 Endpoint Make、Model 或 Type 信息。 上传的数据文件的格式必须满足以下条件才能在上传前通过验证检查：

- 该文件必须是 .tsv 文件， (列由 TAB) 分隔，或者.csv文件 (列用逗号) 分隔。

- 数据文件的内容不包括表标题。 数据文件的第一行应是真实数据，而不是像“EndpointName”这样的标头标签。

- 所有七列仅使用字符串数据类型。 允许的最大长度为 64 个字符。

- 条目区分大小写;EndpointName **ABC123** 将被视为与 EndpointName **abc123** 中唯一的。

- 数据字段可以为空，但仍必须用制表符或逗号分隔。 空数据字段只分配一个空的 String 值。

- EndpointName 必须是唯一的，否则上传失败。 如果存在重复行或两行使用同一 EndpointName，则冲突将导致不正确的联接。

- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。 它们可以是空字符串或值，例如“IT 部门指定 2018 笔记本电脑”或“资产标记 5678”。

- 每行必须有七列，列必须按以下顺序排列：

  **字段顺序：**

  EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **示例行：**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>更新生成文件

在收集生成和子网信息时，管理员通常会在多次迭代中上传生成文件，并在可用时添加新子网及其生成信息。 发生这种情况时，需要重新上传生成文件。 此过程与上一部分中所述的初始上传类似，但以下部分有一些例外。

> [!Important]
> 一次只能有一个生成文件处于活动状态。 多个生成文件不是累积的。

## <a name="add-net-new-subnets"></a>添加新子网

有时，需要将最初不属于网络拓扑的净新子网添加到 CQD。 若要添加新子网，请在 CQD 中的 **“租户数据上传** ”页中执行以下操作：

1.  如果还没有最新的副本，请下载原始文件。

1.  删除 CQD 中的当前文件。

1.  编辑原始生成文件，并提供在获取净新子网之前至少一天的结束日期。

1.  将新子网追加到原始生成文件。

1.  上传新修改的生成文件，并设置上一个生成文件结束后一天的开始日期。

## <a name="add-missing-subnets"></a>添加缺少的子网

上传托管网络的生成信息后，每个托管网络都应具有建筑物关联。 但是，情况并不总是如此：通常，会丢失一些子网。 若要查找这些缺失的网络，请查看 CQD 中“**体验质量报告**”页上的 **“缺失子网** 报告”。 这将显示具有 10 个或更多音频流的所有子网，这些流未在生成数据文件中定义，并且标记为外部。 确保此列表中没有托管网络。 如果缺少子网，请使用以下过程更新原始生成数据文件并将其重新上传到 CQD。

1. 转到 CQD 中的 **“租户数据上传** ”页。

1. 如果还没有最新的副本，请下载原始文件。

1. 删除 CQD 中的当前文件。

1. 将新子网追加到原始文件。

1. 上传生成文件。 请务必将开始日期设置为至少 8 个月前，以便 CQD 处理历史数据。


> [!IMPORTANT]
> 需要向此报表添加租户 ID 作为 **查询** 筛选器，以便筛选报表以仅查看组织的租户数据。 否则，报表将显示联合子网。

> [!NOTE] 
> 请务必将“月份年”报表筛选器调整为当前月份。 选择 **“编辑**”，然后调整“ **月份年份** ”报表筛选器以保存新的默认月份。


## <a name="related-topics"></a>相关主题

[为 CQD 创建构建图](CQD-building-mapping.md)

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[ (CQD) 设置通话质量仪表板 ](turning-on-and-using-call-quality-dashboard.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
