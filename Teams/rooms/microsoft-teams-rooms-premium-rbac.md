---
title: 使用 Microsoft 团队房间高级服务的基于角色的访问控制
author: lanachin
ms.author: v-lanac
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
description: 了解有关 Microsoft 团队聊天室托管服务的基于角色的访问控制。
f1keywords: ''
ms.openlocfilehash: 2f3886d7f7f59521028b87f05ffedfaa1fae9ac2
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300286"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a><span data-ttu-id="0cba9-103">使用 Microsoft 团队聊天室托管服务的基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="0cba9-103">Role-based access control with the Microsoft Teams Rooms managed service</span></span>

<span data-ttu-id="0cba9-104">Microsoft 团队聊天室托管服务 (RBAC) 中基于角色的访问控制可帮助你管理用户对组织中的会议室资源数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0cba9-104">Role-based access control (RBAC) in the Microsoft Teams Rooms managed service helps you manage user access to room resource data in your organization.</span></span> <span data-ttu-id="0cba9-105">通过将角色分配给你的服务门户用户，你可以限制他们可以查看和更改的内容。</span><span class="sxs-lookup"><span data-stu-id="0cba9-105">By assigning roles to your service portal users, you can limit what they can see and change.</span></span> <span data-ttu-id="0cba9-106">每个角色都有一组权限，用于确定具有该角色的用户可以访问和更改你的组织内的哪些用户。</span><span class="sxs-lookup"><span data-stu-id="0cba9-106">Each role has a set of permissions that determine what users with that role can access and change within your organization.</span></span>

<span data-ttu-id="0cba9-107">若要创建、编辑或分配角色，您的帐户必须具有下列权限之一：</span><span class="sxs-lookup"><span data-stu-id="0cba9-107">To create, edit, or assign roles, your account must have one of the following permissions:</span></span>

- <span data-ttu-id="0cba9-108">通过 Azure Active Directory (Azure AD) 的全局管理员</span><span class="sxs-lookup"><span data-stu-id="0cba9-108">Global Administrator through Azure Active Directory (Azure AD)</span></span>
- <span data-ttu-id="0cba9-109">通过 Microsoft 团队聊天室托管服务门户托管服务管理员</span><span class="sxs-lookup"><span data-stu-id="0cba9-109">Managed Service Administrator through the Microsoft Teams Rooms managed service portal</span></span>

## <a name="what-is-a-role"></a><span data-ttu-id="0cba9-110">什么是角色？</span><span class="sxs-lookup"><span data-stu-id="0cba9-110">What is a role?</span></span>

<span data-ttu-id="0cba9-111">角色定义授予分配给该角色的用户的权限集。</span><span class="sxs-lookup"><span data-stu-id="0cba9-111">A role defines the set of permissions granted to users assigned to that role.</span></span> <span data-ttu-id="0cba9-112">目前，Microsoft 团队聊天室托管服务有三个内置角色： **托管服务管理员**、 **网站主管**和 **网站技术**人员。</span><span class="sxs-lookup"><span data-stu-id="0cba9-112">For now, the Microsoft Teams Rooms managed service has three built-in roles: **Managed Service Administrator**, **Site Lead**, and **Site Tech**.</span></span> <span data-ttu-id="0cba9-113">它们涵盖了组织中可能涉及管理会议室的用户的一些常见方案。</span><span class="sxs-lookup"><span data-stu-id="0cba9-113">They cover some common scenarios for users in your organization that may be involved in managing your rooms.</span></span>

<span data-ttu-id="0cba9-114">若要查看角色，请在 Microsoft 团队聊天室托管服务门户的左侧导航中，转到 " **角色**"，然后选择任何角色以查看角色的属性、权限和作业。</span><span class="sxs-lookup"><span data-stu-id="0cba9-114">To see roles, in the left navigation of the Microsoft Teams Rooms managed service portal, go to **Roles**, and then select any of the roles to see the role’s properties, permissions, and assignments.</span></span>  

- <span data-ttu-id="0cba9-115">**属性**：名称、角色类型和说明</span><span class="sxs-lookup"><span data-stu-id="0cba9-115">**Properties**: The name, role type, and description</span></span>
- <span data-ttu-id="0cba9-116">**权限**：列出角色具有访问权限的功能和权限级别。</span><span class="sxs-lookup"><span data-stu-id="0cba9-116">**Permissions**: Lists features and level of permissions to which the role has access.</span></span>
- <span data-ttu-id="0cba9-117">**作业**：角色分配列表，定义在会议室资源帐户范围内配置权限的用户。</span><span class="sxs-lookup"><span data-stu-id="0cba9-117">**Assignments**: A list of role assignments defining which users have the configured permissions over the scope of room resource accounts.</span></span> <span data-ttu-id="0cba9-118">一个角色可以有多个分配，用户可以在多个作业中进行。</span><span class="sxs-lookup"><span data-stu-id="0cba9-118">A role can have multiple assignments, and a user can be in multiple assignments.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="0cba9-119">内置角色</span><span class="sxs-lookup"><span data-stu-id="0cba9-119">Built-in roles</span></span>

<span data-ttu-id="0cba9-120">你可以将内置角色分配给组或用户，而无需进一步配置。</span><span class="sxs-lookup"><span data-stu-id="0cba9-120">You can assign built-in roles to groups or users without further configuration.</span></span> <span data-ttu-id="0cba9-121">请注意，你无法删除或编辑内置角色的名称、说明、类型或权限。</span><span class="sxs-lookup"><span data-stu-id="0cba9-121">Keep in mind that you can't delete or edit the name, description, type, or permissions of a built-in role.</span></span>

- <span data-ttu-id="0cba9-122">**托管服务管理员**：具有对 Microsoft 团队聊天室 Premium 服务门户的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="0cba9-122">**Managed Service Administrator**: Has full access to the Microsoft Teams Room Premium service portal.</span></span>
- <span data-ttu-id="0cba9-123">**网站负责人**：组织会议室、拥有报表的权限并可以管理票证。</span><span class="sxs-lookup"><span data-stu-id="0cba9-123">**Site Lead**: Organizes rooms, has access to reports and can manage tickets.</span></span> <span data-ttu-id="0cba9-124">无法重置注册密钥或对该服务的配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="0cba9-124">Can't reset enrollment key or make changes to the configuration of the service.</span></span>  
- <span data-ttu-id="0cba9-125">**网站技术**：管理特定聊天室的票证。</span><span class="sxs-lookup"><span data-stu-id="0cba9-125">**Site Tech**: Manages tickets for specific rooms.</span></span> <span data-ttu-id="0cba9-126">无权修改服务或整理服务中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0cba9-126">Doesn't have permissions to modify the service or organize rooms in the service.</span></span>

<span data-ttu-id="0cba9-127">下表总结了每个角色可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0cba9-127">The following table summarizes what each role can do.</span></span>

|<span data-ttu-id="0cba9-128">功能</span><span class="sxs-lookup"><span data-stu-id="0cba9-128">Features</span></span> |<span data-ttu-id="0cba9-129">权限</span><span class="sxs-lookup"><span data-stu-id="0cba9-129">Permission</span></span> |<span data-ttu-id="0cba9-130">托管服务管理员</span><span class="sxs-lookup"><span data-stu-id="0cba9-130">Managed Service Administrator</span></span>  |<span data-ttu-id="0cba9-131">网站负责人</span><span class="sxs-lookup"><span data-stu-id="0cba9-131">Site Lead</span></span>  |<span data-ttu-id="0cba9-132">网站技术</span><span class="sxs-lookup"><span data-stu-id="0cba9-132">Site Tech</span></span>  |
|---------|---------|---------|---------|---------|
|<span data-ttu-id="0cba9-133">工作室</span><span class="sxs-lookup"><span data-stu-id="0cba9-133">Rooms</span></span>     |<span data-ttu-id="0cba9-134">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-134">View</span></span>        |<span data-ttu-id="0cba9-135">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-135">&#10004;</span></span>           |<span data-ttu-id="0cba9-136">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-136">&#10004;</span></span>           |<span data-ttu-id="0cba9-137">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-137">&#10004;</span></span>  |
|    |<span data-ttu-id="0cba9-138">更改</span><span class="sxs-lookup"><span data-stu-id="0cba9-138">Modify</span></span>         |<span data-ttu-id="0cba9-139">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-139">&#10004;</span></span>           |<span data-ttu-id="0cba9-140">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-140">&#10004;</span></span>           |<span data-ttu-id="0cba9-141">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-141">&#10004;</span></span> |
|    |<span data-ttu-id="0cba9-142">重置键</span><span class="sxs-lookup"><span data-stu-id="0cba9-142">Reset key</span></span>         |<span data-ttu-id="0cba9-143">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-143">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="0cba9-144">下载密钥</span><span class="sxs-lookup"><span data-stu-id="0cba9-144">Download key</span></span>         |<span data-ttu-id="0cba9-145">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-145">&#10004;</span></span>           |<span data-ttu-id="0cba9-146">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-146">&#10004;</span></span>          |<span data-ttu-id="0cba9-147">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-147">&#10004;</span></span> |
|    |<span data-ttu-id="0cba9-148">取消</span><span class="sxs-lookup"><span data-stu-id="0cba9-148">Unenroll</span></span>         |<span data-ttu-id="0cba9-149">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-149">&#10004;</span></span>           |<span data-ttu-id="0cba9-150">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-150">&#10004;</span></span>           |<span data-ttu-id="0cba9-151">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-151">&#10004;</span></span> |
|<span data-ttu-id="0cba9-152">组管理</span><span class="sxs-lookup"><span data-stu-id="0cba9-152">Group management</span></span>   |<span data-ttu-id="0cba9-153">创建</span><span class="sxs-lookup"><span data-stu-id="0cba9-153">Create</span></span>         |<span data-ttu-id="0cba9-154">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-154">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="0cba9-155">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-155">View</span></span>       |<span data-ttu-id="0cba9-156">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-156">&#10004;</span></span>          |<span data-ttu-id="0cba9-157">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-157">&#10004;</span></span>           ||
|    |<span data-ttu-id="0cba9-158">更改</span><span class="sxs-lookup"><span data-stu-id="0cba9-158">Modify</span></span>         |<span data-ttu-id="0cba9-159">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-159">&#10004;</span></span>           |           ||
|<span data-ttu-id="0cba9-160">更新铃声管理</span><span class="sxs-lookup"><span data-stu-id="0cba9-160">Update ring management</span></span>    |<span data-ttu-id="0cba9-161">创建</span><span class="sxs-lookup"><span data-stu-id="0cba9-161">Create</span></span>         |<span data-ttu-id="0cba9-162">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-162">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="0cba9-163">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-163">View</span></span>         |<span data-ttu-id="0cba9-164">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-164">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="0cba9-165">更改</span><span class="sxs-lookup"><span data-stu-id="0cba9-165">Modify</span></span>         |<span data-ttu-id="0cba9-166">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-166">&#10004;</span></span>           |           ||
|<span data-ttu-id="0cba9-167">报告会</span><span class="sxs-lookup"><span data-stu-id="0cba9-167">Reports</span></span>   |<span data-ttu-id="0cba9-168">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-168">View</span></span>        |<span data-ttu-id="0cba9-169">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-169">&#10004;</span></span>           |<span data-ttu-id="0cba9-170">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-170">&#10004;</span></span>           ||
|<span data-ttu-id="0cba9-171">票证管理</span><span class="sxs-lookup"><span data-stu-id="0cba9-171">Ticket management</span></span>   |<span data-ttu-id="0cba9-172">创建客户事件</span><span class="sxs-lookup"><span data-stu-id="0cba9-172">Create customer incident</span></span>         |<span data-ttu-id="0cba9-173">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-173">&#10004;</span></span>           |<span data-ttu-id="0cba9-174">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-174">&#10004;</span></span>           |<span data-ttu-id="0cba9-175">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-175">&#10004;</span></span>  |
|    |<span data-ttu-id="0cba9-176">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-176">View</span></span>         |<span data-ttu-id="0cba9-177">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-177">&#10004;</span></span>           |<span data-ttu-id="0cba9-178">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-178">&#10004;</span></span>           |<span data-ttu-id="0cba9-179">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-179">&#10004;</span></span>  |
|    |<span data-ttu-id="0cba9-180">更新</span><span class="sxs-lookup"><span data-stu-id="0cba9-180">Update</span></span>         |<span data-ttu-id="0cba9-181">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-181">&#10004;</span></span>           |<span data-ttu-id="0cba9-182">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-182">&#10004;</span></span>           |<span data-ttu-id="0cba9-183">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-183">&#10004;</span></span>  |
|<span data-ttu-id="0cba9-184">Microsoft 团队聊天室托管服务设置</span><span class="sxs-lookup"><span data-stu-id="0cba9-184">Microsoft Teams Rooms managed service settings</span></span>    |<span data-ttu-id="0cba9-185">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-185">View</span></span>         |<span data-ttu-id="0cba9-186">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-186">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="0cba9-187">更改</span><span class="sxs-lookup"><span data-stu-id="0cba9-187">Modify</span></span>        |<span data-ttu-id="0cba9-188">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-188">&#10004;</span></span>           |         ||
|<span data-ttu-id="0cba9-189">角色管理</span><span class="sxs-lookup"><span data-stu-id="0cba9-189">Role management</span></span>    |<span data-ttu-id="0cba9-190">查看</span><span class="sxs-lookup"><span data-stu-id="0cba9-190">View</span></span>         |<span data-ttu-id="0cba9-191">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-191">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="0cba9-192">更改</span><span class="sxs-lookup"><span data-stu-id="0cba9-192">Modify</span></span>         |<span data-ttu-id="0cba9-193">&#10004;</span><span class="sxs-lookup"><span data-stu-id="0cba9-193">&#10004;</span></span>           |         ||

## <a name="assign-a-role"></a><span data-ttu-id="0cba9-194">分配角色</span><span class="sxs-lookup"><span data-stu-id="0cba9-194">Assign a role</span></span>

<span data-ttu-id="0cba9-195">若要分配角色，您必须是全局管理员或托管服务管理员。</span><span class="sxs-lookup"><span data-stu-id="0cba9-195">To assign roles, you must be a Global Administrator or Managed Service Administrator.</span></span>

1. <span data-ttu-id="0cba9-196">在 Microsoft 团队聊天室托管服务门户的左侧导航中，转到 "**设置**  >  **角色**"。</span><span class="sxs-lookup"><span data-stu-id="0cba9-196">In the left navigation of the Microsoft Teams Rooms managed service portal, go to **Settings** > **Roles**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="显示角色的访问控制页面的屏幕截图":::

2. <span data-ttu-id="0cba9-198">选择要分配的角色。</span><span class="sxs-lookup"><span data-stu-id="0cba9-198">Select the role you want to assign.</span></span>
3. <span data-ttu-id="0cba9-199">在 "角色" 窗格中**Assignments**，选择 "  >  **添加**作业"。</span><span class="sxs-lookup"><span data-stu-id="0cba9-199">In the role pane, select **Assignments** > **Add**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="用于添加角色的 "添加" 选项的屏幕截图。":::

4. <span data-ttu-id="0cba9-201">在 " **常规设置** " 页面的 " **作业属性**" 下，输入此作业的名称。</span><span class="sxs-lookup"><span data-stu-id="0cba9-201">On the **General settings** page, under **Assignment properties**, enter a name for this assignment.</span></span> <span data-ttu-id="0cba9-202">说明是可选的。</span><span class="sxs-lookup"><span data-stu-id="0cba9-202">The description is optional.</span></span> <span data-ttu-id="0cba9-203">选择 " **下一步"。**</span><span class="sxs-lookup"><span data-stu-id="0cba9-203">Choose **Next.**</span></span>
5. <span data-ttu-id="0cba9-204">在 " **成员** " 页面上，在 " **搜索用户或安全组** " 框中，输入你希望向其授予权限的租户中的用户或安全组的名称，然后完成选择。</span><span class="sxs-lookup"><span data-stu-id="0cba9-204">On the **Members** page, in the **Search for user or security group** box, enter the name of a user or security group in your tenant to which you want to give permissions, and then complete the selection.</span></span> <span data-ttu-id="0cba9-205">选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0cba9-205">Choose **Next**.</span></span> 
6. <span data-ttu-id="0cba9-206">在 " **范围** " 页面上，在 " **搜索聊天室或聊天室组** " 框中，键入允许用户管理的聊天室或聊天室组的名称。</span><span class="sxs-lookup"><span data-stu-id="0cba9-206">On the **Scope** page, in the **Search for room or room group** box, type the name of either a room or room group that the user will be allowed to manage.</span></span> <span data-ttu-id="0cba9-207">选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0cba9-207">Choose **Next**.</span></span>
7. <span data-ttu-id="0cba9-208">在 " **完成** " 页面上，查看作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0cba9-208">On the **Finish** page, review the details of the assignment.</span></span> <span data-ttu-id="0cba9-209">如果你对配置感到满意，请选择 " **添加作业**"。</span><span class="sxs-lookup"><span data-stu-id="0cba9-209">If you're satisfied with the configuration, choose **Add assignment**.</span></span> <span data-ttu-id="0cba9-210">如果要编辑分区，请使用 " **上一** 步" 按钮或选择左侧导航中的步骤。</span><span class="sxs-lookup"><span data-stu-id="0cba9-210">If you want to edit a section, use the **Previous** button or select the step in the left navigation.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="0cba9-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="0cba9-211">Related topics</span></span>

- [<span data-ttu-id="0cba9-212">Microsoft 团队聊天室托管服务</span><span class="sxs-lookup"><span data-stu-id="0cba9-212">Microsoft Teams Rooms managed service</span></span>](microsoft-teams-rooms-premium.md)
