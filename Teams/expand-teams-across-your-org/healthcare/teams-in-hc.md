---
title: 适用于医疗保健组织的 Teams 入门
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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 了解医疗保健的功能，包括护理协调、安全消息、telehealth、EHR 集成和一线 worker 系统集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2654eab71d240a12f544fbee3521dacd2c49a17
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367662"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="81e13-103">适用于医疗保健组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="81e13-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="81e13-104">Microsoft 团队提供了许多适用于医院和其他医疗保健组织的功能。</span><span class="sxs-lookup"><span data-stu-id="81e13-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="81e13-105">团队功能正在开发中，可帮助医院帮助医院：</span><span class="sxs-lookup"><span data-stu-id="81e13-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="81e13-106">护理协调和协作</span><span class="sxs-lookup"><span data-stu-id="81e13-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="81e13-107">安全消息</span><span class="sxs-lookup"><span data-stu-id="81e13-107">Secure Messaging</span></span>
- <span data-ttu-id="81e13-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="81e13-108">Telehealth</span></span>
- <span data-ttu-id="81e13-109">电子医疗保健记录 (EHR) 集成</span><span class="sxs-lookup"><span data-stu-id="81e13-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="81e13-110">一线 Worker 系统集成</span><span class="sxs-lookup"><span data-stu-id="81e13-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="81e13-111">本部分内容基于团队的基础功能（如会议、呼叫和消息传递），并假设你已经在组织中部署了团队。</span><span class="sxs-lookup"><span data-stu-id="81e13-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="81e13-112">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](../../How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="81e13-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="81e13-113">护理协调-Microsoft 团队患者应用</span><span class="sxs-lookup"><span data-stu-id="81e13-113">Care Coordination - Microsoft Teams Patients app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81e13-114">**2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="81e13-114">**Effective  October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="81e13-115">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="81e13-115">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="81e13-116">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="81e13-116">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="81e13-117">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-117">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="81e13-118">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="81e13-118">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="81e13-119">使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-119">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="81e13-120">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="81e13-120">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="81e13-121">Microsoft 团队现在具有特定于医疗保健组织的护理协调解决方案，可帮助他们提供最佳的患者护理。</span><span class="sxs-lookup"><span data-stu-id="81e13-121">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="81e13-122">Crux "护理协调解决方案" （Microsoft 团队患者应用）是一种第一方选项卡应用，它与电子运行状况记录集成 (EHR) 系统使用快速医疗保健互操作性资源 ([FHIR](https://www.hl7.org/fhir/)) 界面将宝贵的医学信息引入 Microsoft 团队以实现临床协作和通信。</span><span class="sxs-lookup"><span data-stu-id="81e13-122">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="81e13-123">"护理协调" 解决方案可以与主要独立软件供应商进行交互， (Isv) ，可使用 HL7v2 和 FHIR 等现有健康数据标准将患者应用连接到 EHR 系统。</span><span class="sxs-lookup"><span data-stu-id="81e13-123">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="81e13-124">与以下行业领导人的 Microsoft 合作伙伴建立与团队的电子健康记录集成：</span><span class="sxs-lookup"><span data-stu-id="81e13-124">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="81e13-125">Datica (通过其 [CMI](https://datica.com/compliant-managed-integration/) 服务) </span><span class="sxs-lookup"><span data-stu-id="81e13-125">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="81e13-126">Infor Cloverleaf ([INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) </span><span class="sxs-lookup"><span data-stu-id="81e13-126">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="81e13-127">Redox (通过 [R ^ FHIR 服务器](https://www.redoxengine.com/fhir/)) </span><span class="sxs-lookup"><span data-stu-id="81e13-127">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="81e13-128">Dapasoft (通过 [Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) </span><span class="sxs-lookup"><span data-stu-id="81e13-128">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="81e13-129">尝试为医疗保健提供商组织实施 Microsoft 团队的 EHR 集成和互操作合作伙伴需要向患者应用提供与医疗保健提供商组织的 EHR 系统的安全且经过身份验证的连接。</span><span class="sxs-lookup"><span data-stu-id="81e13-129">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="81e13-130">这将启用单向 (只读) 将相关患者记录的流读入患者应用。</span><span class="sxs-lookup"><span data-stu-id="81e13-130">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="81e13-131">患者应用理解 FHIR 格式，因此合作伙伴还负责将聚合数据从各种其他格式（如 HL7v2 等）转换为 FHIR DSTU2 或 STU3。</span><span class="sxs-lookup"><span data-stu-id="81e13-131">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![插图突出显示护理协调和协作](../../media/ehr-1.png)

<br>

<span data-ttu-id="81e13-133">患者应用集成了电子运行状况记录 (EHR) 系统，并支持护理提供商在团队的安全平台中实时交流患者护理。</span><span class="sxs-lookup"><span data-stu-id="81e13-133">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams' secure platform.</span></span> <span data-ttu-id="81e13-134">患者应用是护理协调领域的第一大投资，旨在解决以下难题：</span><span class="sxs-lookup"><span data-stu-id="81e13-134">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="81e13-135">通过患者体验实现高效率和关键通信的低效率</span><span class="sxs-lookup"><span data-stu-id="81e13-135">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="81e13-136">带来管理负担的各自为政的信息</span><span class="sxs-lookup"><span data-stu-id="81e13-136">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="81e13-137">具有复杂且零散的协作工具的临床医生中的不满</span><span class="sxs-lookup"><span data-stu-id="81e13-137">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="81e13-138">非常低效的人员间护理协作，可能会产生太昂贵的临床时间</span><span class="sxs-lookup"><span data-stu-id="81e13-138">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="81e13-139">Microsoft 团队支持医生、临床医生、护士和其他员工通过以下方式高效协作：</span><span class="sxs-lookup"><span data-stu-id="81e13-139">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="81e13-140">成为可在 Office 文档上工作和协作的单个虚拟化团队的一部分</span><span class="sxs-lookup"><span data-stu-id="81e13-140">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="81e13-141">与需要关注的不同患者进行持续对话</span><span class="sxs-lookup"><span data-stu-id="81e13-141">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="81e13-142">将频道与选项卡配合使用来组织其工作，使用可固定信息源的选项卡中的其他帮助</span><span class="sxs-lookup"><span data-stu-id="81e13-142">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="81e13-143">将频道会议与团队的强大功能结合使用音频、视频、屏幕共享、录制和设备功能来管理日常会议</span><span class="sxs-lookup"><span data-stu-id="81e13-143">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="81e13-144">使用患者应用策展必须监控的高风险患者的列表，并从 EHR 系统中提取最新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="81e13-144">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="81e13-145">患者应用本身将以下功能添加到 Microsoft 团队：</span><span class="sxs-lookup"><span data-stu-id="81e13-145">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="81e13-146">可以在单个频道中创建多个患者列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-146">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="81e13-147">能够通过可配置的栏查看和排序患者显示的信息。</span><span class="sxs-lookup"><span data-stu-id="81e13-147">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="81e13-148">通过团队模板自动预配应用的功能。</span><span class="sxs-lookup"><span data-stu-id="81e13-148">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="81e13-149">适用于 iOS 和 Android 适用于 iOS 和 Android 的团队应用，适用于移动用户第一个医疗保健工作人员以及 Microsoft 团队 web 和桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="81e13-149">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="81e13-150">通过分析一致性语句支持 FHIR DSTU2 和 STU3 版本。</span><span class="sxs-lookup"><span data-stu-id="81e13-150">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="81e13-151">针对其用户界面上的所有视图和搜索操作的审核日志，以保护每个 HIPAA 准则的 PHI。</span><span class="sxs-lookup"><span data-stu-id="81e13-151">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="81e13-152">患者应用在团队扩展性平台上构建，并利用选项卡框架在频道内显示丰富的患者内容。</span><span class="sxs-lookup"><span data-stu-id="81e13-152">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="81e13-153">若要了解有关其他团队应用和平台本身的详细信息，请参阅 [Microsoft 团队应用](/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="81e13-153">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="81e13-154">患者应用在私人预览版中，FHIR 界面位于 beta 中。</span><span class="sxs-lookup"><span data-stu-id="81e13-154">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="81e13-155">发布的版本不应向后兼容。</span><span class="sxs-lookup"><span data-stu-id="81e13-155">Released versions are not expected to be backward compatible.</span></span>

![桌面和移动设备上患者应用的屏幕截图](../../media/ehr-2.png)

<span data-ttu-id="81e13-157">有关实现的详细信息，请参阅将 [电子医疗保健记录集成到 Microsoft 团队](patients-app.md) 中。</span><span class="sxs-lookup"><span data-stu-id="81e13-157">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="teams-templates"></a><span data-ttu-id="81e13-158">团队模板</span><span class="sxs-lookup"><span data-stu-id="81e13-158">Teams templates</span></span>

<span data-ttu-id="81e13-159">创建团队的新模板已开发为适用于医院的设置，并且预计会更多。</span><span class="sxs-lookup"><span data-stu-id="81e13-159">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="81e13-160">这使您可以更轻松地创建医疗保健工作者在各种部门或 wards 中协调病人的护理。</span><span class="sxs-lookup"><span data-stu-id="81e13-160">This makes it easier to create teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="81e13-161">请参阅 [面向医疗保健组织的团队模板入门](healthcare-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="81e13-161">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="81e13-162">团队可以为内部部门（如心脏病科）或用于护理 wards 的团队开始，并且更多模板位于开发中。</span><span class="sxs-lookup"><span data-stu-id="81e13-162">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="lists-app"></a><span data-ttu-id="81e13-163">列表应用</span><span class="sxs-lookup"><span data-stu-id="81e13-163">Lists app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="81e13-164">团队中的 "列表" 应用可帮助团队跟踪信息和组织工作。</span><span class="sxs-lookup"><span data-stu-id="81e13-164">The Lists app in Teams helps teams track information and organize work.</span></span> <span data-ttu-id="81e13-165">为所有团队用户预安装应用，并且该应用在每个团队和频道中均可用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="81e13-165">The app is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="81e13-166">可以从预定义的模板或将数据导入到 Excel 中从头开始创建列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-166">Lists can be created from scratch, from predefined templates, or by importing data to Excel.</span></span>

<span data-ttu-id="81e13-167">护理团队可以使用患者模板开始使用。</span><span class="sxs-lookup"><span data-stu-id="81e13-167">Care teams can use the Patients template to get started.</span></span> <span data-ttu-id="81e13-168">他们可以创建列表来跟踪病人的需求和状况。</span><span class="sxs-lookup"><span data-stu-id="81e13-168">They can create lists to track the needs and status of patients.</span></span> <span data-ttu-id="81e13-169">可将 Excel 电子表格中的现有患者数据引入到团队中以创建列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-169">Existing patient data on Excel spreadsheets can be brought in to create a list in Teams.</span></span> <span data-ttu-id="81e13-170">这些列表可用于诸如倒圆角和患者监视等方案来协调护理。</span><span class="sxs-lookup"><span data-stu-id="81e13-170">These lists can be used for scenarios such as rounds and patient monitoring to coordinate care.</span></span>

<span data-ttu-id="81e13-171">例如，收费护士在包含所有护理团队成员的团队中创建一个患者列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-171">For example, a charge nurse creates a patient list in a team that includes all care team members.</span></span> <span data-ttu-id="81e13-172">在舍入过程中，护理团队在其移动设备上访问团队并更新列表中的患者信息，团队中的每个人都可以查看它们以保持同步。在 glide 的舍入会话中，护理团队收集以讨论和评估关键运行状况性能指标以确保患者在合适的路径上，他们可以使用大型显示屏幕上的团队共享此信息。</span><span class="sxs-lookup"><span data-stu-id="81e13-172">During rounds, the care team access Teams on their mobile devices and update patient information in the list, which everyone on the team can view to stay in sync. At rounding sessions where the care team gathers to discuss and evaluate key health performance metrics to ensure a patient is on the right glide path to discharge, they can share this information using Teams on a large display screen.</span></span> <span data-ttu-id="81e13-173">不在网站上的护理团队成员可以远程加入。</span><span class="sxs-lookup"><span data-stu-id="81e13-173">Care team members who aren't on site can join remotely.</span></span>

<span data-ttu-id="81e13-174">下面是为患者舍入设置的示例列表。</span><span class="sxs-lookup"><span data-stu-id="81e13-174">Here's an example list which was set up for patient rounding.</span></span>

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者舍入示例列表的屏幕截图":::

<span data-ttu-id="81e13-176">若要了解详细信息，请参阅 [管理团队中组织的列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="81e13-176">To learn more, see [Manage the Lists app for your organization in Teams](../../manage-lists-app.md).</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="81e13-177">安全消息</span><span class="sxs-lookup"><span data-stu-id="81e13-177">Secure Messaging</span></span>

<span data-ttu-id="81e13-178">安全邮件支持在护理团队内进行协作，包括以下几项新功能：</span><span class="sxs-lookup"><span data-stu-id="81e13-178">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="81e13-179">邮件发件人可以为其邮件设置特殊优先级，以便收件人在阅读邮件之前反复收到通知。</span><span class="sxs-lookup"><span data-stu-id="81e13-179">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="81e13-180">邮件发件人可以请求已读回执，这样当邮件收件人阅读邮件时，会收到通知。</span><span class="sxs-lookup"><span data-stu-id="81e13-180">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="81e13-181">结合这些功能，可以更快地注意紧急邮件，并确保邮件已接收和阅读。</span><span class="sxs-lookup"><span data-stu-id="81e13-181">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="81e13-182">使用这些功能的新的护理团队可以在每个患者的基础上创建。</span><span class="sxs-lookup"><span data-stu-id="81e13-182">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="81e13-183">这些功能是基于策略的，可分配给个人或整个团队。</span><span class="sxs-lookup"><span data-stu-id="81e13-183">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="81e13-184">有关 [医疗保健组织的安全邮件策略](messaging-policies-hc.md) 的详细信息，请参阅入门。</span><span class="sxs-lookup"><span data-stu-id="81e13-184">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="81e13-185">同时与安全消息相关的功能是拥有受医疗保健组织联盟的其他租户，从而实现了更丰富的租户间通信。</span><span class="sxs-lookup"><span data-stu-id="81e13-185">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="81e13-186"> (请参阅 [管理 Microsoft 团队) 中的 "管理外部访问 (联合身份验证") ](../../manage-external-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="81e13-186">(See [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="81e13-187">一线工作人员集成</span><span class="sxs-lookup"><span data-stu-id="81e13-187">Firstline Worker integration</span></span>

<span data-ttu-id="81e13-188">Microsoft 团队与一线工作人员集成，可用于协调倒班人员配备功能。</span><span class="sxs-lookup"><span data-stu-id="81e13-188">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span> <span data-ttu-id="81e13-189">请参阅 [在 Microsoft 团队中管理你的组织的倒班应用](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="81e13-189">See [Manage the Shifts app for your organization in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
