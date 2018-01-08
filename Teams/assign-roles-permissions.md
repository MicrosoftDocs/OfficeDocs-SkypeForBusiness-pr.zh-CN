---
title: "在 Microsoft Teams 中分配角色和权限"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: ec15844064a88cf1e6aa8af9e510107e342dd369
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="a6602-103">在 Microsoft Teams 中分配角色和权限</span><span class="sxs-lookup"><span data-stu-id="a6602-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="a6602-104">在 Microsoft Teams 中有两种角色：**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="a6602-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="a6602-105">默认情况下，会为创建新团队的用户授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="a6602-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="a6602-106">如果团队是从现有 Office 365 组创建的，则将继承权限。</span><span class="sxs-lookup"><span data-stu-id="a6602-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="a6602-107">下表显示了所有者与成员之间的权限差异：</span><span class="sxs-lookup"><span data-stu-id="a6602-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="a6602-108">团队所有者</span><span class="sxs-lookup"><span data-stu-id="a6602-108">Team Owner</span></span>  |<span data-ttu-id="a6602-109">团队成员</span><span class="sxs-lookup"><span data-stu-id="a6602-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a6602-110">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="a6602-110">**Create team**</span></span>     |<span data-ttu-id="a6602-111">是</span><span class="sxs-lookup"><span data-stu-id="a6602-111">Yes</span></span>        |<span data-ttu-id="a6602-112">否</span><span class="sxs-lookup"><span data-stu-id="a6602-112">No</span></span>         |
|<span data-ttu-id="a6602-113">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="a6602-113">**Leave team**</span></span>     |<span data-ttu-id="a6602-114">是</span><span class="sxs-lookup"><span data-stu-id="a6602-114">Yes</span></span>         |<span data-ttu-id="a6602-115">是</span><span class="sxs-lookup"><span data-stu-id="a6602-115">Yes</span></span>         |
|<span data-ttu-id="a6602-116">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="a6602-116">**Edit team name/description**</span></span>      |<span data-ttu-id="a6602-117">是</span><span class="sxs-lookup"><span data-stu-id="a6602-117">Yes</span></span>         |<span data-ttu-id="a6602-118">否</span><span class="sxs-lookup"><span data-stu-id="a6602-118">No</span></span>         |
|<span data-ttu-id="a6602-119">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="a6602-119">**Delete team**</span></span>      |<span data-ttu-id="a6602-120">是</span><span class="sxs-lookup"><span data-stu-id="a6602-120">Yes</span></span>         |<span data-ttu-id="a6602-121">否</span><span class="sxs-lookup"><span data-stu-id="a6602-121">No</span></span>         |
|<span data-ttu-id="a6602-122">**添加频道**</span><span class="sxs-lookup"><span data-stu-id="a6602-122">**Add channel**</span></span>      |<span data-ttu-id="a6602-123">是</span><span class="sxs-lookup"><span data-stu-id="a6602-123">Yes</span></span>         |<span data-ttu-id="a6602-124">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-124">Yes*</span></span>         |
|<span data-ttu-id="a6602-125">**编辑频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="a6602-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="a6602-126">是</span><span class="sxs-lookup"><span data-stu-id="a6602-126">Yes</span></span>         |<span data-ttu-id="a6602-127">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-127">Yes*</span></span>         |
|<span data-ttu-id="a6602-128">**删除频道**</span><span class="sxs-lookup"><span data-stu-id="a6602-128">**Delete channel**</span></span>      |<span data-ttu-id="a6602-129">是</span><span class="sxs-lookup"><span data-stu-id="a6602-129">Yes</span></span>         |<span data-ttu-id="a6602-130">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-130">Yes*</span></span>         |
|<span data-ttu-id="a6602-131">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="a6602-131">**Add members**</span></span>      |<span data-ttu-id="a6602-132">是**</span><span class="sxs-lookup"><span data-stu-id="a6602-132">Yes**</span></span>         |<span data-ttu-id="a6602-133">否</span><span class="sxs-lookup"><span data-stu-id="a6602-133">No</span></span>         |
|<span data-ttu-id="a6602-134">**添加选项卡**</span><span class="sxs-lookup"><span data-stu-id="a6602-134">**Add tabs**</span></span>      |<span data-ttu-id="a6602-135">是</span><span class="sxs-lookup"><span data-stu-id="a6602-135">Yes</span></span>         |<span data-ttu-id="a6602-136">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-136">Yes*</span></span>         |
|<span data-ttu-id="a6602-137">**添加连接器**</span><span class="sxs-lookup"><span data-stu-id="a6602-137">**Add connectors**</span></span>      |<span data-ttu-id="a6602-138">是</span><span class="sxs-lookup"><span data-stu-id="a6602-138">Yes</span></span>         |<span data-ttu-id="a6602-139">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-139">Yes*</span></span>         |
|<span data-ttu-id="a6602-140">**添加聊天机器人**</span><span class="sxs-lookup"><span data-stu-id="a6602-140">**Add bots**</span></span>      |<span data-ttu-id="a6602-141">是</span><span class="sxs-lookup"><span data-stu-id="a6602-141">Yes</span></span>         |<span data-ttu-id="a6602-142">是*</span><span class="sxs-lookup"><span data-stu-id="a6602-142">Yes*</span></span>         |
<span data-ttu-id="a6602-143">\* 所有者可以在团队级别关闭这些项，这样成员将无权访问相应项。</span><span class="sxs-lookup"><span data-stu-id="a6602-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="a6602-144">\*\*向团队添加成员后，所有者也可以将成员提升到所有者状态。</span><span class="sxs-lookup"><span data-stu-id="a6602-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="a6602-145">此外，所有者也可以将自己的状态降级为成员。</span><span class="sxs-lookup"><span data-stu-id="a6602-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="a6602-146">所有者可以在“查看团队”选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="a6602-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="a6602-147">一个团队最多可以有 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="a6602-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="a6602-148">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="a6602-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="a6602-149">有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="a6602-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="a6602-150">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="a6602-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="a6602-151">默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="a6602-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="a6602-152">你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。</span><span class="sxs-lookup"><span data-stu-id="a6602-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="a6602-153">如果贵组织有意执行此操作，下面的说明概述了为此需要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="a6602-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="a6602-154">确定或创建一个安全组 (SG)，该安全组由拥有创建 Office 365 组的委派权限的用户组成。</span><span class="sxs-lookup"><span data-stu-id="a6602-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="a6602-155">a.</span><span class="sxs-lookup"><span data-stu-id="a6602-155">a.</span></span>  <span data-ttu-id="a6602-156">**操作：** 在 Office 365 中设置一个安全组，以便你可以添加能够创建 Office 365 组的用户。</span><span class="sxs-lookup"><span data-stu-id="a6602-156">**Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="a6602-157">b.</span><span class="sxs-lookup"><span data-stu-id="a6602-157">b.</span></span>  <span data-ttu-id="a6602-158">有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)。</span><span class="sxs-lookup"><span data-stu-id="a6602-158">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="a6602-159">确认是否启用了允许用户创建组的公司范围的控制。</span><span class="sxs-lookup"><span data-stu-id="a6602-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="a6602-160">a.</span><span class="sxs-lookup"><span data-stu-id="a6602-160">a.</span></span>  <span data-ttu-id="a6602-161">**操作：** 运行以下 PowerShell 脚本，并确认 UsersPermissiontoCreateGroupsEnabled 参数是否设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="a6602-161">**Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="a6602-162">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="a6602-162">Connect-MsolService</span></span>

    <span data-ttu-id="a6602-163">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="a6602-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="a6602-164">b.</span><span class="sxs-lookup"><span data-stu-id="a6602-164">b.</span></span>  <span data-ttu-id="a6602-165">如果不为 True，请运行 Set-MsolCompanySettings cmdlet **以将其设置为 True**。</span><span class="sxs-lookup"><span data-stu-id="a6602-165">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="a6602-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="a6602-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="a6602-167">c.</span><span class="sxs-lookup"><span data-stu-id="a6602-167">c.</span></span> <span data-ttu-id="a6602-168">有关详细信息，请参阅：[管理 Office 365 组创建](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)。</span><span class="sxs-lookup"><span data-stu-id="a6602-168">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="a6602-169">配置 Office 365 组设置以仅允许标识的安全组有权创建组。</span><span class="sxs-lookup"><span data-stu-id="a6602-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="a6602-170">a.</span><span class="sxs-lookup"><span data-stu-id="a6602-170">a.</span></span>  <span data-ttu-id="a6602-171">**操作：** 创建一个组设置对象，其中包含将为其分配创建组的委派权限的组的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a6602-171">**Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="a6602-172">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="a6602-172">Connect-AzureAD</span></span>

    <span data-ttu-id="a6602-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="a6602-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="a6602-174">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="a6602-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="a6602-175">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="a6602-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="a6602-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span><span class="sxs-lookup"><span data-stu-id="a6602-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="a6602-177">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="a6602-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="a6602-178">b.</span><span class="sxs-lookup"><span data-stu-id="a6602-178">b.</span></span> <span data-ttu-id="a6602-179">有关详细信息，请参阅：[管理 Office 365 组创建](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="a6602-179">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="a6602-181">决策点</span><span class="sxs-lookup"><span data-stu-id="a6602-181">Decision Point</span></span>         |<span data-ttu-id="a6602-182">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="a6602-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="a6602-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a6602-184">Next Steps</span></span>         |<span data-ttu-id="a6602-185">如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限</span><span class="sxs-lookup"><span data-stu-id="a6602-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
