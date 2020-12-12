---
title: 使用 Microsoft Teams Room Premium 服务进行基于角色的访问控制
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解 Microsoft Teams 会议室托管服务的基于角色的访问控制。
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662597"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a><span data-ttu-id="a92df-103">使用 Microsoft Teams 会议室托管服务的基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="a92df-103">Role-based access control with the Microsoft Teams Rooms managed service</span></span>

<span data-ttu-id="a92df-104">Microsoft Teams 会议室 (RBAC) 基于角色的访问控制可帮助管理用户对组织中会议室资源数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a92df-104">Role-based access control (RBAC) in the Microsoft Teams Rooms managed service helps you manage user access to room resource data in your organization.</span></span> <span data-ttu-id="a92df-105">通过向服务门户用户分配角色，可以限制他们可以看到和更改的内容。</span><span class="sxs-lookup"><span data-stu-id="a92df-105">By assigning roles to your service portal users, you can limit what they can see and change.</span></span> <span data-ttu-id="a92df-106">每个角色都有一组权限，这些权限决定了哪些具有该角色的用户可以在组织中访问和更改。</span><span class="sxs-lookup"><span data-stu-id="a92df-106">Each role has a set of permissions that determine what users with that role can access and change within your organization.</span></span>

<span data-ttu-id="a92df-107">若要创建、编辑或分配角色，帐户必须具有以下权限之一：</span><span class="sxs-lookup"><span data-stu-id="a92df-107">To create, edit, or assign roles, your account must have one of the following permissions:</span></span>

- <span data-ttu-id="a92df-108">通过 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="a92df-108">Global Administrator through Azure Active Directory (Azure AD)</span></span>
- <span data-ttu-id="a92df-109">通过 Microsoft Teams 会议室托管服务门户的托管服务管理员</span><span class="sxs-lookup"><span data-stu-id="a92df-109">Managed Service Administrator through the Microsoft Teams Rooms managed service portal</span></span>

## <a name="what-is-a-role"></a><span data-ttu-id="a92df-110">什么是角色？</span><span class="sxs-lookup"><span data-stu-id="a92df-110">What is a role?</span></span>

<span data-ttu-id="a92df-111">角色定义授予分配给该角色的用户的权限集。</span><span class="sxs-lookup"><span data-stu-id="a92df-111">A role defines the set of permissions granted to users assigned to that role.</span></span> <span data-ttu-id="a92df-112">目前，Microsoft Teams 会议室托管服务具有三个内置角色：托管服务管理员、网站 **主管** 和 **网站技术**。</span><span class="sxs-lookup"><span data-stu-id="a92df-112">For now, the Microsoft Teams Rooms managed service has three built-in roles: **Managed Service Administrator**, **Site Lead**, and **Site Tech**.</span></span> <span data-ttu-id="a92df-113">其中涵盖了组织中可能参与管理聊天室的用户的一些常见方案。</span><span class="sxs-lookup"><span data-stu-id="a92df-113">They cover some common scenarios for users in your organization that may be involved in managing your rooms.</span></span>

<span data-ttu-id="a92df-114">若要查看角色，请在 Microsoft Teams 会议室托管服务门户的左侧导航栏中，转到"角色"，然后选择任一角色以查看角色的属性、权限和分配。</span><span class="sxs-lookup"><span data-stu-id="a92df-114">To see roles, in the left navigation of the Microsoft Teams Rooms managed service portal, go to **Roles**, and then select any of the roles to see the role’s properties, permissions, and assignments.</span></span>  

- <span data-ttu-id="a92df-115">**属性**：名称、角色类型和说明</span><span class="sxs-lookup"><span data-stu-id="a92df-115">**Properties**: The name, role type, and description</span></span>
- <span data-ttu-id="a92df-116">**权限**：列出角色有权访问的功能和权限级别。</span><span class="sxs-lookup"><span data-stu-id="a92df-116">**Permissions**: Lists features and level of permissions to which the role has access.</span></span>
- <span data-ttu-id="a92df-117">**分配**：角色分配列表，定义哪些用户对会议室资源帐户的范围具有配置的权限。</span><span class="sxs-lookup"><span data-stu-id="a92df-117">**Assignments**: A list of role assignments defining which users have the configured permissions over the scope of room resource accounts.</span></span> <span data-ttu-id="a92df-118">一个角色可以有多个分配，一个用户可以有多个分配。</span><span class="sxs-lookup"><span data-stu-id="a92df-118">A role can have multiple assignments, and a user can be in multiple assignments.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="a92df-119">内置角色</span><span class="sxs-lookup"><span data-stu-id="a92df-119">Built-in roles</span></span>

<span data-ttu-id="a92df-120">无需进一步配置，即可将内置角色分配给组或用户。</span><span class="sxs-lookup"><span data-stu-id="a92df-120">You can assign built-in roles to groups or users without further configuration.</span></span> <span data-ttu-id="a92df-121">请记住，不能删除或编辑内置角色的名称、说明、类型或权限。</span><span class="sxs-lookup"><span data-stu-id="a92df-121">Keep in mind that you can't delete or edit the name, description, type, or permissions of a built-in role.</span></span>

- <span data-ttu-id="a92df-122">**托管服务管理员**：具有 Microsoft Teams Room Premium 服务门户的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="a92df-122">**Managed Service Administrator**: Has full access to the Microsoft Teams Room Premium service portal.</span></span>
- <span data-ttu-id="a92df-123">**网站主管**：组织会议室、有权访问报表并可以管理票证。</span><span class="sxs-lookup"><span data-stu-id="a92df-123">**Site Lead**: Organizes rooms, has access to reports and can manage tickets.</span></span> <span data-ttu-id="a92df-124">无法重置注册密钥或更改服务的配置。</span><span class="sxs-lookup"><span data-stu-id="a92df-124">Can't reset enrollment key or make changes to the configuration of the service.</span></span>  
- <span data-ttu-id="a92df-125">**网站技术**：管理特定聊天室的门票。</span><span class="sxs-lookup"><span data-stu-id="a92df-125">**Site Tech**: Manages tickets for specific rooms.</span></span> <span data-ttu-id="a92df-126">无权修改服务或组织服务中的会议室。</span><span class="sxs-lookup"><span data-stu-id="a92df-126">Doesn't have permissions to modify the service or organize rooms in the service.</span></span>

<span data-ttu-id="a92df-127">下表汇总了每个角色可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="a92df-127">The following table summarizes what each role can do.</span></span>

|<span data-ttu-id="a92df-128">功能</span><span class="sxs-lookup"><span data-stu-id="a92df-128">Features</span></span> |<span data-ttu-id="a92df-129">权限</span><span class="sxs-lookup"><span data-stu-id="a92df-129">Permission</span></span> |<span data-ttu-id="a92df-130">托管服务管理员</span><span class="sxs-lookup"><span data-stu-id="a92df-130">Managed Service Administrator</span></span>  |<span data-ttu-id="a92df-131">网站潜在顾客</span><span class="sxs-lookup"><span data-stu-id="a92df-131">Site Lead</span></span>  |<span data-ttu-id="a92df-132">网站技术</span><span class="sxs-lookup"><span data-stu-id="a92df-132">Site Tech</span></span>  |
|---------|---------|---------|---------|---------|
|<span data-ttu-id="a92df-133">会议室</span><span class="sxs-lookup"><span data-stu-id="a92df-133">Rooms</span></span>     |<span data-ttu-id="a92df-134">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-134">View</span></span>        |<span data-ttu-id="a92df-135">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-135">&#10004;</span></span>           |<span data-ttu-id="a92df-136">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-136">&#10004;</span></span>           |<span data-ttu-id="a92df-137">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-137">&#10004;</span></span>  |
|    |<span data-ttu-id="a92df-138">修改</span><span class="sxs-lookup"><span data-stu-id="a92df-138">Modify</span></span>         |<span data-ttu-id="a92df-139">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-139">&#10004;</span></span>           |<span data-ttu-id="a92df-140">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-140">&#10004;</span></span>           |<span data-ttu-id="a92df-141">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-141">&#10004;</span></span> |
|    |<span data-ttu-id="a92df-142">重置密钥</span><span class="sxs-lookup"><span data-stu-id="a92df-142">Reset key</span></span>         |<span data-ttu-id="a92df-143">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-143">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="a92df-144">下载密钥</span><span class="sxs-lookup"><span data-stu-id="a92df-144">Download key</span></span>         |<span data-ttu-id="a92df-145">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-145">&#10004;</span></span>           |<span data-ttu-id="a92df-146">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-146">&#10004;</span></span>          |<span data-ttu-id="a92df-147">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-147">&#10004;</span></span> |
|    |<span data-ttu-id="a92df-148">取消注册</span><span class="sxs-lookup"><span data-stu-id="a92df-148">Unenroll</span></span>         |<span data-ttu-id="a92df-149">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-149">&#10004;</span></span>           |<span data-ttu-id="a92df-150">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-150">&#10004;</span></span>           |<span data-ttu-id="a92df-151">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-151">&#10004;</span></span> |
|<span data-ttu-id="a92df-152">组管理</span><span class="sxs-lookup"><span data-stu-id="a92df-152">Group management</span></span>   |<span data-ttu-id="a92df-153">创建</span><span class="sxs-lookup"><span data-stu-id="a92df-153">Create</span></span>         |<span data-ttu-id="a92df-154">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-154">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="a92df-155">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-155">View</span></span>       |<span data-ttu-id="a92df-156">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-156">&#10004;</span></span>          |<span data-ttu-id="a92df-157">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-157">&#10004;</span></span>           ||
|    |<span data-ttu-id="a92df-158">修改</span><span class="sxs-lookup"><span data-stu-id="a92df-158">Modify</span></span>         |<span data-ttu-id="a92df-159">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-159">&#10004;</span></span>           |           ||
|<span data-ttu-id="a92df-160">更新环管理</span><span class="sxs-lookup"><span data-stu-id="a92df-160">Update ring management</span></span>    |<span data-ttu-id="a92df-161">创建</span><span class="sxs-lookup"><span data-stu-id="a92df-161">Create</span></span>         |<span data-ttu-id="a92df-162">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-162">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="a92df-163">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-163">View</span></span>         |<span data-ttu-id="a92df-164">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-164">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="a92df-165">修改</span><span class="sxs-lookup"><span data-stu-id="a92df-165">Modify</span></span>         |<span data-ttu-id="a92df-166">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-166">&#10004;</span></span>           |           ||
|<span data-ttu-id="a92df-167">报表</span><span class="sxs-lookup"><span data-stu-id="a92df-167">Reports</span></span>   |<span data-ttu-id="a92df-168">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-168">View</span></span>        |<span data-ttu-id="a92df-169">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-169">&#10004;</span></span>           |<span data-ttu-id="a92df-170">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-170">&#10004;</span></span>           ||
|<span data-ttu-id="a92df-171">票证管理</span><span class="sxs-lookup"><span data-stu-id="a92df-171">Ticket management</span></span>   |<span data-ttu-id="a92df-172">创建客户事件</span><span class="sxs-lookup"><span data-stu-id="a92df-172">Create customer incident</span></span>         |<span data-ttu-id="a92df-173">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-173">&#10004;</span></span>           |<span data-ttu-id="a92df-174">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-174">&#10004;</span></span>           |<span data-ttu-id="a92df-175">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-175">&#10004;</span></span>  |
|    |<span data-ttu-id="a92df-176">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-176">View</span></span>         |<span data-ttu-id="a92df-177">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-177">&#10004;</span></span>           |<span data-ttu-id="a92df-178">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-178">&#10004;</span></span>           |<span data-ttu-id="a92df-179">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-179">&#10004;</span></span>  |
|    |<span data-ttu-id="a92df-180">更新</span><span class="sxs-lookup"><span data-stu-id="a92df-180">Update</span></span>         |<span data-ttu-id="a92df-181">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-181">&#10004;</span></span>           |<span data-ttu-id="a92df-182">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-182">&#10004;</span></span>           |<span data-ttu-id="a92df-183">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-183">&#10004;</span></span>  |
|<span data-ttu-id="a92df-184">Microsoft Teams 会议室托管服务设置</span><span class="sxs-lookup"><span data-stu-id="a92df-184">Microsoft Teams Rooms managed service settings</span></span>    |<span data-ttu-id="a92df-185">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-185">View</span></span>         |<span data-ttu-id="a92df-186">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-186">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="a92df-187">修改</span><span class="sxs-lookup"><span data-stu-id="a92df-187">Modify</span></span>        |<span data-ttu-id="a92df-188">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-188">&#10004;</span></span>           |         ||
|<span data-ttu-id="a92df-189">角色管理</span><span class="sxs-lookup"><span data-stu-id="a92df-189">Role management</span></span>    |<span data-ttu-id="a92df-190">查看</span><span class="sxs-lookup"><span data-stu-id="a92df-190">View</span></span>         |<span data-ttu-id="a92df-191">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-191">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="a92df-192">修改</span><span class="sxs-lookup"><span data-stu-id="a92df-192">Modify</span></span>         |<span data-ttu-id="a92df-193">&#10004;</span><span class="sxs-lookup"><span data-stu-id="a92df-193">&#10004;</span></span>           |         ||

## <a name="assign-a-role"></a><span data-ttu-id="a92df-194">分配角色</span><span class="sxs-lookup"><span data-stu-id="a92df-194">Assign a role</span></span>

<span data-ttu-id="a92df-195">若要分配角色，必须是全局管理员或托管服务管理员。</span><span class="sxs-lookup"><span data-stu-id="a92df-195">To assign roles, you must be a Global Administrator or Managed Service Administrator.</span></span>

1. <span data-ttu-id="a92df-196">在 Microsoft Teams 会议室托管服务门户的左侧导航栏中，转到"设置 **角色**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-196">In the left navigation of the Microsoft Teams Rooms managed service portal, go to **Settings** > **Roles**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="显示角色的访问控制页的屏幕截图":::

2. <span data-ttu-id="a92df-198">选择要分配的角色。</span><span class="sxs-lookup"><span data-stu-id="a92df-198">Select the role you want to assign.</span></span>
3. <span data-ttu-id="a92df-199">在角色窗格中，选择"**分配添加**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-199">In the role pane, select **Assignments** > **Add**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="用于添加角色的"添加"选项的屏幕截图。":::

4. <span data-ttu-id="a92df-201">在" **常规设置"** 页上的 **"工作分配属性**"下，输入此作业的名称。</span><span class="sxs-lookup"><span data-stu-id="a92df-201">On the **General settings** page, under **Assignment properties**, enter a name for this assignment.</span></span> <span data-ttu-id="a92df-202">说明是可选的。</span><span class="sxs-lookup"><span data-stu-id="a92df-202">The description is optional.</span></span> <span data-ttu-id="a92df-203">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-203">Choose **Next.**</span></span>
5. <span data-ttu-id="a92df-204">在 **"成员**"页上的"搜索用户或安全组"框中，输入租户中要授予权限的用户或安全组的名称，然后完成选择。</span><span class="sxs-lookup"><span data-stu-id="a92df-204">On the **Members** page, in the **Search for user or security group** box, enter the name of a user or security group in your tenant to which you want to give permissions, and then complete the selection.</span></span> <span data-ttu-id="a92df-205">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-205">Choose **Next**.</span></span> 
6. <span data-ttu-id="a92df-206">在 **"范围**"页面上的"搜索会议室或会议室组"框中，键入允许用户管理的聊天室或聊天室组的名称。</span><span class="sxs-lookup"><span data-stu-id="a92df-206">On the **Scope** page, in the **Search for room or room group** box, type the name of either a room or room group that the user will be allowed to manage.</span></span> <span data-ttu-id="a92df-207">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-207">Choose **Next**.</span></span>
7. <span data-ttu-id="a92df-208">在 **"完成** "页上，查看作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a92df-208">On the **Finish** page, review the details of the assignment.</span></span> <span data-ttu-id="a92df-209">如果对配置感到满意，请选择"添加 **分配"。**</span><span class="sxs-lookup"><span data-stu-id="a92df-209">If you're satisfied with the configuration, choose **Add assignment**.</span></span> <span data-ttu-id="a92df-210">如果要编辑分区，请使用"上一步" **按钮或** 选择左侧导航中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a92df-210">If you want to edit a section, use the **Previous** button or select the step in the left navigation.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="a92df-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="a92df-211">Related topics</span></span>

- [<span data-ttu-id="a92df-212">Microsoft Teams 会议室托管服务</span><span class="sxs-lookup"><span data-stu-id="a92df-212">Microsoft Teams Rooms managed service</span></span>](microsoft-teams-rooms-premium.md)
