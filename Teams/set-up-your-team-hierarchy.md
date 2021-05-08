---
title: 设置团队目标层次结构
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 了解如何在组织中设置团队层次结构，以将内容发布到一大组团队。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63a9cf6cab1bfb50c17c8546a65ad50e41759edc
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891279"
---
# <a name="set-up-your-team-targeting-hierarchy"></a><span data-ttu-id="0ba1c-103">设置团队目标层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-103">Set up your team targeting hierarchy</span></span>

<span data-ttu-id="0ba1c-104">设置团队目标层次结构将允许组织将内容发布到一大组团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-104">Setting up a team targeting hierarchy will allow your organization to publish content to a large set of teams.</span></span> <span data-ttu-id="0ba1c-105">团队目标层次结构定义层次结构中所有团队如何彼此关联、哪些用户可以发布任务，以及哪些团队用户有权发布到哪个团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-105">The team targeting hierarchy defines how all the teams in your hierarchy are related to each other, which users can publish tasks, and which teams users have permissions to publish to.</span></span> <span data-ttu-id="0ba1c-106">除非为组织设置了面向团队的层次结构，否则所有用户都禁用发布功能。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-106">Publishing features are disabled for all users unless a team targeting hierarchy is set up for your organization.</span></span> <span data-ttu-id="0ba1c-107">若要设置团队目标层次结构，需要创建一个定义层次结构的文件，并将其上传到Teams以将其应用到组织。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-107">To set up a team targeting hierarchy, you'll need to create a file that defines the hierarchy and then upload it to Teams to apply it to your organization.</span></span> <span data-ttu-id="0ba1c-108">上传架构后，Teams应用可以使用它。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-108">After the schema is uploaded, apps within Teams can use it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba1c-109">对于初始版本，只有"任务"应用支持分层团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-109">For the initial release, only the Tasks app supports hierarchical teams.</span></span>  <span data-ttu-id="0ba1c-110">将团队目标层次结构应用于组织将在 ["任务"应用中](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 启用任务发布。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-110">Applying a team targeting hierarchy to your organization will enable [task publishing](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in the Tasks app.</span></span> <span data-ttu-id="0ba1c-111">你不会在团队的"其他"区域看到团队Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-111">You won't see a hierarchy of teams in other areas of Microsoft Teams.</span></span>

<span data-ttu-id="0ba1c-112">下面是层次结构在任务应用中在任务应用中的表示Teams。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-112">Here's an example of how the hierarchy is represented in the Tasks app in Teams.</span></span> <span data-ttu-id="0ba1c-113">创建任务列表后，发布团队成员可以选择要向任务列表发送 () 的收件人团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-113">After a task list is created, members of the publishing team can then select the recipient teams to send (publish) the task list to.</span></span> <span data-ttu-id="0ba1c-114">选择团队时，发布团队可以按层次结构、属性或两者的组合进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-114">When selecting teams, the publishing team can filter by hierarchy, by attributes, or a combination of both.</span></span><br>

![发布任务的屏幕截图](media/manage-tasks-app-publish.png)

## <a name="terminology"></a><span data-ttu-id="0ba1c-116">术语</span><span class="sxs-lookup"><span data-stu-id="0ba1c-116">Terminology</span></span>

<span data-ttu-id="0ba1c-117">导航层次结构时，以下术语非常重要。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-117">The following terms will be important as you navigate hierarchies.</span></span> <span data-ttu-id="0ba1c-118">Teams将 **称为节点**。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-118">Teams will be referred to as **nodes**.</span></span>

* <span data-ttu-id="0ba1c-119">**根** 节点是层次结构中最顶层的节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-119">**Root nodes** are the topmost nodes in the hierarchy.</span></span> <span data-ttu-id="0ba1c-120">在示例中，零售通信是根节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-120">In the example, Retail Communications is a root node.</span></span>
* <span data-ttu-id="0ba1c-121">**父节点\*\*\*\*和子** 节点是表示两个已连接节点之间的关系的术语。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-121">**Parent nodes** and **child nodes** are terms that represent a relationship between two connected nodes.</span></span> <span data-ttu-id="0ba1c-122">在示例中，区域 01 是区域 1 的子节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-122">In the example, District 01 is a child node of Area 1.</span></span>
* <span data-ttu-id="0ba1c-123">多个级别的子级称为 **后代**。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-123">Multiple levels of children are referred to as **descendants**.</span></span> <span data-ttu-id="0ba1c-124">区域 01、Store 01、Store 03、Store 07、区域 02 和 03 都是区域 1 的后代。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-124">District 01, Store 01, Store 03, Store 07, District 02, and District 03 are all descendants of Area 1.</span></span>
* <span data-ttu-id="0ba1c-125">没有子节点的节点称为叶 **节点**。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-125">A node with no children is called a **leaf node**.</span></span> <span data-ttu-id="0ba1c-126">它们位于层次结构的底部。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-126">They are at the bottom of a hierarchy.</span></span>
* <span data-ttu-id="0ba1c-127">**收件人** 团队是已选择接收要发布的一组特定内容的团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-127">**Recipient teams** are teams that have been selected to receive a specific set of content to be published.</span></span> <span data-ttu-id="0ba1c-128">它们必须是叶节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-128">They must be leaf nodes.</span></span>

## <a name="plan-your-hierarchy"></a><span data-ttu-id="0ba1c-129">规划层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-129">Plan your hierarchy</span></span>

<span data-ttu-id="0ba1c-130">创建定义层次结构的架构之前，需要执行一些规划，并决定要如何塑造组织。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-130">Before you create the schema that defines your hierarchy, you need to do some planning and decide how you want to shape your organization.</span></span>  <span data-ttu-id="0ba1c-131">第一个优先级是确定哪些组织组需要将任务发布到其他组。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-131">One of the first priorities is deciding which organizational groups need to publish tasks to other groups.</span></span> <span data-ttu-id="0ba1c-132">层次结构中的每个节点表示一个工作组或组组。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-132">Each node in the hierarchy represents a working group or group of groups.</span></span>

### <a name="permissions-to-publish"></a><span data-ttu-id="0ba1c-133">发布权限</span><span class="sxs-lookup"><span data-stu-id="0ba1c-133">Permissions to publish</span></span>

<span data-ttu-id="0ba1c-134">发布权限取决于用户是层次结构中任何团队的成员，以及该团队或一组团队与层次结构中其他团队的关系。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-134">Permission to publish depends on whether a user is a member of any teams in the hierarchy plus the relationship of that team or set of teams to other teams in the hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="0ba1c-135">团队的所有者还被授予发布权限。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-135">The owner of a team is also granted publishing permissions.</span></span>

* <span data-ttu-id="0ba1c-136">如果用户是至少一个在层次结构中具有后代的团队的成员，该用户可以发布到这些后代，而无需成为他们想要发布到的所有团队的成员。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-136">If a user is a member of at least one team that has descendants in the hierarchy, that user can publish to those descendants without being a member of all teams they want to publish to.</span></span>
* <span data-ttu-id="0ba1c-137">如果用户是层次结构中至少一个团队的成员，但不是该层次结构中具有后代的任何团队的成员，则该用户可以看到并接收来自其组织的已发布内容。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-137">If a user is a member of a least one team in the hierarchy but isn't a member of any team with descendants in the hierarchy, that user can see and receive published content from their organization.</span></span>
* <span data-ttu-id="0ba1c-138">如果用户不是层次结构中任何团队的成员，该用户将看不到任何与发布相关的功能。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-138">If a user isn't a member of any team in the hierarchy, that user won't see any publishing-related functionality.</span></span>

### <a name="guidelines"></a><span data-ttu-id="0ba1c-139">指南</span><span class="sxs-lookup"><span data-stu-id="0ba1c-139">Guidelines</span></span>

* <span data-ttu-id="0ba1c-140">每个组织只能应用一个层次结构文件。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-140">There can only be one hierarchy file applied per organization.</span></span> <span data-ttu-id="0ba1c-141">但是，可以将组织的不同部分作为不同层次结构一起包含到一个 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-141">However, you can include different parts of your organization together as distinct hierarchies of nodes within one CSV file.</span></span> <span data-ttu-id="0ba1c-142">例如，Contoso Pharmaceuticals 有一个"药店"根节点和一个零售根节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-142">For example, Contoso Pharmaceuticals has a Pharmacy root node and a Retail root node.</span></span> <span data-ttu-id="0ba1c-143">这两个根节点具有多个后代行，并且它们之间没有重叠。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-143">Both root nodes have multiple rows of descendants and there's no overlap between them.</span></span>
* <span data-ttu-id="0ba1c-144">只有叶节点可以是出版物的接收者。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-144">Only leaf nodes can be recipients of a publication.</span></span> <span data-ttu-id="0ba1c-145">层次结构中的其他节点有助于选择出版物的收件人。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-145">Other nodes in the hierarchy are helpful for selecting recipients of a publication.</span></span>
* <span data-ttu-id="0ba1c-146">团队只能在层次结构中表示一次。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-146">A team can only be represented one time in a hierarchy.</span></span>
* <span data-ttu-id="0ba1c-147">一个层次结构可以包含最多 15，000 个节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-147">A hierarchy can contain up to 15,000 nodes.</span></span> <span data-ttu-id="0ba1c-148">我们计划与客户合作，提高较大组织的此限制。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-148">We plan to work with customers to raise this limit for larger organizations.</span></span>

### <a name="example-hierarchy"></a><span data-ttu-id="0ba1c-149">示例层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-149">Example hierarchy</span></span>

<span data-ttu-id="0ba1c-150">例如，在下面的层次结构中，召回率、通信和 HR 可以将任务发布到层次结构中每个底部节点 (团队) ，但东北部区域只能将任务发布到纽约应用商店和波士顿商店团队。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-150">For example, in the following hierarchy, Recall, Communications, and HR can publish tasks to every bottom node (team) in the hierarchy, but Northeast Zone can only publish tasks to the New York Store and Boston Store teams.</span></span> <span data-ttu-id="0ba1c-151">示例层次结构允许召回、通信和人力资源组发布适用于整个公司的任务，例如 CEO 的权益信息或消息。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-151">The example hierarchy allows the Recall, Communications, and HR groups to publish tasks that apply to the entire company, such as benefits information or messages from the CEO.</span></span> <span data-ttu-id="0ba1c-152">东北部区域只能向纽约应用商店和波士顿商店团队发布人员日程安排、天气信息等任务。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-152">Northeast Zone can publish tasks like personnel scheduling, weather information, and so on, only to the New York Store and Boston Store teams.</span></span>

![团队分层示例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a><span data-ttu-id="0ba1c-154">创建层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-154">Create your hierarchy</span></span>

> [!NOTE]
> <span data-ttu-id="0ba1c-155">本文的其余部分讨论如何在将任务发布到收件人团队的上下文中设置团队层次结构。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-155">The remainder of this article discusses setting up a team hierarchy in the context of publishing tasks to recipient teams.</span></span> <span data-ttu-id="0ba1c-156">有关[任务应用（启用时显示](./manage-tasks-app.md)任务发布Teams概述，请参阅在任务应用中管理组织的任务应用。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-156">Refer to [Manage the Tasks app for your organization in Teams](./manage-tasks-app.md) for an overview of the Tasks app, where task publishing appears when enabled.</span></span>

<span data-ttu-id="0ba1c-157">定义层次结构的架构基于 CSV 文件中以逗号分隔 () 值。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-157">The schema that defines your hierarchy is based on a comma-separated values (CSV) file.</span></span> <span data-ttu-id="0ba1c-158">CSV 文件的每一行对应于团队层次结构中的一个节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-158">Each row in the CSV file corresponds to one node within the hierarchy of teams.</span></span> <span data-ttu-id="0ba1c-159">每一行都包含在层次结构中为节点命名的信息，可以选择性地将节点链接到团队，并包含可用于在支持团队的应用中筛选团队的属性。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-159">Each row contains information that names the node within the hierarchy, optionally links it to a team, and includes attributes that can be used to filter teams in apps that support it.</span></span>

<span data-ttu-id="0ba1c-160">还可以定义 **存储桶**，这些类别是发布团队可用于组织发送给收件人团队的内容，以便他们更轻松地查看、排序和关注相关内容。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-160">You can also define **buckets**, which are categories that the publishing team can use to organize content sent to recipient teams to make it easier for them to view, sort, and focus on relevant content.</span></span>

### <a name="add-required-columns"></a><span data-ttu-id="0ba1c-161">添加所需的列</span><span class="sxs-lookup"><span data-stu-id="0ba1c-161">Add required columns</span></span>

<span data-ttu-id="0ba1c-162">CSV 文件必须包含以下三列，顺序如下，从第一列开始。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-162">The CSV file must contain the following three columns, in the following order, starting at the first column.</span></span> <span data-ttu-id="0ba1c-163">节点必须链接到团队，团队接收任务。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-163">A node must be linked to a team for it to receive tasks.</span></span>

| <span data-ttu-id="0ba1c-164">列名称</span><span class="sxs-lookup"><span data-stu-id="0ba1c-164">Column name</span></span>   | <span data-ttu-id="0ba1c-165">是否必需</span><span class="sxs-lookup"><span data-stu-id="0ba1c-165">Required</span></span> | <span data-ttu-id="0ba1c-166">描述</span><span class="sxs-lookup"><span data-stu-id="0ba1c-166">Description</span></span>   |
----------------|----------|---------------|
| <span data-ttu-id="0ba1c-167">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0ba1c-167">DisplayName</span></span>    | <span data-ttu-id="0ba1c-168">是</span><span class="sxs-lookup"><span data-stu-id="0ba1c-168">Yes</span></span>      | <span data-ttu-id="0ba1c-169">此字段是节点的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-169">This field is the name of the node.</span></span> <span data-ttu-id="0ba1c-170">名称最多包含 100 个字符，并且仅包含字符 A-Z、a-z 和 0-9。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-170">The name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="0ba1c-171">节点名称必须唯一。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-171">Node names must be unique.</span></span> |
| <span data-ttu-id="0ba1c-172">ParentName</span><span class="sxs-lookup"><span data-stu-id="0ba1c-172">ParentName</span></span>    | <span data-ttu-id="0ba1c-173">是</span><span class="sxs-lookup"><span data-stu-id="0ba1c-173">Yes</span></span>       | <span data-ttu-id="0ba1c-174">这是父节点的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-174">This is the name of the parent node.</span></span> <span data-ttu-id="0ba1c-175">此处指定的值必须与父节点 **的 DisplayName** 字段中的值完全匹配。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-175">The value you specify here must match the value in the **DisplayName** field of the parent node exactly.</span></span> <span data-ttu-id="0ba1c-176">如果要添加多个父节点，请用分号分隔每个父节点名称; (;) 。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-176">If you want to add more than one parent node, separate each parent node name with a semicolon (;).</span></span> <span data-ttu-id="0ba1c-177">可以添加多达 25 个父节点，每个父节点名称最多包含 2500 个字符。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-177">You can add up to 25 parent nodes, and each parent node name can be up to 2500 characters long.</span></span> <span data-ttu-id="0ba1c-178">只有当父节点是根节点时，一个节点才能具有多个父节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-178">A node can have multiple parent nodes only if the parent nodes are root nodes.</span></span>   <br><br><span data-ttu-id="0ba1c-179">**重要** 请注意不要创建循环，其中层次结构中较高级别的父级引用层次结构中较低级别的子节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-179">**IMPORTANT** Be careful not to create a loop where a parent higher up in the hierarchy references a child node lower in the hierarchy.</span></span> <span data-ttu-id="0ba1c-180">不支持此操作。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-180">This isn't supported.</span></span> |
| <span data-ttu-id="0ba1c-181">TeamId</span><span class="sxs-lookup"><span data-stu-id="0ba1c-181">TeamId</span></span>        | <span data-ttu-id="0ba1c-182">是，如果团队发布任务或从父节点接收任务</span><span class="sxs-lookup"><span data-stu-id="0ba1c-182">Yes, if the team publishes tasks or receives tasks from a parent node</span></span>       | <span data-ttu-id="0ba1c-183">其中包含要将节点链接到的团队的 ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-183">This contains the ID of the team you want to link a node to.</span></span> <span data-ttu-id="0ba1c-184">每个节点必须引用一个唯一团队，因此每个 TeamId 值在层次结构文件中可能只出现一次。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-184">Each node must refer to a unique team, so each TeamId value may appear only once in the hierarchy file.</span></span> <span data-ttu-id="0ba1c-185">若要获取想要将节点链接到的团队的 ID，请运行以下 PowerShell 命令 `Get-Team | Export-Csv TeamList.csv` ：。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-185">To get the ID of a team you want to link a node to, run the following PowerShell command: `Get-Team | Export-Csv TeamList.csv`.</span></span> <span data-ttu-id="0ba1c-186">此命令列出组织中团队，并包括每个团队的名称和 ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-186">This command lists the teams in your organization and includes the name and ID for each team.</span></span> <span data-ttu-id="0ba1c-187">找到要链接到的团队的名称，然后将 ID 复制到此字段中。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-187">Find the name of the team you want to link to, and then copy the ID into this field.</span></span>|

> [!NOTE]
> <span data-ttu-id="0ba1c-188">如果节点不是根节点或叶节点，并且不需要团队成员身份来授予相应的发布和报告权限，可以将 TeamId 留空。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-188">If a node isn't a root node or a leaf node and you don't need the team membership to grant the corresponding permissions for publishing and reporting, you can leave the TeamId blank.</span></span> <span data-ttu-id="0ba1c-189">此方法可用于在选择收件人团队时添加更精细的粒度，或者用于在没有相应团队的情况下查看完成报告。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-189">This method can be used to add more granularity when choosing recipient teams or for viewing completion reports without having a corresponding team.</span></span>

### <a name="add-attribute-columns"></a><span data-ttu-id="0ba1c-190">添加属性列</span><span class="sxs-lookup"><span data-stu-id="0ba1c-190">Add attribute columns</span></span>

<span data-ttu-id="0ba1c-191">添加三个必填列后，可以添加可选属性列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-191">After you add the three required columns, you can add optional attribute columns.</span></span> <span data-ttu-id="0ba1c-192">这些属性可用于筛选节点，以便更轻松地选择要将任务发布到的节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-192">These attributes can be used to filter nodes so that you can more easily select the ones you want to publish tasks to.</span></span> <span data-ttu-id="0ba1c-193">有两种方法可定义属性，具体取决于该属性的值是否互斥。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-193">There are two ways to define your attributes, depending on whether values for that attribute are mutually exclusive.</span></span>

|<span data-ttu-id="0ba1c-194">添加属性的方法</span><span class="sxs-lookup"><span data-stu-id="0ba1c-194">Ways to add attributes</span></span>|<span data-ttu-id="0ba1c-195">说明</span><span class="sxs-lookup"><span data-stu-id="0ba1c-195">Description</span></span> |<span data-ttu-id="0ba1c-196">示例</span><span class="sxs-lookup"><span data-stu-id="0ba1c-196">Example</span></span>  |
|---|---------|---------|
|<span data-ttu-id="0ba1c-197">如果属性的值互斥，则指定的列名称将成为属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-197">If the values for an attribute are mutually exclusive, the column name you specify becomes the name of the attribute.</span></span>|<span data-ttu-id="0ba1c-198">每行可以包含一个属性值，每个属性列最多包含 50 个唯一值。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-198">Each row can contain one value for that attribute, and each attribute column can have up to 50 unique values.</span></span> <span data-ttu-id="0ba1c-199">每个值最多包含 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-199">Each value can be up to 100 characters long.</span></span> <span data-ttu-id="0ba1c-200">使用团队目标层次结构选择收件人团队时，在属性列中指定的属性值集将显示为该属性的筛选器值。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-200">The set of attribute values you specify in the attribute column will be displayed as filter values for that attribute when selecting recipient teams using the team targeting hierarchy.</span></span>|<span data-ttu-id="0ba1c-201">您希望用户能够按布局筛选存储。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-201">You want users to be able to filter stores by layout.</span></span> <span data-ttu-id="0ba1c-202">此属性的值互斥，因为存储只能有一个布局。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-202">The values for this attribute are mutually exclusive because a store can have only one layout.</span></span> <br><br><span data-ttu-id="0ba1c-203">若要添加属性以按布局筛选应用商店，请添加名为"应用商店布局"的列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-203">To add an attribute to filter stores by layout, add a column named Store layout.</span></span> <span data-ttu-id="0ba1c-204">此示例中，应用商店布局属性的值为"压缩型、标准型"和"大"。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-204">In this example, values for the Store layout attribute are Compact, Standard, and Large.</span></span>
|<span data-ttu-id="0ba1c-205">如果需要为一个属性指示多个值，并且这些值不是互斥的，请对列名称使用 **AttributeName：UniqueValue** 格式。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-205">If you need to indicate multiple values for an attribute and the values aren't mutually exclusive, use the **AttributeName:UniqueValue** format for the column names.</span></span> <br><br><span data-ttu-id="0ba1c-206">**重要** 请确保使用仅英语冒号 (：) ，因为不支持将 unicode 用作属性列分隔符。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-206">**IMPORTANT** Make sure to use the English-only colon (:) as unicode isn't supported as an attribute column delimiter.</span></span> |<span data-ttu-id="0ba1c-207">冒号 " (：) 之前的文本字符串将成为 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-207">The text string before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="0ba1c-208">冒号之前包含相同文本字符串的所有列 (：) 分组到筛选菜单中的一个分区中。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-208">All columns that contain the same text string before the colons (:) are grouped together into a section in the filtering menu.</span></span> <span data-ttu-id="0ba1c-209">冒号后的每个字符串将成为该节的值。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-209">Each of the strings after the colon become the values for that section.</span></span><br><br><span data-ttu-id="0ba1c-210">对于该属性，每一行的值 (0) 或 1。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-210">Each row can have a value of 0 (zero) or 1 for that attribute.</span></span> <span data-ttu-id="0ba1c-211">值为 0 表示属性不适用于节点，值为 1 表示该属性应用于该节点。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-211">A value of 0 means that the attribute doesn't apply to the node and a value of 1 means that the attribute applies to that node.</span></span>|<span data-ttu-id="0ba1c-212">您希望用户能够按部门筛选存储。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-212">You want users to be able to filter stores by department.</span></span> <span data-ttu-id="0ba1c-213">一个存储可以有多个部门，因此此属性的值不是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-213">A store can have multiple departments and so the values for this attribute aren't mutually exclusive.</span></span><br><br><span data-ttu-id="0ba1c-214">本示例将"部门：服装、部门：电子、部门：食物、部门：住宅和公园、部门：体育用品"添加为属性列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-214">In this example, we add Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods as attribute columns.</span></span> <span data-ttu-id="0ba1c-215">部门成为属性名称，用户可以按服装、电子、食品、住宅和住宅以及运动用品部门进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-215">Departments becomes the attribute name and users can filter by the Clothing, Electronics, Foods, Home and Garden, and Sporting goods departments.</span></span>|

<span data-ttu-id="0ba1c-216">添加属性列时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="0ba1c-216">When you add an attribute column, keep the following in mind:</span></span>

* <span data-ttu-id="0ba1c-217">指定的列名或在冒号" (：) "之前指定的列名称将成为属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-217">The column name you specify or the column name that you specify before the colon (:) becomes the name of the attribute.</span></span> <span data-ttu-id="0ba1c-218">此值将显示在使用该层次结构Teams应用。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-218">This value will be displayed in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="0ba1c-219">层次结构中最多包含 50 个属性列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-219">You can have up to 50 attribute columns in your hierarchy.</span></span>
* <span data-ttu-id="0ba1c-220">列名称最多包含 100 个字符，并且仅包含字符 A-Z、a-z 和 0-9，以及空格。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-220">The column name can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9, and spaces.</span></span> <span data-ttu-id="0ba1c-221">列名称必须唯一。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-221">Column names must be unique.</span></span>

### <a name="add-bucket-columns"></a><span data-ttu-id="0ba1c-222">添加存储桶列</span><span class="sxs-lookup"><span data-stu-id="0ba1c-222">Add bucket columns</span></span>

<span data-ttu-id="0ba1c-223">可以添加存储桶列以创建存储桶，这些存储桶是任务可以组织到的分组。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-223">You can add bucket columns to create buckets, which are groupings into which tasks can be organized.</span></span> <span data-ttu-id="0ba1c-224">每个存储桶在 CSV 文件中获取其自己的列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-224">Each bucket gets its own column in the CSV file.</span></span> <span data-ttu-id="0ba1c-225">创建的存储桶可供发布团队使用。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-225">The buckets you create are made available to the publishing team.</span></span> <span data-ttu-id="0ba1c-226">然后，发布团队可以使用这些存储桶对收件人团队的任务进行分类。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-226">The publishing team can then use these buckets to categorize tasks for the recipient teams.</span></span> <span data-ttu-id="0ba1c-227">如果团队中不存在存储桶，则发布任务时按需创建存储桶。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-227">If a bucket doesn't already exist on a team, buckets are created on-demand when tasks are published.</span></span>

<span data-ttu-id="0ba1c-228">通过集中对工作项进行分类一次，发布团队可以预先组织收到任务列表的所有数十、数百或数千个收件人团队的任务列表。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-228">By categorizing the work items one time centrally, the publishing team can pre-organize the task list for all the tens, hundreds, or thousands of recipient teams that receive the task list.</span></span> <span data-ttu-id="0ba1c-229">然后，收件人团队可以按存储桶对任务进行排序和筛选，以重点关注与他们的工作最相关的区域。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-229">The recipient teams can then sort and filter their tasks by bucket to focus on the area most relevant to their work.</span></span>

<span data-ttu-id="0ba1c-230">添加存储桶列时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="0ba1c-230">When you add a bucket column, note the following:</span></span>

* <span data-ttu-id="0ba1c-231">列名称将成为存储桶的名称。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-231">The column name becomes the name of the bucket.</span></span> <span data-ttu-id="0ba1c-232">指定的每个存储桶将显示在使用该层次结构的Teams"存储桶"列表中。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-232">Each bucket you specify will appear in the Buckets list in the Teams apps that use the hierarchy.</span></span>
* <span data-ttu-id="0ba1c-233">建议不要在存储桶名称中包括敏感信息。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-233">We recommend that you don't include sensitive information in bucket names.</span></span> <span data-ttu-id="0ba1c-234">目前，发布团队无法通过创建存储桶后通过发布删除存储桶。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-234">At this time, publishing teams can't remove a bucket through publishing after it's created.</span></span>
* <span data-ttu-id="0ba1c-235">列名称前面必须带有井号标签 (#) 。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-235">The column name must be preceded by a hashtag (#).</span></span> <span data-ttu-id="0ba1c-236">它最多可以包含 100 个字符，并且仅包含字符 A-Z、a-z 和 0-9。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-236">It can be up to 100 characters long and contain only the characters A-Z, a-z, and 0-9.</span></span> <span data-ttu-id="0ba1c-237">例如，#Operations#Frozen商品。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-237">For example, #Operations and #Frozen Goods.</span></span>
* <span data-ttu-id="0ba1c-238">一个层次结构可以包含最多 25 个存储桶列。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-238">A hierarchy may contain up to 25 bucket columns.</span></span> <span data-ttu-id="0ba1c-239">我们计划与客户合作，提高较大组织的此限制。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-239">We plan to work with customers to increase this limit for larger organizations.</span></span>

### <a name="example"></a><span data-ttu-id="0ba1c-240">示例</span><span class="sxs-lookup"><span data-stu-id="0ba1c-240">Example</span></span>

<span data-ttu-id="0ba1c-241">下面是一个架构 CSV 文件的示例，该文件将创建该文件以支持上图所示的层次结构。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-241">Here's an example of a schema CSV file that would be created to support the hierarchy shown in the previous image.</span></span> <span data-ttu-id="0ba1c-242">此架构包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="0ba1c-242">This schema contains the following:</span></span>

* <span data-ttu-id="0ba1c-243">名为 、 `TargetName` `ParentName` 和 的三个必需列 `TeamId`</span><span class="sxs-lookup"><span data-stu-id="0ba1c-243">Three required columns named `TargetName`, `ParentName`, and `TeamId`</span></span>
* <span data-ttu-id="0ba1c-244">名为 、 `Store layout` `Departments:Clothing` 和 的三个属性列 `Departments:Foods`</span><span class="sxs-lookup"><span data-stu-id="0ba1c-244">Three attribute columns named `Store layout`, `Departments:Clothing`, and `Departments:Foods`</span></span>
* <span data-ttu-id="0ba1c-245">名为 、 `Fresh Foods` 和 的三 `Frozen Foods` 个存储桶列 `Women's Wear`</span><span class="sxs-lookup"><span data-stu-id="0ba1c-245">Three bucket columns named `Fresh Foods`, `Frozen Foods`, and `Women's Wear`</span></span>

<span data-ttu-id="0ba1c-246">属性 `Store layout` 包含的值包括 `Compact` 、 `Standard` 和 `Large` 。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-246">The `Store layout` attribute has values that include `Compact`, `Standard`, and `Large`.</span></span> <span data-ttu-id="0ba1c-247">属性 `Departments` 列可以设置为值为零 (`0` 或) `1` 值。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-247">The `Departments` attribute columns can be set to a value of `0` (zero) or `1`.</span></span> <span data-ttu-id="0ba1c-248">上 `Store` `Departments` 图未显示布局和属性。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-248">The `Store` layout and `Departments` attributes aren't shown in the image above.</span></span> <span data-ttu-id="0ba1c-249">它们已添加到此处，以帮助显示如何将属性添加到节点条目。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-249">They're added here to help show how attributes can be added to node entries.</span></span> <span data-ttu-id="0ba1c-250">这三个存储桶列也是如此。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-250">The same is true for the three bucket columns.</span></span>

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a><span data-ttu-id="0ba1c-251">应用层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-251">Apply your hierarchy</span></span>

<span data-ttu-id="0ba1c-252">在架构 CSV 文件中定义层次结构后，即可将其上传到Teams。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-252">After you've defined your hierarchy in the schema CSV file, you're ready to upload it to Teams.</span></span> <span data-ttu-id="0ba1c-253">为此，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-253">To do this, run the following command.</span></span> <span data-ttu-id="0ba1c-254">只有全局管理员或Teams才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-254">You must be a global admin or Teams service admin to do this step.</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a><span data-ttu-id="0ba1c-255">更新层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-255">Update your hierarchy</span></span>

<span data-ttu-id="0ba1c-256">可以使用与上述相同的 PowerShell 命令上传新层次结构以替换旧层次结构。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-256">You can upload a new hierarchy to replace the old one using the same PowerShell command as above.</span></span> <span data-ttu-id="0ba1c-257">每次上传新层次结构时，它将替换上一个层次结构。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-257">Each time you upload a new hierarchy, it replaces the previous hierarchy.</span></span>

### <a name="check-the-status-of-your-hierarchy"></a><span data-ttu-id="0ba1c-258">检查层次结构的状态</span><span class="sxs-lookup"><span data-stu-id="0ba1c-258">Check the status of your hierarchy</span></span>

<span data-ttu-id="0ba1c-259">可以运行以下命令来检查层次结构上传的状态。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-259">You can run the following command to check the status of your hierarchy upload.</span></span>

```powershell
Get-TeamTargetingHierarchyStatus
```

<span data-ttu-id="0ba1c-260">该命令将返回以下字段：</span><span class="sxs-lookup"><span data-stu-id="0ba1c-260">The command will return the following fields:</span></span>

<span data-ttu-id="0ba1c-261">字段</span><span class="sxs-lookup"><span data-stu-id="0ba1c-261">Field</span></span>|<span data-ttu-id="0ba1c-262">说明</span><span class="sxs-lookup"><span data-stu-id="0ba1c-262">Description</span></span>
-----|------------
<span data-ttu-id="0ba1c-263">ID</span><span class="sxs-lookup"><span data-stu-id="0ba1c-263">Id</span></span> | <span data-ttu-id="0ba1c-264">上传的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-264">The unique ID for the upload.</span></span>
<span data-ttu-id="0ba1c-265">状态</span><span class="sxs-lookup"><span data-stu-id="0ba1c-265">Status</span></span> | <span data-ttu-id="0ba1c-266">Upload状态。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-266">Upload status.</span></span> <span data-ttu-id="0ba1c-267">值包括 **"正在启动\*\*\*\*"、正在验证\*\*\*\*、"成功"** 和"**失败"**</span><span class="sxs-lookup"><span data-stu-id="0ba1c-267">Values include **Starting**, **Validating**, **Successful**, and **Failed**</span></span>
<span data-ttu-id="0ba1c-268">ErrorDetails</span><span class="sxs-lookup"><span data-stu-id="0ba1c-268">ErrorDetails</span></span> | <span data-ttu-id="0ba1c-269">出现上传错误时的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-269">Details if there's an upload error.</span></span> <span data-ttu-id="0ba1c-270">有关错误详细信息的详细信息，请参阅故障排除部分。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-270">For more information about the error details, see the Troubleshooting section.</span></span> <span data-ttu-id="0ba1c-271">如果没有错误，此字段为空。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-271">If there's no error, this field is blank.</span></span>
<span data-ttu-id="0ba1c-272">LastUpdatedAt</span><span class="sxs-lookup"><span data-stu-id="0ba1c-272">LastUpdatedAt</span></span> | <span data-ttu-id="0ba1c-273">文件的上次更新时间戳和日期。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-273">Timestamp and date of when the file was last updated.</span></span>
<span data-ttu-id="0ba1c-274">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="0ba1c-274">LastModifiedBy</span></span> | <span data-ttu-id="0ba1c-275">修改文件的最后一个用户 ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-275">The ID of the last user who modified the file.</span></span>
<span data-ttu-id="0ba1c-276">FileName</span><span class="sxs-lookup"><span data-stu-id="0ba1c-276">FileName</span></span> | <span data-ttu-id="0ba1c-277">CSV 的文件名。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-277">The file name of the CSV.</span></span>

## <a name="remove-your-hierarchy"></a><span data-ttu-id="0ba1c-278">删除层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-278">Remove your hierarchy</span></span>

<span data-ttu-id="0ba1c-279">如果要立即禁用组织中所有用户的"已发布列表"选项卡，可以删除层次结构。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-279">If you want to immediately disable the **Published lists** tab for all users in your organization, you can remove your hierarchy.</span></span> <span data-ttu-id="0ba1c-280">用户无法访问"已发布列表 **"选项卡或** 选项卡上的任何功能。 这包括创建新的任务列表以发布、访问草稿列表、发布、取消发布和重复列表以及查看报告的能力。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-280">Users won't have access to the **Published lists** tab or any of the functionalities on the tab.  This includes the ability to create new task lists to publish, access draft lists, publish, unpublish, and duplicate lists, and view reporting.</span></span> <span data-ttu-id="0ba1c-281">删除层次结构不会取消发布以前发布的任务。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-281">Removing the hierarchy doesn't unpublish tasks that were previously published.</span></span> <span data-ttu-id="0ba1c-282">这些任务仍可供收件人团队完成。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-282">These tasks will remain available for recipient teams to complete.</span></span>

<span data-ttu-id="0ba1c-283">若要删除层次结构，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-283">To remove your hierarchy, run the following command.</span></span> <span data-ttu-id="0ba1c-284">只有管理员才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-284">You must be an admin to perform this step.</span></span>

```powershell
Remove-TeamTargetingHierarchy
```

<span data-ttu-id="0ba1c-285">确认删除时，状态消息仍显示以前的架构存在，尽管尝试再次删除会返回对象为 null 的错误。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-285">When confirming deletion, the status message will still display the previous schema is present, although attempting to delete again returns an error that the object is null.</span></span>

## <a name="create-a-sample-hierarchy"></a><span data-ttu-id="0ba1c-286">创建示例层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-286">Create a sample hierarchy</span></span>

### <a name="install-the-teams-powershell-module"></a><span data-ttu-id="0ba1c-287">安装 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="0ba1c-287">Install the Teams PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba1c-288">若要执行此步骤，必须安装并使用 PowerShell 库中Teams PowerShell 公共预览[版模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-288">To perform this step, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="0ba1c-289">有关安装模块的步骤，请参阅安装 Teams [PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="0ba1c-289">For steps on how to install the module, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

### <a name="sample-script"></a><span data-ttu-id="0ba1c-290">示例脚本</span><span class="sxs-lookup"><span data-stu-id="0ba1c-290">Sample script</span></span>

<span data-ttu-id="0ba1c-291">以下脚本可用于创建团队，将.csv文件上传到Microsoft Teams租户。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-291">The following script can be used to create the teams and upload a .csv file to your Microsoft Teams tenant.</span></span> <span data-ttu-id="0ba1c-292">如果有现有的层次结构，此脚本将替换它。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-292">If you have an existing hierarchy, this script will replace it.</span></span>

#### <a name="create-teams-for-a-simple-hierarchy"></a><span data-ttu-id="0ba1c-293">为简单层次结构创建团队</span><span class="sxs-lookup"><span data-stu-id="0ba1c-293">Create teams for a simple hierarchy</span></span>

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a><span data-ttu-id="0ba1c-294">使用团队数据创建以逗号分隔的输出 (DisplayName、ParentName、TeamId) </span><span class="sxs-lookup"><span data-stu-id="0ba1c-294">Use team data to create comma-separated output (DisplayName, ParentName, TeamId)</span></span>

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a><span data-ttu-id="0ba1c-295">将输出保存到.csv **下载文件夹中的一个文件**</span><span class="sxs-lookup"><span data-stu-id="0ba1c-295">Save output to a .csv file in the **Downloads** folder</span></span>

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a><span data-ttu-id="0ba1c-296">Upload层次结构</span><span class="sxs-lookup"><span data-stu-id="0ba1c-296">Upload the hierarchy</span></span>

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a><span data-ttu-id="0ba1c-297">疑难解答</span><span class="sxs-lookup"><span data-stu-id="0ba1c-297">Troubleshooting</span></span>

### <a name="how-to-view-error-details"></a><span data-ttu-id="0ba1c-298">如何查看错误详细信息</span><span class="sxs-lookup"><span data-stu-id="0ba1c-298">How to view error details</span></span>

<span data-ttu-id="0ba1c-299">可以运行以下命令，了解导致错误的原因并返回错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-299">You can run the following command to understand what is causing an error and return the error details.</span></span>

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="0ba1c-300">上传架构 CSV 文件时收到错误消息</span><span class="sxs-lookup"><span data-stu-id="0ba1c-300">You receive an error message when you upload your schema CSV file</span></span>

<span data-ttu-id="0ba1c-301">请记下错误消息，因为它应包含故障排除信息，指出无法上传架构的原因。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-301">Take note of the error message as it should include troubleshooting information to indicate why the schema couldn't be uploaded.</span></span> <span data-ttu-id="0ba1c-302">根据错误消息中的信息查看和编辑架构 CSV 文件，然后重试。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-302">Review and edit your schema CSV file based on the information in the error message and then try again.</span></span>

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a><span data-ttu-id="0ba1c-303">上传架构 CSV 文件时，收到"错误： InvalidTeamId"错误消息</span><span class="sxs-lookup"><span data-stu-id="0ba1c-303">You receive an "Error: InvalidTeamId" error message when you upload your schema CSV file</span></span>

<span data-ttu-id="0ba1c-304">尝试上传架构 CSV 文件时，收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="0ba1c-304">When you try to upload your schema CSV file, you get the following error message:</span></span>

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

<span data-ttu-id="0ba1c-305">检查以确保在架构 CSV 文件中为团队使用正确的 TeamId。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-305">Check to make sure that you're using the correct TeamId for the team in your schema CSV file.</span></span> <span data-ttu-id="0ba1c-306">TeamId 应与支持团队Microsoft 365组的组 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-306">The TeamId should be the same as the Group ID of the Microsoft 365 group that backs the team.</span></span> <span data-ttu-id="0ba1c-307">可以在管理中心内查找团队的Microsoft Teams ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-307">You can look up the Group ID of the team in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="0ba1c-308">在管理中心左侧导航 [Microsoft Teams，转到](https://admin.teams.microsoft.com/)**"Teams**  >  **管理团队"。**</span><span class="sxs-lookup"><span data-stu-id="0ba1c-308">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams** > **Manage teams**.</span></span>
2. <span data-ttu-id="0ba1c-309">如果表中未显示"组 **ID"** 列，请选择表右上角的"编辑列"，然后打开"组 **ID"。**</span><span class="sxs-lookup"><span data-stu-id="0ba1c-309">If the **Group ID** column isn't displayed in the table, select **Edit columns** in the upper-right corner of the table, and then turn on **Group ID**.</span></span>
3. <span data-ttu-id="0ba1c-310">在列表中查找团队，然后找到"组 ID"。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-310">Find the team in the list, and then locate the Group ID.</span></span>

<span data-ttu-id="0ba1c-311">请确保架构 CSV 文件中 TeamId 与管理中心中显示的组 ID Microsoft Teams ID。</span><span class="sxs-lookup"><span data-stu-id="0ba1c-311">Make sure that the TeamId in your schema CSV file matches the Group ID that's displayed in the Microsoft Teams admin center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ba1c-312">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ba1c-312">Related topics</span></span>

* [<span data-ttu-id="0ba1c-313">在应用程序中管理组织的任务Teams</span><span class="sxs-lookup"><span data-stu-id="0ba1c-313">Manage the Tasks app for your organization in Teams</span></span>](manage-tasks-app.md)
* [<span data-ttu-id="0ba1c-314">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="0ba1c-314">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
