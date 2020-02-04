---
title: 添加和更新报告标签
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何上载包含要用作呼叫分析和通话质量仪表板报表的报告标签的物理位置列表和关联子网的文本文件。
ms.custom:
- NewAdminCenter_Update
f1.keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d3197d91b7139089a940c19ff23c1dcc99a290
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707855"
---
<a name="add-and-update-reporting-labels"></a>添加和更新报告标签
============================

报告标签用于你的组织中，指示办事处、建筑物或组织网站的物理位置。 Microsoft 团队管理中心中的 "报告标签" 页面允许你提供一个文本文件（.csv 或 tsv），其中包含物理位置列表及其关联的网络子网。 此文件由 "调用分析" 和 "呼叫质量" 仪表板用于生成报告。 当你上载子网映射时，这些服务提供的报表也将包含位置名称，使报表更易于理解和用于修正任何潜在问题。

你提供的报表标签和位置数据是单个数据结构-当前没有可用于对数据进行个别编辑的界面。

**编辑子网和位置表**

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**位置** > **报告标签**"。
2. 单击 "**替换位置数据**"。
3. 在 "**替换位置数据**" 窗格中，单击 "**选择文件**"，然后浏览到并上载已编辑的 .csv 或 tsv 文件。
4. 单击 "**上载**"。

可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例模板。

使用以下示例可帮助创建数据文件。

> [!IMPORTANT]
> 数据文件不应包含列标题（如 "网络"、"网络名称" 等）。 此处仅用于提供信息。 <br>

|网络|网络名称|网络范围|建筑物名称|所有权类型|建筑物类型|构建 Office 类型|城市|邮政编码|该国|省/市/自治区|区域|公司内部|快速路线|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|

有关设置数据文件格式的详细信息，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)。

## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)
