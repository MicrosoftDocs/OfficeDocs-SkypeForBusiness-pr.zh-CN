---
title: '使用 CQD (设置呼叫质量) '
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
description: 了解如何打开和使用呼叫质量仪表板，并获取呼叫质量的摘要报告。
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112835"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="8ed15-103">使用 CQD (设置呼叫质量) </span><span class="sxs-lookup"><span data-stu-id="8ed15-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="8ed15-104">使用管理员凭据 (登录时) CQD (Microsoft 呼叫质量仪表板 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 。</span><span class="sxs-lookup"><span data-stu-id="8ed15-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="8ed15-105">或者转到 Teams 管理中心并选择"通话 **质量仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="8ed15-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理中心的通话质量仪表板按钮的屏幕截图":::

<span data-ttu-id="8ed15-107">在打开的页面上，单击 **"登录** "并输入全局管理员帐户或 Microsoft Teams 服务管理员帐户信息。</span><span class="sxs-lookup"><span data-stu-id="8ed15-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="8ed15-108">首次登录后，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="8ed15-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="8ed15-109">请记住，可能需要一个或多个小时才能处理足够的数据，才能在报告中显示有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="8ed15-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="8ed15-110">CQD 在组织范围内显示 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 2019 的呼叫和会议质量。</span><span class="sxs-lookup"><span data-stu-id="8ed15-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8ed15-111">若要将 CQD 与 Skype for Business Server 2019 一起使用，必须配置 [呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="8ed15-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="8ed15-112">在 [启动之前，请参阅"](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 计划呼叫数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="8ed15-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="8ed15-113">分配管理员角色以访问 CQD</span><span class="sxs-lookup"><span data-stu-id="8ed15-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="8ed15-114">为 [需要](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 使用该 CQD 的用户分配用于访问 CQD 的角色。</span><span class="sxs-lookup"><span data-stu-id="8ed15-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="8ed15-115">如果希望非管理员用户 (支持工程师和支持人员代理) 使用呼叫质量仪表板，您可以为这些用户分配以下角色之一，从而授予对 CQD 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ed15-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="8ed15-116">查看报表</span><span class="sxs-lookup"><span data-stu-id="8ed15-116">View reports</span></span>  |<span data-ttu-id="8ed15-117">查看 EUII 字段</span><span class="sxs-lookup"><span data-stu-id="8ed15-117">View EUII fields</span></span>  |<span data-ttu-id="8ed15-118">创建报表</span><span class="sxs-lookup"><span data-stu-id="8ed15-118">Create reports</span></span>  |<span data-ttu-id="8ed15-119">上传建筑物数据</span><span class="sxs-lookup"><span data-stu-id="8ed15-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="8ed15-120">全局管理员</span><span class="sxs-lookup"><span data-stu-id="8ed15-120">Global Administrator</span></span>     |<span data-ttu-id="8ed15-121">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-121">Yes</span></span>         |<span data-ttu-id="8ed15-122">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-122">Yes</span></span>         |<span data-ttu-id="8ed15-123">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-123">Yes</span></span>         |<span data-ttu-id="8ed15-124">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-124">Yes</span></span>         |
|<span data-ttu-id="8ed15-125">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="8ed15-125">Teams Service Administrator</span></span>     |<span data-ttu-id="8ed15-126">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-126">Yes</span></span>         |<span data-ttu-id="8ed15-127">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-127">Yes</span></span>         |<span data-ttu-id="8ed15-128">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-128">Yes</span></span>         |<span data-ttu-id="8ed15-129">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-129">Yes</span></span>         |
|<span data-ttu-id="8ed15-130">Teams 通信管理员</span><span class="sxs-lookup"><span data-stu-id="8ed15-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="8ed15-131">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-131">Yes</span></span>         |<span data-ttu-id="8ed15-132">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-132">Yes</span></span>         |<span data-ttu-id="8ed15-133">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-133">Yes</span></span>         |<span data-ttu-id="8ed15-134">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-134">Yes</span></span>         |
|<span data-ttu-id="8ed15-135">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="8ed15-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="8ed15-136">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-136">Yes</span></span>         |<span data-ttu-id="8ed15-137">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-137">Yes</span></span>         |<span data-ttu-id="8ed15-138">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-138">Yes</span></span>         |<span data-ttu-id="8ed15-139">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-139">No</span></span>         |
|<span data-ttu-id="8ed15-140">Teams 通信支持专家</span><span class="sxs-lookup"><span data-stu-id="8ed15-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="8ed15-141">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-141">Yes</span></span>         |<span data-ttu-id="8ed15-142">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-142">No</span></span>         |<span data-ttu-id="8ed15-143">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-143">Yes</span></span>         |<span data-ttu-id="8ed15-144">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-144">No</span></span>         |
|<span data-ttu-id="8ed15-145">Skype for Business 管理员</span><span class="sxs-lookup"><span data-stu-id="8ed15-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="8ed15-146">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-146">Yes</span></span>         |<span data-ttu-id="8ed15-147">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-147">Yes</span></span>         |<span data-ttu-id="8ed15-148">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-148">Yes</span></span>         |<span data-ttu-id="8ed15-149">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-149">Yes</span></span>         |
|<span data-ttu-id="8ed15-150">全局阅读器</span><span class="sxs-lookup"><span data-stu-id="8ed15-150">Global Reader</span></span> |<span data-ttu-id="8ed15-151">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-151">Yes</span></span>         |<span data-ttu-id="8ed15-152">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-152">Yes</span></span>         |<span data-ttu-id="8ed15-153">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-153">Yes</span></span>         |<span data-ttu-id="8ed15-154">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-154">No</span></span>         |
|<span data-ttu-id="8ed15-155">报告读者<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8ed15-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="8ed15-156">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-156">Yes</span></span>         |<span data-ttu-id="8ed15-157">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-157">No</span></span>         |<span data-ttu-id="8ed15-158">是</span><span class="sxs-lookup"><span data-stu-id="8ed15-158">Yes</span></span>         |<span data-ttu-id="8ed15-159">否</span><span class="sxs-lookup"><span data-stu-id="8ed15-159">No</span></span>         |

<span data-ttu-id="8ed15-160"><sup>1</sup>除阅读 CQD 报告外，报告读者还可以查看管理[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)中心内的所有活动报表和[Microsoft 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)内容包的任何报表。</span><span class="sxs-lookup"><span data-stu-id="8ed15-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="8ed15-161">如果未看到 EUII (标识信息) 并且具有允许查看此信息的角色之一，请记住，CQD 仅将 [EUII ](CQD-data-and-reports.md#euii-data) 保留 28 天。</span><span class="sxs-lookup"><span data-stu-id="8ed15-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="8ed15-162">删除超过 28 天任何内容。</span><span class="sxs-lookup"><span data-stu-id="8ed15-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="8ed15-163">有关这些角色详细信息，请参阅["关于 Office 365 管理员角色"。](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="8ed15-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="8ed15-164">首次登录后，CQD 将开始收集和处理数据。</span><span class="sxs-lookup"><span data-stu-id="8ed15-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="8ed15-165">从 2019 年 12 月开始，仍可以访问旧版 CQD (cqd.lync.com) ，尽管旧门户提供了指向最新 CQD (cqd.teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="8ed15-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="8ed15-166">最终，旧版本的 CQD 将解除授权。</span><span class="sxs-lookup"><span data-stu-id="8ed15-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="8ed15-167">自 2020 年 7 月 1 日起，较旧版本的 CQD 从最新的 CQD 访问数据。</span><span class="sxs-lookup"><span data-stu-id="8ed15-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="8ed15-168">从早期版本的 CQD 迁移建筑物数据和报表</span><span class="sxs-lookup"><span data-stu-id="8ed15-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ed15-169">自 2020 年 7 月 1 日起，无法再从旧的 CQD 迁移建筑物数据和 https://CQD.lync.com) (。</span><span class="sxs-lookup"><span data-stu-id="8ed15-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="8ed15-170">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="8ed15-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="8ed15-171">2020 年 1 月新增功能 [：下载适用于 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)的 Power BI 查询模板。</span><span class="sxs-lookup"><span data-stu-id="8ed15-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="8ed15-172">可用于分析和报告 CQD 数据的可自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="8ed15-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="8ed15-173">阅读 ["使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) "以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="8ed15-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8ed15-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ed15-174">Related topics</span></span>

[<span data-ttu-id="8ed15-175">改进和监视 Teams 的通话质量</span><span class="sxs-lookup"><span data-stu-id="8ed15-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="8ed15-176">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="8ed15-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="8ed15-177">上传租户和建筑物数据</span><span class="sxs-lookup"><span data-stu-id="8ed15-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="8ed15-178">CQD 数据和报表</span><span class="sxs-lookup"><span data-stu-id="8ed15-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="8ed15-179">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="8ed15-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="8ed15-180">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="8ed15-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="8ed15-181">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="8ed15-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="8ed15-182">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="8ed15-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
