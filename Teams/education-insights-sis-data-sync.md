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
ms.openlocfilehash: 8f6d4a7dca340d297543abb3620a36cdd804ca9f
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196576"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="d6052-103">将学生信息系统 (SIS) 数据与教育版见解同步</span><span class="sxs-lookup"><span data-stu-id="d6052-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="d6052-104">向[教育版见解](class-insights.md)提供的数据越多，教师就越能更好地为学生提供支持，并且教育领导者也可以为教师提供更好的支持。</span><span class="sxs-lookup"><span data-stu-id="d6052-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="d6052-105">若要提供组织级见解，我们必须使用[学校数据同步 (SDS)](https://docs.microsoft.com/SchoolDataSync) 连接到学生信息系统 (SIS)，以便见解正确映射教育系统的层次结构。</span><span class="sxs-lookup"><span data-stu-id="d6052-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="d6052-106">以课堂教师的身份查看课堂级见解 *不* 需要这种同步，因为我们使用 Teams 的课堂结构和权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-sis-integration"></a><span data-ttu-id="d6052-107">规划 SIS 集成</span><span class="sxs-lookup"><span data-stu-id="d6052-107">Plan your SIS integration</span></span>
<span data-ttu-id="d6052-108">SIS 数据提供教育系统的层次结构，并映射在何处分配了哪个用户。</span><span class="sxs-lookup"><span data-stu-id="d6052-108">The SIS data provides the hierarchical structure of the educational system and maps which user is assigned where.</span></span>

<span data-ttu-id="d6052-109">使用 [SDS V2 文件格式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)时，见解效果最佳，但也支持功能 *受限* 的 [SDS V1](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) 文件格式。</span><span class="sxs-lookup"><span data-stu-id="d6052-109">Insights works best when using [SDS V2 file format](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format) but also supports [SDS V1 file format](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) with *limited* functionality.</span></span>

### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="d6052-110">SDS V1 和 V2 文件格式之间的差异</span><span class="sxs-lookup"><span data-stu-id="d6052-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="d6052-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="d6052-111">Data type</span></span> |   <span data-ttu-id="d6052-112">V1</span><span class="sxs-lookup"><span data-stu-id="d6052-112">V1</span></span> | <span data-ttu-id="d6052-113">V2（向新客户推荐）</span><span class="sxs-lookup"><span data-stu-id="d6052-113">V2 (recommended for new customers)</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="d6052-114">**用户**</span><span class="sxs-lookup"><span data-stu-id="d6052-114">**Users**</span></span> | <span data-ttu-id="d6052-115">V1 格式 **仅包含教师**,，因此若要为教育领导者设置组织级别的权限，你需要搜索他们并手动定义每个人的权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-115">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to search for them and define each one's permission manually.</span></span> | <span data-ttu-id="d6052-116">V2 格式包含 **所有角色**，因此你可以分配基于角色的权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-116">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="d6052-117">**组织**</span><span class="sxs-lookup"><span data-stu-id="d6052-117">**Orgs**</span></span> | <span data-ttu-id="d6052-118">V1 格式 **仅包含学校**，因此你只能看到一个汇总级别（所有学校）。</span><span class="sxs-lookup"><span data-stu-id="d6052-118">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="d6052-119">你可以使用平面列表来放大特定的学校，但是此列表可能包含大量学校，或者包含难以比较的不同类型的学校（例如小学与中学，或者理工院校与艺术院校）。</span><span class="sxs-lookup"><span data-stu-id="d6052-119">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="d6052-120">有了层次结构，你可以创建有意义的级别，例如科学或艺术系。</span><span class="sxs-lookup"><span data-stu-id="d6052-120">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="d6052-121">V2 格式包含 **你所在地区或机构的完整层次结构**，包括大学、学院、院系、校园、区域、课程等。</span><span class="sxs-lookup"><span data-stu-id="d6052-121">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs, and so on.</span></span><br/><br/> <span data-ttu-id="d6052-122">使用层次结构，你可以按层次结构的各个级别查看相关汇总、快速比较每个级别的组织单位、为特定级别分配权限、按组织级别设置目标等。</span><span class="sxs-lookup"><span data-stu-id="d6052-122">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

### <a name="type-of-data-required"></a><span data-ttu-id="d6052-123">所需的数据类型</span><span class="sxs-lookup"><span data-stu-id="d6052-123">Type of data required</span></span>
<span data-ttu-id="d6052-124">下表提供了充分利用见解所需的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d6052-124">The following table provides the type of data required to get the best out of Insights.</span></span>

| <span data-ttu-id="d6052-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="d6052-125">Data type</span></span> | <span data-ttu-id="d6052-126">所需数据的示例</span><span class="sxs-lookup"><span data-stu-id="d6052-126">Examples for what you need to provide</span></span>|<span data-ttu-id="d6052-127">为什么它很重要？</span><span class="sxs-lookup"><span data-stu-id="d6052-127">Why it's important?</span></span>|
|:--- |:--- |:--- |
| <span data-ttu-id="d6052-128">**用户**</span><span class="sxs-lookup"><span data-stu-id="d6052-128">**Users**</span></span> |   <span data-ttu-id="d6052-129">角色（如学生）</span><span class="sxs-lookup"><span data-stu-id="d6052-129">Role (such as student)</span></span><br/> <span data-ttu-id="d6052-130">[年级/年份级别](#supported-grade-level-values)（如 10）</span><span class="sxs-lookup"><span data-stu-id="d6052-130">[Grade/Year level](#supported-grade-level-values) (such as 10)</span></span><br/> <span data-ttu-id="d6052-131">组织（名称）</span><span class="sxs-lookup"><span data-stu-id="d6052-131">Org (name)</span></span> | <span data-ttu-id="d6052-132">如果正确为每个人员分配其角色、年级和组织，则我们可确保汇总正确无误。</span><span class="sxs-lookup"><span data-stu-id="d6052-132">When we correctly assign each person to their role, grade/year level, and organization, we can ensure that the summaries and aggregations are correct.</span></span>|
| <span data-ttu-id="d6052-133">**组织**</span><span class="sxs-lookup"><span data-stu-id="d6052-133">**Orgs**</span></span> | <span data-ttu-id="d6052-134">组织类型（如大学）</span><span class="sxs-lookup"><span data-stu-id="d6052-134">Org type (such as college)</span></span> |   <span data-ttu-id="d6052-135">此处的层次结构非常重要。</span><span class="sxs-lookup"><span data-stu-id="d6052-135">The hierarchy here is important.</span></span> <span data-ttu-id="d6052-136">例如，学校可能属于某各地区，该地区可能属于某个州/省。</span><span class="sxs-lookup"><span data-stu-id="d6052-136">For example, schools may belong to a district, and that district may belong to a state.</span></span><br/> <span data-ttu-id="d6052-137">当允许地区教育领导者查看数据时，仅适用于该地区的学校。</span><span class="sxs-lookup"><span data-stu-id="d6052-137">When a district education leader is permitted to see data, it's only for the schools in that district.</span></span>|
| <span data-ttu-id="d6052-138">**班级**</span><span class="sxs-lookup"><span data-stu-id="d6052-138">**Classes**</span></span> | <span data-ttu-id="d6052-139">标题（如计算机科学 101）</span><span class="sxs-lookup"><span data-stu-id="d6052-139">Title (such as Computer science 101)</span></span> | <span data-ttu-id="d6052-140">该表详细说明了组织所举办的课程。</span><span class="sxs-lookup"><span data-stu-id="d6052-140">This table details which classes are held in the organization.</span></span> <span data-ttu-id="d6052-141">该表必须正确映射，以便我们能够把学生分配到正确的班级。</span><span class="sxs-lookup"><span data-stu-id="d6052-141">This table must be correctly mapped so that we can assign the student to the correct class.</span></span> |
| <span data-ttu-id="d6052-142">**注册**</span><span class="sxs-lookup"><span data-stu-id="d6052-142">**Enrollment**</span></span> | <span data-ttu-id="d6052-143">角色（如学生）</span><span class="sxs-lookup"><span data-stu-id="d6052-143">Role (such as student)</span></span> | <span data-ttu-id="d6052-144">该表是为学生和教育工作者准备的，以便让我们知道他们所注册的班级。</span><span class="sxs-lookup"><span data-stu-id="d6052-144">This table is for students and educators and enables us to know in which class they are registered.</span></span> |

> [!NOTE]
> <span data-ttu-id="d6052-145">在部署过程中，你可以决定是要使用 SDS 在 Teams 中预配用户和班级，还是仅使用 SDS 来向见解提供数据。</span><span class="sxs-lookup"><span data-stu-id="d6052-145">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d6052-146">最佳做法</span><span class="sxs-lookup"><span data-stu-id="d6052-146">Best practices</span></span>
<span data-ttu-id="d6052-147">借助层次结构以及每个人在该层次结构中的位置的准确映射，Insights 可以为不同类型的教育领导者提供准确数据以及更为精确且相关的见解。</span><span class="sxs-lookup"><span data-stu-id="d6052-147">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="d6052-148">你在此处提供的详细信息越多，报告和聚光灯就越有用且越相关。</span><span class="sxs-lookup"><span data-stu-id="d6052-148">The more detail you provide here, the better and more relevant the reports and spotlights will be.</span></span>
<span data-ttu-id="d6052-149">下面提供了一些最佳做法来确保 SDS 的顺利部署，以便你的用户能够充分利用 Insights。</span><span class="sxs-lookup"><span data-stu-id="d6052-149">Here are some best practices to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="users"></a><span data-ttu-id="d6052-150">用户</span><span class="sxs-lookup"><span data-stu-id="d6052-150">Users</span></span>
*   <span data-ttu-id="d6052-151">请确保 *所有用户* 都列出在你提供的文件中并且已同步。</span><span class="sxs-lookup"><span data-stu-id="d6052-151">Make sure *all users* are listed in the files you provide and synced.</span></span> <span data-ttu-id="d6052-152">这包括需要查看其所在组织单位的数据的所有学生和教职员工。</span><span class="sxs-lookup"><span data-stu-id="d6052-152">This includes all students and staff that need to see data for the organizational units they cover.</span></span>

    <span data-ttu-id="d6052-153">如果你当前只在 SIS 中列出了教师，则将文件上传到 SIS 并同步数据之前，请手动添加其他用户。</span><span class="sxs-lookup"><span data-stu-id="d6052-153">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SIS and syncing the data.</span></span>

    <span data-ttu-id="d6052-154">如果缺少部分学生，则见解将仅从已注册的学生收集统计信息，这会使数据和结论引起误导。</span><span class="sxs-lookup"><span data-stu-id="d6052-154">If some students are missing, the stats gathered by Insights is only from the registered students, and that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="d6052-155">请确保 *提供每个用户的名字和姓氏*。</span><span class="sxs-lookup"><span data-stu-id="d6052-155">Make sure to *provide the first and last name of each user*.</span></span> <span data-ttu-id="d6052-156">如果未提供，则将引用用户的电子邮件地址，这会使报告和聚光灯（包含学生活动或表现见解的卡片）提供一种不太积极的体验。</span><span class="sxs-lookup"><span data-stu-id="d6052-156">If not, they are referenced by their email address, and this provides a less than positive experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="d6052-157">*必须为年级输入 2 位数字*（例如，7 年级为 07）。</span><span class="sxs-lookup"><span data-stu-id="d6052-157">The *grade/year level must be input as 2 digits* (for example, 07 for Year 7).</span></span> <span data-ttu-id="d6052-158">查看[映射列表](#supported-grade-level-values)。</span><span class="sxs-lookup"><span data-stu-id="d6052-158">Check out the [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="d6052-159">*为所有学生添加年级* 以便年级可以筛选数据，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="d6052-159">It's important to *add the year/grade level to all students* so that a grade/year level can filter the data.</span></span>    

*   <span data-ttu-id="d6052-160">请确保 *将每个用户分配到其相关的组织单位*。</span><span class="sxs-lookup"><span data-stu-id="d6052-160">Make sure to *assign each user to their relevant organizational unit*.</span></span> <span data-ttu-id="d6052-161">这样，我们不会基于每个单位的汇总数据在聚光灯下显示误导性数据。</span><span class="sxs-lookup"><span data-stu-id="d6052-161">In this way, we won't show misleading data in our spotlights based on aggregated data for each unit.</span></span>

    *   <span data-ttu-id="d6052-162">一名学生可以与多个组织单位相关联，例如，在特别课程或两个院系中注册的学生。</span><span class="sxs-lookup"><span data-stu-id="d6052-162">A student can be associated with more than one org unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="d6052-163">在这种情况下，请在该学生的用户文件中提供两行内容 - 每个组织一行。</span><span class="sxs-lookup"><span data-stu-id="d6052-163">In such a case, provide two lines in the users file for that student – one for each organization.</span></span>
    
    *   <span data-ttu-id="d6052-164">根据教职员工的组织单位，你可定义相关权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-164">Based on the org unit for staff, you will be able to define the relevant permissions.</span></span> <span data-ttu-id="d6052-165">确保他们与正确的单位级别相关联，以便获得所需的权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-165">Make sure they are associated with the correct unit level, so they receive the permissions they need.</span></span> <span data-ttu-id="d6052-166">例如，分配给四所学校的辅导员需要查看这些学校的所有课程；校长需要看其学校的所有班级。</span><span class="sxs-lookup"><span data-stu-id="d6052-166">For example, a counselor assigned to four schools needs to see all the classes in these schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="d6052-167">该角色非常重要。</span><span class="sxs-lookup"><span data-stu-id="d6052-167">The role is vital.</span></span> <span data-ttu-id="d6052-168">尽管这是一个封闭列表，但请尝试将[列表](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)中的角色与所上传的每个用户的真实角色进行匹配。</span><span class="sxs-lookup"><span data-stu-id="d6052-168">Although this list is closed, try to match the role from [the list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="d6052-169">这样，你就可以相应地分配基于角色的权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-169">In this way, you can assign role-based permissions accordingly.</span></span> <span data-ttu-id="d6052-170">例如，为所有校长提供查看其学校中的班级的权限，或授予所有教授查看教职员工的权限。</span><span class="sxs-lookup"><span data-stu-id="d6052-170">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="d6052-171">组织</span><span class="sxs-lookup"><span data-stu-id="d6052-171">Organizations</span></span>

* <span data-ttu-id="d6052-172">请确保 *反映组织的真实层次结构*。</span><span class="sxs-lookup"><span data-stu-id="d6052-172">Make sure to *reflect the real hierarchy of your organization*.</span></span> <span data-ttu-id="d6052-173">这可以通过手动添加文件来实现。</span><span class="sxs-lookup"><span data-stu-id="d6052-173">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="d6052-174">在某些情况下，SIS 中未反映此层次结构。</span><span class="sxs-lookup"><span data-stu-id="d6052-174">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="d6052-175">但是，在这里仍可能需要按层次结构的各个级别查看相关汇总、为特定级别分配权限、按组织级别设置目标等。</span><span class="sxs-lookup"><span data-stu-id="d6052-175">Still, it may be necessary here to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by org level, and so on.</span></span> 

* <span data-ttu-id="d6052-176">确保 *组织树下的所有组织单位都包括学生或班级*，以汇总学生数据。</span><span class="sxs-lookup"><span data-stu-id="d6052-176">Ensure that *all org units down the org tree include students or classes* to aggregate student data for them.</span></span> <span data-ttu-id="d6052-177">我们建议学生位于树的最低分支上。</span><span class="sxs-lookup"><span data-stu-id="d6052-177">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="d6052-178">有关 SDS 部署的详细信息，请访问[规划 SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="d6052-178">For more details about SDS deployment, visit [Planning SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-using-sds"></a><span data-ttu-id="d6052-179">使用 SDS 集成 SIS</span><span class="sxs-lookup"><span data-stu-id="d6052-179">Integrate SIS using SDS</span></span>

<span data-ttu-id="d6052-180">Office 365 教育版中提供了学校数据同步 (SDS)。</span><span class="sxs-lookup"><span data-stu-id="d6052-180">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="d6052-181">SDS 将读取教育机构的学生信息系统 (SIS) 数据，并将其与 Teams 集成，以便自动创建在线课堂和用户。</span><span class="sxs-lookup"><span data-stu-id="d6052-181">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="d6052-182">它还将 SIS 数据与见解同步。</span><span class="sxs-lookup"><span data-stu-id="d6052-182">It also synchronizes the SIS data with Insights.</span></span>

### <a name="sync-with-insights"></a><span data-ttu-id="d6052-183">与见解同步</span><span class="sxs-lookup"><span data-stu-id="d6052-183">Sync with Insights</span></span>

<span data-ttu-id="d6052-184">首先，需要打开“见解”开关，以开始同步过程。</span><span class="sxs-lookup"><span data-stu-id="d6052-184">First, you need to turn the Insights toggle on to start the sync process.</span></span>

* <span data-ttu-id="d6052-185">在 [**SDS 门户**](https://sds.microsoft.com)上，进入 **设置**，向下滚动到 **收集数据以了解情况**，并检查其是否已启用（默认情况下已 *启用*）。</span><span class="sxs-lookup"><span data-stu-id="d6052-185">On the [**SDS portal**](https://sds.microsoft.com), go to **Settings**, scroll down to **Collect data for Insights**, and check that it's enabled (it's turned *on* by default).</span></span>

* <span data-ttu-id="d6052-186">向下滚动到下一个开关“**从 SDS 同步组织数据(预览)**”，然后打开它。</span><span class="sxs-lookup"><span data-stu-id="d6052-186">Scroll down to the next switch, **Sync organizational data from SDS (preview)**, and turn on.</span></span>

<span data-ttu-id="d6052-187">如果你在“设置”页面上未看到“*从 SDS 同步组织数据(预览)*”选项，请转到 [注册页面](https://aka.ms/insights/join)以提供你的信息，团队成员随后会与你联系。</span><span class="sxs-lookup"><span data-stu-id="d6052-187">If you do not see the option for *Sync organizational data from SDS (preview)* on the Settings page, go to the [sign-up page](https://aka.ms/insights/join) to provide your information, and a team member will reach out to you.</span></span>

:::image type="content" source="media/insights-sds-settings.png" alt-text="“与见解同步”开关":::

### <a name="deploy-sds"></a><span data-ttu-id="d6052-189">部署 SDS</span><span class="sxs-lookup"><span data-stu-id="d6052-189">Deploy SDS</span></span>
<span data-ttu-id="d6052-190">**如果你已经在使用 SDS**，我们建议你遵循 [最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="d6052-190">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="d6052-191">若要将当前配置文件与见解同步，请转到“**同步配置文件**”，单击“**编辑**”，然后选择“**同步到见解**”。</span><span class="sxs-lookup"><span data-stu-id="d6052-191">To sync your current profiles with Insights, go to your **Sync Profile(s)**, click **Edit**, and select **Sync to Insights**.</span></span> <span data-ttu-id="d6052-192">对于初始同步，我们建议在从 SIS 刷新数据后等待 24 小时，以便报告可用。</span><span class="sxs-lookup"><span data-stu-id="d6052-192">For the initial sync, we recommend waiting 24 hours for the reports to be available after the data is refreshed from your SIS.</span></span>  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="与见解同步配置文件开关":::

<span data-ttu-id="d6052-194">**如果你尚未使用 SDS**，那么现在需要 [部署它](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="d6052-194">**If you don't use SDS yet**, you now need to [deploy it](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="d6052-195">在部署过程中，你可以决定是要使用 SDS 在 Teams 中预配用户和班级，还是仅使用 SDS 来向见解提供数据。</span><span class="sxs-lookup"><span data-stu-id="d6052-195">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="d6052-196">如果现在是年中，并且你已经手动创建团队，则仅使用 SDS 将数据提供给见解，明年再考虑使用 SDS 在 Teams 中预配用户和班级。</span><span class="sxs-lookup"><span data-stu-id="d6052-196">If it's the middle of the year and you already created teams manually, use SDS only to provide the data to Insights, and next year consider to use SDS for provisioning users and classes in Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="d6052-197">验证同步过程</span><span class="sxs-lookup"><span data-stu-id="d6052-197">Verify the sync process</span></span>
<span data-ttu-id="d6052-198">“设置”页面上的“从 SDS 同步组织数据（预览）”旁边将显示一个新的状态区域。</span><span class="sxs-lookup"><span data-stu-id="d6052-198">A new status area appears next to Sync organizational data from SDS (preview) on the Settings page.</span></span>
 
*   <span data-ttu-id="d6052-199">如果状态为 **进行中**，则需在部署 SDS 配置文件后等待最多不超过 24 小时。</span><span class="sxs-lookup"><span data-stu-id="d6052-199">If the status is **In progress**, wait up to 24 hours after deployment of the SDS profile.</span></span>

*   <span data-ttu-id="d6052-200">如果状态为“**已完成**”，那么恭喜你，你可以在组织级别查看见解，然后继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="d6052-200">If the status is **Completed**, congratulations, you can see Insights at the organizational level, and continue to the next step.</span></span>

*   <span data-ttu-id="d6052-201">如果状态为“**已完成但出现错误**”、“**已完成但出现警告**”或“**已中止**”，请下载包含最新同步的错误和警告的日志文件，并检查是否可以修复这些错误。</span><span class="sxs-lookup"><span data-stu-id="d6052-201">If the status is **Completed with errors**, **Completed with warnings**, or **Aborted**, download the log file that contains the errors and warnings for the latest sync and check if you can fix these errors.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d6052-202">如果你遇到任何问题，[客户支持](https://aka.ms/edusupport)将为你提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d6052-202">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="d6052-203">支持的年级值</span><span class="sxs-lookup"><span data-stu-id="d6052-203">Supported grade level values</span></span>

<span data-ttu-id="d6052-204">在SDS文件中，年级/年份级别定义为枚举值，这意味着只能在CSV文件中提供一组选定的值。</span><span class="sxs-lookup"><span data-stu-id="d6052-204">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="d6052-205">在同步处理过程中，任何其他指定的值都会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d6052-205">Anything other than values specified will result in an error during sync processing.</span></span>

> [!NOTE]
> <span data-ttu-id="d6052-206">*年级/年份必须输入 2 位数字*（例如，7 年级为 07）。</span><span class="sxs-lookup"><span data-stu-id="d6052-206">The *grade/year level must be input as 2 digits* (for example, 07 for Year 7).</span></span>

<span data-ttu-id="d6052-207">以下部分定义了用户文件中支持的值。</span><span class="sxs-lookup"><span data-stu-id="d6052-207">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="d6052-208">美国/全球范围内各年级</span><span class="sxs-lookup"><span data-stu-id="d6052-208">United States / worldwide grade levels</span></span>
|<span data-ttu-id="d6052-209">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="d6052-209">Value in file (Grade column)</span></span> | <span data-ttu-id="d6052-210">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="d6052-210">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="d6052-211">IT</span><span class="sxs-lookup"><span data-stu-id="d6052-211">IT</span></span>|<span data-ttu-id="d6052-212">婴幼儿</span><span class="sxs-lookup"><span data-stu-id="d6052-212">Infant</span></span>|
|<span data-ttu-id="d6052-213">PR</span><span class="sxs-lookup"><span data-stu-id="d6052-213">PR</span></span>|<span data-ttu-id="d6052-214">学前教育</span><span class="sxs-lookup"><span data-stu-id="d6052-214">Pre-school</span></span>|
|<span data-ttu-id="d6052-215">PK</span><span class="sxs-lookup"><span data-stu-id="d6052-215">PK</span></span>|<span data-ttu-id="d6052-216">幼儿园前教育</span><span class="sxs-lookup"><span data-stu-id="d6052-216">Pre-kindergarten</span></span>|
|<span data-ttu-id="d6052-217">TK</span><span class="sxs-lookup"><span data-stu-id="d6052-217">TK</span></span>|<span data-ttu-id="d6052-218">过渡性幼儿园</span><span class="sxs-lookup"><span data-stu-id="d6052-218">Transitional Kindergarten</span></span>|
|<span data-ttu-id="d6052-219">KG</span><span class="sxs-lookup"><span data-stu-id="d6052-219">KG</span></span>|<span data-ttu-id="d6052-220">幼儿园</span><span class="sxs-lookup"><span data-stu-id="d6052-220">Kindergarten</span></span>|
|<span data-ttu-id="d6052-221">01</span><span class="sxs-lookup"><span data-stu-id="d6052-221">01</span></span>|<span data-ttu-id="d6052-222">一年级</span><span class="sxs-lookup"><span data-stu-id="d6052-222">First grade</span></span>|
|<span data-ttu-id="d6052-223">02</span><span class="sxs-lookup"><span data-stu-id="d6052-223">02</span></span>|<span data-ttu-id="d6052-224">第二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-224">Second grade</span></span>|
|<span data-ttu-id="d6052-225">03</span><span class="sxs-lookup"><span data-stu-id="d6052-225">03</span></span>|<span data-ttu-id="d6052-226">三年级</span><span class="sxs-lookup"><span data-stu-id="d6052-226">Third grade</span></span>|
|<span data-ttu-id="d6052-227">04</span><span class="sxs-lookup"><span data-stu-id="d6052-227">04</span></span>|<span data-ttu-id="d6052-228">四年级</span><span class="sxs-lookup"><span data-stu-id="d6052-228">Fourth grade</span></span>|
|<span data-ttu-id="d6052-229">05</span><span class="sxs-lookup"><span data-stu-id="d6052-229">05</span></span>|<span data-ttu-id="d6052-230">五年级</span><span class="sxs-lookup"><span data-stu-id="d6052-230">Fifth grade</span></span>|
|<span data-ttu-id="d6052-231">06</span><span class="sxs-lookup"><span data-stu-id="d6052-231">06</span></span>|<span data-ttu-id="d6052-232">六年级</span><span class="sxs-lookup"><span data-stu-id="d6052-232">Sixth grade</span></span>|
|<span data-ttu-id="d6052-233">07</span><span class="sxs-lookup"><span data-stu-id="d6052-233">07</span></span>|<span data-ttu-id="d6052-234">七年级</span><span class="sxs-lookup"><span data-stu-id="d6052-234">Seventh grade</span></span>|
|<span data-ttu-id="d6052-235">08</span><span class="sxs-lookup"><span data-stu-id="d6052-235">08</span></span>|<span data-ttu-id="d6052-236">八年级</span><span class="sxs-lookup"><span data-stu-id="d6052-236">Eighth grade</span></span>|
|<span data-ttu-id="d6052-237">09</span><span class="sxs-lookup"><span data-stu-id="d6052-237">09</span></span>|<span data-ttu-id="d6052-238">九年级</span><span class="sxs-lookup"><span data-stu-id="d6052-238">Ninth grade</span></span>|
|<span data-ttu-id="d6052-239">10</span><span class="sxs-lookup"><span data-stu-id="d6052-239">10</span></span>|<span data-ttu-id="d6052-240">十年级</span><span class="sxs-lookup"><span data-stu-id="d6052-240">Tenth grade</span></span>|
|<span data-ttu-id="d6052-241">11</span><span class="sxs-lookup"><span data-stu-id="d6052-241">11</span></span>|<span data-ttu-id="d6052-242">十一年级</span><span class="sxs-lookup"><span data-stu-id="d6052-242">Eleventh grade</span></span>|
|<span data-ttu-id="d6052-243">12</span><span class="sxs-lookup"><span data-stu-id="d6052-243">12</span></span>|<span data-ttu-id="d6052-244">十二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-244">Twelfth grade</span></span>|
|<span data-ttu-id="d6052-245">PS</span><span class="sxs-lookup"><span data-stu-id="d6052-245">PS</span></span>|<span data-ttu-id="d6052-246">大专</span><span class="sxs-lookup"><span data-stu-id="d6052-246">Postsecondary</span></span>|
|<span data-ttu-id="d6052-247">PS1</span><span class="sxs-lookup"><span data-stu-id="d6052-247">PS1</span></span>|<span data-ttu-id="d6052-248">大专新生</span><span class="sxs-lookup"><span data-stu-id="d6052-248">Postsecondary freshman</span></span>|
|<span data-ttu-id="d6052-249">PS2</span><span class="sxs-lookup"><span data-stu-id="d6052-249">PS2</span></span>|<span data-ttu-id="d6052-250">大专二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-250">Postsecondary sophomore</span></span>|
|<span data-ttu-id="d6052-251">PS3</span><span class="sxs-lookup"><span data-stu-id="d6052-251">PS3</span></span>|<span data-ttu-id="d6052-252">大专三年级</span><span class="sxs-lookup"><span data-stu-id="d6052-252">Postsecondary junior</span></span>|
|<span data-ttu-id="d6052-253">PS4</span><span class="sxs-lookup"><span data-stu-id="d6052-253">PS4</span></span>|<span data-ttu-id="d6052-254">大专四年级</span><span class="sxs-lookup"><span data-stu-id="d6052-254">Postsecondary senior</span></span>|
|<span data-ttu-id="d6052-255">本科</span><span class="sxs-lookup"><span data-stu-id="d6052-255">undergraduate</span></span>|<span data-ttu-id="d6052-256">本科</span><span class="sxs-lookup"><span data-stu-id="d6052-256">Undergraduate</span></span>|
|<span data-ttu-id="d6052-257">毕业生</span><span class="sxs-lookup"><span data-stu-id="d6052-257">graduate</span></span>|<span data-ttu-id="d6052-258">毕业生</span><span class="sxs-lookup"><span data-stu-id="d6052-258">Graduate</span></span>|
|<span data-ttu-id="d6052-259">研究生</span><span class="sxs-lookup"><span data-stu-id="d6052-259">postgraduate</span></span>|<span data-ttu-id="d6052-260">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="d6052-260">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="d6052-261">校友</span><span class="sxs-lookup"><span data-stu-id="d6052-261">alumni</span></span>|<span data-ttu-id="d6052-262">校友</span><span class="sxs-lookup"><span data-stu-id="d6052-262">Alumni</span></span>|
|<span data-ttu-id="d6052-263">成人教育</span><span class="sxs-lookup"><span data-stu-id="d6052-263">adultEducation</span></span>|<span data-ttu-id="d6052-264">成人教育</span><span class="sxs-lookup"><span data-stu-id="d6052-264">Adult Education</span></span>|
|<span data-ttu-id="d6052-265">UG</span><span class="sxs-lookup"><span data-stu-id="d6052-265">UG</span></span>|<span data-ttu-id="d6052-266">未分级</span><span class="sxs-lookup"><span data-stu-id="d6052-266">Ungraded</span></span>|
|<span data-ttu-id="d6052-267">其他</span><span class="sxs-lookup"><span data-stu-id="d6052-267">Other</span></span>|<span data-ttu-id="d6052-268">其他</span><span class="sxs-lookup"><span data-stu-id="d6052-268">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="d6052-269">英国各年级</span><span class="sxs-lookup"><span data-stu-id="d6052-269">United Kingdom year groups</span></span>
|<span data-ttu-id="d6052-270">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="d6052-270">Value in file (Grade column)</span></span> | <span data-ttu-id="d6052-271">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="d6052-271">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="d6052-272">IT</span><span class="sxs-lookup"><span data-stu-id="d6052-272">IT</span></span>|<span data-ttu-id="d6052-273">托儿所</span><span class="sxs-lookup"><span data-stu-id="d6052-273">Nursery</span></span>|
|<span data-ttu-id="d6052-274">PR</span><span class="sxs-lookup"><span data-stu-id="d6052-274">PR</span></span>|<span data-ttu-id="d6052-275">学前教育</span><span class="sxs-lookup"><span data-stu-id="d6052-275">Pre-school</span></span>|
|<span data-ttu-id="d6052-276">PK</span><span class="sxs-lookup"><span data-stu-id="d6052-276">PK</span></span>|<span data-ttu-id="d6052-277">接收</span><span class="sxs-lookup"><span data-stu-id="d6052-277">Reception</span></span>|
|<span data-ttu-id="d6052-278">01</span><span class="sxs-lookup"><span data-stu-id="d6052-278">01</span></span>|<span data-ttu-id="d6052-279">一年级</span><span class="sxs-lookup"><span data-stu-id="d6052-279">Year 1</span></span>|
|<span data-ttu-id="d6052-280">02</span><span class="sxs-lookup"><span data-stu-id="d6052-280">02</span></span>|<span data-ttu-id="d6052-281">二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-281">Year 2</span></span>|
|<span data-ttu-id="d6052-282">03</span><span class="sxs-lookup"><span data-stu-id="d6052-282">03</span></span>|<span data-ttu-id="d6052-283">三年级</span><span class="sxs-lookup"><span data-stu-id="d6052-283">Year 3</span></span>|
|<span data-ttu-id="d6052-284">04</span><span class="sxs-lookup"><span data-stu-id="d6052-284">04</span></span>|<span data-ttu-id="d6052-285">四年级</span><span class="sxs-lookup"><span data-stu-id="d6052-285">Year 4</span></span>|
|<span data-ttu-id="d6052-286">05</span><span class="sxs-lookup"><span data-stu-id="d6052-286">05</span></span>|<span data-ttu-id="d6052-287">五年级</span><span class="sxs-lookup"><span data-stu-id="d6052-287">Year 5</span></span>|
|<span data-ttu-id="d6052-288">06</span><span class="sxs-lookup"><span data-stu-id="d6052-288">06</span></span>|<span data-ttu-id="d6052-289">六年级</span><span class="sxs-lookup"><span data-stu-id="d6052-289">Year 6</span></span>|
|<span data-ttu-id="d6052-290">07</span><span class="sxs-lookup"><span data-stu-id="d6052-290">07</span></span>|<span data-ttu-id="d6052-291">七年级</span><span class="sxs-lookup"><span data-stu-id="d6052-291">Year 7</span></span>|
|<span data-ttu-id="d6052-292">08</span><span class="sxs-lookup"><span data-stu-id="d6052-292">08</span></span>|<span data-ttu-id="d6052-293">八年级</span><span class="sxs-lookup"><span data-stu-id="d6052-293">Year 8</span></span>|
|<span data-ttu-id="d6052-294">09</span><span class="sxs-lookup"><span data-stu-id="d6052-294">09</span></span>|<span data-ttu-id="d6052-295">九年级</span><span class="sxs-lookup"><span data-stu-id="d6052-295">Year 9</span></span>|
|<span data-ttu-id="d6052-296">10</span><span class="sxs-lookup"><span data-stu-id="d6052-296">10</span></span>|<span data-ttu-id="d6052-297">十年级</span><span class="sxs-lookup"><span data-stu-id="d6052-297">Year 10</span></span>|
|<span data-ttu-id="d6052-298">11</span><span class="sxs-lookup"><span data-stu-id="d6052-298">11</span></span>|<span data-ttu-id="d6052-299">十一年级</span><span class="sxs-lookup"><span data-stu-id="d6052-299">Year 11</span></span>|
|<span data-ttu-id="d6052-300">12</span><span class="sxs-lookup"><span data-stu-id="d6052-300">12</span></span>|<span data-ttu-id="d6052-301">十二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-301">Year 12</span></span>|
|<span data-ttu-id="d6052-302">13</span><span class="sxs-lookup"><span data-stu-id="d6052-302">13</span></span>|<span data-ttu-id="d6052-303">十三年级</span><span class="sxs-lookup"><span data-stu-id="d6052-303">Year 13</span></span>|
|<span data-ttu-id="d6052-304">PS</span><span class="sxs-lookup"><span data-stu-id="d6052-304">PS</span></span>|<span data-ttu-id="d6052-305">大专</span><span class="sxs-lookup"><span data-stu-id="d6052-305">Postsecondary</span></span>|
|<span data-ttu-id="d6052-306">PS1</span><span class="sxs-lookup"><span data-stu-id="d6052-306">PS1</span></span>|<span data-ttu-id="d6052-307">大专一年级</span><span class="sxs-lookup"><span data-stu-id="d6052-307">Postsecondary Year 1</span></span>|
|<span data-ttu-id="d6052-308">PS2</span><span class="sxs-lookup"><span data-stu-id="d6052-308">PS2</span></span>|<span data-ttu-id="d6052-309">大专二年级</span><span class="sxs-lookup"><span data-stu-id="d6052-309">Postsecondary Year 2</span></span>|
|<span data-ttu-id="d6052-310">PS3</span><span class="sxs-lookup"><span data-stu-id="d6052-310">PS3</span></span>|<span data-ttu-id="d6052-311">大专三年级</span><span class="sxs-lookup"><span data-stu-id="d6052-311">Postsecondary Year 3</span></span>|
|<span data-ttu-id="d6052-312">PS4</span><span class="sxs-lookup"><span data-stu-id="d6052-312">PS4</span></span>|<span data-ttu-id="d6052-313">大专四年级</span><span class="sxs-lookup"><span data-stu-id="d6052-313">Postsecondary Year 4</span></span>|
|<span data-ttu-id="d6052-314">本科</span><span class="sxs-lookup"><span data-stu-id="d6052-314">undergraduate</span></span>|<span data-ttu-id="d6052-315">本科</span><span class="sxs-lookup"><span data-stu-id="d6052-315">Undergraduate</span></span>|
|<span data-ttu-id="d6052-316">毕业生</span><span class="sxs-lookup"><span data-stu-id="d6052-316">graduate</span></span>|<span data-ttu-id="d6052-317">毕业生</span><span class="sxs-lookup"><span data-stu-id="d6052-317">Graduate</span></span>|
|<span data-ttu-id="d6052-318">研究生</span><span class="sxs-lookup"><span data-stu-id="d6052-318">postgraduate</span></span>|<span data-ttu-id="d6052-319">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="d6052-319">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="d6052-320">校友</span><span class="sxs-lookup"><span data-stu-id="d6052-320">alumni</span></span>|<span data-ttu-id="d6052-321">校友</span><span class="sxs-lookup"><span data-stu-id="d6052-321">Alumni</span></span>|
|<span data-ttu-id="d6052-322">成人教育</span><span class="sxs-lookup"><span data-stu-id="d6052-322">adultEducation</span></span>|<span data-ttu-id="d6052-323">成人教育</span><span class="sxs-lookup"><span data-stu-id="d6052-323">Adult Education</span></span>|
|<span data-ttu-id="d6052-324">UG</span><span class="sxs-lookup"><span data-stu-id="d6052-324">UG</span></span>|<span data-ttu-id="d6052-325">未分级</span><span class="sxs-lookup"><span data-stu-id="d6052-325">Ungraded</span></span>|
|<span data-ttu-id="d6052-326">其他</span><span class="sxs-lookup"><span data-stu-id="d6052-326">Other</span></span>|<span data-ttu-id="d6052-327">其他</span><span class="sxs-lookup"><span data-stu-id="d6052-327">Other</span></span>|