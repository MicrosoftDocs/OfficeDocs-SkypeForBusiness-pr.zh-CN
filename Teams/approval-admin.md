---
title: Teams 中的审批应用程序可用性
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的审批应用程序可用性。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909516"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="81e91-103">Teams 审批应用可用性</span><span class="sxs-lookup"><span data-stu-id="81e91-103">Teams Approvals app availability</span></span>

<span data-ttu-id="81e91-104">审批应用作为个人应用可供所有 Microsoft Teams 用户使用。</span><span class="sxs-lookup"><span data-stu-id="81e91-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="81e91-105">"审批"应用提供了一种简单方法，在 Teams 中为结构化和非结构化审批提供审核、合规性、责任和工作流。</span><span class="sxs-lookup"><span data-stu-id="81e91-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![显示审批应用](media/approvals-selection.png)

<span data-ttu-id="81e91-107">用户可以固定"审批"应用以将其保存到菜单栏。</span><span class="sxs-lookup"><span data-stu-id="81e91-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![显示具有固定选项的审批应用](media/approvalApp-pin.png)

<span data-ttu-id="81e91-109">从"审批"应用创建的第一个审批将触发在默认通用数据服务 (CDS) 预配。</span><span class="sxs-lookup"><span data-stu-id="81e91-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="81e91-110">从"审批"应用创建的审批将存储在默认 CDS 环境中。</span><span class="sxs-lookup"><span data-stu-id="81e91-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="81e91-111">本文介绍"审批"应用要求和角色。</span><span class="sxs-lookup"><span data-stu-id="81e91-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="81e91-112">所需的权限和许可证</span><span class="sxs-lookup"><span data-stu-id="81e91-112">Required permissions and licenses</span></span>

<span data-ttu-id="81e91-113">若要使用"审批"应用，需要以下项目的权限：</span><span class="sxs-lookup"><span data-stu-id="81e91-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="81e91-114">创建 Microsoft CDS 数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="81e91-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="81e91-115">flow.microsoft.com [](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="81e91-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="81e91-116">目标环境中管理员角色。</span><span class="sxs-lookup"><span data-stu-id="81e91-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="81e91-117">[Power Automate、Office](https://docs.microsoft.com/power-automate/get-started-approvals)365 或 Dynamics 365 的许可证。</span><span class="sxs-lookup"><span data-stu-id="81e91-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="81e91-118">使用 CDS 存储</span><span class="sxs-lookup"><span data-stu-id="81e91-118">Storage with CDS</span></span>

<span data-ttu-id="81e91-119">COMMON Data Model (CDM) 是 CDS 中的业务和分析应用程序使用的共享数据语言。</span><span class="sxs-lookup"><span data-stu-id="81e91-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="81e91-120">它由 Microsoft 和合作伙伴发布的一组标准化可扩展数据架构组成，可在应用程序和业务流程之间实现数据的一致性及其含义。</span><span class="sxs-lookup"><span data-stu-id="81e91-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="81e91-121">详细了解 Microsoft [Power Platform 的常见数据模型](https://docs.microsoft.com/power-automate/get-started-approvals)。</span><span class="sxs-lookup"><span data-stu-id="81e91-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="81e91-122">了解有关"审批 ["工作流的更多内容](https://docs.microsoft.com/power-automate/modern-approvals)。</span><span class="sxs-lookup"><span data-stu-id="81e91-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="81e91-123">审批 Teams 应用权限</span><span class="sxs-lookup"><span data-stu-id="81e91-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="81e91-124">"审批团队"应用允许你访问以下功能：</span><span class="sxs-lookup"><span data-stu-id="81e91-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="81e91-125">接收你向它提供的消息和数据。</span><span class="sxs-lookup"><span data-stu-id="81e91-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="81e91-126">向您发送消息和通知。</span><span class="sxs-lookup"><span data-stu-id="81e91-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="81e91-127">在没有 Teams 提供的标头的情况下呈现个人应用和对话框。</span><span class="sxs-lookup"><span data-stu-id="81e91-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="81e91-128">访问个人资料信息，例如姓名、电子邮件地址、公司名称和首选语言。</span><span class="sxs-lookup"><span data-stu-id="81e91-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="81e91-129">接收团队成员在频道中提供的消息和数据。</span><span class="sxs-lookup"><span data-stu-id="81e91-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="81e91-130">在频道中发送消息和通知。</span><span class="sxs-lookup"><span data-stu-id="81e91-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="81e91-131">访问团队的信息：</span><span class="sxs-lookup"><span data-stu-id="81e91-131">Access your team's information:</span></span>
  - <span data-ttu-id="81e91-132">团队名称</span><span class="sxs-lookup"><span data-stu-id="81e91-132">team name</span></span>
  - <span data-ttu-id="81e91-133">频道列表</span><span class="sxs-lookup"><span data-stu-id="81e91-133">channel list</span></span>
  - <span data-ttu-id="81e91-134">名单 (团队成员的姓名和电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="81e91-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="81e91-135">使用团队的信息联系他们。</span><span class="sxs-lookup"><span data-stu-id="81e91-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="81e91-136">禁用"审批"应用</span><span class="sxs-lookup"><span data-stu-id="81e91-136">Disable the Approvals app</span></span>

<span data-ttu-id="81e91-137">"审批"应用默认可用。</span><span class="sxs-lookup"><span data-stu-id="81e91-137">The Approvals app is available by default.</span></span> <span data-ttu-id="81e91-138">可以在 Teams 管理中心禁用该应用。</span><span class="sxs-lookup"><span data-stu-id="81e91-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="81e91-139">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="81e91-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="81e91-140">展开 **Teams 应用，** 然后选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="81e91-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="81e91-141">搜索"审批"应用。</span><span class="sxs-lookup"><span data-stu-id="81e91-141">Search for the Approvals app.</span></span>

![显示管理中心导航，突出显示"管理> Teams 应用](media/manage-approval-apps.png)

  4. <span data-ttu-id="81e91-143">选择"审批"。</span><span class="sxs-lookup"><span data-stu-id="81e91-143">Select Approvals.</span></span>

  5. <span data-ttu-id="81e91-144">选择切换开关，为组织禁用应用。</span><span class="sxs-lookup"><span data-stu-id="81e91-144">Select the toggle to disable the app for your organization.</span></span>

![显示"审批"应用的详细信息](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="81e91-146">保留策略</span><span class="sxs-lookup"><span data-stu-id="81e91-146">Retention policy</span></span>

<span data-ttu-id="81e91-147">从"审批"应用创建的审批存储在默认 CDS 环境中，该环境目前不支持备份。</span><span class="sxs-lookup"><span data-stu-id="81e91-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="81e91-148">详细了解如何备份[和还原环境 - Power Platform \| Microsoft Docs。](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)</span><span class="sxs-lookup"><span data-stu-id="81e91-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="81e91-149">审核</span><span class="sxs-lookup"><span data-stu-id="81e91-149">Auditing</span></span>

<span data-ttu-id="81e91-150">审批应用记录 Microsoft 365 安全与合规中心内的审核事件。</span><span class="sxs-lookup"><span data-stu-id="81e91-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="81e91-151">可以查看审核日志。</span><span class="sxs-lookup"><span data-stu-id="81e91-151">You can view the audit log.</span></span>

1. <span data-ttu-id="81e91-152">转到 Microsoft 365 合规性网站。</span><span class="sxs-lookup"><span data-stu-id="81e91-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="81e91-153">选择" **审核"** 部分。</span><span class="sxs-lookup"><span data-stu-id="81e91-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="81e91-154">在 Microsoft **Teams 审批活动下搜索活动**。</span><span class="sxs-lookup"><span data-stu-id="81e91-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="81e91-155">可以搜索以下活动：</span><span class="sxs-lookup"><span data-stu-id="81e91-155">You can search for the following activities:</span></span>

- <span data-ttu-id="81e91-156">创建新的审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-156">Create new approval request</span></span>

- <span data-ttu-id="81e91-157">查看审批请求详细信息</span><span class="sxs-lookup"><span data-stu-id="81e91-157">View approval request details</span></span>

- <span data-ttu-id="81e91-158">已批准的审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-158">Approved approval request</span></span>

- <span data-ttu-id="81e91-159">已拒绝审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-159">Rejected approval request</span></span>

- <span data-ttu-id="81e91-160">已取消审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-160">Canceled approval request</span></span>

- <span data-ttu-id="81e91-161">共享审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-161">Shared approval request</span></span>

- <span data-ttu-id="81e91-162">附加到审批请求的文件</span><span class="sxs-lookup"><span data-stu-id="81e91-162">File attached to approval request</span></span>

- <span data-ttu-id="81e91-163">重新分配的审批请求</span><span class="sxs-lookup"><span data-stu-id="81e91-163">Reassigned approval request</span></span>

- <span data-ttu-id="81e91-164">向审批请求添加了电子签名</span><span class="sxs-lookup"><span data-stu-id="81e91-164">Added e-signature to approval request</span></span>

<span data-ttu-id="81e91-165">若要在 Flow 中访问更多审核审批，请为主要审批实体（审批、审批请求和审批响应）在默认环境中启用和配置审核。</span><span class="sxs-lookup"><span data-stu-id="81e91-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="81e91-166">创建、更新和删除操作是审批记录的可审核事件。</span><span class="sxs-lookup"><span data-stu-id="81e91-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="81e91-167">详细了解审核数据和[用户活动以确保安全性和符合性 - Power Platform \| Microsoft Docs。](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)</span><span class="sxs-lookup"><span data-stu-id="81e91-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="81e91-168">可以在 Microsoft 365 安全与合规中心 [进一步自定义审核](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="81e91-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="81e91-169">若要使用预配置的报表，请登录到 Microsoft 365 安全与合规。</span><span class="sxs-lookup"><span data-stu-id="81e91-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="81e91-170">选择 **"搜索&调查**。</span><span class="sxs-lookup"><span data-stu-id="81e91-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="81e91-171">搜索审核日志并选择 **Dynamics 365 活动** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="81e91-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="81e91-172">详细了解[Microsoft Dataverse 和模型驱动的应用活动日志记录 - Power Platform。](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)</span><span class="sxs-lookup"><span data-stu-id="81e91-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="81e91-173">安全性</span><span class="sxs-lookup"><span data-stu-id="81e91-173">Security</span></span>

<span data-ttu-id="81e91-174">从 Teams 审批应用中，用户可以创建新的审批并查看已发送和收到的审批。</span><span class="sxs-lookup"><span data-stu-id="81e91-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="81e91-175">除非用户是请求的回复者或查看者，否则他们无法访问其他人创建的审批。</span><span class="sxs-lookup"><span data-stu-id="81e91-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="81e91-176">如果用户是创建审批的聊天或频道的一部分，则他们将被赋予请求的查看者角色。</span><span class="sxs-lookup"><span data-stu-id="81e91-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="81e91-177">如果在创建审批时未赋予他们该角色，他们无法对请求采取措施。</span><span class="sxs-lookup"><span data-stu-id="81e91-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
