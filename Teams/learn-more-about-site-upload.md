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
description: 了解如何通过上载包含物理位置和关联子网的列表的文本文件来添加和更新报告标签。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b32e9db020b3498e8185b4d38e25d1d9a1feca5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085288"
---
<a name="add-and-update-reporting-labels"></a>添加和更新报告标签
============================

报告标签用于你的组织中，指示办事处、建筑物或组织网站的物理位置。 Microsoft 团队管理中心中的 "报告标签" 页面允许你提供一个文本文件（.csv 或 tsv），其中包含物理位置列表及其关联的网络子网。 此文件由用于生成报表的调用分析使用。 当你上载子网映射时，这些服务提供的报表也将包含位置名称，使报表更易于理解和用于修正任何潜在问题。

> [!IMPORTANT]
> 你上载的报告标签将作为你的 Office 365 协议下的*支持数据*进行处理，包括任何其他被视为*客户数据*或*个人资料*的信息。 请不要包含您不希望作为*支持数据*提供给 microsoft 的数据，因为出于支持的目的，microsoft 工程师将会看到此信息。

你提供的报表标签和位置数据是单个数据结构-当前没有可用于对数据进行个别编辑的界面。

**编辑子网和位置表**

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **报告标签**"。
2. 单击 "**替换位置数据**"。
3. 在 "**替换位置数据**" 窗格中，单击 "**选择文件**"，然后浏览到并上载已编辑的 .csv 或 tsv 文件。
4. 单击 "**上载**"。

可以[在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例模板。

使用以下示例可帮助创建数据文件。

> [!IMPORTANT]
> 数据文件不应包含列标题（如 "网络"、"网络名称" 等）。 此处仅用于提供信息。 <br>

|网络|网络名称|网络范围|建筑物名称|所有权类型|建筑物类型|构建 Office 类型|城市|邮政编码|该国|省/市/自治区|区域|公司内部|快速路线|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso 租赁 RE&F|Office|重新&F|山地视图|94043|我们|认证|我们|1|1|

有关设置数据文件格式的详细信息，请参阅[租户数据文件格式和构建数据文件结构](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)
