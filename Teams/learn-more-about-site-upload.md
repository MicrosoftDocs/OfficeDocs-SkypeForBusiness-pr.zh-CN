---
title: 添加和更新位置数据
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何上传到网站。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e7e9211b207c008de22fe86ae0c7bb6c9f9ac51
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34667479"
---
<a name="adding-and-updating-locations-data"></a>添加和更新位置数据
============================

在您的组织中使用位置来指示办公室、建筑物或组织网站的物理位置。 "位置" 页面使管理员能够提供包含物理位置列表及其关联网络子网的文本文件 (.csv 或 tsv)。 此文件由 "调用分析" 和 "呼叫质量" 仪表板用于生成报告。 当客户上载其子网映射时, 这些服务提供的报表将包含位置名称, 使报表更易于理解和用于修正任何潜在问题。

您提供的位置数据是单个数据结构-当前没有可用于对位置数据进行个别编辑的界面。 

**编辑子网和位置表**

1. 单击 "**替换位置数据**"。
2. 在 "**替换位置数据**" 窗格中, 单击 "**选择文件**", 然后浏览到并上载已编辑的 .csv 或 tsv 文件。 
3. 单击 "**上载**"。 


可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例模板。

你可以使用以下示例来帮助创建数据文件。 

> [!IMPORTANT]
> 数据文件不应包含列标题 (如 "网络"、"网络名称" 等)。 此处仅用于提供信息。 </br>

|网络|网络名称|网络范围|建筑物名称|所有权类型|建筑物类型|构建 Office 类型|城市|邮政编码|该国|省/市/自治区|区域|公司内部|快速路线|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|


有关设置数据文件格式的详细信息, 请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)。


## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)
