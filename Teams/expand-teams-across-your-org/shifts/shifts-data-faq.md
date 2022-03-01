---
title: 班次数据常见问题解答
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
description: 获取有关 Shifts 数据的常见问题的解答，包括 Shifts 数据的存储位置、数据保留、检索和加密。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039950"
---
# <a name="shifts-data-faq"></a>班次数据常见问题解答

本文介绍有关 Shifts 数据的常见问题，包括 Shifts 数据的存储位置、数据保留、检索和加密。

## <a name="where-is-shifts-data-stored"></a>Shifts 数据存储在何处？

Shifts 数据存储在三个地理位置之一 (地理位置) ：亚太 (APAC) 、欧盟 () 或美国。 每个地理区域将数据存储在至少两个 Azure 数据中心区域，用于高可用性 (HA) 灾难恢复 (DR) 。 目前，美国/北美地区使用美国中北部和美国中南部数据中心。 有关详细信息，请参阅[存储Microsoft 365的位置](/microsoft-365/enterprise/o365-data-locations)。

目前，Shifts 提供澳大利亚、加拿大、法国、日本和英国的数据驻留。 我们正在努力将支持扩展到更多位置。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>能否选择 Shifts 数据的存储位置？

首次设置订阅Teams，请选择在订阅级别设置的一个或多个国家/地区。 如果支持该区域，Shifts 将采用此选择，并使用在 Teams 中设置的区域设置和地区。 如果尚未位于该区域，我们会将数据存储在我们支持的邻近区域。 将来，我们计划将现有数据（如果存储在邻近区域）迁移到在 Teams 中预配的区域。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>我能否在 Shifts 中访问和导出或删除用户的个人数据？

班次是符合 GDPR (一) 数据保护条例。称为数据主体 (用户对个人数据采取) 的正式请求称为数据主体请求 (DSR) 。 可以在 Shifts 中查找个人数据并处理这些数据以响应 DSR。

您可以使用搜索工具中的内容搜索电子数据Microsoft 365 合规中心搜索和导出日程安排和时间时钟数据以Excel。 对于所有其他 Shifts 数据，可以拍摄数据的屏幕截图。

有关详细信息，请参阅Office 365 [GDPR 和 CCPA 的数据主体请求](/microsoft-365/compliance/gdpr-dsr-office365)。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>如果我为组织关闭班次，Shifts 数据会发生什么情况？

关闭组织中班次 *不会* 删除数据。 如果关闭"班次"，之后再打开"班次"，则"班次"数据仍然可用。

如果删除租户，则保留期结束后会删除所有 Shifts 数据。

没有仅删除 Shifts 数据的选项。 如果删除团队，Teams保留期结束后，将删除与该团队关联的 Shifts 计划数据。 有关详细信息，请参阅数据[保留、删除和销毁Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>能否恢复已删除的排班计划？

如果备份已删除计划Microsoft 365组或 (团队，可以恢复Teams) 计划。

默认情况下，已删除的Microsoft 365组将保留 30 天。 此 30 天期限称为"软删除"，因为仍然可以还原组。 有关详细信息，请参阅[还原已删除的Microsoft 365组](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>能否对 Shifts 数据使用自定义保留策略？

目前，Shifts 不支持自定义保留策略。

若要详细了解 Teams 中的保留策略，请参阅[了解](/microsoft-365/compliance/retention-policies-teams) [Teams 保留策略](../../retention-policies.md)和管理Teams。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>我能否检索许可证被吊销的用户的 Shifts 数据？

目前，我们不提供检索许可证被吊销的用户的数据的能力。 此功能是我们正在致力于实现的功能。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts 对静态数据和传输中数据使用哪种类型的加密？

Shifts 数据由 Azure Cosmos DB 和 Azure 存储 进行存储。 有关详细信息，请参阅 [Azure 静态数据加密](/azure/security/fundamentals/encryption-atrest)和 [Azure Cosmos DB 中数据加密](/azure/cosmos-db/database-encryption-at-rest)。

班次遵循Microsoft 365传输中数据加密的准则。 有关详细信息，请参阅 [传输中数据的加密](/compliance/assurance/assurance-encryption-in-transit)。

SOC2 符合性审核每年验证静态数据和传输中数据的轮次加密。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>我能否访问 Shifts 数据的不可变副本？

我们不存储 Shifts 数据的不可变副本。 例如，经理可以更改日程安排，例如添加备注、更改排班时间、分配任务等。

## <a name="can-shifts-data-be-edited"></a>可以编辑 Shifts 数据吗？

Shift 的某些方面无法更改，某些方面是可更改的。 例如，可以编辑诸如备注和颜色等班次详细信息，就像在 Shifts 应用中更改它们的方式一样。 除非请求被撤消，否则无法编辑班次请求。

若要了解哪些字段已更改，可以在"更改"字段中Microsoft 365 审核日志"Shifts 事件"。 若要了解有关在活动记录到的 Shifts 活动Microsoft 365 审核日志，请参阅活动Teams[班次](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>我的组织使用员工管理系统进行日程安排。 我们能否与 Shifts 数据集成并访问这些数据？

使用 shifts Graph API 可以将 Shifts 数据与 WFM (外部员工) 集成。 有关详细信息，请参阅 [Shifts Graph API](/graph/api/resources/shift)。

我们还提供托管的 Shifts 连接器和开源 Shifts 连接器。 使用这些连接器，可以直接将 WFM 系统与 Shifts 集成。 若要详细了解 Shifts 连接器和支持的 WFM 系统，请参阅 [Shifts 连接器](shifts-connectors.md)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts 数据能否在指定的时间段后永久删除？

目前，我们不会删除您的 Shifts 数据。 使用 [Shifts Graph](/graph/api/resources/shift) API，可以创建使用 Power Apps 以将数据保留指定的一段时间[](/powerapps/maker/)的应用。 但是，我们本机不支持此操作。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>可以在租户到租户迁移中移动 Shifts 数据吗？

根据特定请求，可以将 Shifts 数据从一个租户迁移到另一个租户。 请记住，租户到租户的迁移不受开箱即用的支持，但可以作为客户请求提出。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](../shifts-for-teams-landing-page.md)
- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
