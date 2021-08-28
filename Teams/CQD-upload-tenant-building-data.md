---
title: 'Upload CQD 仪表板中的"呼叫质量仪表板" (租户和) '
ms.author: serdars
author: SerdarSoysal
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
description: 了解如何在 CQD 仪表板的呼叫质量仪表板 (租户和) 。
ms.openlocfilehash: 847abe5aeb18f7cb19bdad9213334f119c101e20
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583696"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Upload CQD 仪表板中的"呼叫质量仪表板" (租户和) 


若要在 CQD (质量仪表板) ，建议上传租户和建筑物数据。 有 2 种类型的租户数据文件，[即"生成"和"](#upload-building-data-file)[终结点"。](#endpoint-data-file)

可以在此处下载示例租户数据 [模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。 有关建筑物映射的帮助，请阅读 [为 CQD 创建建筑地图](CQD-building-mapping.md)。

在 CQD 摘要报表仪表板中，从 CQD 设置 菜单中选择"租户数据Upload"， (CQD 报表顶部的齿轮图标) 。 在这里，管理员可以上传其组织的建筑物和终结点信息，例如 IP 地址和地理信息映射、映射每个无线接入点及其 MAC 地址，等等。

1. 从 Teams 管理中心或) 打开 CQD (，然后选择右上角的齿轮图标，然后从"摘要报表"页Upload"租户数据"。 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)  

   ![上传数据时出现的对话框的屏幕截图](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果这是您第一次访问 CQD，将要求您上传建筑物数据。 可以选择 **"Upload"** 以快速导航到"租户数据 **Upload页。**

   ![通知用户上传建筑物数据的横幅屏幕截图](media/qerguide-image-buildingdatauploadbanner.png)

3. 在"**租户数据Upload** 页上，选择 **"浏览**"以选择数据文件。

4. 选择数据文件后 **，指定开始日期** ，并选择性地指定结束日期。

5. 选择"**开始日期"** 后 **，Upload** 文件上传到 CQD。 <br><br>在上传文件之前，会验证该文件。 如果验证失败，则会显示一条错误消息，要求更正文件。 下图显示了当数据文件中的列数不正确时发生的错误。

   ![显示建筑物数据上传错误的对话框示例](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果在验证期间未发生错误，文件上传会成功。 然后，可以在"我的上传"表中查看上传的数据文件，其中显示页面底部的当前租户的所有已上传文件的完整列表。

> [!NOTE]
> 可能需要 4 小时才能完成建筑物文件的处理。 <br><br> 如果已上传建筑物文件，并且需要添加可能错过或排除的子网，请通过添加新子网来修改原始文件，删除当前文件，然后重新上传新编辑的文件。 CQD 中只能有一个活动的建筑物数据文件。 


## <a name="upload-building-data-file"></a>Upload生成数据文件

CQD 中第一种类型的租户数据文件是 **建筑物** 数据文件。 通过展开"Network+NetworkRange"列，然后将"子网"列联接到呼叫记录的"第一个子网"或"第二个子网"列以显示"建筑物、城市、国家/地区"或"区域"信息，派生子网列。 上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：
  
- 该文件必须是 .tsv 文件， (列由 Tab 键分隔) 或 .csv 文件 (以逗号分隔) 。

- 数据文件不包括表标题行。 数据文件的第一行应该是实际数据，而不是标头标签（如"网络"）。

- 该文件中的数据类型只能是字符串、整数或布尔值。 对于整数数据类型，该值必须是数值。 布尔值必须为 0 或 1。

- 如果列使用字符串数据类型，则数据字段可以为空，但仍必须以制表符或逗号分隔。 空数据字段只分配一个空的字符串值。

- 每个租户数据文件有 1，000，000 个扩展行限制。

- 每行必须包含 15 列，每一列必须具有相应的 数据类型，列必须按照下表中列出的顺序（逗号或制表符 (分隔) ：

  **构建数据文件格式**
  
  | 列名称        | 数据类型 | 示例                   | 指引              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | 必需              |
  | NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | 必需<sup>1</sup>  |
  | NetworkRange       | 数字    | 26                        | 必需              |
  | BuildingName       | String    | SEATTLE-SEA-1             | 必需<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | 可选              |
  | BuildingType       | String    | IT 终止            | 可选              |
  | BuildingOfficeType | String    | 工程               | 可选              |
  | 城市               | String    | 西雅图                   | 推荐           |
  | ZipCode            | String    | 98001                     | 推荐           |
  | 国家/地区            | String    | 美国                        | 推荐           |
  | 省/市/自治区              | String    | WA                        | 推荐           |
  | 区域             | String    | MSUS                      | 推荐           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | 必需              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | 必需              |
  | VPN                | Bool      | 0                         | 可选              |

  <sup>1</sup> 尽管 CQD 不需要，但模板配置为显示"建筑物"和"网络名称"。

  <sup>2</sup> 此设置可用于反映子网是否在企业网络中。 可以出于其他目的自定义使用情况。

  <sup>3</sup> 此设置可用于反映网络是否使用 Azure ExpressRoute。 可以出于其他目的自定义使用情况。  

  **示例行：**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 网络范围可用于表示具有单个路由前缀的 (子网的超网络) 。 所有新建筑物上载都将检查是否有重叠的范围。 如果以前上传过一个建筑物文件，应下载当前文件，然后重新上传该文件，以识别任何重叠，并修复问题，然后再重新上传。 以前上传的文件的任何重叠都可能导致报告中子网与建筑物之间的映射错误。 某些 VPN 实现无法准确报告子网信息。 
>
> VPN 列是可选的，默认为 0。 如果 VPN 列的值设置为 1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。 请尽量少用，仅对 VPN 子网使用，因为完全扩展这些子网会对涉及生成数据的查询的查询时间产生负面影响。 如果子网的扩展导致超出 1，000，000 的扩展行限制，则不接受生成文件。


### <a name="supernetting"></a>Supernetting

可以使用超级网络（通常称为无Inter-Domain路由 (CIDR，) 来取代定义每个子网。 超级 *网络* 是共享单个路由前缀的几个子网的组合。 可以使用超网络地址，而不是添加每个子网的条目。 支持超网络功能，但我们不建议使用它。

例如，Contoso 的营销大楼由以下子网决定：

-   10.1.0.0/24 — 一楼
-   10.1.1.0/24 — 二楼
-   10.1.2.0/24 — 三楼
-   10.1.3.0/24 — 第四层

可以使用超网络地址（本示例中为 10.1.0.0/22）而不是添加每个子网的条目。

-   网络 = 10.1.0.0
-   网络范围 = 22

实现超网之前，需要考虑以下一些操作：

-   超级网络只能在具有 8 位到 28 位掩码的子网映射中使用。

-   超网占用的前面时间更少，但代价是降低数据的丰富性。 假设存在涉及子网 10.1.2.0 的质量问题。 如果实现了超网络化，则不知道子网在建筑物中的什么位置，或者它 (类型的网络，例如实验室) 。 如果已定义建筑物的所有子网和上载的楼层位置信息，则能够看到这种区别。

-   确保超网络地址正确且不会捕获不需要的子网，这一点很重要。

-   在数据中查找 192.168.0.0 很常见。 对于许多组织，这表示用户在家里。 对于其他人，这是卫星办公室的 IP 地址方案。 如果组织有使用此配置办公室，请不要将其包括在建筑物文件中，因为使用公共子网难以区分家庭网络和内部 [网络](quality-of-experience-review-guide.md#common-subnets)。 

> [!IMPORTANT]
> 网络范围可用于表示超网络。 所有新的建筑物数据文件上传都将检查是否有重叠的范围。 如果以前上传过一个建筑物文件，应下载当前文件并再次上传该文件，以识别任何重叠并解决问题。 以前上传的文件的任何重叠都可能导致报告中子网与建筑物之间的映射错误。

### <a name="vpn"></a>VPN

QoE (质量) 客户端发送到 Microsoft 365 或 Office 365 的数据（CQD 数据的来源位置）包括 VPN 标志。 CQD 将看到此为第一个 VPN 维度和第二个 VPN 维度。 但是，此标志依赖于 VPN 供应商向Windows注册的 VPN 网络适配器是远程访问适配器的报告。 并非所有 VPN 供应商都正确注册远程访问适配器。 因此，可能无法使用内置的 VPN 查询筛选器。 使用上面讨论的 VPN 列准确标记和标识 VPN 子网。 此外，为 VPN 网络添加标签也是一种很好的做法，便于在报告中识别。 下面是如何标记 VPN 子网的两个示例：

- 在 VPN **子网的** 此字段中输入"VPN"，定义网络名称。

  ![显示使用网络名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnnetworkname.png)

- 在 VPN **子网的** 此字段中输入"VPN"，定义建筑物名称。

  ![显示使用建筑物名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> VPN 连接已知在基础连接为无线时将网络连接类型错误识别为有线。 通过 VPN 连接查看质量时，无法假定已准确标识连接类型。

## <a name="endpoint-data-file"></a>终结点数据文件

另一种类型的 CQD 租户数据文件是 **终结点** 数据文件。 列值用于调用记录的"第一个客户端终结点名称"或"第二个客户端终结点名称"列中，以显示终结点制造、模型或类型信息。 上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：

- 该文件必须是 .tsv 文件， (列由 Tab 键分隔) 或 .csv 文件 (以逗号分隔) 。

- 数据文件的内容不包括表标题。 数据文件的第一行应该是实际数据，而不是标头标签（如"EndpointName"）。

- 所有七列都仅使用字符串数据类型字符串。 允许的最大长度为 64 个字符。

- 数据字段可以为空，但仍必须以制表符或逗号分隔。 空数据字段只分配一个空的字符串值。

- EndpointName 必须唯一，否则上传失败。 如果存在重复的一行或两行使用相同的 EndpointName，则冲突将导致联接错误。

- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。 它们可以为空字符串或值，例如"IT 部门指定的 2018 笔记本电脑"或"资产标记 5678"。

- 每行必须有七列，列必须按以下顺序排列：

  **域顺序：**

  EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **示例行：**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>更新建筑物文件

收集建筑物和子网信息时，管理员通常会在一段时间的多次迭代中上传该建筑物文件，并添加新的子网及其建筑物信息（可用时）。 发生这种情况时，需要重新上传建筑物文件。 此过程与上一部分中所述的初始上传类似，但以下部分介绍了一些例外。

> [!Important]
> 一次只能有一个建筑物文件处于活动状态。 多个建筑物文件不是累积的。

## <a name="add-net-new-subnets"></a>添加新子网

有时，需要向 CQD 添加最初不是网络拓扑一部分的新子网。 若要添加新子网，请从 CQD 中的"租户数据 **"Upload** 页执行以下操作：

1.  下载原始文件（如果还没有最新副本）。

1.  删除 CQD 中的当前文件。

1.  编辑原始建筑物文件，并提供在获取新子网之前至少一天的结束日期。

1.  将网络新子网追加到原始建筑物文件。

1.  Upload新修改的建筑物文件，将开始日期设置为上一个建筑物文件结束后的一天。

## <a name="add-missing-subnets"></a>添加缺少的子网

上传托管网络的建筑物信息后，每个托管网络都应具有建筑物关联。 但是，情况并非总是如此;通常，会遗漏几个子网。 若要查找这些缺失的网络，请查看CQD 中"体验质量报告 **"页上的**"缺少子网报告"。 这会向所有子网显示 10 个或多个音频流，这些音频流未在建筑物数据文件中定义，并且被标记为外部。 请确保此列表中没有托管网络。 如果缺少子网，请使用以下过程更新原始建筑物数据文件，并将其重新上传到 CQD。

1. 转到 CQD **Upload** 租户数据"页。

1. 下载原始文件（如果还没有最新副本）。

1. 删除 CQD 中的当前文件。

1. 将新子网追加到原始文件。

1. Upload生成文件。 请确保将开始日期设置为至少八个月之前，以便 CQD 将处理历史数据。


> [!IMPORTANT]
> 需要将租户 ID 作为第二租户 **ID** 的查询筛选器添加到此报表，以筛选报表，以便仅查看组织的租户数据。 否则，报告会显示联合子网。

> [!NOTE] 
> 请务必将"月年"报表筛选器调整为当前月份。 选择 **"编辑**"，然后调整 **"月份年份** "报表筛选器以保存新的默认月份。


## <a name="related-topics"></a>相关主题

[为 CQD 创建建筑地图](CQD-building-mapping.md)

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置 CQD (呼叫质量) ](turning-on-and-using-call-quality-dashboard.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)
