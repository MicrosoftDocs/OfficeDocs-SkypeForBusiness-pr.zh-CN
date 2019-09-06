---
title: 使用 Skype for business 服务器的呼叫质量仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：了解如何使用通话质量仪表板。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 09eb8bdae508ff9a5fe39fec67b0f440859efad0
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774702"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>使用 Skype for business 服务器的呼叫质量仪表板

**摘要：** 了解如何使用通话质量仪表板。 通话质量仪表板是 Skype for business 服务器的工具。

通话质量仪表板（CQD）允许 IT 专业人员使用聚合数据通过比较用户组的统计信息来识别产生媒体质量问题的问题，从而确定趋势和模式。 CQD 不专注于解决单个呼叫问题，而是确定适用于多个用户的问题和解决方案。

## <a name="call-quality-dashboard-user-guide"></a>呼叫质量仪表板用户指南

CQD 是一种 web 门户，用于快速创建和组织基于体验质量（QoE）数据的报表。 CQD 部署一个 SSAS 多维数据集以聚合 QoE 指标数据库中的数据，并允许管理员实时创建和修改报表或进行调查。 虽然可以使用 Excel 直接连接到多维数据集，但门户已针对涉及 QoE 数据的几个工作流进行了优化。 数据包括：

- 用于快速访问的缓存报表数据
- 指向信息共享和发布的报表页面的深层链接
- 简化的报表编辑和创建以及报表说明的可编辑元数据。

此外，CQD 还会公开 web Api，该 Api 允许用户以编程方式访问多维数据集数据以在自定义仪表板中使用。

### <a name="feature-overview"></a>功能概述

当您访问 "呼叫质量" 仪表板时，将看到以下屏幕：

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. "摘要窗格" 是指可以找到 "报表集" （向右）的上下文。
2. 单击摘要 PaneReport 中的 "编辑" 以设置级别属性（包括 Y 轴高度）。
3. 痕迹导航可帮助你在报表集层次结构中标识你的当前位置。
4. 带有子报表的报表显示为蓝色链接。 单击链接以向下钻取到子报表。

将鼠标移动到条形图和趋势线上以显示详细值。 具有焦点的报表显示 "操作" 菜单： "编辑"、"克隆"、"删除" 和 "下载"。

### <a name="default-reports"></a>默认报告

首次访问 "呼叫质量" 仪表板门户时，将自动创建一个默认报表集。 这些报告有时称为系统报告。 你可以通过创建新的同辈报表和子报表来自由修改或删除这些报表或对其进行扩展。

在顶级，"音频流每月趋势" 报表显示所有音频流的每月趋势。 将鼠标移动到条形图中的条形上，以显示条形图所表示的数据的更详细视图。 单击音频流的 "每月趋势" 报表的标题以导航到 "托管和非托管音频流" 报表，其中的报表在托管和非托管调用之间拆分。 管理呼叫是从公司防火墙内通过有线连接进行的呼叫。 非托管通话包括从公司防火墙外部发出的呼叫以及通过 Wi-fi 发出的所有通话。

另一个顶级报表称为 "用户报告的通话质量评估直方图"。 通话质量评级是 Skype for Business 用户在通话结束时给出的数字，用于指示呼叫的质量。 分级号码的范围从1到5，1是最差，5是最佳。 直方图显示一个月中具有指示评级的音频通话数。

单击任何报表的标题以导航到报表，其中包含数据的更多筛选器。 在系统报告中，每个子报告显示其父报告中的一部分数据。 解决问题的模型很简单：调查哪些子报表的数据或趋势表明问题已被限制，并逐渐缩小问题空间。 创建子报表的功能允许你调查有关特定数据趋势的原因的推测。

### <a name="create-and-edit-reports"></a>创建和编辑报表

单击报表的 "操作" 菜单中的 "编辑" 以查看报表编辑器。 每个报告都可以通过对多维数据集进行查询得到。 报告是其查询返回的数据的可视化形式。 报表编辑器可帮助你编辑报表的这些查询和显示选项。 当您打开 "报表编辑器" 时，将看到：

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. 左侧窗格中选择了维度、度量和筛选器。 将鼠标悬停在某个现有值上以显示 "x" 按钮，该按钮允许删除值。 单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加新的维度、度量值或筛选器。
2. 顶部显示了图表自定义选项。
3. 报告编辑器中提供了报告预览。
4. 可以使用底部的 "编辑" 框创建详细的报表说明。

### <a name="sparklines-in-tables"></a>表中的迷你图

将 StartDate.Month 添加为一个维度，且数据以表格形式呈现为趋势时，可以在表格单元格内显示条形图和迷你图。 将鼠标指针移动到条形图和迷你图上，以显示各个月份的值。

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

为了显示条形图和迷你图，必须选中报表编辑器顶部的 "显示迷你图" 复选框。 这将选择趋势选项，并将 Month 下移到最后一个维度，也可以通过单击月份并使用向上和向下箭头，将 "开始日期" 或 "向下键"。

### <a name="settings"></a>设置

"设置" 菜单包含指向有用页面（如 "系统运行状况" 和 "关于页面"）的链接，位于仪表板的右上角。

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

是否显示说明和时间戳由单个用户决定，并且这些设置仅影响个人的仪表板版本，不要修改报表集或其他用户所看到的内容。 清除缓存会导致所有查询从多维数据集中重新加载其数据，而还原默认值将删除所有用户创建或修改的报表，并重新创建系统报表集—用户首次登录时将看到的内容。

用户仪表板链接显示用户可以在其中查看 CQD 的其他用户并浏览其报告的页面。 若要共享报表集，请复制 URL 栏中的链接，并将其与另一个 CQD 用户共享。 此链接与其他用户将在用户仪表板链接页面中的用户用户名下看到的链接相同。

### <a name="supplying-subnet-information"></a>提供子网信息

如果将特定于站点的信息输入到存档数据库以提供子网间映射信息（例如，有线/无线呼叫质量，通过构建），则可能会泄漏其他信息。

至少，完成下表以创建这些报表：

- CqdBuilding
- CqdNetwork

可在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息以进行进一步的筛选和向下钻取。

用于这些表的数据定义如下：

**CqdBuilding**

|列|数据类型|是否允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |否 |CqdBuilding 表的主键。 |
|BuildingName |varchar(80) |否 |大楼名称。 |
|BuildingShortName |varchar(10) |否 |大楼名称的简短版本。 |
|OwnershipTypeId |int |否 |外键，匹配 CqdBuildingOwners 表中的其中一个条目。 |
|BuildingTypeId |int |否 |外键，匹配 CqdBuildingType 表中的其中一个条目。 |
|纬度 |float |是 |大楼的纬度。 |
|经度 |float |是 |大楼的经度。 |
|CityName |varchar(30) |是 |大楼所在的城市名称。 |
|ZipCode |varchar(25) |是 |大楼所在的邮编。 |
|CountryShortCode |varchar(2) |是 |大楼所在的国家/地区的 ISO 3166-1 alpha-2 代码。 |
|StateProvinceCode |varchar(3) |是 |生成所在的州/省的三个字母的缩写。 |
|InsideCorp |bit |是 |位表示建筑物是否是企业网络的一部分。 |
|BuildingOfficeType |nvarchar(150) |是 |大楼办公室类型的说明。 |
|区域 |varchar(25) |是 |大楼所在的地区。 |
|||||

**CqdNetwork**

|列|数据类型|是否允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|网络 |varchar(25) |否 |子网地址。 |
|NetworkRange |tinyint |是 |子网掩码。 |
|NetworkNameID |int |是 |可选地映射到 CqdNetworkName 表中的一行。 |
|BuildingKey |int |是 |外键，匹配 CqdBuilding 表中的其中一个条目。 |
|UpdatedDate |datetime |否 |条目最后更新的日期时间。 |
||||||

默认情况下，下一个表包含一个条目（0，"Unknown"）。

**CqdBuildingType**

|列|数据类型|是否允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |否 |CqdBuildingType 表的主键。 |
|BuildingTypeDesc |char(18) |否 |大楼类型说明。 |
|||||

默认情况下，下一个表包含一个条目（0、"Unknown"、0、null）。

**CqdBuildingOwnershipType**

|列|数据类型|是否允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |否 |CqdBuildingOwnershipType 表的主键。 |
|OwnershipTypeDesc |varchar(25) |否 |所有权类型说明。 |
|LeaseInd |tinyint |是 |引用 CqdBuildingOwnershipType 表中其他行的索引，用于确定租用的大楼。 |
|所有者 |varchar(50) |是 |大楼所有者。 |
|||||

默认情况下，下一个表包含一个条目（0、"Unknown"、0、null）。

**CqdBssid**

|列|数据类型|是否允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |否 |CqdBssid 表的主键。 是 WiFi 接入点的 BSSID。 |
|ess |nvarchar(50) |是 |WiFi 接入点控制器信息。 |
|phy |nvarchar(50) |是 |Phy 信息。 |
|ap |nvarchar(50) |是 |WiFi 接入点名称。 |
|大楼 |nvarchar(500) |是 |WiFi 接入点所在的建筑物名称。 |
||||

## <a name="cqd-streams"></a>CQD 流

CQD 流被视为 "良好"、"差" 或 "未分类"。 CQM 1.5 现在使用以下 CQD 定义：

- 较差的流是不超过阈值的较差调用指标的任意组合。
- 当通话中的一个流较差时，两个通话流都被标记为差。 在会议中，每个参与者都计为唯一通话，并单独报告给所有其他参与者。
- 未分类流是没有质量指标（即，合成事务或短调用）的数据流。
- 有效流 = 非移动客户端
- 分类器不能修改

**较差呼叫定义/分类器**

|指标|阈值|
|:-----|:-----|
|DegradationAvg |大于 1.0（-1 网络 MOS） |
|RoundTrip |大于 500  |
|PacketLossRate |大于0.1 （10%） |
|JitterInterArrival |大于 30  |
|RatioConcealedSamplesAvg |大于0.07 |
|||

JPDR 定义 = 较差呼叫定义减去 RatioConcealedSamplesAvg 

## <a name="where-is-callercallee"></a>呼叫方/被呼叫方在哪里？

CQD 不使用 "调用方/被调用方" 字段，而是使用 "First" 和 "Second"，因为调用方和被调用方之间有介入的步骤。

 **第一个**如果流中涉及服务器，则始终为服务器终结点（例如，AV MCU 或中介服务器）。

 **第二个**将始终是客户端端点，除非是服务器-服务器流。

**“第一个”和“第二个”分类示例**

|端点 1 UAType |端点 2 UUAType |第一个|第二个|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype for Business)  |端点 1 |端点 2 |
|2 (AVMCU)  |1 (mMediationServer)  |端点 2 |端点 1 |
|4 (Skype for Business) |4 (Skype for Business)  |MediaLine 中的呼叫方  |MMediaLine 中的被呼叫方  |
|||||

如果两个终结点的类型相同，CQD 将使调用方条目成为第二个终结点和被调用方的条目。 有关终结点名称的详细信息，请参阅[此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。

## <a name="accounting-for-vpn"></a>VPN 考虑事项

如果已知 VPN 解决方案能够准确地设置 VPN 标志，则您已经设置完毕。 否则，请使用以下方法之一：

- 创建名为 VPN 的网络类型（首选），然后将 VPN 子网与此新 VPN 网络类型关联。
- 创建名为 VPN 的大楼，然后将 VPN 子网与此大楼关联。

## <a name="query-fundamentals"></a>查询基础知识

格式正确的查询包含以下三个参数：

- 度量
- 维度
- 筛选器

例如，“按子网[维度]显示大楼 6 [筛选器]的较差流[度量]”是一个格式正确的查询。

## <a name="what-does-union-do"></a>“联合”起什么作用？

Union 允许你用 AND 运算符筛选条件。 在某些情况下，你可以将多个筛选条件结合在一起以获得类似于 OR 操作的结果。

示例：若要从建筑物获取所有流，UNION 将提供合并数据集的独特视图。 要使用“联合”，请在你要联合的两个筛选条件上的“联合”字段中插入普通文本。

## <a name="default-report-breakdown"></a>默认报告细分

如果在内部管理无线，你可以在管理存储桶中重新创建“无线”报告。

![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>可选过程

先查看和修正托管流。 此区域中的质量应该完全在你的控制范围内，因此最容易修复。

### <a name="managed-streams"></a>管理流 

按以下顺序查看并更正管理流：

1. 服务器-服务器 
2.  服务器-有线-内部
3. 有线-有线-内部 

### <a name="unmanaged-streams"></a>非管理流

按以下顺序查看并更正非管理流：

1. 服务器-WiFi-内部
2. 服务器-有线-外部
3. 服务器-WiFi-外部
4. 有线-外部-直接
5. 有线-外部-中继
6. 其他非管理
