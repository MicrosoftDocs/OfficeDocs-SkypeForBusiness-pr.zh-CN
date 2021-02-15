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
ms.openlocfilehash: 70cef1893b0260e690f5470bff0111dda5e7e7fe
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145819"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>将学生信息系统 (SIS) 数据与教育版见解同步
向[教育版见解](class-insights.md)提供的数据越多，教师就越能更好地为学生提供支持，并且教育领导者也可以为教师提供更好的支持。

若要提供组织级见解，我们必须使用[学校数据同步 (SDS)](https://docs.microsoft.com/SchoolDataSync) 连接到学生信息系统 (SIS)，以便见解正确映射教育系统的层次结构。 

以课堂教师的身份查看课堂级见解 *不* 需要这样做，因为我们使用 Teams 的课堂结构和权限。

## <a name="plan-your-sis-integration"></a>规划 SIS 集成
SIS 数据提供教育系统的层次结构，并映射在何处分配了哪个用户。

使用 [SDS V2 文件格式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)时，见解效果最佳，但也支持功能 *受限* 的 [SDS V1](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) 文件格式。

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 和 V2 文件格式之间的差异

| 数据类型 |   V1 | V2（向新客户推荐） |
|:--- |:--- |:--- |
| **用户** | V1 格式 **仅包含教师**,，因此若要为教育领导者设置组织级别的权限，你需要搜索他们并手动定义每个人的权限。 | V2 格式包含 **所有角色**，因此你可以分配基于角色的权限。 |
| **组织** | V1 格式 **仅包含学校**，因此你只能看到一个汇总级别（所有学校）。 你可以使用平面列表来放大特定的学校，但是此列表可能包含大量学校，或者包含难以比较的不同类型的学校（例如小学与中学，或者理工院校与艺术院校）。<br/><br/> 有了层次结构，你可以创建有意义的级别，例如科学或艺术系。| V2 格式包含 **你所在地区或机构的完整层次结构**，包括大学、学院、院系、校园、区域、课程等。<br/><br/> 使用层次结构，你可以按层次结构的各个级别查看相关汇总、快速比较每个级别的组织单位、为特定级别分配权限、按组织级别设置目标等。|

### <a name="type-of-data-required"></a>所需的数据类型
下表提供了充分利用见解所需的数据类型。

| 数据类型 | 所需数据的示例|为什么它很重要？|
|:--- |:--- |:--- |
| **用户** |   角色（如学生）<br/> 年级（如 10）<br/> 组织（名称） | 如果正确为每个人员分配其角色、年级和组织，则我们可确保汇总正确无误。|
| **组织** | 组织类型（如大学） |   此处的层次结构非常重要。 例如，学校可能属于某各地区，该地区可能属于某个州/省。<br/> 当允许地区教育领导者查看数据时，仅适用于该地区的学校。|
| **班级** | 标题（如计算机科学 101） | 它详细说明了组织开办的班级。 必须正确地映射它，以便我们可以为学生分配正确的班级。 |
| **注册** | 角色（如学生） | 这适用于学生和教师，使我们能够知道他们在哪个班级注册。 |

> [!NOTE]
> 在部署过程中，你可以决定是要使用 SDS 在 Teams 中预配用户和班级，还是仅使用 SDS 来向见解提供数据。

## <a name="best-practices"></a>最佳做法
借助层次结构以及每个人在该层次结构中的位置的准确映射，Insights 可以为不同类型的教育领导者提供准确数据以及更为精确且相关的见解。

你在此处提供的详细信息越多，报告和聚光灯就越有用且越相关。
下面提供了一些最佳做法来确保 SDS 的顺利部署，以便你的用户能够充分利用 Insights。

### <a name="users"></a>用户
*   请确保 *所有用户* 都列出在你提供的文件中并且已同步。 这包括需要查看其所在组织单位的数据的所有学生和教职员工。

    如果你当前只在 SIS 中列出了教师，则将文件上传到 SIS 并同步数据之前，请手动添加其他用户。

    如果缺少部分学生，则见解将仅从已注册的学生收集统计信息，这会使数据和结论引起误导。
    
*   请确保 *提供每个用户的名字和姓氏*。 如果未提供，则将引用用户的电子邮件地址，这会使报告和聚光灯（包含学生活动或表现见解的卡片）提供一种不太积极的体验。

*   *必须为年级输入 2 位数字*（例如，7 年级为 07）。 查看[映射列表](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)。 

*   *为所有学生添加年级* 以便年级可以筛选数据，这一点非常重要。    

*   请确保 *将每个用户分配到其相关的组织单位*。 这样，我们不会基于每个单位的汇总数据在聚光灯下显示误导性数据。

    *   一名学生可以与多个组织单位相关联，例如，在特别课程或两个院系中注册的学生。 在这种情况下，请在该学生的用户文件中提供两行内容 - 每个组织一行。
    
    *   根据教职员工的组织单位，你可定义相关权限。 确保他们与正确的单位级别相关联，以便获得所需的权限。 例如，分配给四所学校的辅导员需要查看这些学校的所有课程；校长需要看其学校的所有班级。 
    
*   该角色非常重要。 尽管这是一个封闭列表，但请尝试将[列表](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)中的角色与你上传的每个用户的真实角色进行匹配。 这样，你就可以相应地分配基于角色的权限。 例如，为所有校长提供查看其学校中的班级的权限，或授予所有教授查看教职员工的权限。 

### <a name="organizations"></a>组织

* 请确保 *反映组织的真实层次结构*。 这可以通过手动添加文件来实现。 在某些情况下，SIS 中未反映此层次结构。 但是，在这里仍可能需要按层次结构的各个级别查看相关汇总、为特定级别分配权限、按组织级别设置目标等。 

* 确保 *组织树下的所有组织单位都包括学生或班级*，以汇总学生数据。 我们建议学生位于树的最低分支上。

> [!NOTE]
> 有关 SDS 部署的详细信息，请访问[规划 SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)。

## <a name="integrate-sis-using-sds"></a>使用 SDS 集成 SIS

Office 365 教育版中提供了学校数据同步 (SDS)。 SDS 将读取教育机构的学生信息系统 (SIS) 数据，并将其与 Teams 集成，以便自动创建在线课堂和用户。

它还将 SIS 数据与见解同步。

### <a name="sync-with-insights"></a>与见解同步

首先，需要打开“见解”开关，以开始同步过程。

* 在“[**SDS 门户**](https://sds.microsoft.com)”上，转到“**设置**”，向下滚动到“**为见解收集数据**”并检查其是否已启用（默认情况下已 *启用*）。

* 向下滚动到下一个开关“**从 SDS 同步组织数据(预览)**”，然后打开它。

如果你在“设置”页面上未看到“*从 SDS 同步组织数据(预览)*”选项，请转到 [注册页面](https://aka.ms/insights/join)以提供你的信息，团队成员随后会与你联系。

:::image type="content" source="media/insights-sds-settings.png" alt-text="“与见解同步”开关":::

### <a name="deploy-sds"></a>部署 SDS
**如果你已经在使用 SDS**，我们建议你遵循 [最佳做法](#best-practices)。 

若要将当前配置文件与见解同步，请转到“**同步配置文件**”，单击“**编辑**”，然后选择“**同步到见解**”。 对于初始同步，我们建议在从 SIS 刷新数据后等待 24 小时，以便报告可用。  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="与见解同步配置文件开关":::

**如果你尚未使用 SDS**，那么现在需要 [部署它](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)。

在部署过程中，你可以决定是要使用 SDS 在 Teams 中预配用户和班级，还是仅使用 SDS 来向见解提供数据。

> [!NOTE]
> 如果现在是年中，并且你已经手动创建团队，则仅使用 SDS 将数据提供给见解，明年再考虑使用 SDS 在 Teams 中预配用户和班级。

### <a name="verify-the-sync-process"></a>验证同步过程
“设置”页面上的“从 SDS 同步组织数据（预览）”旁边将显示一个新的状态区域。
 
*   如果状态为“**正在进行**”，请在部署 SDS 配置文件后最多等待 24 小时。

*   如果状态为“**已完成**”，那么恭喜你，你可以在组织级别查看见解，然后继续执行下一步。

*   如果状态为“**已完成但出现错误**”、“**已完成但出现警告**”或“**已中止**”，请下载包含最新同步的错误和警告的日志文件，并检查是否可以修复这些错误。 

> [!IMPORTANT]
> 如果你遇到任何问题，[客户支持](https://aka.ms/edusupport)将为你提供帮助。
