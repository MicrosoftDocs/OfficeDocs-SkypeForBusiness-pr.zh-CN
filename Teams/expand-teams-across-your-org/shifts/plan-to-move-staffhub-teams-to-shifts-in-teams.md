---
title: 计划将 StaffHub 团队移动到倒班
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 使用此日程表帮助你的组织从 StaffHub 团队过渡到 Microsoft 团队中的倒班。
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: d38b3d7c67fd546fe73106413cd3505ea792b407
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350286"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>计划将 StaffHub 团队移动到 Microsoft 团队中的倒班

> [!IMPORTANT]
> 2020年6月30日生效，Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 将在2020年6月30日停止为所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。 

在开始规划更改时，从 StaffHub 到团队开始过渡。 为了帮助确保你的迁移到团队成功，我们创建了一个演示典型过渡计划的示例日程表。 示例日程表概括介绍了准备进行移动的规划活动，并指导您将组织的 StaffHub 团队迁移到团队。

将日程表用作规划从 StaffHub 迁移到团队的指导，并根据组织的需要对其进行自定义。 请务必查看链接到日程表中的步骤的资源。

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>准备将 StaffHub 团队移动到团队

|步骤 |指引  |源 |
|---------|---------|---------|
|1    |准备和识别利益干系人         |         |
|2     |查看有关从 StaffHub 切换到团队和团队成员的文档         |[StaffHub 已停用](microsoft-staffhub-to-be-retired.md)<br><br>[将 StaffHub 团队移动到团队中的倒班](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[开始使用 Teams](../../get-started-with-teams-quick-start.md)         |
|3    |为你的组织启用 Microsoft 365 组        |[Microsoft 365 组和团队](../../Office-365-groups.md)      |
|4    |请确保满足先决条件         |[检查是否满足先决条件](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |将团队许可证分配给组织中的 StaffHub 用户|[分配 Teams 许可证](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[管理用户对 Teams 的访问管理](../../user-access.md)      |
|6    |安装 StaffHub PowerShell 模块        |[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)        |
|7     |确定日程表和标识 StaffHub 用户以转到团队       |[运行报告以显示活动 StaffHub 的使用情况](run-report-to-show-staffhub-usage.md) |
|个     |确定没有 Azure AD 帐户的 StaffHub 用户（在 StaffHub 中显示为 "非活动"），并为其链接帐户     |[为没有联系人的 StaffHub 团队成员链接 Azure AD 帐户](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|db-9    |为您的组织量身定制的用户创建培训内容         |[为团队准备用户准备情况计划](../../upgrade-user-readiness.md)     |
|10    |向 StaffHub 用户传达切换到团队中的倒班         |[StaffHub 到团队的示例向用户发送电子邮件通信](staffhub-to-teams-email-template.md)         |
|11     |安装团队客户端         |[获取 Teams 客户端](../../get-clients.md) |
|至    |将 FirstLineWorker 应用设置策略分配给用户（或创建并分配自定义应用设置策略）以将倒班应用固定到团队客户端  |[将 FirstlineWorker 应用设置策略分配给用户](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|13     |培训用户如何使用倒班和团队         |[向团队中的用户的板载用户](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[班次帮助文档](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Teams 帮助文档](https://support.office.com/teams)<br><br>[Teams 培训视频](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |查看 StaffHub 团队的列表，确保应将这些团队中的所有用户移到团队。 删除不应在日程安排中的用户。 |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>将组织的 StaffHub 团队移动到团队

|步骤 |指引 |源  |
|---------|---------|---------|
|1  |确定试点团队并移动一个团队          |[移动 StaffHub 团队](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |验证试点团队并确定任何移动问题。 根据需要更新培训文档。         |         |
|3     |确定其他试点团队并移动五到十个团队         |[移动 StaffHub 团队](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |识别剩余的 StaffHub 团队并以分阶段方式移动         |[移动 StaffHub 团队](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |继续为倒班和团队提供支持         |         |
|6     |如果启用了自助密码重置，请运行报表，以支持团队中的登录问题       |[运行自助密码重置设置报告](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
