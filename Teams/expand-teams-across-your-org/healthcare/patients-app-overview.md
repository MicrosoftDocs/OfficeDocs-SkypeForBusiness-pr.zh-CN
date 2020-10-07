---
title: '适用于团队管理员的患者应用 '
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
description: 适用于团队管理员的患者应用
ms.openlocfilehash: 1b6db686be1acbc7ee23be555c9794c644e5c5cc
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367582"
---
# <a name="patients-app-overview"></a><span data-ttu-id="8a8ed-103">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="8a8ed-103">Patients app overview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a8ed-104">**2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="8a8ed-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="8a8ed-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="8a8ed-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="8a8ed-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="8a8ed-109">使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="8a8ed-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="8a8ed-111">患者应用程序是适用于所有团队用户的 Microsoft 团队应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-111">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="8a8ed-112">该应用支持由临床工作者组成的患者护理团队 (例如，护士、医生、社会工作者) 可以策展和查看患者的列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控的情形。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-112">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>

<span data-ttu-id="8a8ed-113">应用具有两种模式：</span><span class="sxs-lookup"><span data-stu-id="8a8ed-113">The app has two modes:</span></span>

- <span data-ttu-id="8a8ed-114">通过 FHIR 连接到 EMRs 的 EMR 连接模式。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-114">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="8a8ed-115">EMR 连接模式应用保留在私人预览版中，并且感兴趣的客户或管理员可能会通过在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 中删除 microsoft 电子邮件，获取有关其 Microsoft 365 组织的信息，从而请求对应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-115">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) with information about their Microsoft 365 organization.</span></span>
- <span data-ttu-id="8a8ed-116">允许护理团队手动添加/添加患者信息的手动模式。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-116">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="8a8ed-117">应用程序位于团队应用商店中，最终用户可在私人预览版中下载。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-117">The application is available in the Teams app store for end users to download in private preview.</span></span> <span data-ttu-id="8a8ed-118">可使用团队中的 [应用设置策略](../../teams-app-setup-policies.md) 将应用限制到特定部分的用户。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-118">The app can be restricted to certain sections of users using [app setup policies](../../teams-app-setup-policies.md) in Teams.</span></span> <span data-ttu-id="8a8ed-119">若要获取对应用的访问权限，你的租户需要参与技术采纳计划 (点击 ") "。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-119">To get access to the app, your tenant needs to be part of the Technology Adoption Program (TAP).</span></span> <span data-ttu-id="8a8ed-120">请在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 上向我们发送电子邮件，以启动请求访问的流程。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-120">Please drop us an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) to start the process to request access.</span></span>

## <a name="usage-example"></a><span data-ttu-id="8a8ed-121">用法示例</span><span class="sxs-lookup"><span data-stu-id="8a8ed-121">Usage example</span></span>

<span data-ttu-id="8a8ed-122">在医疗 wards 中每个班次的舍入期内，临床医生在 nursing 工作站上进行收集，以便在拖动中讨论患者的最新更新。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-122">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="8a8ed-123">他们突出显示关键指标， (不一定是医疗的，或者它在病人的医疗记录) 上是明确的，确保患者基于其诊断的 glide 途径。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-123">They highlight the key critical metrics (not necessarily medical or that it's explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="8a8ed-124">为了围绕这些患者，"费用" 护士在一个团队中设置患者应用，其中添加了所有临床医生，并将患者添加到患者列表。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-124">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="8a8ed-125">在舍入期间，护士和其他护理 givers 在其移动设备上的患者 access Microsoft 团队和患者应用，并在其设备上更新相关的患者信息，并且在护理团队中的其他人可以看到这些更新和注释并保持同步。一天两次，在班次的开始和结束时间，他们也有多个专业的团队会议可以通过患者列表，并使用患者应用在大型显示屏上使用患者应用共享有关每个患者的信息。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-125">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-disciplinary team meetings to go over the patient list and use the Patients app to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="8a8ed-126">通常情况下，某些临床医生可能还会远程拨入这些团队会议，并且仍是讨论的一部分。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-126">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span>

## <a name="configure-patients-app"></a><span data-ttu-id="8a8ed-127">配置患者应用</span><span class="sxs-lookup"><span data-stu-id="8a8ed-127">Configure Patients app</span></span>

<span data-ttu-id="8a8ed-128">有关如何准备您的环境以使用 EMR 模式患者应用的信息，请参阅将 [电子医疗保健记录集成到 Microsoft 团队](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-128">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="8a8ed-129">你还需要查看 [Microsoft 团队中的 "管理应用设置策略"](../../teams-app-setup-policies.md) 以为你的组织启用患者应用。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-129">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<span data-ttu-id="8a8ed-130">有关最终用户如何才能访问患者应用并将其安装到他们拥有或管理的团队的信息，请参阅 [Microsoft 团队患者入门](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-130">For information on how your end users can access and install the Patients App to a team that they own or manage, see [Get started with Microsoft Teams Patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).</span></span>

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="8a8ed-131">常见问题 (常见问题) </span><span class="sxs-lookup"><span data-stu-id="8a8ed-131">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="8a8ed-132">**患者应用数据存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-132">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="8a8ed-133">最终用户输入到患者应用中的所有数据，包括列/字段架构、输入到列表中的实际数据和列表项 (（即患者) ）存储在安全和合规的 Exchange Online 基础结构中。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-133">All of the data entered by end users into the Patients app, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="8a8ed-134">所有数据都存储在与团队相关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-134">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="8a8ed-135">此体系结构使患者应用能够轻松完成数据派驻、政府云支持 (未来) 以及电子数据展示支持等其他合规性/信息保护功能。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-135">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="8a8ed-136">患者应用在团队范围内运行。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-136">The Patients app operates in a team scope.</span></span> <span data-ttu-id="8a8ed-137">你将需要为每个团队安装应用的实例。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-137">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="8a8ed-138">**从哪里可以获取患者应用？**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-138">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="8a8ed-139">如果患者应用由其管理员启用，则任何最终用户都可以转到 "团队" 应用商店，并将患者应用添加到他们所属的团队。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-139">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="8a8ed-140">有关详细信息，请参阅 [管理 Microsoft 团队中的应用设置策略](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-140">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="8a8ed-141">**我是否可以在团队中拥有患者应用的多个实例，因为这是我的拖动/单元的运营方式？**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-141">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="8a8ed-142">目前，您只能为给定团队安装一个患者应用实例，并且仅在 "常规" 频道中安装。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-142">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="8a8ed-143">但是，在应用内，可以创建多个列表来处理多通道或隔离/隔离方案。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-143">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="8a8ed-144">默认情况下，团队的所有成员都将有权访问常规频道中的 "患者" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-144">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="8a8ed-145">**是否可以导出患者应用中的所有数据？**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-145">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="8a8ed-146">目前尚不能，但此功能即将推出。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-146">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="8a8ed-147">**由于此应用适用于 PHI，因此是否有审核来防止未经授权的访问或遵守管理法规？**</span><span class="sxs-lookup"><span data-stu-id="8a8ed-147">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="8a8ed-148">是的，有。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-148">Yes, there is.</span></span> <span data-ttu-id="8a8ed-149">Microsoft 团队用户在患者应用上执行的每个单个 UI 操作都会在安全和合规中心进行审核和使用。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-149">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="8a8ed-150">在 [患者应用的审核日志](patients-audit.md)中介绍了详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-150">The details are explained in [Audit logs for Patients app](patients-audit.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a8ed-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="8a8ed-151">Related topics</span></span>

[<span data-ttu-id="8a8ed-152">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="8a8ed-152">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
