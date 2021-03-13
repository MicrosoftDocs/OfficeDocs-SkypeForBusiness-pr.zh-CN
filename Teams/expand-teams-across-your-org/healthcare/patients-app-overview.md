---
title: '适用于 Teams 管理员的"患者"应用 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解适用于 Teams 管理员的"患者"应用
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803500"
---
# <a name="patients-app-overview"></a><span data-ttu-id="6512f-103">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="6512f-103">Patients app overview</span></span>

> [!NOTE]
> <span data-ttu-id="6512f-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="6512f-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="6512f-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="6512f-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="6512f-106">与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="6512f-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="6512f-107">用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="6512f-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="6512f-108">借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。</span><span class="sxs-lookup"><span data-stu-id="6512f-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="6512f-109">查看列表的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="6512f-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="6512f-110">若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="6512f-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="6512f-111">"患者"应用程序是一款可用于所有 Teams 用户的 Microsoft Teams 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="6512f-111">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="6512f-112">通过该应用，由患者健康团队（如医师、医师、社保等）组成，他们可针对各种方案（从圆形和内联团队会议到常规患者监视）创建和审阅患者列表。</span><span class="sxs-lookup"><span data-stu-id="6512f-112">The app enables patient health teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>

<span data-ttu-id="6512f-113">该应用有两种模式：</span><span class="sxs-lookup"><span data-stu-id="6512f-113">The app has two modes:</span></span>

- <span data-ttu-id="6512f-114">通过 FHIR 连接到 EMR 的 EMR 连接模式。</span><span class="sxs-lookup"><span data-stu-id="6512f-114">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="6512f-115">连接 EMR 模式的应用将保留在专用预览中，感兴趣的客户或管理员可能会通过退出 microsoft 电子邮件（包含其 Microsoft 365 组织相关信息） [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 来请求访问该应用。</span><span class="sxs-lookup"><span data-stu-id="6512f-115">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) with information about their Microsoft 365 organization.</span></span>
- <span data-ttu-id="6512f-116">使运行状况团队可以手动添加/引入患者信息的手动模式。</span><span class="sxs-lookup"><span data-stu-id="6512f-116">The manual mode that enables health teams to manually add/bring in patient information.</span></span> <span data-ttu-id="6512f-117">该应用程序可在 Teams 应用商店中供最终用户以专用预览版下载。</span><span class="sxs-lookup"><span data-stu-id="6512f-117">The application is available in the Teams app store for end users to download in private preview.</span></span> <span data-ttu-id="6512f-118">在 Teams 中，应用只能使用 [应用设置策略](../../teams-app-setup-policies.md) 特定分区的用户。</span><span class="sxs-lookup"><span data-stu-id="6512f-118">The app can be restricted to certain sections of users using [app setup policies](../../teams-app-setup-policies.md) in Teams.</span></span> <span data-ttu-id="6512f-119">若要获取该应用，租户需成为技术采用计划 （TAP） 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6512f-119">To get access to the app, your tenant needs to be part of the Technology Adoption Program (TAP).</span></span> <span data-ttu-id="6512f-120">请在联系你 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 电子邮件，以开始请求访问的流程。</span><span class="sxs-lookup"><span data-stu-id="6512f-120">Please drop us an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) to start the process to request access.</span></span>

## <a name="usage-example"></a><span data-ttu-id="6512f-121">用法示例</span><span class="sxs-lookup"><span data-stu-id="6512f-121">Usage example</span></span>

<span data-ttu-id="6512f-122">在每周值班期间，医师在医疗站集合，与患者讨论进度的最新更新。</span><span class="sxs-lookup"><span data-stu-id="6512f-122">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="6512f-123">他们着重强调关键关键指标（不一定是医疗指标，或者明确记录患者医疗记录），并确保患者按照患者患者护理，选择正确的方法。</span><span class="sxs-lookup"><span data-stu-id="6512f-123">They highlight the key critical metrics (not necessarily medical or that it's explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="6512f-124">为了四处环绕这些患者，收费中心在添加了所有医师的团队中设置患者应用并将患者添加到患者列表。</span><span class="sxs-lookup"><span data-stu-id="6512f-124">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="6512f-125">在检查期间，患者的患者和其他患者护理人员会通过自己的移动设备访问 Microsoft Teams 和患者应用，并更新其设备上相关的患者信息，这样运行状况团队中的其他人就可以查看这些更新和笔记，保持同步。一天两次，在轮班开始和结束时，他们还会举行多方团队会议来检查患者列表，使用"患者"应用自行为，并共享有关使用大型显示屏上的"患者"应用的每个患者的信息。</span><span class="sxs-lookup"><span data-stu-id="6512f-125">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the health team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-disciplinary team meetings to go over the patient list and use the Patients app to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="6512f-126">通常情况下，某些医师可能还远程拨入这些 Teams 会议，他们仍然参与讨论。</span><span class="sxs-lookup"><span data-stu-id="6512f-126">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span>

## <a name="configure-patients-app"></a><span data-ttu-id="6512f-127">配置"患者"应用</span><span class="sxs-lookup"><span data-stu-id="6512f-127">Configure Patients app</span></span>

<span data-ttu-id="6512f-128">若要了解如何为环境准备使用 EMR 模式患者应用，请参阅 [电子医疗保健记录集成到 Microsoft Teams](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="6512f-128">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="6512f-129">还需要查看有关在 Microsoft Teams [管理应用设置策略](../../teams-app-setup-policies.md) 为组织启用"患者"应用的信息。</span><span class="sxs-lookup"><span data-stu-id="6512f-129">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<span data-ttu-id="6512f-130">有关你的最终用户如何访问这些应用程序并安装到他们拥有或管理的团队的信息，请参阅 [Microsoft Teams 患者信息](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。</span><span class="sxs-lookup"><span data-stu-id="6512f-130">For information on how your end users can access and install the Patients App to a team that they own or manage, see [Get started with Microsoft Teams Patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).</span></span>

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="6512f-131">常见问题 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="6512f-131">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="6512f-132">**"患者"应用数据存储在什么位置？**</span><span class="sxs-lookup"><span data-stu-id="6512f-132">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="6512f-133">最终用户在"患者"应用中输入的所有数据，包括列/字段架构，输入到列表和列表项（即患者）的实际数据，均存储在安全合规的 Exchange Online 基础结构中。</span><span class="sxs-lookup"><span data-stu-id="6512f-133">All of the data entered by end users into the Patients app, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="6512f-134">所有数据存储在与团队关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="6512f-134">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="6512f-135">此体系结构使 Patients 应用可以轻松满足数据驻留、政府云支持（即将将来提供）和其他合规性/信息保护功能（如电子数据展示支持）。</span><span class="sxs-lookup"><span data-stu-id="6512f-135">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="6512f-136">"患者"应用在团队范围内运行。</span><span class="sxs-lookup"><span data-stu-id="6512f-136">The Patients app operates in a team scope.</span></span> <span data-ttu-id="6512f-137">需要按团队安装应用程序实例。</span><span class="sxs-lookup"><span data-stu-id="6512f-137">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="6512f-138">**我可以从哪里获取"患者"应用？**</span><span class="sxs-lookup"><span data-stu-id="6512f-138">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="6512f-139">如果管理员为组织启用了"患者"应用，任何最终用户都可以转到 Teams 应用商店，将"患者"应用添加到他们加入的团队。</span><span class="sxs-lookup"><span data-stu-id="6512f-139">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="6512f-140">要了解详细信息，请参阅[在 Teams 中管理应用设置策略](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6512f-140">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="6512f-141">**能否在团队中有多个"患者"应用实例，因为这两个组都进行操作？**</span><span class="sxs-lookup"><span data-stu-id="6512f-141">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="6512f-142">目前，你只能为给定团队安装一个"患者"应用实例，只能在常规频道中安装。</span><span class="sxs-lookup"><span data-stu-id="6512f-142">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="6512f-143">但在应用内，可创建多个列表以解决多频道或隔离/分隔方案。</span><span class="sxs-lookup"><span data-stu-id="6512f-143">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="6512f-144">默认情况下，团队的所有成员将有权访问常规频道中的"患者"选项卡。</span><span class="sxs-lookup"><span data-stu-id="6512f-144">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="6512f-145">**我能否从"患者"应用导出所有数据？**</span><span class="sxs-lookup"><span data-stu-id="6512f-145">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="6512f-146">目前还不会，但即将推出此功能。</span><span class="sxs-lookup"><span data-stu-id="6512f-146">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="6512f-147">**由于此应用容纳 PREVENT，因此是否有审核以防止未经授权的访问或遵守法规？**</span><span class="sxs-lookup"><span data-stu-id="6512f-147">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="6512f-148">是的，有。</span><span class="sxs-lookup"><span data-stu-id="6512f-148">Yes, there is.</span></span> <span data-ttu-id="6512f-149">安全与合规中心会审核 Microsoft Teams 用户对"患者"应用执行的每一个 UI 操作。</span><span class="sxs-lookup"><span data-stu-id="6512f-149">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="6512f-150">在"患者" [审核日志中介绍了详细信息](patients-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="6512f-150">The details are explained in [Audit logs for Patients app](patients-audit.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6512f-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="6512f-151">Related topics</span></span>

[<span data-ttu-id="6512f-152">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="6512f-152">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
