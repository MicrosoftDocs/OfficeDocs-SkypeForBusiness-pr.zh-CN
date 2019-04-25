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
description: 了解如何管理批量 Microsoft 团队管理中心中的 Microsoft 团队用户设置。
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
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="c696f-103">编辑批量的 Microsoft 团队用户设置</span><span class="sxs-lookup"><span data-stu-id="c696f-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="c696f-104">作为一名管理员，您可以管理团队的 Microsoft 团队管理中心中的用户设置。</span><span class="sxs-lookup"><span data-stu-id="c696f-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c696f-105">在**用户**页上，您可以查看信息，如帐户和许可的详细信息和编辑策略和其他设置。</span><span class="sxs-lookup"><span data-stu-id="c696f-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="c696f-106">单独或多个用户同时，您可以编辑用户的设置。</span><span class="sxs-lookup"><span data-stu-id="c696f-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="c696f-107">编辑批量的用户设置</span><span class="sxs-lookup"><span data-stu-id="c696f-107">Edit user settings in bulk</span></span>

<span data-ttu-id="c696f-108">使用 Microsoft 团队管理中心一次编辑多个用户的设置。</span><span class="sxs-lookup"><span data-stu-id="c696f-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="c696f-109">我们建议每次编辑 20 个用户的设置。</span><span class="sxs-lookup"><span data-stu-id="c696f-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="c696f-110">若要编辑的大量用户设置，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c696f-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="c696f-111">有关详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c696f-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="c696f-112">在 Microsoft 团队管理中心的左侧导航窗格中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="c696f-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="c696f-113">您想要编辑或筛选视图以向用户显示要编辑的用户的搜索。</span><span class="sxs-lookup"><span data-stu-id="c696f-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="c696f-114">在 **& #x 2713;**（复选标记） 列中，选择用户通过执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="c696f-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="c696f-115">一次选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="c696f-115">Select users one at a time.</span></span> <span data-ttu-id="c696f-116">**_AMP_ #x 2713;** 会显示您选择每个用户旁边。</span><span class="sxs-lookup"><span data-stu-id="c696f-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="c696f-117">如果您选择超过 20 个用户，您不会阻止，但请记住，您选择的多个用户，该操作将需要更长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="c696f-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![显示用户选择用户页的屏幕截图](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="c696f-119">单击 & #x 2713;（复选标记） 要选择 （最多 20 个用户最多），所有用户，然后在**所选内容限制**对话框中，单击都**继续都选择全部**以完成所选内容的表的顶部。</span><span class="sxs-lookup"><span data-stu-id="c696f-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="c696f-120">![显示所选内容限制用户页的屏幕截图](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="c696f-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="c696f-121">**_AMP_ #x 2713;** 会显示所选用户旁边。</span><span class="sxs-lookup"><span data-stu-id="c696f-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![用户页，显示所选的 20 个用户的屏幕截图](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="c696f-123">单击**编辑设置**，进行所需的更改，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c696f-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![编辑设置窗格的屏幕截图](media/bulk-edit-user-settings-edit-settings.png)
