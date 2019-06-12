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
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245055"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="76ace-103">批量编辑 Microsoft 团队用户设置</span><span class="sxs-lookup"><span data-stu-id="76ace-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="76ace-104">作为管理员, 你可以在 Microsoft 团队管理中心管理团队用户设置。</span><span class="sxs-lookup"><span data-stu-id="76ace-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="76ace-105">在 "**用户**" 页面上, 您可以查看有关帐户和授权详细信息, 以及编辑策略和其他设置的信息。</span><span class="sxs-lookup"><span data-stu-id="76ace-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="76ace-106">您可以为用户单独或多个用户编辑设置。</span><span class="sxs-lookup"><span data-stu-id="76ace-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="76ace-107">批量编辑用户设置</span><span class="sxs-lookup"><span data-stu-id="76ace-107">Edit user settings in bulk</span></span>

<span data-ttu-id="76ace-108">使用 Microsoft 团队管理中心编辑多个用户一次的设置。</span><span class="sxs-lookup"><span data-stu-id="76ace-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="76ace-109">我们建议您每次编辑20个用户的设置。</span><span class="sxs-lookup"><span data-stu-id="76ace-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="76ace-110">若要编辑大量用户的设置, 请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="76ace-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="76ace-111">有关详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="76ace-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="76ace-112">在 Microsoft 团队管理中心的左侧导航中, 选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="76ace-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="76ace-113">搜索要编辑的用户或筛选视图以显示要编辑的用户。</span><span class="sxs-lookup"><span data-stu-id="76ace-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="76ace-114">在 " **&#x2713;** " (复选标记) 列中, 通过执行下列操作之一选择 "用户":</span><span class="sxs-lookup"><span data-stu-id="76ace-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="76ace-115">一次选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="76ace-115">Select users one at a time.</span></span> <span data-ttu-id="76ace-116">将在您选择的每个用户旁显示一个 **&#x2713;** 。</span><span class="sxs-lookup"><span data-stu-id="76ace-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="76ace-117">如果你选择超过20个用户, 则不会被阻止, 但请记住, 你选择的用户越多, 操作将需要较长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="76ace-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![显示用户选择的 "用户" 页面的屏幕截图](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="76ace-119">单击表格顶部的 "&#x2713;" (复选标记), 选择 "所有用户 (最多20个用户)", 然后在 "**选择限制**" 对话框中, 单击 "**继续选择全部**" 以完成选择。</span><span class="sxs-lookup"><span data-stu-id="76ace-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="76ace-120">!["用户" 页面的屏幕截图, 显示所选内容的限制](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="76ace-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="76ace-121">所选用户旁将显示一个 **&#x2713;** 。</span><span class="sxs-lookup"><span data-stu-id="76ace-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        !["用户" 页面的屏幕截图, 显示选择了20个用户](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="76ace-123">单击 "**编辑设置**", 进行所需的更改, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="76ace-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    !["编辑设置" 窗格的屏幕截图](media/bulk-edit-user-settings-edit-settings.png)
