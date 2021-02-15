---
title: 管理用户对教育版 Insights 的访问权限
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 管理用户对 Microsoft Teams 中的教育版 Insights 的访问权限。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145930"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="ed531-103">管理用户对教育版 Insights 的访问权限</span><span class="sxs-lookup"><span data-stu-id="ed531-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="ed531-104">本文档提供了管理用户对 [Microsoft Teams 中的教育版 Insights](class-insights.md) 的访问权限所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="ed531-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="ed531-105">你需要为教育领导者、地区领导、学校校长、班主任、辅导员、学区主管、项目主管、社会工作者和心理学家提供权限。</span><span class="sxs-lookup"><span data-stu-id="ed531-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="ed531-106">如果教师拥有课堂团队，则会 *自动* 获得权限。</span><span class="sxs-lookup"><span data-stu-id="ed531-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="ed531-107">若要提供组织级 Insights，你必须[从学生信息系统 (SIS) 导入数据](education-insights-sis-data-sync.md)，以便 Insights 正确映射教育系统的层次结构。</span><span class="sxs-lookup"><span data-stu-id="ed531-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="ed531-108">只有全局管理员才能管理用户对 Insights 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ed531-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="ed531-109">我们建议为所有教育领导者启用 Insights，以便他们能够获得了解每所学校所需的数据，并能够快速发现问题并为其教师提供支持。</span><span class="sxs-lookup"><span data-stu-id="ed531-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="ed531-110">即使你只是进行试点，为所有教育领导者启用 Insights 也仍然可能很有用，但这只针对试点用户组的通信。</span><span class="sxs-lookup"><span data-stu-id="ed531-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="ed531-111">授予权限</span><span class="sxs-lookup"><span data-stu-id="ed531-111">Grant permissions</span></span>

* <span data-ttu-id="ed531-112">打开 Insights 应用，单击“**设置**”，然后选择“**用户权限**”</span><span class="sxs-lookup"><span data-stu-id="ed531-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="设置":::

* <span data-ttu-id="ed531-114">选择“**添加用户**”。</span><span class="sxs-lookup"><span data-stu-id="ed531-114">Select **Add users**.</span></span>
* <span data-ttu-id="ed531-115">输入每个用户的用户名或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ed531-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="ed531-116">选择权限级别：</span><span class="sxs-lookup"><span data-stu-id="ed531-116">Select the permission level:</span></span>
  * <span data-ttu-id="ed531-117">**对所有组织的访问权限** 意味着用户将能够看到所有级别的组织单位。</span><span class="sxs-lookup"><span data-stu-id="ed531-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="ed531-118">**对特定学校的访问权限** 意味着用户将能够看到所选学校。</span><span class="sxs-lookup"><span data-stu-id="ed531-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="ed531-119">开始键入，然后从列表中选择相应学校。</span><span class="sxs-lookup"><span data-stu-id="ed531-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="ed531-120">你可以将多所学校添加到一起。</span><span class="sxs-lookup"><span data-stu-id="ed531-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="ed531-121">单击“**添加新用户**”。</span><span class="sxs-lookup"><span data-stu-id="ed531-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="授予权限":::

> [!NOTE]
> <span data-ttu-id="ed531-123">仅向需要的教育领导者和他们负责的组织单位提供权限。</span><span class="sxs-lookup"><span data-stu-id="ed531-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="ed531-124">如果你不确定是否需要特定组织的用户权限，请咨询机构的隐私主题专家，例如法律或人事部门人员。</span><span class="sxs-lookup"><span data-stu-id="ed531-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="ed531-125">编辑权限</span><span class="sxs-lookup"><span data-stu-id="ed531-125">Edit permissions</span></span>
* <span data-ttu-id="ed531-126">选择特定用户，然后选择“**编辑权限**”。</span><span class="sxs-lookup"><span data-stu-id="ed531-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="ed531-127">更新权限级别或学校列表，然后单击“**更新权限**”。</span><span class="sxs-lookup"><span data-stu-id="ed531-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="编辑权限":::

## <a name="remove-permissions"></a><span data-ttu-id="ed531-129">删除权限</span><span class="sxs-lookup"><span data-stu-id="ed531-129">Remove permissions</span></span>
* <span data-ttu-id="ed531-130">选择要删除的用户，然后选择“**删除用户**”。</span><span class="sxs-lookup"><span data-stu-id="ed531-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="ed531-131">这些用户将不再有权访问组织级 Insights，但如果他们拥有课堂团队，则将仍然有权访问课堂级 Insights。</span><span class="sxs-lookup"><span data-stu-id="ed531-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="删除权限":::
