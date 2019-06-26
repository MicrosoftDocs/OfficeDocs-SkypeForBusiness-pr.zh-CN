---
title: 批量编辑 Microsoft Teams 用户设置
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft 团队管理中心中批量管理 Microsoft 团队用户设置。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a80b39513fe86e0c49cd88988cb3f245129b2d0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221353"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>批量编辑 Microsoft 团队用户设置

作为管理员, 你可以在 Microsoft 团队管理中心管理团队用户设置。 在 "**用户**" 页面上, 您可以查看有关帐户和授权详细信息, 以及编辑策略和其他设置的信息。 您可以为用户单独或多个用户编辑设置。

## <a name="edit-user-settings-in-bulk"></a>批量编辑用户设置

使用 Microsoft 团队管理中心编辑多个用户一次的设置。 我们建议您每次编辑20个用户的设置。 若要编辑大量用户的设置, 请使用 PowerShell。 有关详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

1. 在 Microsoft 团队管理中心的左侧导航中, 选择 "**用户**"。
2. 搜索要编辑的用户或筛选视图以显示要编辑的用户。
3. 在 " **&#x2713;** " (复选标记) 列中, 通过执行下列操作之一选择 "用户":
    - 一次选择一个用户。 将在您选择的每个用户旁显示一个 **&#x2713;** 。 如果你选择超过20个用户, 则不会被阻止, 但请记住, 你选择的用户越多, 完成操作所需的时间就越长。

        ![显示用户选择的 "用户" 页面的屏幕截图](media/bulk-edit-user-settings-select-users.png)

    - 单击表格顶部的 "&#x2713;" (复选标记), 选择 "所有用户 (最多20个用户)", 然后在 "**选择限制**" 对话框中, 单击 "**继续选择全部**" 以完成选择。

        !["用户" 页面的屏幕截图, 显示所选内容的限制](media/bulk-edit-user-settings-select-all-limit.png) <br> 所选用户旁将显示一个 **&#x2713;** 。

        !["用户" 页面的屏幕截图, 显示选择了20个用户](media/bulk-edit-user-settings-select-all.png)
4. 单击 "**编辑设置**", 进行所需的更改, 然后单击 "**保存**"。

    !["编辑设置" 窗格的屏幕截图](media/bulk-edit-user-settings-edit-settings.png)
