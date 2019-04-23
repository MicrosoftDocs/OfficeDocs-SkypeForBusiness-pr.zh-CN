---
title: 编辑批量的 Microsoft 团队用户设置
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何管理批量 Microsoft 团队管理中心中的 Microsoft 团队用户设置。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988970"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>编辑批量的 Microsoft 团队用户设置

作为一名管理员，您可以管理团队的 Microsoft 团队管理中心中的用户设置。 在**用户**页上，您可以查看信息，如帐户和许可的详细信息和编辑策略和其他设置。 单独或多个用户同时，您可以编辑用户的设置。

## <a name="edit-user-settings-in-bulk"></a>编辑批量的用户设置

使用 Microsoft 团队管理中心一次编辑多个用户的设置。 我们建议每次编辑 20 个用户的设置。 若要编辑的大量用户设置，请使用 PowerShell。 有关详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。

1. 在 Microsoft 团队管理中心的左侧导航窗格中，选择**用户**。
2. 您想要编辑或筛选视图以向用户显示要编辑的用户的搜索。
3. 在 **& #x 2713;**（复选标记） 列中，选择用户通过执行以下任一操作：
    - 一次选择一个用户。 **_AMP_ #x 2713;** 会显示您选择每个用户旁边。 如果您选择超过 20 个用户，您不会阻止，但请记住，您选择的多个用户，该操作将需要更长时间才能完成。

        ![显示用户选择用户页的屏幕截图](media/bulk-edit-user-settings-select-users.png)

    - 单击 & #x 2713;（复选标记） 要选择 （最多 20 个用户最多），所有用户，然后在**所选内容限制**对话框中，单击都**继续都选择全部**以完成所选内容的表的顶部。

        ![显示所选内容限制用户页的屏幕截图](media/bulk-edit-user-settings-select-all-limit.png) <br> **_AMP_ #x 2713;** 会显示所选用户旁边。

        ![用户页，显示所选的 20 个用户的屏幕截图](media/bulk-edit-user-settings-select-all.png)
4. 单击**编辑设置**，进行所需的更改，然后单击**保存**。

    ![编辑设置窗格的屏幕截图](media/bulk-edit-user-settings-edit-settings.png)
