---
title: 转移数据常见问题解答
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 获取有关 Shifts 数据的常见问题解答，包括 Shifts 数据的存储位置、数据保留、检索和加密。
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
ms.openlocfilehash: 35aaa2ed083c4e8d52c6154f31fbfc537cee9cdc
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046732"
---
# <a name="shifts-data-faq"></a>转移数据常见问题解答

本文介绍有关 Shifts 数据的常见问题，包括 Shifts 数据的存储位置、数据保留、检索和加密。

## <a name="where-is-shifts-data-stored"></a>Shifts 数据存储在何处？

移位数据存储在三个地理位置之一 () ：亚太地区 (APAC) 、欧盟 (欧盟) 或美国。 每个地理位置将数据存储在至少两个 Azure 数据中心区域中，以实现高可用性 (HA) 和灾难恢复 (DR) 。 今天，美国/北美地理位置使用中北部和中南部美国的数据中心。 若要了解详细信息，请参阅 [Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)。

目前，Shifts 在澳大利亚、加拿大、法国、日本和英国提供数据驻留。 我们正积极努力将支持扩展到更多位置。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>是否可以选择 Shifts 数据的存储位置？

首次设置 Teams 时，选择在订阅级别设置的国家或地区。 Shifts 遵循此选择，并使用 Teams 中设置的区域设置（如果我们支持该区域）。 如果尚未在该区域中，我们会将数据存储在我们支持的附近区域中。 将来，我们计划将现有数据（如果存储在附近区域）迁移到 Teams 中预配的区域。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>是否可以在 Shifts 中访问和导出或删除用户的个人数据？

换班是符合 GDPR (一般数据保护法规) 。  (称为数据主体) 对其个人数据采取行动的人员的正式请求称为数据主体请求 (DSR) 。 可以在 Shifts 中查找和处理个人数据，以响应 DSR。

可以使用Microsoft Purview 合规门户中的内容搜索电子数据展示工具搜索计划和时间时钟数据并将其导出到 Excel。 对于所有其他 Shifts 数据，可以拍摄数据的屏幕截图。

若要了解详细信息，请参阅 [OFFICE 365 GDPR 和 CCPA 的数据主体请求](/microsoft-365/compliance/gdpr-dsr-office365)。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>如果我为组织关闭 Shifts，Shifts 数据会发生什么情况？

在组织中关闭 Shifts *不会* 删除数据。 如果关闭 Shifts，然后打开 Shifts，则 Shifts 数据仍将可用。

如果删除租户，则会在保留期结束后删除所有 Shifts 数据。

没有仅删除 Shifts 数据的选项。 如果在 Teams 中删除团队，则在保留期结束后删除与该团队关联的 Shifts 计划数据。 若要了解详细信息，请参阅 [Microsoft 365 中的数据保留、删除和销毁](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>是否可以恢复已删除的 Shifts 计划？

如果支持它的 Microsoft 365 组 (或 Teams) 中的团队还原，则可以恢复已删除的计划。

默认情况下，已删除的 Microsoft 365 组将保留 30 天。 此 30 天时间段称为“软删除”，因为您仍然可以还原组。 若要了解详细信息，请参阅 [还原已删除的 Microsoft 365 组](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>是否可以对 Shifts 数据使用自定义保留策略？

目前，Shifts 不支持自定义保留策略。

若要详细了解 Teams 中的保留策略，请 [参阅了解 Teams 的保留](/microsoft-365/compliance/retention-policies-teams) 情况 [和管理 Teams 的保留策略](../../retention-policies.md)。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>是否可以检索已吊销许可证的用户的 Shifts 数据？

目前，我们不提供为已吊销许可证的用户检索数据的功能。 此功能是我们正在努力实现的。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts 对静态数据和传输中的数据使用哪种类型的加密？

移位数据由 Azure Cosmos DB 和 Azure 存储进行静态加密。 若要了解详细信息，请参阅 Azure [Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) [中的静态 Azure 数据](/azure/security/fundamentals/encryption-atrest)加密和数据加密。

班次遵循 Microsoft 365 传输中数据加密指南。 若要了解详细信息，请参阅传输 [中数据的加密](/compliance/assurance/assurance-encryption-in-transit)。

SOC2 合规性审核每年验证静态和传输中数据的班次加密。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>是否可以访问 Shifts 数据的不可变副本？

我们不存储 Shifts 数据的不可变副本。 例如，管理器可以对计划进行更改，例如添加笔记、更改班次、分配任务等。

## <a name="can-shifts-data-be-edited"></a>是否可以编辑 Shifts 数据？

班次的某些方面是无法更改的，某些方面是可以更改的。 例如，可以编辑诸如备注和颜色等移位详细信息，类似于在 Shifts 应用中更改它们的方式。 除非撤回请求，否则无法编辑班次请求。

若要查看哪些字段已更改，可以搜索 Shifts 事件的 Microsoft 365 审核日志。 若要详细了解在 Microsoft 365 审核日志中为 Shifts 活动记录的事件，请参阅 [Teams 中的 Shifts 活动](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>我的组织使用员工管理系统进行计划。 我们能否与 Shifts 数据集成并访问 Shifts 数据？

通过 Shifts Graph API，可以将 Shifts 数据与外部员工管理 (WFM) 系统集成。 若要了解详细信息，请参阅 [Shifts Graph API](/graph/api/resources/shift)。

我们还提供托管 Shifts 连接器。 借助这些连接器，可以直接将WFM系统与 Shifts 集成。 若要详细了解 Shifts 连接器和支持的WFM系统，请[参阅 Shifts 连接器](/microsoft-365/frontline/shifts-connectors)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>在指定的时间段后，是否可以永久删除 Shifts 数据？

今天，我们根本不会删除 Shifts 数据。 使用 [Shifts Graph API](/graph/api/resources/shift)，可以 [使用 Power Apps 创建应用](/powerapps/maker/) 来保留指定时间段的数据。 但是，我们不以本机方式支持此功能。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>是否可以在租户到租户的迁移中移动 Shifts 数据？

根据特定请求，可以将数据从一个租户迁移到另一个租户。 请记住，不支持现成的租户到租户迁移，但可以作为客户请求提出。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](../shifts-for-teams-landing-page.md)
- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
