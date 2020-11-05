---
title: '设置通话质量仪表板 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解如何打开和使用呼叫质量仪表板，获取通话质量的摘要报告。
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918652"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="3a2d0-103">设置通话质量仪表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="3a2d0-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="3a2d0-104">打开 Microsoft 通话质量仪表板 (CQD) ， [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (用管理员凭据登录) 。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="3a2d0-105">或转到 "团队管理中心"，然后选择 " **呼叫质量" 仪表板** 。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

<span data-ttu-id="3a2d0-107">在打开的页面上，单击 " **登录** "，然后输入全局管理员帐户或 Microsoft 团队服务管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="3a2d0-108">第一次登录后，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="3a2d0-109">请记住，可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="3a2d0-110">CQD 显示呼叫和会议质量、组织范围级别、Microsoft 团队、Skype for business Online 和 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3a2d0-111">要将 CQD 与 Skype for Business Server 2019 配合使用，您必须 [配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="3a2d0-112">请参阅在开始之前 [计划通话数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="3a2d0-113">分配管理员角色以访问 CQD</span><span class="sxs-lookup"><span data-stu-id="3a2d0-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="3a2d0-114">将 CQD 的 [角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 分配给需要使用它的人员。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="3a2d0-115">如果您希望非管理员用户 (例如支持工程师和帮助台工程师) 使用 "呼叫质量" 仪表板，则可以为这些用户分配以下角色之一，从而提供对 CQD 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="3a2d0-116">查看报表</span><span class="sxs-lookup"><span data-stu-id="3a2d0-116">View reports</span></span>  |<span data-ttu-id="3a2d0-117">查看 EUII 字段</span><span class="sxs-lookup"><span data-stu-id="3a2d0-117">View EUII fields</span></span>  |<span data-ttu-id="3a2d0-118">创建报表</span><span class="sxs-lookup"><span data-stu-id="3a2d0-118">Create reports</span></span>  |<span data-ttu-id="3a2d0-119">上载构建数据</span><span class="sxs-lookup"><span data-stu-id="3a2d0-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="3a2d0-120">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="3a2d0-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="3a2d0-121">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-121">Yes</span></span>         |<span data-ttu-id="3a2d0-122">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-122">Yes</span></span>         |<span data-ttu-id="3a2d0-123">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-123">Yes</span></span>         |<span data-ttu-id="3a2d0-124">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-124">Yes</span></span>         |
|<span data-ttu-id="3a2d0-125">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="3a2d0-125">Teams Service Administrator</span></span>     |<span data-ttu-id="3a2d0-126">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-126">Yes</span></span>         |<span data-ttu-id="3a2d0-127">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-127">Yes</span></span>         |<span data-ttu-id="3a2d0-128">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-128">Yes</span></span>         |<span data-ttu-id="3a2d0-129">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-129">Yes</span></span>         |
|<span data-ttu-id="3a2d0-130">Teams 通信管理员</span><span class="sxs-lookup"><span data-stu-id="3a2d0-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="3a2d0-131">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-131">Yes</span></span>         |<span data-ttu-id="3a2d0-132">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-132">Yes</span></span>         |<span data-ttu-id="3a2d0-133">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-133">Yes</span></span>         |<span data-ttu-id="3a2d0-134">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-134">Yes</span></span>         |
|<span data-ttu-id="3a2d0-135">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="3a2d0-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="3a2d0-136">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-136">Yes</span></span>         |<span data-ttu-id="3a2d0-137">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-137">Yes</span></span>         |<span data-ttu-id="3a2d0-138">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-138">Yes</span></span>         |<span data-ttu-id="3a2d0-139">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-139">No</span></span>         |
|<span data-ttu-id="3a2d0-140">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="3a2d0-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="3a2d0-141">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-141">Yes</span></span>         |<span data-ttu-id="3a2d0-142">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-142">No</span></span>         |<span data-ttu-id="3a2d0-143">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-143">Yes</span></span>         |<span data-ttu-id="3a2d0-144">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-144">No</span></span>         |
|<span data-ttu-id="3a2d0-145">Skype for Business 管理员</span><span class="sxs-lookup"><span data-stu-id="3a2d0-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="3a2d0-146">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-146">Yes</span></span>         |<span data-ttu-id="3a2d0-147">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-147">Yes</span></span>         |<span data-ttu-id="3a2d0-148">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-148">Yes</span></span>         |<span data-ttu-id="3a2d0-149">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-149">Yes</span></span>         |
|<span data-ttu-id="3a2d0-150">Azure AD 全局阅读器</span><span class="sxs-lookup"><span data-stu-id="3a2d0-150">Azure AD Global Reader</span></span> |<span data-ttu-id="3a2d0-151">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-151">Yes</span></span>         |<span data-ttu-id="3a2d0-152">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-152">Yes</span></span>         |<span data-ttu-id="3a2d0-153">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-153">Yes</span></span>         |<span data-ttu-id="3a2d0-154">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-154">No</span></span>         |
|<span data-ttu-id="3a2d0-155">Office 365 报告阅读器<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3a2d0-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="3a2d0-156">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-156">Yes</span></span>         |<span data-ttu-id="3a2d0-157">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-157">No</span></span>         |<span data-ttu-id="3a2d0-158">是</span><span class="sxs-lookup"><span data-stu-id="3a2d0-158">Yes</span></span>         |<span data-ttu-id="3a2d0-159">否</span><span class="sxs-lookup"><span data-stu-id="3a2d0-159">No</span></span>         |

<span data-ttu-id="3a2d0-160"><sup>1</sup> 除了阅读 CQD 报表，Office 365 报表读者还可以查看管理中心中的所有 [活动报表](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 和 [Microsoft 365 采纳内容包](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的所有报表。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="3a2d0-161">如果您没有看到 [EUII (最终用户的可识别信息) ](CQD-data-and-reports.md#euii-data) ，并且您拥有允许查看此信息的角色之一，请记住 CQD 仅保留28天的 EUII。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="3a2d0-162">任何早于28天的内容都将被删除。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="3a2d0-163">有关这些角色的详细信息，请参阅 [关于 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="3a2d0-164">第一次登录后，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="3a2d0-165">从2019年12月到，您仍然可以访问 CQD (cqd.lync.com) 的旧版本，尽管旧版门户提供了指向最新 CQD (cqd.teams.microsoft.com) 的链接。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="3a2d0-166">最终，旧版本的 CQD 将会停止。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="3a2d0-167">从2020年7月1日起，较早版本的 CQD 访问最新 CQD 中的数据。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="3a2d0-168">从早期版本的 CQD 中迁移构建数据和报表</span><span class="sxs-lookup"><span data-stu-id="3a2d0-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a2d0-169">从2020年7月1日起，您无法再从旧的 CQD (中进行数据和报告的迁移 https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="3a2d0-170">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="3a2d0-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="3a2d0-171">2020年1月 [的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="3a2d0-172">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="3a2d0-173">已阅读 " [使用 POWER BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) " 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="3a2d0-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3a2d0-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="3a2d0-174">Related topics</span></span>

[<span data-ttu-id="3a2d0-175">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="3a2d0-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="3a2d0-176">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="3a2d0-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="3a2d0-177">上载租户和生成数据</span><span class="sxs-lookup"><span data-stu-id="3a2d0-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="3a2d0-178">CQD 数据和报告</span><span class="sxs-lookup"><span data-stu-id="3a2d0-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="3a2d0-179">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="3a2d0-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="3a2d0-180">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="3a2d0-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="3a2d0-181">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="3a2d0-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="3a2d0-182">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="3a2d0-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
