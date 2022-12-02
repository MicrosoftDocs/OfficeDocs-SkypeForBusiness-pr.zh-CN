---
title: 职业指导数据和合规性信息
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: 了解Microsoft在教育或 EDU 职业指导方面采取的隐私、合规性和权限措施。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 1a21f3337ca9255572c25fd152f928c6444dc317
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242486"
---
# <a name="career-coach-data-and-compliance"></a>职业指导数据和合规性

本文讨论如何使用应用内功能以及其他工具来帮助你查找和处理个人数据或个人信息，以响应数据主体请求， (DSR) 符合 GDPR 义务。 职业指导将数据大致分为两类：客户内容和系统生成的日志。 在职业指导中，客户内容包括用户数据、租户配置数据和学生活动数据，而系统生成的日志包括Microsoft生成的日志和相关数据，可帮助Microsoft向用户提供企业服务。

## <a name="customer-content"></a>客户内容

### <a name="user-data"></a>用户数据

职业指导收集的用户数据包括个人资料信息，例如目标和活动进度、研究领域、学校年份、保存的技能、保存的职业、上传的简历和成绩单。

#### <a name="deleting-user-data"></a>删除用户数据

按照以下步骤从职业指导中删除用户数据：

1. 全局管理员必须 [开具支持票证](https://edusupport.microsoft.com/support?product_id=career_coach) ，明确说明对 GDPR 删除 DSR (数据主体请求) 操作的请求。 **无法限制删除的数据集或时间范围**。
2. 请求应明确说明需要删除的数据类型：
    1. 租户的所有用户数据。
    2. 特定用户的用户数据。 请在删除请求) 包含用户的 OID (对象标识符。
3. 提交后，支持票证将在一周后解决，以满足符合性的最低保留策略。 在此期间可以取消操作。
4. 一周后，职业指导团队将删除与租户相关的所有数据。 Microsoft支持人员监视票证，并在删除过程完成后（ **不超过 30 天**）通知你。

#### <a name="exporting-user-data"></a>导出用户数据

按照以下步骤从职业指导导出用户数据：

1. [开放式职业指导](https://aka.ms/Career_Coach_App) 并查看个人资料。
1. 滚动到“隐私和安全”部分。
1. 选择“下载”以导出帐户的所有客户数据。

### <a name="tenant-configuration-data"></a>租户配置数据

租户数据包括作为 Career Coach 应用程序配置的一部分上传或生成的信息。 此数据包括租户的品牌信息、徽标和学习图标、课程目录、LinkedIn学校 URL、学习领域列表，以及 Teams 管理中心的职业指导租户配置期间添加的所有其他数据。

#### <a name="deleting-tenant-configuration-data"></a>删除租户配置数据

按照以下步骤从职业指导中删除租户配置数据：

1. 全局管理员必须 [打开支持票证](https://edusupport.microsoft.com/support?product_id=career_coach) ，明确说明删除租户配置数据的请求。 **无法限制删除的数据集或时间范围**。
1. 提交后，支持票证将在一周后解决，以满足符合性的最低保留策略。 在此期间可以取消操作。
1. 一周后，职业指导团队将删除与租户相关的所有数据。 Microsoft支持人员监视票证，并在删除过程完成后（ **不超过 30 天**）通知你。

### <a name="student-activity-data"></a>学生活动数据

职业指导将学生活动数据存储在 [与教育版 Insights](class-insights.md)相同的位置。 聚合数据显示在职业指导学生活动见解体验中。 为支持此功能而捕获的学生使用情况数据将存储并保留一年。

#### <a name="deleting-student-activity-data"></a>删除学生活动数据

若要删除个人或租户的学生活动数据，请按照 [如何从教育见解中删除用户数据](class-insights.md#how-to-delete-user-data-from-education-insights)中的步骤操作。

## <a name="system-generated-logs"></a>系统生成的日志

系统生成的日志包括Microsoft生成的日志和相关数据，可帮助Microsoft向用户提供企业服务。 系统生成的日志主要包含假名化数据，例如唯一标识符 (通常由系统) 生成的数字，无法自行识别个人，但用于向用户提供企业服务。 此数据的示例包括：

- 产品和服务使用情况数据，例如用户活动日志。
- 用户搜索请求和查询数据。
- 由产品和服务生成的数据作为系统功能以及用户或其他系统的交互的产物。

> [!NOTE]
> 不支持限制或纠正系统生成的日志中的数据。 系统生成的日志中的数据构成Microsoft云和诊断数据中执行的事实操作，对此类数据的修改将损害操作的历史记录，并增加欺诈和安全风险。 职业指导将系统生成的日志保留 30 天。

### <a name="exporting-and-deleting-system-generated-logs"></a>导出和删除系统生成的日志

租户全局管理员是组织内唯一可以访问与特定用户使用Office 365服务和应用程序关联的系统生成日志的人员。 职业指导遵循 [访问和导出Office 365提供的系统生成日志的过程](/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs)。

## <a name="more-information"></a>更多信息

- [Microsoft Teams 职业教练入门](career-coach.md)
- [隐私常见问题](https://privacy.microsoft.com/faq)
- [Microsoft产品和数据 - Microsoft隐私](https://privacy.microsoft.com/privacy-in-our-products)
- [Microsoft帐户隐私设置](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
