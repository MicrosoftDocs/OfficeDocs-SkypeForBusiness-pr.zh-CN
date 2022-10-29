---
title: 排班数据常见问题解答
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 获取有关排班数据的常见问题解答，包括排班数据的存储位置、数据保留、检索和加密。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a8b6620b86154ba3903024d3b48c53e717b204a5
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784447"
---
# <a name="shifts-data-faq"></a>排班数据常见问题解答

本文介绍有关排班数据的常见问题，包括排班数据的存储位置、数据保留、检索和加密。

## <a name="where-is-shifts-data-stored"></a>排班数据存储在哪里？

排班数据存储在以下三个地理位置之一 (地理) ：亚太地区 (亚太地区) 、欧盟 (欧盟) 或美国。 每个异地将数据存储在至少两个 Azure 数据中心区域，以实现高可用性 (HA) 和灾难恢复 (DR) 。 目前，美国/北美地理区域使用中北部和中南部美国的数据中心。 若要了解详细信息，请参阅 [Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)。

目前，Shifts 在澳大利亚、加拿大、法国、日本和英国提供数据驻留。 我们正积极努力将支持扩展到更多位置。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>是否可以选择排班数据的存储位置？

首次设置 Teams 时，选择在订阅级别设置的国家或地区。 班次遵循此选择，并使用在 Teams 中设置的区域设置和区域（如果我们支持该区域）。 如果尚未位于该区域，我们会将数据存储在我们支持的附近区域。 将来，我们计划将存储在附近区域中的现有数据迁移到 Teams 中预配的区域。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>是否可以在排班中访问和导出或删除用户的个人数据？

班次符合 GDPR (一般数据保护条例) 。  (称为数据主体) 对其个人数据执行操作的人员的正式请求称为数据主体请求 (DSR) 。 可以在班次中查找个人数据并对其执行操作，以响应 DSR。

可以使用Microsoft Purview 合规门户中的内容搜索电子数据展示工具搜索计划和时钟数据并将其导出到 Excel。 对于所有其他排班数据，可以获取数据的屏幕截图。

若要了解详细信息，请参阅 [GDPR 和 CCPA Office 365数据主体请求](/microsoft-365/compliance/gdpr-dsr-office365)。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>如果为组织关闭排班，排班数据会发生什么情况？

关闭组织中的排班 *不会* 删除数据。 如果关闭“排班”，然后打开“班次”，则排班数据仍将可用。

如果删除租户，则会在保留期结束后删除所有排班数据。

没有仅删除 Shifts 数据的选项。 如果在 Teams 中删除团队，则与该团队关联的排班计划数据将在保留期结束后删除。 若要了解详细信息，请参阅 [Microsoft 365 中的数据保留、删除和销毁](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>是否可以恢复已删除的排班计划？

如果还原了 (Microsoft 365 组或 Teams) 中的团队，则可以恢复已删除的计划。

默认情况下，已删除的 Microsoft 365 组将保留 30 天。 此 30 天期限称为“软删除”，因为您仍然可以还原组。 若要了解详细信息，请参阅 [还原已删除的 Microsoft 365 组](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>是否可以对排班数据使用自定义保留策略？

目前，班次不支持自定义保留策略。

若要详细了解 Teams 中的保留策略，请参阅 [了解 Teams 的保留](/microsoft-365/compliance/retention-policies-teams) 和管理 [Teams 的保留策略](../../retention-policies.md)。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>是否可以检索许可证被吊销的用户的排班数据？

目前，我们不提供检索许可证已吊销用户数据的功能。 此功能是我们正在努力实现的。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts 对静态数据和传输中的数据使用哪种类型的加密？

班次数据由 Azure Cosmos DB 和 Azure 存储进行静态加密。 若要了解详细信息，请参阅 [Azure 静态数据加密](/azure/security/fundamentals/encryption-atrest) 和 [Azure Cosmos DB 中的数据加密](/azure/cosmos-db/database-encryption-at-rest)。

班次遵循 Microsoft 365 中传输数据加密指南。 若要了解详细信息，请参阅 [传输中数据的加密](/compliance/assurance/assurance-encryption-in-transit)。

SOC2 合规性审核每年验证静态和传输中的数据的班次加密。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>是否可以访问排班数据的不可变副本？

我们不存储排班数据的不可变副本。 例如，经理可以对计划进行更改，例如添加备注、更改轮班时间、分配任务等。

## <a name="can-shifts-data-be-edited"></a>是否可以编辑排班数据？

班次的某些方面是无法更改的，某些方面是可以更改的。 例如，可以编辑排班详细信息（如备注和颜色），类似于在排班应用中更改它们的方式。 除非请求被撤销，否则无法编辑移位请求。

若要查看哪些字段已更改，可以在 Microsoft 365 审核日志中搜索排班事件。 若要详细了解 Microsoft 365 审核日志中为排班活动记录的事件，请参阅 [Teams 中的排班活动](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>我的组织使用劳动力管理系统进行计划。 是否可以集成并访问排班数据？

Shifts Graph API 使你可以将排班数据与外部劳动力管理 (WFM) 系统集成。 若要了解详细信息，请参阅 [Shifts Graph API](/graph/api/resources/shift)。

我们还提供托管排班连接器。 使用这些连接器，可以直接将 WFM 系统与 Shifts 集成。 若要详细了解排班连接器和支持的WFM系统，请参阅[排班连接器](/microsoft-365/frontline/shifts-connectors)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>是否可以在指定时间段后永久删除 Shifts 数据？

目前，我们根本不删除你的排班数据。 使用 [Shifts Graph API](/graph/api/resources/shift)，可以使用 [Power Apps 创建应用](/powerapps/maker/) ，以在指定时间段内保留数据。 但是，我们本身不支持此功能。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>是否可以在租户到租户迁移中移动 Shifts 数据？

若要将现有排班数据迁移到另一个租户，需要导出日期范围的排班计划，根据需要修改用户名 () ，然后将计划导入到目标租户。 一次最多可以导出 100 天的排班数据。 日期范围可以是过去或将来。 如果需要导出数据的时间范围超过 100 天，请重复此过程。

在迁移排班数据之前，请确保满足以下要求：

- 目标租户域、团队和团队成员必须已存在。 迁移不会创建团队或更改团队成员身份或所有权。
- 班次应用必须在目标租户的团队中设置，并且计划为空。 请记住，迁移不会替换或删除现有数据。 这意味着，如果团队有现有计划，用户可能会看到重复或冲突的班次，需要手动解决。
- 未迁移待审批) 的开放请求 (，例如交换请求和休假请求。 建议在开始迁移数据之前关闭所有打开的请求。

下面概述了将排班数据迁移到另一个租户的步骤。

1. 在源租户中，对于每个团队，导出排班计划：
    1. 在“排班”的“ **计划** ”页上，转到 **“更多选项 (...)** > **导出计划**”。
    1. 选择日期范围。
    1. 启用 **可导入的格式** 的“导出”，然后选择“ **导出**”。 排班计划数据导出到 Excel 文件。
1. 在迁移过程中，如果任何团队成员正在切换其电子邮件域，请手动更新 Excel 文件，将用户主体名称 (UPN) 更改为目标租户域。
1. 在目标租户中，将计划导入到每个团队。
    1. 在“排班”的“ **计划** ”页上，转到 **“ (...)** > **导入计划的** 更多选项”。
    1. 选择“ **上传文件**”，转到该团队的 Excel 文件，然后选择“ **打开**”。

若要了解详细信息，请参阅 [排班的 Excel 模板](https://support.microsoft.com/office/the-excel-template-for-shifts-6fc6a206-e7cc-4907-87b8-a296bae84ce3)。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](../shifts-for-teams-landing-page.md)
- [管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
