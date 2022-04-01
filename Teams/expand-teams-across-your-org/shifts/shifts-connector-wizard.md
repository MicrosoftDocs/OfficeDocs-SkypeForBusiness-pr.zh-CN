---
title: 使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用 Shifts 连接器向导将 Shifts Teams Blue Yonder Workforce Management 集成。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593635"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management

## <a name="overview"></a>概述

使用 Microsoft 365 管理中心 中的 Shifts 连接器向导，可以将 Microsoft Teams 中的 Shifts 应用与员工管理 (WFM) 系统。 设置连接后，一线员工可以从 Shifts 中无缝查看和管理 WFM 系统中日程安排。

向导将配置 Shifts 连接器，创建到 WFM 系统的连接，并应用选择的同步设置和团队映射。 同步设置确定在 WFM 系统和 Shifts 之间同步的计划信息。 团队映射定义 WFM 网站与团队之间的同步Teams。 可以映射到现有团队和新团队。

可以设置多个连接，每个连接具有不同的同步设置。 例如，如果组织有多个具有不同计划要求的位置，请为每个位置创建具有唯一同步设置的连接。 请记住，WFM 网站在任何给定时间只能映射到一个团队。 如果 WFM 网站已映射到团队，则不能映射到另一个团队。

使用 WFM 系统作为记录系统，一线员工可以在他们的设备上查看和调班、管理其可用性以及请求请假。 一线经理可以继续使用 WFM 系统来设置计划。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>将 Shifts 与 Blue Yonder Workforce Management 集成

目前，该向导支持 [Microsoft Teams Blue Yonder 的 Shifts 连接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)。 此连接器使你能够将 Shifts 与 Blue Yonder Workforce Management (Blue Yonder WFM) ，以管理计划并使它们保持最新。 本文将演练如何运行向导，以通过连接器设置与 Blue Yonder WFM 的连接。

> [!NOTE]
> 也可使用 PowerShell 将 Shifts 与 Blue Yonder WFM 集成。 有关详细信息，请参阅 [使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)。

## <a name="before-you-begin"></a>开始之前

只有全局管理员Microsoft 365才能运行向导。

### <a name="prerequisites"></a>先决条件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 要映射的团队没有任何日程安排。 如果团队已有计划，请从团队[](#remove-schedules-from-teams-you-want-to-map)中删除计划，然后再将 Blue Yonder WFM 网站映射到该团队。 否则，你将看到重复的班次。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>从要映射的团队中删除日程安排
<a name="remove_schedules"> </a>

> [!NOTE]
> 如果要将 Blue Yonder WFM 网站映射到具有计划的现有团队，请完成此步骤。 如果要映射到没有任何计划的团队，或者要创建要映射到的新团队，可以跳过此步骤。

使用 PowerShell 从团队中删除日程安排。

1. 首先，需要安装 PowerShell 模块并完成设置。 按照步骤 [设置环境](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 运行以下命令：

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    若要获取参数的方案 `EntityType` 列表，请运行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。 将删除指定的日期和时间范围内的计划数据。

有关详细信息，请参阅 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)。

## <a name="run-the-wizard"></a>运行向导

### <a name="get-started"></a>开始使用

1. 在页面左侧导航 [Microsoft 365 管理中心，选择](https://admin.microsoft.com/)**"设置"**，然后转到"应用 **和电子邮件"** 部分。
1. 选择 **连接员工管理系统"**。 在此处，可以了解有关 Shifts 连接器以及将 Shifts 连接到 WFM 系统的一线员工和经理体验。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text=""Shifts 连接器"向导详细信息页的屏幕截图Microsoft 365 管理中心。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 准备就绪后，选择"开始 **"**。
1. 选择 **"下** 一步"创建蓝色 Yonder WFM 连接。

### <a name="enter-connection-details"></a>输入连接详细信息
<a name="connection_details"> </a>

1. 在"连接详细信息"页上，为连接指定唯一名称。 不能超过 128 个字符或包含任何特殊字符。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="向导的"连接详细信息"页的屏幕截图，显示连接设置。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. 输入 Blue Yonder WFM 服务帐户名称和密码和服务 URL。
1. 完成后，选择"下一步"，使用输入的设置测试连接。

### <a name="choose-sync-settings"></a>选择同步设置
<a name="sync"> </a>

在"同步设置"页上，选择要从 Blue Yonder WFM 同步到 Shifts 的信息、同步频率以及 Shifts 用户是否可以更改数据。

1. 输入Microsoft 365帐户。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="向导的"同步设置"页的屏幕截图，显示同步设置。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. 在 **"电子邮件通知收件人"** 下，选择接收有关此连接的电子邮件通知的人。 可以添加单个用户和组。 电子邮件通知包含有关连接设置状态以及设置连接后可能会出现的任何问题或错误的信息。
1. 选择同步设置：
    1. 在 **"日程安排和排班**"下，选择 Shifts 用户可以查看或更改的 Blue Yonder WFM 数据，然后设置同步频率。
    2. 在 **"请求**"下，选择 Shifts 用户可以查看和创建的请求类型。

    > [!IMPORTANT]
    > 如果选择以下任一选项来禁用开班、打开班次请求、调班请求或请假请求，则需要执行另一个步骤来隐藏 Shifts 中的功能。
    >
    > - 打开班次 **：班次用户将看不到 Blue Yonder WFM 数据**
    > - 交换请求： **为所有用户禁用了功能**
    > - 请假请求： **已禁用所有用户的功能**
    >
    > 运行向导后，请确保按照本文稍后的禁用班次、打开班次请求、调班请求和请假 [请求部分中](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 的步骤操作。
 
1. 选择完设置后，选择"创建 **连接"**。

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>将 Blue Yonder Workforce 管理网站映射到团队
<a name="sites"> </a>

选择要连接到 Shifts 的 Blue Yonder WFM 站点。 可以选择最多 100 个网站。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="向导的屏幕截图，显示蓝色 Yonder WFM 站点列表。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a>然后，将所选每个 Blue Yonder WFM 站点映射到 Teams。 您可以将网站映射到现有团队，也可以创建新团队。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="显示搜索团队选项并创建新团队选项的窗格的屏幕截图。" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>将网站映射到现有团队

1. 选择网站名称。
2. 在窗格中，搜索团队，然后选择它。 请记住，已映射到此连接中的网站的团队不会显示在搜索中。
3. 选择时区和最近的城市。
4. 选择 **"保存**"，然后选择"下一 **步"**。

#### <a name="to-map-a-site-to-a-new-team"></a>将网站映射到新团队

1. 选择网站名称。
2. 在窗格中，选择 **"创建新团队"**。 你将在浏览器中找到一个新选项卡，可以在其中创建新Microsoft 365 管理中心。
    1. 输入团队的名称和可选说明。
    1. 添加一个或多个团队所有者。 请确保将系统帐户Microsoft 365所有者。
    1. 添加团队成员。
    1. 添加团队电子邮件地址并选择隐私设置。
    1. 查看设置，然后选择"添加 **团队"**。 创建团队后，选择"关闭 **"**。
3. 返回向导，搜索并选择你创建的新团队。
4. 选择时区和最近的城市。
5. 选择 **"保存**"，然后选择"下一 **步"**。

### <a name="review-and-finish"></a>审阅并完成

查看设置。 如果需要更改任何团队映射，请选择" **编辑** "以执行更改。 准备就绪后，选择"完成 **"**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="向导的"审阅"页的屏幕截图，显示映射。" lightbox="../../media/shifts-connector-wizard-review.png":::

你将看到一条消息，确认我们收到了你的请求以及操作 ID。 记下操作 ID。 需要它来检查连接的设置状态。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="向导页的屏幕截图，显示确认消息和操作 ID。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

向导将启动设置连接的过程，将网站映射到所选团队。 此过程可能需要一些时间才能完成。 你选择的收件人将收到有关设置状态的电子邮件通知。

选择 **"完成** "退出向导。

你已上路，但尚未完成！ 请务必检查电子邮件。 你将收到一条确认消息，指出我们已收到你的请求，以及[](shifts-connector-powershell-manage.md#check-connection-setup-status)一个链接，指向如何检查设置状态。

> [!NOTE]
> 如果在设置连接后连接中出现问题或错误，你将收到电子邮件通知。 请按照电子邮件中的说明解决问题。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>禁用开班、打开班次请求、调班请求和请假请求

> [!IMPORTANT]
> 只有在向导中选择了以下任一选项来禁用开班、打开班次请求、调班请求或请假请求时，才执行以下步骤。 完成此步骤会隐藏 Shifts 中的 功能。
>
> - 打开班次 **：班次用户将看不到 Blue Yonder WFM 数据**
> - 交换请求： **为所有用户禁用了功能**
> - 请假请求： **已禁用所有用户的功能**
>
> 如果不执行第二个步骤，用户仍将看到 Shifts 中的功能，如果用户尝试使用该功能，则收到"不支持的操作"错误消息。

若要在 Shifts 中隐藏未处理班次、调班请求和请假请求，请使用 图形 API [计划](/graph/api/resources/schedule?view=graph-rest-1.0)```false```资源类型，为映射到 Blue Yonder WFM 站点的每个团队设置以下参数：

- 打开班次： ```openShiftsEnabled```
- 交换请求：  ```swapShiftsRequestsEnabled```
- 请假请求： ```timeOffRequestsEnabled```

若要在 Shifts 中隐藏打开的班次请求，请转到设置中的"打开班次"设置，然后关闭"打开班次 **"** 设置。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>如果需要对连接进行更改
<a name="update_connection"> </a>

设置连接后，可以使用 PowerShell 对连接进行更改。 例如，可以更新同步设置、团队映射和禁用连接的同步。 有关分步指南，请参阅使用 [PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>相关文章

- [Shifts 连接线](shifts-connectors.md)
- [使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)
- [在应用程序中管理 Shifts Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
