---
title: '适用于 IT 和Teams管理员的审核患者应用 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: 了解如何审核患者应用Teams管理员
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 288877032c662ee03e0fd575a1f9ce2e96d1b4336c290899e98eeef92a11fecf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308731"
---
# <a name="audit-logs-for-patients-app"></a>患者应用的审核日志

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

"患者"应用活动的审核日志允许事件后响应团队查看对患者电子医疗记录 (EMR) 或患者医疗保健信息 (PHI) 的更改，并确定是否需要更改或改进生产力工具中 PHI 访问的策略或过程。 本审核日志事件涵盖通过 Patients 应用用户界面执行的操作。

## <a name="meet-hipaa-requirements"></a>满足 HIPAA 要求

根据 HIPAA 指南，医疗保健提供商需要保留对 PHI 的所有访问的记录，以便对更改进行审核。 Microsoft 致力于向使用 MICROSOFT TEAMS 的企业客户提供帮助，帮助他们满足 HIPAA 要求和控制。 根据审核日志搜索功能一文中所述，完全跟踪通过患者应用对 PHI 的访问，Microsoft 365合规性中心[提供日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

> [!IMPORTANT]
> 根据法律，维护患者隐私的负担由医疗保健提供商承担。 法律使患者享有隐私，并要求 IT 管理员或 HIPAA 控制人员可以轻松确定哪些护理人员、医生或社交工作者访问或更改了患者记录。 PHI 访问违规的最常见示例之一是访问 VIP 患者。 若要审核日志 PHI 访问违反情况进行调查，并满足 HIPAA 要求，需使用此功能。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>为患者应用启用审核日志

审核依赖于多个以前的配置：

1. 管理员必须咨询其 FHIR 服务提供商，以患者应用使用的格式安装 EMR。 
2. 医疗保健提供商管理员必须启用患者应用，Teams管理中心。 有关详细信息[，请参阅](../../teams-app-setup-policies.md)管理Microsoft Teams和相关文章中的应用设置策略。
3. 管理员必须启用活动审核，就像启用任何活动日志审核一样，如开始之前和打开或关闭审核日志[搜索中所述](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)。 [](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 如果审核日志记录已打开，则"患者"应用不需要任何特殊功能。 当医疗保健提供商在团队中安装和运行应用时，审核日志会记录其 PHI 活动。
4. 然后，管理员需要宣布"患者"应用的可用性，并且医疗保健工作人员必须开始生成活动才能包括在审核中。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>运行审核

有关运行活动日志搜索的说明，请参阅 [搜索](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)审核日志。

## <a name="logged-activities-for-patients-app"></a>"患者"应用的记录活动

Patients 应用具有其自己的记录活动，如下表所示：

|友好名称 | 操作 | 说明|
|:---|:---|:---|
| 已查看患者列表 | PatientListView | 用户查看了患者列表。|
| 已删除患者列表 | PatientListDelete | 用户删除了患者列表。|
| 将患者添加到列表 | PatientListAddPatient | 一位患者已添加到患者列表。 |
| 添加了患者备注 | PatientNoteAdd | 向患者记录添加了一个便笺。 |
| 创建患者架构 | PatientSchemaCreate | 已创建患者记录中使用的一组列。 |
| 用户启动了导出 | ExportInitiation | 患者数据从 Patients 应用导出到 Excel 文件中。 该文件将保存在工作组 Sharepoint 网站中。 |
| 已创建患者列表 | PatientListCreate | 用户创建了患者列表。|
| 设置默认患者列表| PatientListDefaultSet| 用户将特定列表设置为默认列表。|
| 已从列表中删除患者| PatientListRemovePatient | 从患者列表中删除了一位患者。 |
| 已搜索患者 | PatientSearch | 在 EHR 服务中搜索了患者记录。 |
| 更新了患者架构 | PatientSchemaUpdate  | 更新了患者记录中使用的现有列集。 |<!-- | 将患者移至其他列表| PatientMoved | 患者记录从一个列表移到另一个列表。 |-->
| 重命名患者列表 | PatientListRename | 已重命名患者列表。 |
| 患者列表中的已编辑列 | PatientListEditColumns | 已编辑患者列表中的列， (或删除) 。 |
| 查看了患者详细信息 | PatientView | 用户查看了患者记录。|
| 编辑了患者详细信息 | PatientDetailsEdit | 编辑了患者记录的详细信息。 |
| 设置 EHR 连接 | EHRConnectionSet | 设置用于连接到 EHR FHIR 服务连接的 URL。 示例：https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

可以根据需要自定义审核，以搜索或筛选任何这些记录的活动。

一般情况下，Microsoft Teams记录的活动在 Microsoft Teams[中介绍](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)。

## <a name="related-topics"></a>相关主题

[搜索审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
