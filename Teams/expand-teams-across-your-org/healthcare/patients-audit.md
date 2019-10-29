---
title: '审核患者应用，面向团队 IT 和合规性管理员 '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: 适用于团队管理员的患者应用
ms.openlocfilehash: 7afa6004191c460428200e7804dfb10a748fc65b
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749544"
---
# <a name="audit-logs-for-patients-app"></a>患者应用的审核日志

患者应用活动的审核日志允许事件响应团队查看患者的电子医疗记录（EMR）或患者医疗保健信息（PHI）的更改，并确定要在其中进行 PHI 访问的策略或过程中的更改或改进需要生产工具。 审核日志事件涵盖通过患者应用用户界面执行的操作。

## <a name="meet-hipaa-requirements"></a>满足 HIPAA 要求

根据 HIPAA 指南，医疗保健提供商需要保留对 PHI 的所有访问的记录，以便审核所做的更改。 Microsoft 致力于使用 Microsoft 团队的企业客户，并帮助他们满足 HIPAA 要求和控制措施。 通过 "患者" 应用对 PHI 进行完全跟踪，日志可在 M365 安全和合规性中心提供，如 "[审核日志搜索功能](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)" 文章中所述。

> [!IMPORTANT]
> 法律规定，保持患者隐私的负担由医疗保健提供商承担。 法律证明病人对隐私的要求，并要求 IT 管理员或 HIPAA 控制器能够轻松地确定哪些护士、clinician 或社会工作者访问或更改了患者记录。 最常见的 PHI 访问冲突示例之一是访问 VIP 患者。 审核日志功能是执行任何 PHI 访问冲突调查和满足 HIPAA 要求所必需的。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>为患者应用启用审核日志

审核依赖于几个以前的配置：

1. 管理员必须使用其 FHIR 服务提供商，才能以患者应用使用的格式使用 EMR。 请参阅将[电子医疗保健记录集成到 Microsoft 团队](patients-app.md)。
2. 医疗保健提供商管理员必须在 "团队管理中心" 中启用 "患者" 应用。 有关详细信息，请参阅 Microsoft 团队和相关文章[中的管理应用设置策略](../../teams-app-setup-policies.md)。
3. 管理员必须在 O365 中启用活动审核，这与在 Office 365 中启用任何活动日志审核的方式相同，如 "[开始](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) [" 和 "打开或关闭 office 365 审核日志搜索](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)" 中所述。 如果审核日志记录已打开，则患者应用不需要任何特殊内容。 每当医疗保健提供商在团队内部安装和运行应用时，审核日志都会记录其 PHI 活动。
4. 管理员随后需要宣布患者应用的可用性，并且医疗保健工作人员必须开始生成活动才能纳入审核。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>运行审核

有关运行活动日志搜索的说明，请参阅[搜索审核日志](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

## <a name="logged-activities-for-patients-app"></a>患者应用的已记录活动

患者应用有自己的记录的活动，如下表所列：

|友好名称 |操作|说明|
|:---|:---|:---|
| 查看患者列表 | PatientListView | 用户查看了一个患者列表。|
| 已删除的患者列表 | PatientListDelete | 用户删除了一个患者列表。|
| 已将患者添加到列表 | PatientListAddPatient | 患者已添加到患者列表。 |
| 已添加患者笔记 | PatientNoteAdd | 已将笔记添加到患者记录。 |
| 已创建患者架构 | PatientSchemaCreate | 已创建患者记录中使用的一组列。 |
| 用户启动了导出 | ExportInitiation | 患者数据已从 "患者" 应用导出到 Excel 文件中。 该文件将保存在团队 sharepoint 网站中。 |
| 已创建患者列表 | PatientListCreate | 用户创建了一个患者列表。|
| 设置默认患者列表| PatientListDefaultSet| 用户将特定列表设置为默认列表。|
| 已从列表中删除患者| PatientListRemovePatient | 患者已从患者列表中删除。 |
| 已搜索患者 | PatientSearch | 已搜索 EHR 服务中的患者记录。 |
| 更新的患者架构 | PatientSchemaUpdate  | 已更新患者记录中使用的一组现有列。 |<!-- | 已将患者移动到其他列表| PatientMoved | 患者记录从一个列表移动到另一个列表。 |-->
| 已重命名的患者列表 | PatientListRename | 已重命名患者列表。 |
| 已编辑的患者列表中的列 | PatientListEditColumns | 已编辑（添加或删除）患者列表中的列。 |
| 查看患者详细信息 | PatientView | 用户查看了一条患者记录。|
| 已编辑的患者详细信息 | PatientDetailsEdit | 已编辑患者记录的详细信息。 |
| 设置 EHR 连接 | EHRConnectionSet | 设置用于连接 EHR FHIR 服务连接的 URL。 示例： https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

您可以根据需要自定义审核以搜索或筛选任何这些已记录的活动。

Microsoft 团队[活动](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)中介绍了常规 microsoft 团队的已记录活动。

## <a name="related-topics"></a>相关主题

[搜索 Office 365 审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[将电子医疗记录集成到 Microsoft Teams 中](patients-app.md)
