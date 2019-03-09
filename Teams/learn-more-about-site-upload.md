---
title: 添加和更新位置数据
author: tonysmit
ms.author: lolaj
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
description: 了解如何将上载到网站。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: a84b022c7b5553a15ff8862a175ba5f856cdd149
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494074"
---
<a name="adding-and-updating-locations-data"></a>添加和更新位置数据
============================

您的组织中使用的位置用于指示办公室、 建筑或组织的网站的物理位置。 位置页使管理员能够提供一个文本文件 （.csv 或.tsv） 包含列表的物理位置和其关联的网络子网。 此文件用于通过调用分析和呼叫质量仪表板生成报告。 当客户上载其子网映射时，提供这些服务的报告将包含位置名称也进行了报告更轻松地了解和使用的补救存在任何潜在问题。

您提供的位置数据是单个数据结构 – 当前没有可用于对位置数据进行单个编辑界面。 

**若要编辑的子网和位置表**

1. 单击**替换位置数据**。
2. 在**替换位置数据**窗格中，单击**选择文件**，然后浏览到，并上载您的已编辑的.csv 或.tsv 文件。 
3. 单击**上载**。 


您可以下载示例模板[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

您可以使用下面的示例来帮助创建数据文件。 

> [!IMPORTANT]
> 数据文件不应包含 （如网络、 网络名称等） 的列标题。 这些仅作说明用途此处使用。 </br>

|网络|网络名称|网络范围|构建名称|所有权类型|构建基类型|构建 Office 类型|城市|邮政编码|国家/地区|省/市/自治区|区域|内部 Corp|Express 路由|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山地视图|94043|我们|CA|我们|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山地视图|94043|我们|CA|我们|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山地视图|94043|我们|CA|我们|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山地视图|94043|我们|CA|我们|1|1|


有关格式化数据文件的详细信息，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure)。


## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)