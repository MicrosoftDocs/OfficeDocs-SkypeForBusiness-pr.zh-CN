---
title: 在 Microsoft Teams 中存档或删除团队
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 在本文中，你将了解如何在 Microsoft 团队中存档或永久删除团队。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 334ecfdc387f1b3dd6d7f1312b90d81aee320df0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582759"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="0ab49-103">在 Microsoft Teams 中存档或删除团队</span><span class="sxs-lookup"><span data-stu-id="0ab49-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="0ab49-104">随着时间的推移，在 Microsoft Teams 中创建的团队可能不再使用，或者你可能希望在项目结束时存档或删除团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="0ab49-105">如果你是 Microsoft Teams 的管理员，请按照本文中的步骤进行操作，以存档或删除不再需要的团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="0ab49-106">将团队存档时，该团队的所有活动都会停止。</span><span class="sxs-lookup"><span data-stu-id="0ab49-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="0ab49-107">存档团队还会存档团队中的专用频道及其关联的网站集。</span><span class="sxs-lookup"><span data-stu-id="0ab49-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="0ab49-108">但是，你仍然可以添加或删除成员以及更新角色，而且仍可查看标准和专用通道、文件和聊天中的所有团队活动。</span><span class="sxs-lookup"><span data-stu-id="0ab49-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="0ab49-109">删除团队时，也将删除标准和专用频道（及关联的网站集）、文件和聊天中的团队活动。</span><span class="sxs-lookup"><span data-stu-id="0ab49-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ab49-110">你可以重新激活已存档的团队，但无法直接还原已删除的团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="0ab49-111">应先考虑将团队存档并推迟删除，直至确定不再需要团队再进行删除操作。</span><span class="sxs-lookup"><span data-stu-id="0ab49-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="0ab49-112">存档团队</span><span class="sxs-lookup"><span data-stu-id="0ab49-112">Archive a team</span></span>

<span data-ttu-id="0ab49-113">请按照以下步骤将团队存档。</span><span class="sxs-lookup"><span data-stu-id="0ab49-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="0ab49-114">您必须是团队服务管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="0ab49-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="0ab49-115">请参阅[使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles)，了解如何获取管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="0ab49-115">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="0ab49-116">在管理中心中，选择 "**团队**"。</span><span class="sxs-lookup"><span data-stu-id="0ab49-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="0ab49-117">通过单击团队名称选择团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="0ab49-118">选择“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="0ab49-118">Select **Archive**.</span></span> <span data-ttu-id="0ab49-119">此时将显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="0ab49-119">The following message will appear.</span></span>

    ![Teams 存档消息的屏幕截图](media/teams-archive-message.png)

4. <span data-ttu-id="0ab49-121">若要防止用户编辑 SharePoint 网站和与团队关联的 "Wiki" 选项卡中的内容，请选择 **"使 sharepoint 网站对团队成员只读**"。</span><span class="sxs-lookup"><span data-stu-id="0ab49-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="0ab49-122"> (团队所有者仍然可以编辑此内容。 ) </span><span class="sxs-lookup"><span data-stu-id="0ab49-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="0ab49-123">选择“**存档**”以存档团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="0ab49-124">团队的状态将更改为“**已存档**”。</span><span class="sxs-lookup"><span data-stu-id="0ab49-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="0ab49-125">激活已存档的团队</span><span class="sxs-lookup"><span data-stu-id="0ab49-125">Make an archived team active</span></span>

<span data-ttu-id="0ab49-126">请按照以下步骤使已存档的团队再次处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0ab49-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="0ab49-127">在管理中心中，选择 "**团队**"。</span><span class="sxs-lookup"><span data-stu-id="0ab49-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="0ab49-128">通过单击团队名称选择团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="0ab49-129">选择“**取消存档**”。</span><span class="sxs-lookup"><span data-stu-id="0ab49-129">Select **Unarchive**.</span></span> <span data-ttu-id="0ab49-130">团队的状态将更改为“**活动**”。</span><span class="sxs-lookup"><span data-stu-id="0ab49-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="0ab49-131">删除团队</span><span class="sxs-lookup"><span data-stu-id="0ab49-131">Delete a team</span></span>

<span data-ttu-id="0ab49-132">如果将来不再需要该团队，则可将其删除，而不是将其存档。</span><span class="sxs-lookup"><span data-stu-id="0ab49-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="0ab49-133">请按照以下步骤删除团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="0ab49-134">在管理中心中，选择 "**团队**"。</span><span class="sxs-lookup"><span data-stu-id="0ab49-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="0ab49-135">通过单击团队名称选择团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="0ab49-136">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="0ab49-136">Select **Delete**.</span></span> <span data-ttu-id="0ab49-137">此时将显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="0ab49-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="0ab49-138">选择“**删除**”以永久删除团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="0ab49-139">还原已删除的团队</span><span class="sxs-lookup"><span data-stu-id="0ab49-139">Restore a deleted team</span></span>

<span data-ttu-id="0ab49-140">通过还原与团队相关联的 Microsoft 365 组，请按照以下步骤还原已删除的团队。</span><span class="sxs-lookup"><span data-stu-id="0ab49-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="0ab49-141">还原团队的 Microsoft 365 组将恢复团队内容，包括选项卡、标准频道和专用频道及其关联的网站集。</span><span class="sxs-lookup"><span data-stu-id="0ab49-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="0ab49-142">默认情况下，已删除的 Microsoft 365 组将保留30天。</span><span class="sxs-lookup"><span data-stu-id="0ab49-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="0ab49-143">这 30 天时间被称为“软删除”，因为还可以对组进行还原。</span><span class="sxs-lookup"><span data-stu-id="0ab49-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="0ab49-144">若要了解详细信息，请参阅[还原已删除的组](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="0ab49-144">To learn more, see [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="0ab49-145">安装 AzureADPreview 模块</span><span class="sxs-lookup"><span data-stu-id="0ab49-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="0ab49-146">以管理员身份打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0ab49-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="0ab49-147">如果安装了早期版本的 AzureADPreview 模块或安装了 AzureAD 模块，请通过运行以下命令之一将其卸载：</span><span class="sxs-lookup"><span data-stu-id="0ab49-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="0ab49-148">通过运行以下命令安装最新版本的 AzureADPreview 模块：</span><span class="sxs-lookup"><span data-stu-id="0ab49-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="0ab49-149">还原已删除的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="0ab49-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="0ab49-150">通过运行以下命令连接到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="0ab49-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="0ab49-151">提示登录时，请使用管理员帐户和密码登录。</span><span class="sxs-lookup"><span data-stu-id="0ab49-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="0ab49-152">运行以下操作以显示仍在30天保留期内的所有软删除的 Microsoft 365 组的列表。</span><span class="sxs-lookup"><span data-stu-id="0ab49-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="0ab49-153">如果有大量组，请使用 **-All $True** 参数。</span><span class="sxs-lookup"><span data-stu-id="0ab49-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="0ab49-154">找到要还原的组，然后记下 ID。</span><span class="sxs-lookup"><span data-stu-id="0ab49-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="0ab49-155">运行以下命令以还原该组，其中 [Id] 是组 ID。</span><span class="sxs-lookup"><span data-stu-id="0ab49-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="0ab49-156">运行以下命令以验证是否已成功还原组，其中 [Id] 是组 ID。</span><span class="sxs-lookup"><span data-stu-id="0ab49-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="0ab49-157">完成还原过程可能需要长达 24 小时，此后在 Teams 中将显示团队以及与团队关联的内容（包括选项卡和频道）。</span><span class="sxs-lookup"><span data-stu-id="0ab49-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
