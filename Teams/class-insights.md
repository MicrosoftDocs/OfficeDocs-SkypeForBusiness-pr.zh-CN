---
title: Teams 教育版见解 IT 管理员指南
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版见解 IT 管理员指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7869d5030f5a2f778fb4988c49d7f48274f4f792
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778094"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a><span data-ttu-id="48607-103">Teams 教育版见解 IT 管理员指南</span><span class="sxs-lookup"><span data-stu-id="48607-103">IT Admin Guide to Insights in Teams for Education</span></span>

<span data-ttu-id="48607-104">借助 Microsoft Teams 教育版见解，教师和主管可以获取与数字化互动、评估工作量、分数以及沟通等方面相关的分析数据。</span><span class="sxs-lookup"><span data-stu-id="48607-104">With Insights in Microsoft Teams for Education, educators and leaders can access analytics data about digital engagement, assignment workload, grades, communication and more.</span></span>

<span data-ttu-id="48607-105">见解目前可在 Office 365 教育版 SKUs A1、A3 和 A5 中使用。</span><span class="sxs-lookup"><span data-stu-id="48607-105">Insights is active in Office 365 Education SKUs A1, A3, and A5.</span></span>

> [!NOTE]
> <span data-ttu-id="48607-106">教师，[点击此处](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)了解如何使用见解。</span><span class="sxs-lookup"><span data-stu-id="48607-106">Educators, learn how to use Insights [here](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).</span></span>

## <a name="permissions"></a><span data-ttu-id="48607-107">权限</span><span class="sxs-lookup"><span data-stu-id="48607-107">Permissions</span></span>

<span data-ttu-id="48607-108">用户类型：</span><span class="sxs-lookup"><span data-stu-id="48607-108">User types:</span></span> 
- <span data-ttu-id="48607-109">学生由其许可证标识，并且无权访问“见解”选项卡（即使他们是团队的所有者）。</span><span class="sxs-lookup"><span data-stu-id="48607-109">Students are identified by their license and do not have access to the Insights tab (even if they are an owner of the team).</span></span> 
- <span data-ttu-id="48607-110">教师由教职员工许可证标识。</span><span class="sxs-lookup"><span data-stu-id="48607-110">Educators are identified by faculty licenses.</span></span> <span data-ttu-id="48607-111">教师必须拥有教职员工许可证，并且是课堂团队所有者，以便添加和查看“见解”选项卡中显示的数据。</span><span class="sxs-lookup"><span data-stu-id="48607-111">Educators must have a faculty license and be a class team owner to add and see the data presented in the Insights tab.</span></span> 
- <span data-ttu-id="48607-112">主管也由教职员工许可证标识，但是此外，他们需要从 IT 全局管理员获取显式权限，才能在“见解”应用中查看报告。</span><span class="sxs-lookup"><span data-stu-id="48607-112">Leaders are also identified by faculty license, but in addition they need explicit permissions from the IT global admin to view the reports in the Insights app.</span></span>

<span data-ttu-id="48607-113">教师和主管具有不同的权限级别和逻辑：</span><span class="sxs-lookup"><span data-stu-id="48607-113">Educators and leaders have different permission levels and logic:</span></span>
- <span data-ttu-id="48607-114">教师可以通过导航到 Microsoft Teams 应用栏中的“应用”并搜索“见解”，将“见解”应用添加到课堂团队的公共频道中。</span><span class="sxs-lookup"><span data-stu-id="48607-114">Educators can add the Insights app to a public channel within a class team by navigating to Apps in the Teams app bar and searching for Insights.</span></span> <span data-ttu-id="48607-115">此选项卡反映了班级团队中所有者以外的所有人（包括不是团队所有者的教师）的活动。</span><span class="sxs-lookup"><span data-stu-id="48607-115">The tab reflects activity from everyone in the class team who isn’t an owner (including educators who aren’t owners of the team).</span></span> 
- <span data-ttu-id="48607-116">主管可将“见解”应用添加为个人应用（出现在 Microsoft Teams 菜单上），方法是在 Microsoft Teams 应用栏中导航到“应用”并搜索“见解”。</span><span class="sxs-lookup"><span data-stu-id="48607-116">Leaders can add the Insights app as a personal app (appears on Teams left menu) by navigating to Apps in the Teams app bar and searching for Insights.</span></span> 

## <a name="compliance"></a><span data-ttu-id="48607-117">合规性</span><span class="sxs-lookup"><span data-stu-id="48607-117">Compliance</span></span>

<span data-ttu-id="48607-118">见解具有业界领先的合规性承诺，并且在 Office 365 合规性框架内被归类为 C 层服务。</span><span class="sxs-lookup"><span data-stu-id="48607-118">Insights has industry-leading compliance commitments, and is classified as a Tier-C service within the Office 365 Compliance Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="48607-119">访问 [Microsoft 信任中心](https://www.microsoft.com/trust-center)，以深入了解有关 Microsoft 如何保护您的数据。</span><span class="sxs-lookup"><span data-stu-id="48607-119">Visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center) to learn more about how Microsoft protects your data.</span></span>

## <a name="privacy"></a><span data-ttu-id="48607-120">隐私</span><span class="sxs-lookup"><span data-stu-id="48607-120">Privacy</span></span>

<span data-ttu-id="48607-121">通过见解收集和显示的信息确实符合 90 多个法规和行业标准，包括 GDPR 和关于学生和儿童安全的《家庭教育权利和隐私法案》(FERPA)，以及其他类似的面向隐私的法规。</span><span class="sxs-lookup"><span data-stu-id="48607-121">The information collected and shown through Insights does meets more than 90 regulatory and industry standards, including GDPR and the Family Education Rights and Privacy Act (FERPA) for the security of students and children and other, similar, privacy-oriented regulations.</span></span> <span data-ttu-id="48607-122">对于 IT 管理员来说，了解对每个学生收集的信息仅可用于课堂环境非常重要，以便教师和主管确定学生的行为。</span><span class="sxs-lookup"><span data-stu-id="48607-122">It's important for IT admins to know that the information collected on a per-student basis is intended to be used in a class context only, to allow educators and leaders to determine students' behavior.</span></span> <span data-ttu-id="48607-123">收集这些信息是为了进行有意义的学习活动，例如参加课堂会议、发布消息、回复同学的帖子、处理作业、编辑文件等。</span><span class="sxs-lookup"><span data-stu-id="48607-123">The information is collected for meaningful learning activities, such as class meetings attendance, posting messages, responding to classmates' posts, working on assignments, editing files, and more.</span></span> <span data-ttu-id="48607-124">例如，我们不显示有关私人聊天或 Teams 登录的信息。</span><span class="sxs-lookup"><span data-stu-id="48607-124">We don't show information about private chat or a Teams login, as an example.</span></span>

<span data-ttu-id="48607-125">我们的目标是帮助教师了解参与度、专注于学生的学习。</span><span class="sxs-lookup"><span data-stu-id="48607-125">Our goal is to help educators to understand engagement and shine a spotlight on student learning.</span></span> <span data-ttu-id="48607-126">虽然这些课堂活动可以集中在学生级别的行动上，但是 Microsoft Teams 没有为这些行动分配正面或负面的价值，也没有基于标准对每个学生进行判断性识别。</span><span class="sxs-lookup"><span data-stu-id="48607-126">While these class activities can be focused down to actions at the student level, there is no positive or negative value assigned to these actions by Microsoft Teams, and there is no judgmental identification of individual students based on criteria.</span></span> <span data-ttu-id="48607-127">见解中的信息通知教师，例如，某个学生在特定时期内未使用该工具，或者上周准时完成了所有作业。</span><span class="sxs-lookup"><span data-stu-id="48607-127">The information in  Insights informs an educator that, for example, a student has not been active in the tool during a certain period in time, or has completed all their assignments last week on-time.</span></span> <span data-ttu-id="48607-128">教师有责任与学生以及学生的家人或监护人互动，以确定所发现的任何活动或非活动的根本原因。</span><span class="sxs-lookup"><span data-stu-id="48607-128">It remains the responsibility of the educator to interact with the student and that student's family or guardians to determine the underlying reason for any activity or inactivity detected.</span></span>

## <a name="data-collection"></a><span data-ttu-id="48607-129">数据收集</span><span class="sxs-lookup"><span data-stu-id="48607-129">Data collection</span></span>

<span data-ttu-id="48607-130">当为租户启用教育版分析时，我们会收集见解的数据。</span><span class="sxs-lookup"><span data-stu-id="48607-130">We collect data for Insights when Education Analytics is turned on for the tenant.</span></span> <span data-ttu-id="48607-131">数据收集自 Teams 活动，目的为教学和学习提供可操作的见解。</span><span class="sxs-lookup"><span data-stu-id="48607-131">The data is collected from Teams activity in order to surface actionable insights for teaching and learning.</span></span>

<span data-ttu-id="48607-132">默认情况下，**开启**教育版分析。</span><span class="sxs-lookup"><span data-stu-id="48607-132">By default, Education Analytics is turned **On**.</span></span>

<span data-ttu-id="48607-133">目前，此数据从课堂团队的学生和教师活动的以下区域提取：</span><span class="sxs-lookup"><span data-stu-id="48607-133">Currently, this data is pulled from the following areas of student and educator activity in class teams:</span></span>

|<span data-ttu-id="48607-134">Teams 组件</span><span class="sxs-lookup"><span data-stu-id="48607-134">Teams component</span></span>  |<span data-ttu-id="48607-135">收集的数据</span><span class="sxs-lookup"><span data-stu-id="48607-135">Data collected</span></span>  |
|-----------------|------------------------|------------------------|
|<span data-ttu-id="48607-136">作业</span><span class="sxs-lookup"><span data-stu-id="48607-136">Assignments</span></span> |<span data-ttu-id="48607-137">打开、上交作业并评分。</span><span class="sxs-lookup"><span data-stu-id="48607-137">Opening, turning in, and grade on assignments.</span></span> |
|<span data-ttu-id="48607-138">频道参与</span><span class="sxs-lookup"><span data-stu-id="48607-138">Channel engagement</span></span> |<span data-ttu-id="48607-139">访问频道、创建帖子、回复和赞帖子（不包括聊天内容）。</span><span class="sxs-lookup"><span data-stu-id="48607-139">Visiting a channel, creating a post, replying to and liking a post (not including chat content).</span></span> |
|<span data-ttu-id="48607-140">文件</span><span class="sxs-lookup"><span data-stu-id="48607-140">Files</span></span> |<span data-ttu-id="48607-141">上传、下载、访问、修改、批注和共享文件（不包括文件内容）。</span><span class="sxs-lookup"><span data-stu-id="48607-141">Uploading, downloading, accessing, modifying, commenting on, and sharing a file (not including file content).</span></span> |
|<span data-ttu-id="48607-142">会议</span><span class="sxs-lookup"><span data-stu-id="48607-142">Meetings</span></span> |<span data-ttu-id="48607-143">出席（不包括会议内容）。</span><span class="sxs-lookup"><span data-stu-id="48607-143">Attendance (not including meeting content).</span></span> |

## <a name="data-location"></a><span data-ttu-id="48607-144">数据位置</span><span class="sxs-lookup"><span data-stu-id="48607-144">Data location</span></span>

<span data-ttu-id="48607-145">位于欧洲的租户见解数据存储在欧洲服务器上。</span><span class="sxs-lookup"><span data-stu-id="48607-145">Insights data for European-based tenants is stored on servers in Europe.</span></span> <span data-ttu-id="48607-146">位于美国的租户数据存储在美国服务器上。</span><span class="sxs-lookup"><span data-stu-id="48607-146">Data for US-based tenants is stored on servers in the United States.</span></span> <span data-ttu-id="48607-147">如果您使用见解，并且 Office 365 租户位于欧洲或美国以外地区，则您的数据将存储在相应的地理区域。</span><span class="sxs-lookup"><span data-stu-id="48607-147">If you use Insights and your Office 365 tenant is in a region outside of Europe or the United States, your data will be stored in the appropriate geographic region.</span></span>

## <a name="performance-and-reliability"></a><span data-ttu-id="48607-148">性能和可靠性</span><span class="sxs-lookup"><span data-stu-id="48607-148">Performance and reliability</span></span>

<span data-ttu-id="48607-149">见解旨在以最佳性能和可靠性处理从 Microsoft Teams 活动收集的大量数据。</span><span class="sxs-lookup"><span data-stu-id="48607-149">Insights is designed to handle a high volume of data collected from Teams activity with optimal performance and reliability.</span></span>

<span data-ttu-id="48607-150">无论 Microsoft Teams 中的“见解”选项卡如何安装，均会在单独服务器上进行数据收集过程。</span><span class="sxs-lookup"><span data-stu-id="48607-150">The data collection process takes place on separate servers regardless of the installation of the Insights tab in Teams.</span></span> <span data-ttu-id="48607-151">“见解”选项卡或个人应用不影响使用 Microsoft Teams 其他功能的教师和学生应用程序的性能或网络带宽。</span><span class="sxs-lookup"><span data-stu-id="48607-151">The Insights tab or personal app does not affect application performance or network bandwidth for educators and students using the rest of Teams functionality.</span></span>

> [!TIP]
> <span data-ttu-id="48607-152">阅读[此处](edu-remote-low-bandwidth.md)，了解有关在带宽不足时使用 Teams 教育版的信息。</span><span class="sxs-lookup"><span data-stu-id="48607-152">Read [here](edu-remote-low-bandwidth.md) about using Teams for Education when bandwidth is low.</span></span>

## <a name="how-to-delete-your-data"></a><span data-ttu-id="48607-153">如何删除数据</span><span class="sxs-lookup"><span data-stu-id="48607-153">How to delete your data</span></span>

<span data-ttu-id="48607-154">教育服务存储学生和教师在课堂团队中进行的操作。</span><span class="sxs-lookup"><span data-stu-id="48607-154">Education services stores student and educator actions performed in the context of a class team.</span></span> <span data-ttu-id="48607-155">此数据被视为混合数据集，因此一旦从组织中删除学生或教育者用户帐户，就不会自动将其从服务中删除。</span><span class="sxs-lookup"><span data-stu-id="48607-155">This data is considered a co-mingled data set and therefore isn't automatically deleted from the service once student or educator user accounts are deleted from your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="48607-156">删除数据会对见解分析课堂团队参与度的能力产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="48607-156">Deleting data has a negative impact on Insights' ability to analyze class team engagement over time.</span></span>

- <span data-ttu-id="48607-157">[点击这里](https://edusupport.microsoft.com/support)打开支持票证。</span><span class="sxs-lookup"><span data-stu-id="48607-157">Open a support ticket [here](https://edusupport.microsoft.com/support).</span></span> <span data-ttu-id="48607-158">支持票证必须清楚说明对 GDPR Delete DSR 操作的请求，并包含要删除的用户对象ID。</span><span class="sxs-lookup"><span data-stu-id="48607-158">The support ticket must state clearly the request for a GDPR Delete DSR operation and contain the user object ID to be deleted.</span></span> <span data-ttu-id="48607-159">无法限制删除的数据集或时间范围。</span><span class="sxs-lookup"><span data-stu-id="48607-159">There is no ability to limit the data set or time window of the deletion.</span></span>
- <span data-ttu-id="48607-160">存档后，支持票证将在队列中等待一周，以便达到合规性最低保留策略。</span><span class="sxs-lookup"><span data-stu-id="48607-160">Once filed, the support ticket waits in the queue for one week in order to meet compliance minimal retention policy.</span></span> <span data-ttu-id="48607-161">您有机会在这段时间内取消操作。</span><span class="sxs-lookup"><span data-stu-id="48607-161">You have the opportunity to cancel the operation during this time.</span></span>
- <span data-ttu-id="48607-162">一周后，教育分析小组将采取措施，确保从服务中删除所有与用户 ID 相关的数据。</span><span class="sxs-lookup"><span data-stu-id="48607-162">After one week, the Education Analytics team takes action to ensure all data related to the user ID is deleted from the service.</span></span> <span data-ttu-id="48607-163">Microsoft 支持人员将监视 ICM 票证，并在不超过 28 天的删除过程完成后通知您。</span><span class="sxs-lookup"><span data-stu-id="48607-163">Microsoft support monitors the ICM ticket and will notify you once the deletion process is complete, in no more than 28 days.</span></span>

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a><span data-ttu-id="48607-164">使用学校数据同步（SDS）关闭见解</span><span class="sxs-lookup"><span data-stu-id="48607-164">Turn Insights off and on using School Data Sync (SDS)</span></span>

<span data-ttu-id="48607-165">学校数据同步(SDS)有助于自动执行将学生信息系统 (SIS) 数据导入和同步到 Office 365 的过程。</span><span class="sxs-lookup"><span data-stu-id="48607-165">School Data Sync (SDS) helps to automate the process of importing and synchronizing Student Information System (SIS) data with Office 365.</span></span>

<span data-ttu-id="48607-166">使用见解不需要使用 SDS。</span><span class="sxs-lookup"><span data-stu-id="48607-166">The use of Insights does not require the use of SDS.</span></span> <span data-ttu-id="48607-167">但是可以随时在“**设置**” > “**管理教育版分析**”下，选择在 SDS 管理中心中关闭切换来退出教育版分析。</span><span class="sxs-lookup"><span data-stu-id="48607-167">However, you may choose to opt out from Education Analytics at any time by turning off the toggle in the SDS Admin Center under **Settings** > **Manage Education Analytics**.</span></span>

:::image type="content" source="media/class-insights-on-off.png" alt-text="启用或禁用见解的开关。":::

<span data-ttu-id="48607-169">默认情况下，启用教育版分析和见解。</span><span class="sxs-lookup"><span data-stu-id="48607-169">By default, Education Analytics, and therefore Insights, is turned on.</span></span> <span data-ttu-id="48607-170">选择退出 Google Analytics 时，我们会删除为“见解”标签收集的所有数据。重新启用 Google Analytics，我们从重新启用之时开始收集数据。</span><span class="sxs-lookup"><span data-stu-id="48607-170">When you opt out of Analytics, we delete all data collected for the Insights tab. Turn Analytics back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="48607-171">了解详细信息：[见解教师指南](https://support.microsoft.com/zh-CN/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)</span><span class="sxs-lookup"><span data-stu-id="48607-171">Learn more: [Educator's guide to Insights](https://support.microsoft.com/zh-CN/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)</span></span>
