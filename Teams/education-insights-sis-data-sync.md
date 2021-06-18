---
title: 将学生信息系统 (SIS) 数据与教育版见解同步
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 将学生信息系统 (SIS) 数据与 Microsoft Teams 教育版见解同步。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997731"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="4dfb4-103">将学生信息系统 (SIS) 数据与教育版见解同步</span><span class="sxs-lookup"><span data-stu-id="4dfb4-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="4dfb4-104">向[教育版见解](class-insights.md)提供的数据越多，教师就越能更好地为学生提供支持，并且教育领导者也可以为教师提供更好的支持。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="4dfb4-105">若要提供组织级见解，我们必须使用[学校数据同步 (SDS)](/SchoolDataSync) 连接到学生信息系统 (SIS)，以便见解正确映射教育系统的层次结构。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="4dfb4-106">以课堂教师的身份查看课堂级见解 *不* 需要这种同步，因为我们使用 Teams 的课堂结构和权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="4dfb4-107">计划学校数据同步集成</span><span class="sxs-lookup"><span data-stu-id="4dfb4-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="4dfb4-108">Microsoft 学校数据同步系统 (又称 SDS) 提供了学校信息系统 (又称 SIS) 的数据和它的教育系统的层次结构，并映射出哪个用户分配到哪里，还提供了关于学生和组织层次的额外数据。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="4dfb4-109">Insights 在使用 [SDS V2 及以上文件格式](/schooldatasync/sds-v2-csv-file-format) 时效果最佳，但也支持 *功能受限* 的 [SDS V1 文件格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-109">Insights works best when using [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and up, but also supports [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="4dfb4-110">SDS V1 和 V2 文件格式之间的差异</span><span class="sxs-lookup"><span data-stu-id="4dfb4-110">Differences between SDS V1 and V2 file formats</span></span>

<span data-ttu-id="4dfb4-111">若要充分利用见解，建议使用文件格式 v2 或 v2.1 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="4dfb4-111">To get the most out of insights it is recommended to use file format v2 or v2.1 (Coming soon)</span></span>

| <span data-ttu-id="4dfb4-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="4dfb4-112">Data type</span></span> | <span data-ttu-id="4dfb4-113">V1</span><span class="sxs-lookup"><span data-stu-id="4dfb4-113">V1</span></span> | <span data-ttu-id="4dfb4-114">V2</span><span class="sxs-lookup"><span data-stu-id="4dfb4-114">V2</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="4dfb4-115">**用户**</span><span class="sxs-lookup"><span data-stu-id="4dfb4-115">**Users**</span></span> | <span data-ttu-id="4dfb4-116">V1 格式 **仅包含教育工作者**，因此若要为教育领导者设置组织级权限，则需要手动定义每个人的权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-116">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to define each one's permission manually.</span></span> | <span data-ttu-id="4dfb4-117">V2 格式包含 **所有角色**，因此你可以分配基于角色的权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-117">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="4dfb4-118">**组织**</span><span class="sxs-lookup"><span data-stu-id="4dfb4-118">**Orgs**</span></span> | <span data-ttu-id="4dfb4-119">V1 格式 **仅包含学校**，因此你只能看到一个汇总级别（所有学校）。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-119">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="4dfb4-120">你可以使用平面列表来放大特定的学校，但是此列表可能包含大量学校，或者包含难以比较的不同类型的学校（例如小学与中学，或者理工院校与艺术院校）。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-120">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="4dfb4-121">有了层次结构，你可以创建有意义的级别，例如科学或艺术系。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-121">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="4dfb4-122">V2 格式包含 **你所在地区或机构的完整层次结构**，包括大学、学院、院系、校园、区域、课程等。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-122">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs, and so on.</span></span><br/><br/> <span data-ttu-id="4dfb4-123">使用层次结构，你可以按层次结构的各个级别查看相关汇总、快速比较每个级别的组织单位、为特定级别分配权限、按组织级别设置目标等。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-123">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

> [!NOTE]
> <span data-ttu-id="4dfb4-124">自 2021 年 7 月 15 日起，客户将不能使用 v2 文件格式，而需要使用 v2.1 格式，所有未来的升级和新能力将在 v2.1 格式上完成且它将完全向后兼容 v1 文件格式。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-124">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

## <a name="best-practices"></a><span data-ttu-id="4dfb4-125">最佳做法</span><span class="sxs-lookup"><span data-stu-id="4dfb4-125">Best practices</span></span>
<span data-ttu-id="4dfb4-126">借助层次结构以及每个人在该层次结构中的位置的准确映射，Insights 可以为不同类型的教育领导者提供准确数据以及更为精确且相关的见解。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-126">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="4dfb4-127">所提供的细节越多，报告和聚光灯就越有用且越有针对性。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-127">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

<span data-ttu-id="4dfb4-128">下面提供了一些最佳做法来确保 SDS 的顺利部署，以便你的用户能够充分利用 Insights。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-128">Here are some best practices to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="file-format-version-to-ue"></a><span data-ttu-id="4dfb4-129">文件格式版本要 ue</span><span class="sxs-lookup"><span data-stu-id="4dfb4-129">File format version to ue</span></span>
*   <span data-ttu-id="4dfb4-130">使用文件格式 V2.1 (即将推出) 并同步教育版 Insights 使用的可选数据</span><span class="sxs-lookup"><span data-stu-id="4dfb4-130">Use file format V2.1 (coming soon) and sync the optional data used by Education Insights</span></span>

### <a name="users-and-roles"></a><span data-ttu-id="4dfb4-131">用户和角色</span><span class="sxs-lookup"><span data-stu-id="4dfb4-131">Users and Roles</span></span>
*   <span data-ttu-id="4dfb4-132">请确保 **所有用户** 都列出在你提供的文件中并且已同步。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-132">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="4dfb4-133">这包括需要查看其所在组织单位的数据的所有学生和教职员工。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-133">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
    <span data-ttu-id="4dfb4-134">如果你当前只在 SIS 中列出了教师，则将文件上传到 SDS 并同步数据之前，请手动添加其他用户。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-134">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SDS and syncing the data.</span></span>
    <span data-ttu-id="4dfb4-135">Insights 收集的数据仅来自于注册的学生，如果遗漏了某些学生，这将对数据和结论产生误导。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-135">The stats gathered by Insights is only from the registered students, if some students re missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="4dfb4-136">请确保 **提供每个用户的名字和姓氏**。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-136">Make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="4dfb4-137">否则，他们将通过他们的电子邮件地址受到引用，这在报告和聚光灯 (有关于学生活动或表现 Insights 的卡片) 中提供了非最优化的体验。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-137">Otherwise, they will be referenced by their email address, and this provides a non-optimal experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="4dfb4-138">年级/年份必须基于此 [映射列表](#supported-grade-level-values)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-138">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="4dfb4-139">为 **所有学生添加年份/年级** 是非常重要的，这样活动数据就可以通过它进行汇总和过滤。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-139">It's important to **add the year/grade level to all students** so that the activity data can be aggregated and filtered by it.</span></span>    

*   <span data-ttu-id="4dfb4-140">请确保 **将每个用户分配到其相关的组织单位**。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-140">Make sure to **assign each user to their relevant organizational unit**.</span></span> <span data-ttu-id="4dfb4-141">这样，教育版 Insights 就不会在教育版 Inisghts 聚光灯下显示误导性数据。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-141">That way, Education Insights will not show misleading data in the Education Inisghts spotlights.</span></span>

    *   <span data-ttu-id="4dfb4-142">一名学生可以与一个以上的组织单位相关联，例如，注册在一个特殊项目或两个院系的学生。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-142">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="4dfb4-143">如果学生有一个以上的组织单位，请在该学生的用户文件中为每个单位提供一行。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-143">In case the student has more hte one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="4dfb4-144">IT 管理员可以根据组织单位为员工授予权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-144">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="4dfb4-145">**请确保工作人员与正确的单位级别相关联**，以便他们获得他们需要的权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-145">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="4dfb4-146">例如，分配到四所学校的辅导员需要看到这些学校的所有年级; 校长需要看到他们学校的所有课程。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-146">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="4dfb4-147">**该角色至关重要**。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-147">**The role is vital**.</span></span> <span data-ttu-id="4dfb4-148">尽管这是一个封闭列表，但请尝试将[列表](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)中的角色与所上传的每个用户的真实角色进行匹配。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-148">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="4dfb4-149">这将使你能够相应地分配基于角色的权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-149">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="4dfb4-150">例如，为所有校长提供查看其学校中的班级的权限，或授予所有教授查看教职员工的权限。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-150">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="4dfb4-151">组织</span><span class="sxs-lookup"><span data-stu-id="4dfb4-151">Organizations</span></span>

* <span data-ttu-id="4dfb4-152">请确保 **反映组织真实和完整的层次结构**。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-152">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="4dfb4-153">这可以通过手动添加文件来实现。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-153">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="4dfb4-154">在某些情况下，SIS 中未反映此层次结构。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-154">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="4dfb4-155">尽管如此，可能仍有必要按层次结构的每一级查看相关的汇总情况，将权限分配给特定级别，按组织级别设置目标，等等。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-155">Still, it may be necessary  to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by organization level, and so on.</span></span> 

* <span data-ttu-id="4dfb4-156">请确保 **组织树下的所有组织单位都包括学生或班级**，为他们汇总学生数据。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-156">Ensure that **all organization units down the organization tree include students or classes** to aggregate student data for them.</span></span> <span data-ttu-id="4dfb4-157">我们建议学生位于树的最低分支上。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-157">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="4dfb4-158">有关 SDS 部署的详细信息，请访问[规划 SDS](/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-158">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="4dfb4-159">使用 SDS 集成 SIS 数据</span><span class="sxs-lookup"><span data-stu-id="4dfb4-159">Integrate SIS data using SDS</span></span>

<span data-ttu-id="4dfb4-160">Office 365 教育版中提供了学校数据同步 (SDS)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-160">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="4dfb4-161">SDS 从教育机构的学生信息系统 (SIS) 中读取数据，并将其与 Microsoft 的应用程序 (如 Teams) 整合，以实现自动创建在线教室和用户。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-161">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="4dfb4-162">它还将 SIS 数据与 Insights 同步。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-162">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="4dfb4-163">作为 IT 管理员，可以选择仅使用 SDS 进行配置，仅使用 Insights 或两者都使用。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-163">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="4dfb4-164">若要将 SIS 信息与教育版 Insights 同步，请按照 [如何为 Insights 部署 SDS](/schooldatasync/how-to-deploy-sds-for-insights) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-164">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="4dfb4-165">部署 SDS</span><span class="sxs-lookup"><span data-stu-id="4dfb4-165">Deploy SDS</span></span>
<span data-ttu-id="4dfb4-166">**如果你已经在使用 SDS**，我们建议你遵循 [最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-166">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="4dfb4-167">**如果你尚未使用 SDS**，那么现在需要 [部署它](/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-167">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="4dfb4-168">在部署过程中，可以决定是否要使用 SDS 为 Teams 提供用户和类别，或者仅使用它为 Insights 提供用户和组织层次结构。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-168">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="4dfb4-169">如果现在是年中，而且已手动创建了团队，那就只用 SDS 向 Insights 提供用户和组织层次数据，明年再考虑用 SDS 为团队配置用户和类别。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-169">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="4dfb4-170">验证同步过程</span><span class="sxs-lookup"><span data-stu-id="4dfb4-170">Verify the sync process</span></span>
<span data-ttu-id="4dfb4-171">若要验证同步状态进度，请按照 [SDS for Insights 数据运行状况和监视](/schooldatasync/sds-for-insights-data-health-and-monitoring) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-171">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dfb4-172">如果你遇到任何问题，[客户支持](https://aka.ms/edusupport)将为你提供帮助。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-172">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="4dfb4-173">支持的年级值</span><span class="sxs-lookup"><span data-stu-id="4dfb4-173">Supported grade level values</span></span>

<span data-ttu-id="4dfb4-174">在SDS文件中，年级/年份级别定义为枚举值，这意味着只能在CSV文件中提供一组选定的值。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-174">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="4dfb4-175">在同步处理过程中，任何其他指定的值都会导致错误。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-175">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="4dfb4-176">以下部分定义了用户文件中支持的值。</span><span class="sxs-lookup"><span data-stu-id="4dfb4-176">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="4dfb4-177">美国/全球范围内各年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-177">United States / worldwide grade levels</span></span>
|<span data-ttu-id="4dfb4-178">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="4dfb4-178">Value in file (Grade column)</span></span> | <span data-ttu-id="4dfb4-179">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="4dfb4-179">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="4dfb4-180">IT</span><span class="sxs-lookup"><span data-stu-id="4dfb4-180">IT</span></span>|<span data-ttu-id="4dfb4-181">婴幼儿</span><span class="sxs-lookup"><span data-stu-id="4dfb4-181">Infant</span></span>|
|<span data-ttu-id="4dfb4-182">PR</span><span class="sxs-lookup"><span data-stu-id="4dfb4-182">PR</span></span>|<span data-ttu-id="4dfb4-183">学前教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-183">Pre-school</span></span>|
|<span data-ttu-id="4dfb4-184">PK</span><span class="sxs-lookup"><span data-stu-id="4dfb4-184">PK</span></span>|<span data-ttu-id="4dfb4-185">幼儿园前教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-185">Pre-kindergarten</span></span>|
|<span data-ttu-id="4dfb4-186">TK</span><span class="sxs-lookup"><span data-stu-id="4dfb4-186">TK</span></span>|<span data-ttu-id="4dfb4-187">过渡性幼儿园</span><span class="sxs-lookup"><span data-stu-id="4dfb4-187">Transitional Kindergarten</span></span>|
|<span data-ttu-id="4dfb4-188">KG</span><span class="sxs-lookup"><span data-stu-id="4dfb4-188">KG</span></span>|<span data-ttu-id="4dfb4-189">幼儿园</span><span class="sxs-lookup"><span data-stu-id="4dfb4-189">Kindergarten</span></span>|
|<span data-ttu-id="4dfb4-190">01 或 1</span><span class="sxs-lookup"><span data-stu-id="4dfb4-190">01 or 1</span></span>|<span data-ttu-id="4dfb4-191">一年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-191">First grade</span></span>|
|<span data-ttu-id="4dfb4-192">02 或 2</span><span class="sxs-lookup"><span data-stu-id="4dfb4-192">02 or 2</span></span>|<span data-ttu-id="4dfb4-193">第二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-193">Second grade</span></span>|
|<span data-ttu-id="4dfb4-194">03 或 3</span><span class="sxs-lookup"><span data-stu-id="4dfb4-194">03 or 3</span></span>|<span data-ttu-id="4dfb4-195">三年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-195">Third grade</span></span>|
|<span data-ttu-id="4dfb4-196">04 或 4</span><span class="sxs-lookup"><span data-stu-id="4dfb4-196">04 or 4</span></span>|<span data-ttu-id="4dfb4-197">四年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-197">Fourth grade</span></span>|
|<span data-ttu-id="4dfb4-198">05 或 5</span><span class="sxs-lookup"><span data-stu-id="4dfb4-198">05 or 5</span></span>|<span data-ttu-id="4dfb4-199">五年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-199">Fifth grade</span></span>|
|<span data-ttu-id="4dfb4-200">06 或 6</span><span class="sxs-lookup"><span data-stu-id="4dfb4-200">06 or 6</span></span>|<span data-ttu-id="4dfb4-201">六年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-201">Sixth grade</span></span>|
|<span data-ttu-id="4dfb4-202">07 或 7</span><span class="sxs-lookup"><span data-stu-id="4dfb4-202">07 or 7</span></span>|<span data-ttu-id="4dfb4-203">七年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-203">Seventh grade</span></span>|
|<span data-ttu-id="4dfb4-204">08 或 8</span><span class="sxs-lookup"><span data-stu-id="4dfb4-204">08 or 8</span></span>|<span data-ttu-id="4dfb4-205">八年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-205">Eighth grade</span></span>|
|<span data-ttu-id="4dfb4-206">09 或 9</span><span class="sxs-lookup"><span data-stu-id="4dfb4-206">09 or 9</span></span>|<span data-ttu-id="4dfb4-207">九年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-207">Ninth grade</span></span>|
|<span data-ttu-id="4dfb4-208">10</span><span class="sxs-lookup"><span data-stu-id="4dfb4-208">10</span></span>|<span data-ttu-id="4dfb4-209">十年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-209">Tenth grade</span></span>|
|<span data-ttu-id="4dfb4-210">11</span><span class="sxs-lookup"><span data-stu-id="4dfb4-210">11</span></span>|<span data-ttu-id="4dfb4-211">十一年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-211">Eleventh grade</span></span>|
|<span data-ttu-id="4dfb4-212">12</span><span class="sxs-lookup"><span data-stu-id="4dfb4-212">12</span></span>|<span data-ttu-id="4dfb4-213">十二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-213">Twelfth grade</span></span>|
|<span data-ttu-id="4dfb4-214">PS</span><span class="sxs-lookup"><span data-stu-id="4dfb4-214">PS</span></span>|<span data-ttu-id="4dfb4-215">大专</span><span class="sxs-lookup"><span data-stu-id="4dfb4-215">Postsecondary</span></span>|
|<span data-ttu-id="4dfb4-216">PS1</span><span class="sxs-lookup"><span data-stu-id="4dfb4-216">PS1</span></span>|<span data-ttu-id="4dfb4-217">大专新生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-217">Postsecondary freshman</span></span>|
|<span data-ttu-id="4dfb4-218">PS2</span><span class="sxs-lookup"><span data-stu-id="4dfb4-218">PS2</span></span>|<span data-ttu-id="4dfb4-219">大专二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-219">Postsecondary sophomore</span></span>|
|<span data-ttu-id="4dfb4-220">PS3</span><span class="sxs-lookup"><span data-stu-id="4dfb4-220">PS3</span></span>|<span data-ttu-id="4dfb4-221">大专三年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-221">Postsecondary junior</span></span>|
|<span data-ttu-id="4dfb4-222">PS4</span><span class="sxs-lookup"><span data-stu-id="4dfb4-222">PS4</span></span>|<span data-ttu-id="4dfb4-223">大专四年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-223">Postsecondary senior</span></span>|
|<span data-ttu-id="4dfb4-224">本科</span><span class="sxs-lookup"><span data-stu-id="4dfb4-224">undergraduate</span></span>|<span data-ttu-id="4dfb4-225">本科</span><span class="sxs-lookup"><span data-stu-id="4dfb4-225">Undergraduate</span></span>|
|<span data-ttu-id="4dfb4-226">毕业生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-226">graduate</span></span>|<span data-ttu-id="4dfb4-227">毕业生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-227">Graduate</span></span>|
|<span data-ttu-id="4dfb4-228">研究生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-228">postgraduate</span></span>|<span data-ttu-id="4dfb4-229">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="4dfb4-229">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="4dfb4-230">校友</span><span class="sxs-lookup"><span data-stu-id="4dfb4-230">alumni</span></span>|<span data-ttu-id="4dfb4-231">校友</span><span class="sxs-lookup"><span data-stu-id="4dfb4-231">Alumni</span></span>|
|<span data-ttu-id="4dfb4-232">成人教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-232">adultEducation</span></span>|<span data-ttu-id="4dfb4-233">成人教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-233">Adult Education</span></span>|
|<span data-ttu-id="4dfb4-234">UG</span><span class="sxs-lookup"><span data-stu-id="4dfb4-234">UG</span></span>|<span data-ttu-id="4dfb4-235">未分级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-235">Ungraded</span></span>|
|<span data-ttu-id="4dfb4-236">其他</span><span class="sxs-lookup"><span data-stu-id="4dfb4-236">Other</span></span>|<span data-ttu-id="4dfb4-237">其他</span><span class="sxs-lookup"><span data-stu-id="4dfb4-237">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="4dfb4-238">英国各年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-238">United Kingdom year groups</span></span>
|<span data-ttu-id="4dfb4-239">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="4dfb4-239">Value in file (Grade column)</span></span> | <span data-ttu-id="4dfb4-240">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="4dfb4-240">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="4dfb4-241">IT</span><span class="sxs-lookup"><span data-stu-id="4dfb4-241">IT</span></span>|<span data-ttu-id="4dfb4-242">托儿所</span><span class="sxs-lookup"><span data-stu-id="4dfb4-242">Nursery</span></span>|
|<span data-ttu-id="4dfb4-243">PR</span><span class="sxs-lookup"><span data-stu-id="4dfb4-243">PR</span></span>|<span data-ttu-id="4dfb4-244">学前教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-244">Pre-school</span></span>|
|<span data-ttu-id="4dfb4-245">PK</span><span class="sxs-lookup"><span data-stu-id="4dfb4-245">PK</span></span>|<span data-ttu-id="4dfb4-246">接收</span><span class="sxs-lookup"><span data-stu-id="4dfb4-246">Reception</span></span>|
|<span data-ttu-id="4dfb4-247">01 或 1</span><span class="sxs-lookup"><span data-stu-id="4dfb4-247">01 or 1</span></span>|<span data-ttu-id="4dfb4-248">一年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-248">Year 1</span></span>|
|<span data-ttu-id="4dfb4-249">02 或 2</span><span class="sxs-lookup"><span data-stu-id="4dfb4-249">02 or 2</span></span>|<span data-ttu-id="4dfb4-250">二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-250">Year 2</span></span>|
|<span data-ttu-id="4dfb4-251">03 或 3</span><span class="sxs-lookup"><span data-stu-id="4dfb4-251">03 or 3</span></span>|<span data-ttu-id="4dfb4-252">三年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-252">Year 3</span></span>|
|<span data-ttu-id="4dfb4-253">04 或 4</span><span class="sxs-lookup"><span data-stu-id="4dfb4-253">04 or 4</span></span>|<span data-ttu-id="4dfb4-254">四年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-254">Year 4</span></span>|
|<span data-ttu-id="4dfb4-255">05 或 5</span><span class="sxs-lookup"><span data-stu-id="4dfb4-255">05 or 5</span></span>|<span data-ttu-id="4dfb4-256">五年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-256">Year 5</span></span>|
|<span data-ttu-id="4dfb4-257">06 或 6</span><span class="sxs-lookup"><span data-stu-id="4dfb4-257">06 or 6</span></span>|<span data-ttu-id="4dfb4-258">六年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-258">Year 6</span></span>|
|<span data-ttu-id="4dfb4-259">07 或 7</span><span class="sxs-lookup"><span data-stu-id="4dfb4-259">07 or 7</span></span>|<span data-ttu-id="4dfb4-260">七年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-260">Year 7</span></span>|
|<span data-ttu-id="4dfb4-261">08 或 8</span><span class="sxs-lookup"><span data-stu-id="4dfb4-261">08 or 8</span></span>|<span data-ttu-id="4dfb4-262">八年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-262">Year 8</span></span>|
|<span data-ttu-id="4dfb4-263">09 或 9</span><span class="sxs-lookup"><span data-stu-id="4dfb4-263">09 or 9</span></span>|<span data-ttu-id="4dfb4-264">九年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-264">Year 9</span></span>|
|<span data-ttu-id="4dfb4-265">10</span><span class="sxs-lookup"><span data-stu-id="4dfb4-265">10</span></span>|<span data-ttu-id="4dfb4-266">十年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-266">Year 10</span></span>|
|<span data-ttu-id="4dfb4-267">11</span><span class="sxs-lookup"><span data-stu-id="4dfb4-267">11</span></span>|<span data-ttu-id="4dfb4-268">十一年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-268">Year 11</span></span>|
|<span data-ttu-id="4dfb4-269">12</span><span class="sxs-lookup"><span data-stu-id="4dfb4-269">12</span></span>|<span data-ttu-id="4dfb4-270">十二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-270">Year 12</span></span>|
|<span data-ttu-id="4dfb4-271">13</span><span class="sxs-lookup"><span data-stu-id="4dfb4-271">13</span></span>|<span data-ttu-id="4dfb4-272">十三年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-272">Year 13</span></span>|
|<span data-ttu-id="4dfb4-273">PS</span><span class="sxs-lookup"><span data-stu-id="4dfb4-273">PS</span></span>|<span data-ttu-id="4dfb4-274">大专</span><span class="sxs-lookup"><span data-stu-id="4dfb4-274">Postsecondary</span></span>|
|<span data-ttu-id="4dfb4-275">PS1</span><span class="sxs-lookup"><span data-stu-id="4dfb4-275">PS1</span></span>|<span data-ttu-id="4dfb4-276">大专一年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-276">Postsecondary Year 1</span></span>|
|<span data-ttu-id="4dfb4-277">PS2</span><span class="sxs-lookup"><span data-stu-id="4dfb4-277">PS2</span></span>|<span data-ttu-id="4dfb4-278">大专二年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-278">Postsecondary Year 2</span></span>|
|<span data-ttu-id="4dfb4-279">PS3</span><span class="sxs-lookup"><span data-stu-id="4dfb4-279">PS3</span></span>|<span data-ttu-id="4dfb4-280">大专三年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-280">Postsecondary Year 3</span></span>|
|<span data-ttu-id="4dfb4-281">PS4</span><span class="sxs-lookup"><span data-stu-id="4dfb4-281">PS4</span></span>|<span data-ttu-id="4dfb4-282">大专四年级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-282">Postsecondary Year 4</span></span>|
|<span data-ttu-id="4dfb4-283">本科</span><span class="sxs-lookup"><span data-stu-id="4dfb4-283">undergraduate</span></span>|<span data-ttu-id="4dfb4-284">本科</span><span class="sxs-lookup"><span data-stu-id="4dfb4-284">Undergraduate</span></span>|
|<span data-ttu-id="4dfb4-285">毕业生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-285">graduate</span></span>|<span data-ttu-id="4dfb4-286">毕业生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-286">Graduate</span></span>|
|<span data-ttu-id="4dfb4-287">研究生</span><span class="sxs-lookup"><span data-stu-id="4dfb4-287">postgraduate</span></span>|<span data-ttu-id="4dfb4-288">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="4dfb4-288">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="4dfb4-289">校友</span><span class="sxs-lookup"><span data-stu-id="4dfb4-289">alumni</span></span>|<span data-ttu-id="4dfb4-290">校友</span><span class="sxs-lookup"><span data-stu-id="4dfb4-290">Alumni</span></span>|
|<span data-ttu-id="4dfb4-291">成人教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-291">adultEducation</span></span>|<span data-ttu-id="4dfb4-292">成人教育</span><span class="sxs-lookup"><span data-stu-id="4dfb4-292">Adult Education</span></span>|
|<span data-ttu-id="4dfb4-293">UG</span><span class="sxs-lookup"><span data-stu-id="4dfb4-293">UG</span></span>|<span data-ttu-id="4dfb4-294">未分级</span><span class="sxs-lookup"><span data-stu-id="4dfb4-294">Ungraded</span></span>|
|<span data-ttu-id="4dfb4-295">其他</span><span class="sxs-lookup"><span data-stu-id="4dfb4-295">Other</span></span>|<span data-ttu-id="4dfb4-296">其他</span><span class="sxs-lookup"><span data-stu-id="4dfb4-296">Other</span></span>|

