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
description: 了解如何使用 Shifts 连接器向导将 Teams 中的 Shifts 与 Blue Yonder Workforce Management 集成。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593635"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management

## <a name="overview"></a>概述

Microsoft 365 管理中心中的 Shifts 连接器向导使你能够将 Microsoft Teams 中的 Shifts 应用与 WFM) 系统 (员工管理集成。 设置连接后，一线工作人员可以从 Shifts 中无缝查看和管理 WFM 系统中的日程安排。

向导配置 Shifts 连接器，创建到 WFM 系统的连接，并应用所选的同步设置和团队映射。 同步设置确定在 WFM 系统和 Shifts 之间同步的计划信息。 团队映射定义 WFM 站点与Teams中的团队之间的同步关系。 可以映射到现有团队和新团队。

可以设置多个连接，每个连接都具有不同的同步设置。 例如，如果你的组织具有多个具有不同计划要求的位置，请为每个位置创建具有唯一同步设置的连接。 请记住，WFM 站点只能在任何给定时间映射到一个团队。 如果 WFM 站点已映射到团队，则无法将其映射到另一个团队。

使用 WFM 系统作为记录系统，一线工作人员可以在其设备上的 Shifts 中查看和交换班次、管理其可用性和请求休假时间。 一线管理人员可以继续使用 WFM 系统来设置计划。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>将 Shifts 与 Blue Yonder 员工管理集成

目前，该向导支持[适用于 Blue Yonder 的 Microsoft Teams Shifts 连接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)。 使用此连接器，可以将 Shifts 与 Blue Yonder Workforce Management (Blue Yonder WFM) 集成，以管理计划并使其保持最新状态。 本文介绍如何运行向导，通过连接器设置与 Blue Yonder WFM 的连接。

> [!NOTE]
> 还可以使用 PowerShell 将 Shifts 与 Blue Yonder WFM 集成。 若要了解详细信息，请参阅 [使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)。

## <a name="before-you-begin"></a>开始之前

必须是Microsoft 365全局管理员才能运行向导。

### <a name="prerequisites"></a>先决条件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 要映射的团队没有任何计划。 如果团队有现有计划，请 [先从团队中删除计划](#remove-schedules-from-teams-you-want-to-map) ，然后再将 Blue Yonder WFM 站点映射到它。 否则，你将看到重复的班次。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>从要映射的团队中删除计划
<a name="remove_schedules"> </a>

> [!NOTE]
> 如果要将 Blue Yonder WFM 站点映射到具有计划的现有团队，请完成此步骤。 如果映射到没有任何计划的团队，或者正在创建要映射到的新团队，则可以跳过此步骤。

使用 PowerShell 从团队中删除计划。

1. 首先，需要安装 PowerShell 模块并进行设置。 按照步骤 [设置环境](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 运行以下命令：

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    若要 `EntityType` 获取参数的方案列表，请运行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。 将删除指定的日期和时间范围的计划数据。

若要了解详细信息，请参阅 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)。

## <a name="run-the-wizard"></a>运行向导

### <a name="get-started"></a>开始使用

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com/)的左侧导航中，选择 **“设置**”，然后转到 **“应用”和“电子邮件**”部分。
1. **选择连接员工管理系统**。 在这里，可以在将 Shifts 连接器连接到 WFM 系统时详细了解 Shifts 连接器以及一线工作人员和管理器体验。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 管理中心中 Shifts 连接器向导的详细信息页的屏幕截图。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 准备就绪后，选择 **开始**。
1. 选择 **“下一步** ”以创建蓝色 Yonder WFM 连接。

### <a name="enter-connection-details"></a>输入连接详细信息
<a name="connection_details"> </a>

1. 在“连接详细信息”页上，为连接提供唯一名称。 它不能超过 128 个字符或具有任何特殊字符。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="向导的“连接详细信息”页的屏幕截图，其中显示了连接设置。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. 输入 Blue Yonder WFM 服务帐户名称、密码和服务 URL。
1. 完成后，选择 **“下一步** ”以测试与输入的设置的连接。

### <a name="choose-sync-settings"></a>选择同步设置
<a name="sync"> </a>

在“同步设置”页上，选择要从 Blue Yonder WFM 同步到 Shifts 的信息、同步频率以及 Shifts 用户是否可以对数据进行更改。

1. 输入Microsoft 365系统帐户。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="向导的“同步设置”页的屏幕截图，其中显示了同步设置。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. 在 **“电子邮件通知收件人**”下，选择接收有关此连接的电子邮件通知的人员。 可以添加单个用户和组。 电子邮件通知包含有关连接设置状态以及设置连接后可能发生的任何问题或错误的信息。
1. 选择同步设置：
    1. 在 **“计划”和“班次**”下，选择班次用户可以看到或更改的 Blue Yonder WFM 数据，然后设置同步频率。
    2. 在 **“请求**”下，选择班次用户可以看到和创建的请求类型。

    > [!IMPORTANT]
    > 如果选择以下任一选项来禁用打开的班次、打开的班次请求、交换请求或休假请求，则需要执行另一个步骤来隐藏 Shifts 中的功能。
    >
    > - 打开的班次： **班次用户将看不到 Blue Yonder WFM 数据**
    > - 交换请求： **为所有用户禁用功能**
    > - 休假请求： **为所有用户禁用功能**
    >
    > 运行向导后，请确保按照本文后面的 [“禁用打开的班次”、“打开班次请求”、“交换请求”和“休假请求](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) ”部分中的步骤操作。
 
1. 选择完设置后，选择 **“创建连接**”。

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>将 Blue Yonder Workforce Management 站点映射到团队
<a name="sites"> </a>

选择要连接到 Shifts 的 Blue Yonder WFM 站点。 最多可以选择 100 个站点。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="向导的屏幕截图，其中显示了 Blue Yonder WFM 站点的列表。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a>然后，将你选择的每个 Blue Yonder WFM 站点映射到Teams中的团队。 可以将站点映射到现有团队，也可以创建新团队。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="显示搜索团队选项并创建新团队选项的窗格的屏幕截图。" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>将站点映射到现有团队

1. 选择网站名称。
2. 在窗格中，搜索团队，然后选择它。 请记住，已映射到此连接中的网站的团队不会显示在搜索中。
3. 选择时区和最近的城市。
4. 选择 **“保存**”，然后选择 **“下一步**”。

#### <a name="to-map-a-site-to-a-new-team"></a>将站点映射到新团队

1. 选择网站名称。
2. 在窗格中，选择 **“创建新团队**”。 你将转到浏览器中的新选项卡，可在Microsoft 365 管理中心中创建新团队。
    1. 输入团队的名称和可选说明。
    1. 添加一个或多个团队所有者。 请确保将Microsoft 365系统帐户添加为所有者。
    1. 添加团队成员。
    1. 添加团队电子邮件地址并选择隐私设置。
    1. 查看设置，然后选择 **“添加团队**”。 创建团队后，选择 **“关闭**”。
3. 返回向导，搜索，然后选择创建的新团队。
4. 选择时区和最近的城市。
5. 选择 **“保存**”，然后选择 **“下一步**”。

### <a name="review-and-finish"></a>查看并完成

查看设置。 如果需要更改任何团队映射，请选择 **“编辑** ”以执行此操作。 准备就绪后，选择 **“完成**”。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="向导的“审阅”页的屏幕截图，其中显示了映射。" lightbox="../../media/shifts-connector-wizard-review.png":::

你将看到一条消息，确认我们收到了你的请求以及操作 ID。 记下操作 ID。 需要它来检查连接的安装状态。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="向导页的屏幕截图，其中显示了确认消息和操作 ID。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

向导启动设置连接并将站点映射到所选团队的过程。 此过程可能需要一些时间才能完成。 选择的收件人将收到有关设置状态的电子邮件通知。

选择 **“完成”** 以退出向导。

你在路上， 但你还没有完成！ 请务必检查电子邮件。 你将收到一个确认消息，确认我们收到了你的请求，以及有关如何检查安装状态的 [链接](shifts-connector-powershell-manage.md#check-connection-setup-status) 。

> [!NOTE]
> 如果在设置连接后连接中出现问题或错误，你将收到电子邮件通知。 按照电子邮件中的说明排查问题。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>禁用打开的班次、打开的班次请求、交换请求和休假请求

> [!IMPORTANT]
> 仅当选择以下任一选项以禁用打开的班次、打开的班次请求、交换请求或在向导中关闭请求时，才执行以下步骤。 完成此步骤会隐藏 Shifts 中的功能。
>
> - 打开的班次： **班次用户将看不到 Blue Yonder WFM 数据**
> - 交换请求： **为所有用户禁用功能**
> - 休假请求： **为所有用户禁用功能**
>
> 如果没有第二步，用户仍会在 Shifts 中看到该功能，如果尝试使用该功能，则会收到“不受支持的操作”错误消息。

若要隐藏 Shifts 中的打开班次、交换请求和休假请求，请使用图形 API[计划资源类型](/graph/api/resources/schedule?view=graph-rest-1.0)为映射到 ```false``` Blue Yonder WFM 站点的每个团队设置以下参数：

- 打开班次： ```openShiftsEnabled```
- 交换请求：  ```swapShiftsRequestsEnabled```
- 休假请求： ```timeOffRequestsEnabled```

若要在 Shifts 中隐藏打开的班次请求，请转到 **Shifts 中的设置**，然后关闭 **“打开班次**”设置。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>如果需要更改连接
<a name="update_connection"> </a>

设置连接后，可以使用 PowerShell 对其进行更改。 例如，可以更新同步设置、团队映射和禁用连接同步。 有关分步指南，请参阅 [使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>相关文章

- [Shifts 连接器](shifts-connectors.md)
- [使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)
- [在Teams中管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
