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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142838"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="73a7b-103">将学生信息系统 (SIS) 数据与教育版见解同步</span><span class="sxs-lookup"><span data-stu-id="73a7b-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="73a7b-104">向[教育版见解](class-insights.md)提供的数据越多，教师就越能更好地为学生提供支持，并且教育领导者也可以为教师提供更好的支持。</span><span class="sxs-lookup"><span data-stu-id="73a7b-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="73a7b-105">若要提供组织级见解，我们必须使用[学校数据同步 (SDS)](/SchoolDataSync) 连接到学生信息系统 (SIS)，以便见解正确映射教育系统的层次结构。</span><span class="sxs-lookup"><span data-stu-id="73a7b-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="73a7b-106">以课堂教师的身份查看课堂级见解 *不* 需要这种同步，因为我们使用 Teams 的课堂结构和权限。</span><span class="sxs-lookup"><span data-stu-id="73a7b-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="73a7b-107">计划学校数据同步集成</span><span class="sxs-lookup"><span data-stu-id="73a7b-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="73a7b-108">Microsoft 学校数据同步系统 (又称 SDS) 提供了学校信息系统 (又称 SIS) 的数据和它的教育系统的层次结构，并映射出哪个用户分配到哪里，还提供了关于学生和组织层次的额外数据。</span><span class="sxs-lookup"><span data-stu-id="73a7b-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="73a7b-109">Insights 在使用 [SDS V2.1 文件格式](/schooldatasync/sds-v2.1-csv-file-format) 时效果最佳，但也支持 *功能受限* 的 [SDS V2 文件格式](/schooldatasync/sds-v2-csv-file-format) 和 [SDS V1 文件格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。</span><span class="sxs-lookup"><span data-stu-id="73a7b-109">Insights works best when using [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) but also supports [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and  [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="73a7b-110">SDS V1 和 V2 文件格式之间的差异</span><span class="sxs-lookup"><span data-stu-id="73a7b-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="73a7b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="73a7b-111">Data type</span></span> | <span data-ttu-id="73a7b-112">V1</span><span class="sxs-lookup"><span data-stu-id="73a7b-112">V1</span></span> | <span data-ttu-id="73a7b-113">V2 和 V2.1</span><span class="sxs-lookup"><span data-stu-id="73a7b-113">V2 and V2.1</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="73a7b-114">**用户**</span><span class="sxs-lookup"><span data-stu-id="73a7b-114">**Users**</span></span> |<span data-ttu-id="73a7b-115">仅支持“教师”角色，因此需要手动设置教育领导者的组织级别权限</span><span class="sxs-lookup"><span data-stu-id="73a7b-115">Supports only ‘educator’ role, as a result org-level permissions for your education leaders need to be set manually</span></span>|<span data-ttu-id="73a7b-116">支持多个角色，以便可以设置基于角色的权限</span><span class="sxs-lookup"><span data-stu-id="73a7b-116">Supports multiple roles so that role-based permissions can be set</span></span>|
| <span data-ttu-id="73a7b-117">**组织**</span><span class="sxs-lookup"><span data-stu-id="73a7b-117">**Orgs**</span></span> | <span data-ttu-id="73a7b-118">仅支持“学校”，聚合级别。</span><span class="sxs-lookup"><span data-stu-id="73a7b-118">Supports only ‘schools’, aggregation level.</span></span><br><br><span data-ttu-id="73a7b-119">因此，不提供多个聚合级别，并提供有限的功能来比较不同类型的学校（例如，小学与中学、科学学校和艺术学校）</span><span class="sxs-lookup"><span data-stu-id="73a7b-119">As a result, does not provide multiple aggregation levels and provide limited ability to compare different types of schools (e.g primary vs. secondary school, science vs. art school)</span></span>|<span data-ttu-id="73a7b-120">支持多层层次结构，包括地区/机构、大学、学院、院系、校区、区域、计划等。</span><span class="sxs-lookup"><span data-stu-id="73a7b-120">Supports multi-layer hierarchy, including district/institution, universities, colleges, faculties, campuses, regions, programs, etc.</span></span><br><br><span data-ttu-id="73a7b-121">允许多个聚合级别，并轻松比较每个级别的组织单位、向特定级别分配权限、按组织级别设置目标等。</span><span class="sxs-lookup"><span data-stu-id="73a7b-121">Allows for multiple aggregation levels and to easily compare between organizational units at each level, assign permissions to specific levels, set goals by org level, etc.</span></span>|
| <span data-ttu-id="73a7b-122">**其他可选信息**</span><span class="sxs-lookup"><span data-stu-id="73a7b-122">**Additional optional information**</span></span> |<span data-ttu-id="73a7b-123">无</span><span class="sxs-lookup"><span data-stu-id="73a7b-123">None</span></span>|<span data-ttu-id="73a7b-124">**仅 V2.1 文件格式**</span><span class="sxs-lookup"><span data-stu-id="73a7b-124">**V2.1 file format only**</span></span><br><br><span data-ttu-id="73a7b-125">*学术课程* - 课程的时间范围（学期、学年等）</span><span class="sxs-lookup"><span data-stu-id="73a7b-125">*Academic Sessions* - timeframes of sessions (semesters, school years etc.)</span></span><br><br><span data-ttu-id="73a7b-126">人口统计和学生标志\* - 诸如种族、民族和性别的数据，以及特殊计划（IEP、504）</span><span class="sxs-lookup"><span data-stu-id="73a7b-126">Demographics and student flags\* - data like race, ethnicity, and gender, as well as special programs (IEP, 504)</span></span>|

> [!NOTE]
> <span data-ttu-id="73a7b-127">自 2021 年 7 月 15 日起，客户将不能使用 v2 文件格式，而需要使用 v2.1 格式，所有未来的升级和新能力将在 v2.1 格式上完成且它将完全向后兼容 v1 文件格式。</span><span class="sxs-lookup"><span data-stu-id="73a7b-127">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

### <a name="best-practices"></a><span data-ttu-id="73a7b-128">最佳做法</span><span class="sxs-lookup"><span data-stu-id="73a7b-128">Best practices</span></span>

<span data-ttu-id="73a7b-129">借助层次结构以及每个人在该层次结构中的位置的准确映射，Insights 可以为不同类型的教育领导者提供准确数据以及更为精确且相关的见解。</span><span class="sxs-lookup"><span data-stu-id="73a7b-129">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="73a7b-130">所提供的细节越多，报告和聚光灯就越有用且越有针对性。</span><span class="sxs-lookup"><span data-stu-id="73a7b-130">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

#### <a name="file-format-version-to-use-adn-data-to-sync"></a><span data-ttu-id="73a7b-131">要使用的文件格式版本和要同步的数据</span><span class="sxs-lookup"><span data-stu-id="73a7b-131">File format version to use adn data to sync</span></span>
*   <span data-ttu-id="73a7b-132">使用文件格式 V2.1 并同步教育版 Insights 使用的如 [此处](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv) 所述的可选数据。</span><span class="sxs-lookup"><span data-stu-id="73a7b-132">Use file format V2.1 and sync the optional data used by Education Insights as described [here](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).</span></span>

#### <a name="users-and-roles"></a><span data-ttu-id="73a7b-133">用户和角色</span><span class="sxs-lookup"><span data-stu-id="73a7b-133">Users and Roles</span></span>
*   <span data-ttu-id="73a7b-134">请确保 **所有用户** 都列出在你提供的文件中并且已同步。</span><span class="sxs-lookup"><span data-stu-id="73a7b-134">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="73a7b-135">这包括需要查看其所在组织单位的数据的所有学生和教职员工。</span><span class="sxs-lookup"><span data-stu-id="73a7b-135">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
*   <span data-ttu-id="73a7b-136">如果当前只在 SIS 中列出了教师，请先手动添加其他用户，再将文件上传到 SDS 并同步数据。</span><span class="sxs-lookup"><span data-stu-id="73a7b-136">If you currently only have educators listed in your SIS, add all other users manually before uploading the files to SDS and syncing the data.</span></span> <span data-ttu-id="73a7b-137">Insights 收集的数据仅来自于注册的学生，如果遗漏了某些学生，所得数据和结论将产生误导。</span><span class="sxs-lookup"><span data-stu-id="73a7b-137">The stats gathered by Insights will onlybe  from the registered students, if some students are missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="73a7b-138">如果还使用 SDS 进行预配，请确保 **提供每个用户的名字和姓氏**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-138">If you use SDS for provisioning as well, make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="73a7b-139">否则，将按学生的电子邮件地址引用学生，从而获得非最佳体验。</span><span class="sxs-lookup"><span data-stu-id="73a7b-139">Otherwise, students will be referenced by their email address, resulting in a non-optimal experience.</span></span>

*   <span data-ttu-id="73a7b-140">年级/年份必须基于此 [映射列表](#supported-grade-level-values)。</span><span class="sxs-lookup"><span data-stu-id="73a7b-140">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="73a7b-141">请务必 **将年级/年份级别添加到所有学生**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-141">Make sure to **add the year/grade level to all students** .</span></span>    

*   <span data-ttu-id="73a7b-142">请确保 **将每个用户分配到其相关的组织单位**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-142">Make sure to **assign each user to their relevant organizational unit**.</span></span>

    *   <span data-ttu-id="73a7b-143">一名学生可以与一个以上的组织单位相关联，例如，注册在一个特殊项目或两个院系的学生。</span><span class="sxs-lookup"><span data-stu-id="73a7b-143">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="73a7b-144">如果学生有一个以上的组织单位，请在该学生的用户文件中为每个单位提供一行。</span><span class="sxs-lookup"><span data-stu-id="73a7b-144">In case the student has more then one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="73a7b-145">IT 管理员可以根据组织单位为员工授予权限。</span><span class="sxs-lookup"><span data-stu-id="73a7b-145">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="73a7b-146">**请确保工作人员与正确的单位级别相关联**，以便他们获得他们需要的权限。</span><span class="sxs-lookup"><span data-stu-id="73a7b-146">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="73a7b-147">例如，分配到四所学校的辅导员需要看到这些学校的所有年级; 校长需要看到他们学校的所有课程。</span><span class="sxs-lookup"><span data-stu-id="73a7b-147">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="73a7b-148">**该角色至关重要**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-148">**The role is vital**.</span></span> <span data-ttu-id="73a7b-149">尽管这是一个封闭列表，但请尝试将[列表](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)中的角色与所上传的每个用户的真实角色进行匹配。</span><span class="sxs-lookup"><span data-stu-id="73a7b-149">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="73a7b-150">这将使你能够相应地分配基于角色的权限。</span><span class="sxs-lookup"><span data-stu-id="73a7b-150">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="73a7b-151">例如，为所有校长提供查看其学校中的班级的权限，或授予所有教授查看教职员工的权限。</span><span class="sxs-lookup"><span data-stu-id="73a7b-151">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

#### <a name="organizations"></a><span data-ttu-id="73a7b-152">组织</span><span class="sxs-lookup"><span data-stu-id="73a7b-152">Organizations</span></span>

* <span data-ttu-id="73a7b-153">请确保 **反映组织真实和完整的层次结构**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-153">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="73a7b-154">在某些情况下，此层次结构不会反映在 SIS 中，在这种情况下，需要在同步前将其手动添加到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="73a7b-154">In some cases, this hierarchy is not reflected in the SIS, in which case it needs to be added manually to the CSV file efore syncing.</span></span>

* <span data-ttu-id="73a7b-155">确保 **组织树下的所有组织单位包括学生或班级**。</span><span class="sxs-lookup"><span data-stu-id="73a7b-155">Make sure that **all organization units down the organization tree include students or classes**.</span></span> <span data-ttu-id="73a7b-156">我们建议学生位于树的最低分支上。</span><span class="sxs-lookup"><span data-stu-id="73a7b-156">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="73a7b-157">有关 SDS 部署的详细信息，请访问[规划 SDS](/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="73a7b-157">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="73a7b-158">使用 SDS 集成 SIS 数据</span><span class="sxs-lookup"><span data-stu-id="73a7b-158">Integrate SIS data using SDS</span></span>

<span data-ttu-id="73a7b-p109">学校数据同步 (SDS) 随 Office 365 教育版一并提供。SDS 从教育机构的学生信息系统 (SIS) 中读取数据，并将其与 Microsoft 的应用程序（如 Teams）整合，以实现自动创建在线教室和用户。</span><span class="sxs-lookup"><span data-stu-id="73a7b-p109">School Data Sync (SDS) is provided with Office 365 for Education. SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="73a7b-161">它还将 SIS 数据与 Insights 同步。</span><span class="sxs-lookup"><span data-stu-id="73a7b-161">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="73a7b-162">作为 IT 管理员，可以选择仅使用 SDS 进行配置，仅使用 Insights 或两者都使用。</span><span class="sxs-lookup"><span data-stu-id="73a7b-162">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="73a7b-163">若要将 SIS 信息与教育版 Insights 同步，请按照 [如何为 Insights 部署 SDS](/schooldatasync/how-to-deploy-sds-for-insights) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="73a7b-163">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="73a7b-164">部署 SDS</span><span class="sxs-lookup"><span data-stu-id="73a7b-164">Deploy SDS</span></span>
<span data-ttu-id="73a7b-165">**如果你已经在使用 SDS**，我们建议你遵循 [最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="73a7b-165">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="73a7b-166">**如果你尚未使用 SDS**，那么现在需要 [部署它](/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="73a7b-166">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="73a7b-167">在部署过程中，可以决定是否要使用 SDS 为 Teams 提供用户和类别，或者仅使用它为 Insights 提供用户和组织层次结构。</span><span class="sxs-lookup"><span data-stu-id="73a7b-167">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="73a7b-168">如果现在是年中，而且已手动创建了团队，那就只用 SDS 向 Insights 提供用户和组织层次数据，明年再考虑用 SDS 为团队配置用户和类别。</span><span class="sxs-lookup"><span data-stu-id="73a7b-168">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="73a7b-169">验证同步过程</span><span class="sxs-lookup"><span data-stu-id="73a7b-169">Verify the sync process</span></span>
<span data-ttu-id="73a7b-170">若要验证同步状态进度，请按照 [SDS for Insights 数据运行状况和监视](/schooldatasync/sds-for-insights-data-health-and-monitoring) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="73a7b-170">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73a7b-171">如果你遇到任何问题，[客户支持](https://aka.ms/edusupport)将为你提供帮助。</span><span class="sxs-lookup"><span data-stu-id="73a7b-171">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="73a7b-172">支持的年级值</span><span class="sxs-lookup"><span data-stu-id="73a7b-172">Supported grade level values</span></span>

<span data-ttu-id="73a7b-173">在SDS文件中，年级/年份级别定义为枚举值，这意味着只能在CSV文件中提供一组选定的值。</span><span class="sxs-lookup"><span data-stu-id="73a7b-173">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="73a7b-174">在同步处理过程中，任何其他指定的值都会导致错误。</span><span class="sxs-lookup"><span data-stu-id="73a7b-174">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="73a7b-175">以下部分定义了用户文件中支持的值。</span><span class="sxs-lookup"><span data-stu-id="73a7b-175">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="73a7b-176">美国/全球范围内各年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-176">United States / worldwide grade levels</span></span>
|<span data-ttu-id="73a7b-177">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="73a7b-177">Value in file (Grade column)</span></span> | <span data-ttu-id="73a7b-178">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="73a7b-178">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="73a7b-179">IT</span><span class="sxs-lookup"><span data-stu-id="73a7b-179">IT</span></span>|<span data-ttu-id="73a7b-180">婴幼儿</span><span class="sxs-lookup"><span data-stu-id="73a7b-180">Infant</span></span>|
|<span data-ttu-id="73a7b-181">PR</span><span class="sxs-lookup"><span data-stu-id="73a7b-181">PR</span></span>|<span data-ttu-id="73a7b-182">学前教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-182">Pre-school</span></span>|
|<span data-ttu-id="73a7b-183">PK</span><span class="sxs-lookup"><span data-stu-id="73a7b-183">PK</span></span>|<span data-ttu-id="73a7b-184">幼儿园前教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-184">Pre-kindergarten</span></span>|
|<span data-ttu-id="73a7b-185">TK</span><span class="sxs-lookup"><span data-stu-id="73a7b-185">TK</span></span>|<span data-ttu-id="73a7b-186">过渡性幼儿园</span><span class="sxs-lookup"><span data-stu-id="73a7b-186">Transitional Kindergarten</span></span>|
|<span data-ttu-id="73a7b-187">KG</span><span class="sxs-lookup"><span data-stu-id="73a7b-187">KG</span></span>|<span data-ttu-id="73a7b-188">幼儿园</span><span class="sxs-lookup"><span data-stu-id="73a7b-188">Kindergarten</span></span>|
|<span data-ttu-id="73a7b-189">01 或 1</span><span class="sxs-lookup"><span data-stu-id="73a7b-189">01 or 1</span></span>|<span data-ttu-id="73a7b-190">一年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-190">First grade</span></span>|
|<span data-ttu-id="73a7b-191">02 或 2</span><span class="sxs-lookup"><span data-stu-id="73a7b-191">02 or 2</span></span>|<span data-ttu-id="73a7b-192">第二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-192">Second grade</span></span>|
|<span data-ttu-id="73a7b-193">03 或 3</span><span class="sxs-lookup"><span data-stu-id="73a7b-193">03 or 3</span></span>|<span data-ttu-id="73a7b-194">三年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-194">Third grade</span></span>|
|<span data-ttu-id="73a7b-195">04 或 4</span><span class="sxs-lookup"><span data-stu-id="73a7b-195">04 or 4</span></span>|<span data-ttu-id="73a7b-196">四年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-196">Fourth grade</span></span>|
|<span data-ttu-id="73a7b-197">05 或 5</span><span class="sxs-lookup"><span data-stu-id="73a7b-197">05 or 5</span></span>|<span data-ttu-id="73a7b-198">五年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-198">Fifth grade</span></span>|
|<span data-ttu-id="73a7b-199">06 或 6</span><span class="sxs-lookup"><span data-stu-id="73a7b-199">06 or 6</span></span>|<span data-ttu-id="73a7b-200">六年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-200">Sixth grade</span></span>|
|<span data-ttu-id="73a7b-201">07 或 7</span><span class="sxs-lookup"><span data-stu-id="73a7b-201">07 or 7</span></span>|<span data-ttu-id="73a7b-202">七年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-202">Seventh grade</span></span>|
|<span data-ttu-id="73a7b-203">08 或 8</span><span class="sxs-lookup"><span data-stu-id="73a7b-203">08 or 8</span></span>|<span data-ttu-id="73a7b-204">八年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-204">Eighth grade</span></span>|
|<span data-ttu-id="73a7b-205">09 或 9</span><span class="sxs-lookup"><span data-stu-id="73a7b-205">09 or 9</span></span>|<span data-ttu-id="73a7b-206">九年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-206">Ninth grade</span></span>|
|<span data-ttu-id="73a7b-207">10</span><span class="sxs-lookup"><span data-stu-id="73a7b-207">10</span></span>|<span data-ttu-id="73a7b-208">十年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-208">Tenth grade</span></span>|
|<span data-ttu-id="73a7b-209">11</span><span class="sxs-lookup"><span data-stu-id="73a7b-209">11</span></span>|<span data-ttu-id="73a7b-210">十一年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-210">Eleventh grade</span></span>|
|<span data-ttu-id="73a7b-211">12</span><span class="sxs-lookup"><span data-stu-id="73a7b-211">12</span></span>|<span data-ttu-id="73a7b-212">十二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-212">Twelfth grade</span></span>|
|<span data-ttu-id="73a7b-213">PS</span><span class="sxs-lookup"><span data-stu-id="73a7b-213">PS</span></span>|<span data-ttu-id="73a7b-214">大专</span><span class="sxs-lookup"><span data-stu-id="73a7b-214">Postsecondary</span></span>|
|<span data-ttu-id="73a7b-215">PS1</span><span class="sxs-lookup"><span data-stu-id="73a7b-215">PS1</span></span>|<span data-ttu-id="73a7b-216">大专新生</span><span class="sxs-lookup"><span data-stu-id="73a7b-216">Postsecondary freshman</span></span>|
|<span data-ttu-id="73a7b-217">PS2</span><span class="sxs-lookup"><span data-stu-id="73a7b-217">PS2</span></span>|<span data-ttu-id="73a7b-218">大专二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-218">Postsecondary sophomore</span></span>|
|<span data-ttu-id="73a7b-219">PS3</span><span class="sxs-lookup"><span data-stu-id="73a7b-219">PS3</span></span>|<span data-ttu-id="73a7b-220">大专三年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-220">Postsecondary junior</span></span>|
|<span data-ttu-id="73a7b-221">PS4</span><span class="sxs-lookup"><span data-stu-id="73a7b-221">PS4</span></span>|<span data-ttu-id="73a7b-222">大专四年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-222">Postsecondary senior</span></span>|
|<span data-ttu-id="73a7b-223">本科</span><span class="sxs-lookup"><span data-stu-id="73a7b-223">undergraduate</span></span>|<span data-ttu-id="73a7b-224">本科</span><span class="sxs-lookup"><span data-stu-id="73a7b-224">Undergraduate</span></span>|
|<span data-ttu-id="73a7b-225">毕业生</span><span class="sxs-lookup"><span data-stu-id="73a7b-225">graduate</span></span>|<span data-ttu-id="73a7b-226">毕业生</span><span class="sxs-lookup"><span data-stu-id="73a7b-226">Graduate</span></span>|
|<span data-ttu-id="73a7b-227">研究生</span><span class="sxs-lookup"><span data-stu-id="73a7b-227">postgraduate</span></span>|<span data-ttu-id="73a7b-228">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="73a7b-228">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="73a7b-229">校友</span><span class="sxs-lookup"><span data-stu-id="73a7b-229">alumni</span></span>|<span data-ttu-id="73a7b-230">校友</span><span class="sxs-lookup"><span data-stu-id="73a7b-230">Alumni</span></span>|
|<span data-ttu-id="73a7b-231">成人教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-231">adultEducation</span></span>|<span data-ttu-id="73a7b-232">成人教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-232">Adult Education</span></span>|
|<span data-ttu-id="73a7b-233">UG</span><span class="sxs-lookup"><span data-stu-id="73a7b-233">UG</span></span>|<span data-ttu-id="73a7b-234">未分级</span><span class="sxs-lookup"><span data-stu-id="73a7b-234">Ungraded</span></span>|
|<span data-ttu-id="73a7b-235">其他</span><span class="sxs-lookup"><span data-stu-id="73a7b-235">Other</span></span>|<span data-ttu-id="73a7b-236">其他</span><span class="sxs-lookup"><span data-stu-id="73a7b-236">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="73a7b-237">英国各年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-237">United Kingdom year groups</span></span>
|<span data-ttu-id="73a7b-238">文件中的值（等级列）</span><span class="sxs-lookup"><span data-stu-id="73a7b-238">Value in file (Grade column)</span></span> | <span data-ttu-id="73a7b-239">Insights的标签</span><span class="sxs-lookup"><span data-stu-id="73a7b-239">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="73a7b-240">IT</span><span class="sxs-lookup"><span data-stu-id="73a7b-240">IT</span></span>|<span data-ttu-id="73a7b-241">托儿所</span><span class="sxs-lookup"><span data-stu-id="73a7b-241">Nursery</span></span>|
|<span data-ttu-id="73a7b-242">PR</span><span class="sxs-lookup"><span data-stu-id="73a7b-242">PR</span></span>|<span data-ttu-id="73a7b-243">学前教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-243">Pre-school</span></span>|
|<span data-ttu-id="73a7b-244">PK</span><span class="sxs-lookup"><span data-stu-id="73a7b-244">PK</span></span>|<span data-ttu-id="73a7b-245">接收</span><span class="sxs-lookup"><span data-stu-id="73a7b-245">Reception</span></span>|
|<span data-ttu-id="73a7b-246">01 或 1</span><span class="sxs-lookup"><span data-stu-id="73a7b-246">01 or 1</span></span>|<span data-ttu-id="73a7b-247">一年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-247">Year 1</span></span>|
|<span data-ttu-id="73a7b-248">02 或 2</span><span class="sxs-lookup"><span data-stu-id="73a7b-248">02 or 2</span></span>|<span data-ttu-id="73a7b-249">二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-249">Year 2</span></span>|
|<span data-ttu-id="73a7b-250">03 或 3</span><span class="sxs-lookup"><span data-stu-id="73a7b-250">03 or 3</span></span>|<span data-ttu-id="73a7b-251">三年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-251">Year 3</span></span>|
|<span data-ttu-id="73a7b-252">04 或 4</span><span class="sxs-lookup"><span data-stu-id="73a7b-252">04 or 4</span></span>|<span data-ttu-id="73a7b-253">四年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-253">Year 4</span></span>|
|<span data-ttu-id="73a7b-254">05 或 5</span><span class="sxs-lookup"><span data-stu-id="73a7b-254">05 or 5</span></span>|<span data-ttu-id="73a7b-255">五年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-255">Year 5</span></span>|
|<span data-ttu-id="73a7b-256">06 或 6</span><span class="sxs-lookup"><span data-stu-id="73a7b-256">06 or 6</span></span>|<span data-ttu-id="73a7b-257">六年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-257">Year 6</span></span>|
|<span data-ttu-id="73a7b-258">07 或 7</span><span class="sxs-lookup"><span data-stu-id="73a7b-258">07 or 7</span></span>|<span data-ttu-id="73a7b-259">七年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-259">Year 7</span></span>|
|<span data-ttu-id="73a7b-260">08 或 8</span><span class="sxs-lookup"><span data-stu-id="73a7b-260">08 or 8</span></span>|<span data-ttu-id="73a7b-261">八年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-261">Year 8</span></span>|
|<span data-ttu-id="73a7b-262">09 或 9</span><span class="sxs-lookup"><span data-stu-id="73a7b-262">09 or 9</span></span>|<span data-ttu-id="73a7b-263">九年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-263">Year 9</span></span>|
|<span data-ttu-id="73a7b-264">10</span><span class="sxs-lookup"><span data-stu-id="73a7b-264">10</span></span>|<span data-ttu-id="73a7b-265">十年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-265">Year 10</span></span>|
|<span data-ttu-id="73a7b-266">11</span><span class="sxs-lookup"><span data-stu-id="73a7b-266">11</span></span>|<span data-ttu-id="73a7b-267">十一年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-267">Year 11</span></span>|
|<span data-ttu-id="73a7b-268">12</span><span class="sxs-lookup"><span data-stu-id="73a7b-268">12</span></span>|<span data-ttu-id="73a7b-269">十二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-269">Year 12</span></span>|
|<span data-ttu-id="73a7b-270">13</span><span class="sxs-lookup"><span data-stu-id="73a7b-270">13</span></span>|<span data-ttu-id="73a7b-271">十三年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-271">Year 13</span></span>|
|<span data-ttu-id="73a7b-272">PS</span><span class="sxs-lookup"><span data-stu-id="73a7b-272">PS</span></span>|<span data-ttu-id="73a7b-273">大专</span><span class="sxs-lookup"><span data-stu-id="73a7b-273">Postsecondary</span></span>|
|<span data-ttu-id="73a7b-274">PS1</span><span class="sxs-lookup"><span data-stu-id="73a7b-274">PS1</span></span>|<span data-ttu-id="73a7b-275">大专一年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-275">Postsecondary Year 1</span></span>|
|<span data-ttu-id="73a7b-276">PS2</span><span class="sxs-lookup"><span data-stu-id="73a7b-276">PS2</span></span>|<span data-ttu-id="73a7b-277">大专二年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-277">Postsecondary Year 2</span></span>|
|<span data-ttu-id="73a7b-278">PS3</span><span class="sxs-lookup"><span data-stu-id="73a7b-278">PS3</span></span>|<span data-ttu-id="73a7b-279">大专三年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-279">Postsecondary Year 3</span></span>|
|<span data-ttu-id="73a7b-280">PS4</span><span class="sxs-lookup"><span data-stu-id="73a7b-280">PS4</span></span>|<span data-ttu-id="73a7b-281">大专四年级</span><span class="sxs-lookup"><span data-stu-id="73a7b-281">Postsecondary Year 4</span></span>|
|<span data-ttu-id="73a7b-282">本科</span><span class="sxs-lookup"><span data-stu-id="73a7b-282">undergraduate</span></span>|<span data-ttu-id="73a7b-283">本科</span><span class="sxs-lookup"><span data-stu-id="73a7b-283">Undergraduate</span></span>|
|<span data-ttu-id="73a7b-284">毕业生</span><span class="sxs-lookup"><span data-stu-id="73a7b-284">graduate</span></span>|<span data-ttu-id="73a7b-285">毕业生</span><span class="sxs-lookup"><span data-stu-id="73a7b-285">Graduate</span></span>|
|<span data-ttu-id="73a7b-286">研究生</span><span class="sxs-lookup"><span data-stu-id="73a7b-286">postgraduate</span></span>|<span data-ttu-id="73a7b-287">研究生（以研究为重点的研究生）</span><span class="sxs-lookup"><span data-stu-id="73a7b-287">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="73a7b-288">校友</span><span class="sxs-lookup"><span data-stu-id="73a7b-288">alumni</span></span>|<span data-ttu-id="73a7b-289">校友</span><span class="sxs-lookup"><span data-stu-id="73a7b-289">Alumni</span></span>|
|<span data-ttu-id="73a7b-290">成人教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-290">adultEducation</span></span>|<span data-ttu-id="73a7b-291">成人教育</span><span class="sxs-lookup"><span data-stu-id="73a7b-291">Adult Education</span></span>|
|<span data-ttu-id="73a7b-292">UG</span><span class="sxs-lookup"><span data-stu-id="73a7b-292">UG</span></span>|<span data-ttu-id="73a7b-293">未分级</span><span class="sxs-lookup"><span data-stu-id="73a7b-293">Ungraded</span></span>|
|<span data-ttu-id="73a7b-294">其他</span><span class="sxs-lookup"><span data-stu-id="73a7b-294">Other</span></span>|<span data-ttu-id="73a7b-295">其他</span><span class="sxs-lookup"><span data-stu-id="73a7b-295">Other</span></span>|

