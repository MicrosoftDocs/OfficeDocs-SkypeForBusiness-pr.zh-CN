---
title: 使用 Skype for Business Server 的呼叫质量仪表板
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：了解如何使用呼叫质量仪表板。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: ed1e5563a4677dce33648280590530ca2a9b1b9b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803102"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>使用 Skype for Business Server 的呼叫质量仪表板

**摘要：** 了解如何使用呼叫质量仪表板。 通话质量仪表板是 Skype for Business Server 的工具。

呼叫质量仪表板 (CQD) 允许 IT 专业人员使用聚合数据，通过比较用户组的统计信息来识别趋势和模式，从而发现产生媒体质量问题的问题。 CQD 不专注于解决单个呼叫问题，而是确定适用于许多用户的问题和解决方案。

## <a name="call-quality-dashboard-user-guide"></a>通话质量仪表板用户指南

CQD 是一个 Web 门户，用于快速创建和组织基于 QoE (用户体验质量) 报告。 CQD 部署 SSAS 多维数据集以聚合 QoE 指标数据库中的数据，使管理员能够创建和修改报告或实时进行调查。 虽然可以使用 Excel 直接连接到多维数据集，但门户已针对多个涉及 QoE 数据的工作流进行了优化。 数据包括：

- 用于快速访问的缓存报表数据
- 指向用于信息共享和发布的报告页面的深层链接
- 简化了报告编辑和创建，以及报表说明的可编辑元数据。

此外，CQD 还公开了 Web API，这些 API 允许用户以编程方式访问多维数据集数据，以用于自定义仪表板。

### <a name="feature-overview"></a>功能概述

访问呼叫质量仪表板时，将看到以下屏幕：

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. "摘要窗格"是"报告集"的 (位于右侧) 的上下文。
2. 在摘要窗格报表中单击"编辑"以设置级别属性 (包括 Y 轴高度) 。
3. 痕迹导航可帮助您标识报告集层次结构中的当前位置。
4. 包含子报表的报告将显示为一个蓝色链接。 单击链接可向下钻取到子报告。

将鼠标移到条形图和趋势线上以显示详细值。 具有焦点的报告显示操作菜单："编辑"、"克隆"、"删除"和"下载"。

### <a name="default-reports"></a>默认报告

首次访问呼叫质量仪表板门户时，将自动创建一组默认报告。 这些报告有时称为系统报告。 您可以自由修改或删除这些报告，或者通过创建新的同级和子报告来扩展它们。

在顶级，"音频流每月趋势"报告显示所有音频流的每月趋势。 将鼠标移到条形图中的条形图上，以显示条形图所代表的数据的更详细视图。 单击"音频流每月趋势"报告的标题以导航到"托管音频流与非托管音频流"报告，其中报告在托管呼叫和未托管呼叫之间拆分。 托管呼叫是公司防火墙内部通过有线连接拨打的呼叫。 非托管呼叫包括从公司防火墙外拨打的呼叫，以及通过 WI-Fi 进行的所有呼叫。

另一个顶级报告称为"用户报告的呼叫质量分级直方图"。 通话质量评级是 Skype for Business 用户在呼叫结束时提供的数字，用于指示呼叫质量。 评分数字范围为 1 到 5，1 是最差的，5 表示最佳。 直方图显示一个月内评级为指示的音频呼叫数。

单击任何报告的标题以导航到具有更多数据筛选器的报表。 在系统报告中，每个子报告都显示其父报告中可用的数据的子集。 问题解决模型很简单：调查将问题限制到的数据或趋势的子报告，并逐渐缩小问题空间。 创建子报表的能力允许你调查自己对特定数据趋势原因的猜测。

### <a name="create-and-edit-reports"></a>创建和编辑报告

单击报表的操作菜单中的"编辑"以查看报告编辑器。 每个报表都由多维数据集中的查询进行备份。 报表是查询返回的数据的可视化效果。 报表编辑器可帮助您编辑这些查询和报表的显示选项。 打开报告编辑器时，可以看到：

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. 在左窗格中选择维度、度量和筛选器。 将鼠标悬停在其中一个现有值上可显示允许删除值的"x"按钮。 单击标题旁边的"加号"按钮，打开可在其中添加新维度、度量值或筛选器的对话框。
2. 图表自定义选项显示在顶部。
3. 报告编辑器中提供了报表预览。
4. 可以使用底部的编辑框创建详细的报告说明。

### <a name="sparklines-in-tables"></a>表中的迷你图

将 StartDate.Month 添加为维度并且数据以表格形式呈现为趋势时，条形图和迷你图可以在表格单元格内显示。 将鼠标指针移到条形图和迷你图上，以显示各个月份的值。

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

为了显示条形图和迷你图，必须选中报告编辑器顶部的"显示迷你图"复选框。 这将选择"趋势"选项，将 Month 向下移动为最后一个维度，这也可通过单击"月"，然后使用向上和向下箭头向上或向下移动 StartDate.Month 实现。

### <a name="settings"></a>设置

"设置"菜单包含指向有用页面（如"系统运行状况"和"关于"页面）的链接，位于仪表板的右上角。

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

是否显示说明和时间戳取决于单个用户，并且这些设置仅影响个人版本的仪表板，并且不会修改报告集或其他用户看到的信息。 清除缓存会导致所有查询从多维数据集重新加载其数据，而还原默认值会删除用户创建或修改的所有报告，并重新创建系统报告集 —用户首次登录时会看到的内容。

用户仪表板链接显示一个页面，用户可以在此页面查看 CQD 的其他用户并浏览其报告。 若要共享报告集，请复制 URL 栏中的链接，并与另一个 CQD 用户共享它。 此链接是其他用户在用户用户名下的"用户仪表板链接"页看到的相同链接。

### <a name="supplying-subnet-information"></a>提供子网信息

如果存档数据库中输入了特定于站点的信息以提供子网到建筑物的映射信息， (例如，通过构建网络网络来提供有线/无线呼叫质量) 。

至少填写下表以创建这些报告：

- CqdBuilding
- CqdNetwork

可以在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息，以便进一步筛选和向下钻取。

用于这些表的数据定义如下：

**CqdBuilding**

|列|数据类型|允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |否 |CqdBuilding 表的主键。 |
|BuildingName |varchar (80)  |否 |建筑物名称。 |
|BuildingShortName |varchar (10)  |否 |生成名称的更短版本。 |
|OwnershipTypeId |int |否 |外键，与 CqdBuildingOwners 表中的条目之一匹配。 |
|BuildingTypeId |int |否 |外键，与 CqdBuildingType 表中的条目之一匹配。 |
|Latitude |float |是 |建筑物的纬度。 |
|Longitude |float |是 |大楼的经度。 |
|CityName |varchar (30)  |是 |大楼所在的城市名称。 |
|ZipCode |varchar (25)  |是 |大楼所在的邮政编码。 |
|CountryShortCode |varchar (2)  |是 |大楼所在的国家/地区 ISO 3166-1 alpha-2 代码。 |
|StateProvinceCode |varchar (3)  |是 |大楼所在的省/市/市/县的三字母缩写。 |
|InsideCorp |bit |是 |位指示大楼是否是企业网络的一部分。 |
|BuildingOfficeType |nvarchar (150)  |是 |大楼办公类型的说明。 |
|地区 |varchar (25)  |是 |大楼所在的区域。 |
|||||

**CqdNetwork**

|列|数据类型|允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|Network |varchar (25)  |否 |子网地址。 |
|NetworkRange |tinyint |是 |子网掩码。 |
|NetworkNameID |int |是 |（可选）映射到 CqdNetworkName 表中的行。 |
|BuildingKey |int |是 |外键，与 CqdBuilding 表中的条目之一匹配。 |
|UpdatedDate |datetime |否 |上次更新条目的日期/时间。 |
||||||

默认情况下，此下一个表具有一 (0，"未知") 。

**CqdBuildingType**

|列|数据类型|允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |否 |CqdBuildingType 表的主键。 |
|BuildingTypeDesc |char (18)  |否 |生成类型说明。 |
|||||

默认情况下，此下一个表具有一 (0、"Unknown"、0、null) 。

**CqdBuildingOwnershipType**

|列|数据类型|允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |否 |CqdBuildingOwnershipType 表的主键。 |
|OwnershipTypeDesc |varchar (25)  |否 |所有权类型说明。 |
|LeaseInd |tinyint |是 |引用 CqdBuildingOwnershipType 表中另一行的索引，用于标识租用的大楼。 |
|所有者 |varchar (50)  |是 |建筑物所有者。 |
|||||

默认情况下，此下一个表具有一 (0、"Unknown"、0、null) 。

**CqdBssid**

|列|数据类型|允许 Null？|详细信息|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |否 |CqdBssid 表的主键。 是 WiFi 接入点的 BSSID。 |
|ess |nvarchar(50) |是 |Wifi 接入点控制器信息。 |
|phy |nvarchar(50) |是 |Phy 信息。 |
|ap |nvarchar(50) |是 |Wifi 接入点名称。 |
|生成 |nvarchar (500)  |是 |WiFi 接入点所在的建筑物名称。 |
||||

## <a name="cqd-streams"></a>CQD 流

CQD 流被视为良好、差或未经分类。 CQM 1.5 现在使用以下 CQD 定义：

- 质量欠佳的流是超出阈值的较差呼叫指标的任意组合。
- 当呼叫中的一个流较差时，呼叫的两个流都标记为差。 在会议中，每个参与者都计为唯一呼叫，并独立于所有其他参与者进行报告。
- 未分类流是无质量指标的流 (即综合事务或短时间) 。
- 有效流 = 非移动客户端
- 无法修改分类器

**较差的呼叫定义/分类器**

|跃点数|阈值|
|:-----|:-----|
|DegradationAvg |大于 1.0 (-1 网络 MOS)  |
|RoundTrip |大于 500 |
|PacketLossRate |大于 0.1 (10%)  |
|JitterInterArrival |大于 30 |
|RatioConcealedSamplesAvg |大于 0.07 |
|||

JPDR 定义 = 质量欠佳的呼叫定义减去 RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>呼叫者/被叫方在哪里？

CQD 不使用呼叫方/被叫方字段，而是使用"First"和"Second"，因为呼叫者与被叫方之间存在干预步骤。

 **First** 始终为服务器终结点 (例如，AV MCU 或中介服务器) （如果流中涉及服务器）。

 **Second** 始终为客户端终结点，除非它是一个Server-Server流。

**第一和第二分类的示例**

|终结点 1 UAType|终结点 2 UUAType|First|秒|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype for Business)  |终结点 1 |终结点 2 |
|2 (AVMCU)  |1 (mMediationServer)  |终结点 2 |终结点 1 |
|4 (Skype for Business)  |4 (Skype for Business)  |MediaLine 中的呼叫者 |MMediaLine 中的被叫方 |
|||||

如果两个终结点的类型相同，则 CQD 将呼叫者条目"第一"和"被叫方第二"。 有关终结点名称详细信息，请参阅 [此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。

## <a name="accounting-for-vpn"></a>VPN 会计

如果已知 VPN 解决方案能够准确设置 VPN 标志，则你已全部设置。 否则，请使用下列方法之一：

- 创建名为 VPN 的网络类型 (首选) ，然后将 VPN 子网与这个新 VPN NetworkType 关联。
- 创建一个称为 VPN 的建筑物，然后将 VPN 子网与该建筑物关联。

## <a name="query-fundamentals"></a>查询基础

格式良好的查询包含以下三个参数：

- 度量
- Dimension
- 筛选

格式良好的查询示例为"按子网 [Dimension] 显示差流 [度量] 生成 6 [筛选器]。"

## <a name="what-does-union-do"></a>UNION 有什么功能？

Union 允许您使用 AND 运算符筛选条件。 在某些情况下，可以将多个 Filter 条件组合在一起，以实现类似于 OR 操作的结果。

示例：为了从建筑物获取所有流，UNION 提供了合并数据集的一个独特视图。 若要使用 UNION，请将常见文本插入到要联合的两个筛选条件的 UNION 字段中。

## <a name="default-report-breakdown"></a>默认报告细分

如果无线在内部管理，可以在托管存储桶中重新创建无线报告。

![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>运营流程

首先查看并修正托管流。 此区域中的质量应 100% 在你的控制范围内，因此最易于修正。

### <a name="managed-streams"></a>托管流

按以下顺序查看和修正托管流：

1. Server-Server
2. Server-Wired-Inside
3. 有线-有线-内部

### <a name="unmanaged-streams"></a>非托管流

按以下顺序查看和修正非托管流：

1. Server-Wifi-Inside
2. Server-Wired-Outside
3. Server-Wifi-Outside
4. 有线-外部-直接
5. 有线-外中继
6. 其他非托管
