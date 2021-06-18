---
title: 将学生信息系统 (SIS) 数据与教育版见解同步
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 将学生信息系统 (SIS) 数据与 Microsoft Teams 教育版见解同步。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997731"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>将学生信息系统 (SIS) 数据与教育版见解同步
向[教育版见解](class-insights.md)提供的数据越多，教师就越能更好地为学生提供支持，并且教育领导者也可以为教师提供更好的支持。

若要提供组织级见解，我们必须使用[学校数据同步 (SDS)](/SchoolDataSync) 连接到学生信息系统 (SIS)，以便见解正确映射教育系统的层次结构。 

以课堂教师的身份查看课堂级见解 *不* 需要这种同步，因为我们使用 Teams 的课堂结构和权限。

## <a name="plan-your-school-data-sync-integration"></a>计划学校数据同步集成
Microsoft 学校数据同步系统 (又称 SDS) 提供了学校信息系统 (又称 SIS) 的数据和它的教育系统的层次结构，并映射出哪个用户分配到哪里，还提供了关于学生和组织层次的额外数据。

Insights 在使用 [SDS V2 及以上文件格式](/schooldatasync/sds-v2-csv-file-format) 时效果最佳，但也支持 *功能受限* 的 [SDS V1 文件格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 和 V2 文件格式之间的差异

若要充分利用见解，建议使用文件格式 v2 或 v2.1 (即将推出)

| 数据类型 | V1 | V2 |
|:--- |:--- |:--- |
| **用户** | V1 格式 **仅包含教育工作者**，因此若要为教育领导者设置组织级权限，则需要手动定义每个人的权限。 | V2 格式包含 **所有角色**，因此你可以分配基于角色的权限。 |
| **组织** | V1 格式 **仅包含学校**，因此你只能看到一个汇总级别（所有学校）。 你可以使用平面列表来放大特定的学校，但是此列表可能包含大量学校，或者包含难以比较的不同类型的学校（例如小学与中学，或者理工院校与艺术院校）。<br/><br/> 有了层次结构，你可以创建有意义的级别，例如科学或艺术系。| V2 格式包含 **你所在地区或机构的完整层次结构**，包括大学、学院、院系、校园、区域、课程等。<br/><br/> 使用层次结构，你可以按层次结构的各个级别查看相关汇总、快速比较每个级别的组织单位、为特定级别分配权限、按组织级别设置目标等。|

> [!NOTE]
> 自 2021 年 7 月 15 日起，客户将不能使用 v2 文件格式，而需要使用 v2.1 格式，所有未来的升级和新能力将在 v2.1 格式上完成且它将完全向后兼容 v1 文件格式。

## <a name="best-practices"></a>最佳做法
借助层次结构以及每个人在该层次结构中的位置的准确映射，Insights 可以为不同类型的教育领导者提供准确数据以及更为精确且相关的见解。

所提供的细节越多，报告和聚光灯就越有用且越有针对性。

下面提供了一些最佳做法来确保 SDS 的顺利部署，以便你的用户能够充分利用 Insights。

### <a name="file-format-version-to-ue"></a>文件格式版本要 ue
*   使用文件格式 V2.1 (即将推出) 并同步教育版 Insights 使用的可选数据

### <a name="users-and-roles"></a>用户和角色
*   请确保 **所有用户** 都列出在你提供的文件中并且已同步。 这包括需要查看其所在组织单位的数据的所有学生和教职员工。
    如果你当前只在 SIS 中列出了教师，则将文件上传到 SDS 并同步数据之前，请手动添加其他用户。
    Insights 收集的数据仅来自于注册的学生，如果遗漏了某些学生，这将对数据和结论产生误导。
    
*   请确保 **提供每个用户的名字和姓氏**。 否则，他们将通过他们的电子邮件地址受到引用，这在报告和聚光灯 (有关于学生活动或表现 Insights 的卡片) 中提供了非最优化的体验。

*   年级/年份必须基于此 [映射列表](#supported-grade-level-values)。 

*   为 **所有学生添加年份/年级** 是非常重要的，这样活动数据就可以通过它进行汇总和过滤。    

*   请确保 **将每个用户分配到其相关的组织单位**。 这样，教育版 Insights 就不会在教育版 Inisghts 聚光灯下显示误导性数据。

    *   一名学生可以与一个以上的组织单位相关联，例如，注册在一个特殊项目或两个院系的学生。 如果学生有一个以上的组织单位，请在该学生的用户文件中为每个单位提供一行。
    
    *   IT 管理员可以根据组织单位为员工授予权限。 **请确保工作人员与正确的单位级别相关联**，以便他们获得他们需要的权限。 例如，分配到四所学校的辅导员需要看到这些学校的所有年级; 校长需要看到他们学校的所有课程。 
    
*   **该角色至关重要**。 尽管这是一个封闭列表，但请尝试将[列表](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)中的角色与所上传的每个用户的真实角色进行匹配。 这将使你能够相应地分配基于角色的权限。 例如，为所有校长提供查看其学校中的班级的权限，或授予所有教授查看教职员工的权限。 

### <a name="organizations"></a>组织

* 请确保 **反映组织真实和完整的层次结构**。 这可以通过手动添加文件来实现。 在某些情况下，SIS 中未反映此层次结构。 尽管如此，可能仍有必要按层次结构的每一级查看相关的汇总情况，将权限分配给特定级别，按组织级别设置目标，等等。 

* 请确保 **组织树下的所有组织单位都包括学生或班级**，为他们汇总学生数据。 我们建议学生位于树的最低分支上。

> [!NOTE]
> 有关 SDS 部署的详细信息，请访问[规划 SDS](/schooldatasync/planning-school-data-sync)。

## <a name="integrate-sis-data-using-sds"></a>使用 SDS 集成 SIS 数据

Office 365 教育版中提供了学校数据同步 (SDS)。 SDS 从教育机构的学生信息系统 (SIS) 中读取数据，并将其与 Microsoft 的应用程序 (如 Teams) 整合，以实现自动创建在线教室和用户。

它还将 SIS 数据与 Insights 同步。

作为 IT 管理员，可以选择仅使用 SDS 进行配置，仅使用 Insights 或两者都使用。

若要将 SIS 信息与教育版 Insights 同步，请按照 [如何为 Insights 部署 SDS](/schooldatasync/how-to-deploy-sds-for-insights) 中的说明进行操作。

### <a name="deploy-sds"></a>部署 SDS
**如果你已经在使用 SDS**，我们建议你遵循 [最佳做法](#best-practices)。 

**如果你尚未使用 SDS**，那么现在需要 [部署它](/schooldatasync/deploying-school-data-sync)。

在部署过程中，可以决定是否要使用 SDS 为 Teams 提供用户和类别，或者仅使用它为 Insights 提供用户和组织层次结构。

> [!NOTE]
> 如果现在是年中，而且已手动创建了团队，那就只用 SDS 向 Insights 提供用户和组织层次数据，明年再考虑用 SDS 为团队配置用户和类别。

### <a name="verify-the-sync-process"></a>验证同步过程
若要验证同步状态进度，请按照 [SDS for Insights 数据运行状况和监视](/schooldatasync/sds-for-insights-data-health-and-monitoring) 中的说明操作。

> [!IMPORTANT]
> 如果你遇到任何问题，[客户支持](https://aka.ms/edusupport)将为你提供帮助。

## <a name="supported-grade-level-values"></a>支持的年级值

在SDS文件中，年级/年份级别定义为枚举值，这意味着只能在CSV文件中提供一组选定的值。 在同步处理过程中，任何其他指定的值都会导致错误。

以下部分定义了用户文件中支持的值。

### <a name="united-states--worldwide-grade-levels"></a>美国/全球范围内各年级
|文件中的值（等级列） | Insights的标签|
|:---|:---| 
|IT|婴幼儿|
|PR|学前教育|
|PK|幼儿园前教育|
|TK|过渡性幼儿园|
|KG|幼儿园|
|01 或 1|一年级|
|02 或 2|第二年级|
|03 或 3|三年级|
|04 或 4|四年级|
|05 或 5|五年级|
|06 或 6|六年级|
|07 或 7|七年级|
|08 或 8|八年级|
|09 或 9|九年级|
|10|十年级|
|11|十一年级|
|12|十二年级|
|PS|大专|
|PS1|大专新生|
|PS2|大专二年级|
|PS3|大专三年级|
|PS4|大专四年级|
|本科|本科|
|毕业生|毕业生|
|研究生|研究生（以研究为重点的研究生）|
|校友|校友|
|成人教育|成人教育|
|UG|未分级|
|其他|其他|

### <a name="united-kingdom-year-groups"></a>英国各年级
|文件中的值（等级列） | Insights的标签|
|:---|:---| 
|IT|托儿所|
|PR|学前教育|
|PK|接收|
|01 或 1|一年级|
|02 或 2|二年级|
|03 或 3|三年级|
|04 或 4|四年级|
|05 或 5|五年级|
|06 或 6|六年级|
|07 或 7|七年级|
|08 或 8|八年级|
|09 或 9|九年级|
|10|十年级|
|11|十一年级|
|12|十二年级|
|13|十三年级|
|PS|大专|
|PS1|大专一年级|
|PS2|大专二年级|
|PS3|大专三年级|
|PS4|大专四年级|
|本科|本科|
|毕业生|毕业生|
|研究生|研究生（以研究为重点的研究生）|
|校友|校友|
|成人教育|成人教育|
|UG|未分级|
|其他|其他|

