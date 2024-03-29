---
title: 添加和更新报告标签
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何通过上传包含物理位置和关联子网列表的文本文件来添加和更新报告标签。
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
ms.openlocfilehash: 189b821e7238911190c4c72c07b863fc961f3074
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984607"
---
# <a name="add-and-update-reporting-labels"></a>添加和更新报告标签

报告标签在组织中用于指示办公室、建筑物或组织网站的物理位置。 使用 Microsoft Teams 管理中心中的"报告标签"页，可以提供文本文件 (.csv 或 .tsv) ，其中包含物理位置及其关联网络子网的列表。 调用分析使用此文件生成报告。 上传子网映射时，这些服务提供的报表也将包含位置名称，使报表更易于理解和用于修正任何潜在问题。

> [!IMPORTANT]
> 您上传的报告标签将按照您的协议处理为 *支持数据* Office 365，包括否则被视为"客户数据"*或"**个人数据"的任何信息*。 请不要包含不希望作为支持数据向 Microsoft 提供的数据，因为出于支持目的，Microsoft 工程师将看到此信息。

您提供的报表标签和位置数据是单个数据结构 – 当前没有可用于对数据进行单独编辑的界面。

**编辑子网和位置的表**

1. 在管理中心的左侧导航Microsoft Teams，单击 **"分析"&报告**  >  **标签"。**
2. 单击 **"Upload数据"。**
3. 在 **"Upload"** 窗格中，单击"选择文件"，然后浏览到已编辑的文件.csv .tsv 文件。
4. 单击 **"Upload"。**

可以在此处下载示例 [模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

使用以下示例来帮助创建数据文件。

> [!IMPORTANT]
> 数据文件不应包含列标题 (例如网络、网络名称等) 。 此处仅用于提供信息。 <br>

|网络|网络名称|网络范围|建筑物名称|所有权类型|建筑物类型|构建Office类型|城市|邮政编码|国家/地区|省/市/自治区|区域|内部公司|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山脉视图|94043|美国|CA|美国|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山脉视图|94043|美国|CA|美国|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山脉视图|94043|美国|CA|美国|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso 租用 RE&F|Office|RE&F|山脉视图|94043|美国|CA|美国|1|1|

有关设置数据文件格式的信息，请参阅租户 [数据文件格式和构建数据文件结构](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)

[使用呼叫分析排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)
