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
description: 适用于医疗保健组织的 Teams 入门
ms.openlocfilehash: 15e10a69174787d104a990f8b71a6e8ef4f8be04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147685"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="ad757-103">适用于医疗保健组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="ad757-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="ad757-104">Microsoft 团队提供了许多适用于医院和其他医疗保健组织的功能。</span><span class="sxs-lookup"><span data-stu-id="ad757-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="ad757-105">团队功能正在开发中，可帮助医院帮助医院：</span><span class="sxs-lookup"><span data-stu-id="ad757-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="ad757-106">护理协调和协作</span><span class="sxs-lookup"><span data-stu-id="ad757-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="ad757-107">安全消息</span><span class="sxs-lookup"><span data-stu-id="ad757-107">Secure Messaging</span></span>
- <span data-ttu-id="ad757-108">Telehealth</span><span class="sxs-lookup"><span data-stu-id="ad757-108">Telehealth</span></span>
- <span data-ttu-id="ad757-109">电子医疗保健记录（EHR）集成</span><span class="sxs-lookup"><span data-stu-id="ad757-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="ad757-110">一线 Worker 系统集成</span><span class="sxs-lookup"><span data-stu-id="ad757-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="ad757-111">本部分内容基于团队的基础功能（如会议、呼叫和消息传递），并假设你已经在组织中部署了团队。</span><span class="sxs-lookup"><span data-stu-id="ad757-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="ad757-112">如果尚未推出团队，请先阅读[如何展示 Microsoft 团队](../../How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ad757-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="ad757-113">护理协调-Microsoft 团队患者应用</span><span class="sxs-lookup"><span data-stu-id="ad757-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="ad757-114">Microsoft 团队现在具有特定于医疗保健组织的护理协调解决方案，可帮助他们提供最佳的患者护理。</span><span class="sxs-lookup"><span data-stu-id="ad757-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="ad757-115">护理协调解决方案的 crux （Microsoft 团队患者应用）是第一方选项卡应用，它与使用快速医疗保健互操作性资源（[FHIR](https://www.hl7.org/fhir/)）接口的电子医疗记录（EHR）系统集成，以将宝贵的医疗信息引入 Microsoft 团队，以实现临床协作和通信。</span><span class="sxs-lookup"><span data-stu-id="ad757-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="ad757-116">"护理协调" 解决方案可以与主要独立软件供应商（Isv）进行交互，这些供应商（Isv）可以使用现有的运行状况数据标准（如 HL7v2 和 FHIR）将患者应用连接到 EHR 系统。</span><span class="sxs-lookup"><span data-stu-id="ad757-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="ad757-117">与以下行业领导人的 Microsoft 合作伙伴建立与团队的电子健康记录集成：</span><span class="sxs-lookup"><span data-stu-id="ad757-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="ad757-118">Datica （通过其[CMI](https://datica.com/compliant-managed-integration/)产品）</span><span class="sxs-lookup"><span data-stu-id="ad757-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="ad757-119">Infor Cloverleaf （通过[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）</span><span class="sxs-lookup"><span data-stu-id="ad757-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="ad757-120">Redox （通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/)）</span><span class="sxs-lookup"><span data-stu-id="ad757-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="ad757-121">Dapasoft （通过[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)）</span><span class="sxs-lookup"><span data-stu-id="ad757-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="ad757-122">尝试为医疗保健提供商组织实施 Microsoft 团队的 EHR 集成和互操作合作伙伴需要向患者应用提供与医疗保健提供商组织的 EHR 系统的安全且经过身份验证的连接。</span><span class="sxs-lookup"><span data-stu-id="ad757-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="ad757-123">这将向患者应用启用相关患者记录的单向（只读）流。</span><span class="sxs-lookup"><span data-stu-id="ad757-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="ad757-124">患者应用理解 FHIR 格式，因此合作伙伴还负责将聚合数据从各种其他格式（如 HL7v2 等）转换为 FHIR DSTU2 或 STU3。</span><span class="sxs-lookup"><span data-stu-id="ad757-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![插图突出显示护理协调和协作](../../media/ehr-1.png)

<br>

<span data-ttu-id="ad757-126">患者应用集成了电子运行状况记录（EHR）系统，使护理提供商可以实时地与团队的安全平台中的患者护理进行沟通。</span><span class="sxs-lookup"><span data-stu-id="ad757-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="ad757-127">患者应用是护理协调领域的第一大投资，旨在解决以下难题：</span><span class="sxs-lookup"><span data-stu-id="ad757-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="ad757-128">通过患者体验实现高效率和关键通信的低效率</span><span class="sxs-lookup"><span data-stu-id="ad757-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="ad757-129">带来管理负担的各自为政的信息</span><span class="sxs-lookup"><span data-stu-id="ad757-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="ad757-130">具有复杂且零散的协作工具的临床医生中的不满</span><span class="sxs-lookup"><span data-stu-id="ad757-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="ad757-131">非常低效的人员间护理协作，可能会产生太昂贵的临床时间</span><span class="sxs-lookup"><span data-stu-id="ad757-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="ad757-132">Microsoft 团队支持医生、临床医生、护士和其他员工通过以下方式高效协作：</span><span class="sxs-lookup"><span data-stu-id="ad757-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="ad757-133">成为可在 Office 文档上工作和协作的单个虚拟化团队的一部分</span><span class="sxs-lookup"><span data-stu-id="ad757-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="ad757-134">与需要关注的不同患者进行持续对话</span><span class="sxs-lookup"><span data-stu-id="ad757-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="ad757-135">将频道与选项卡配合使用来组织其工作，使用可固定信息源的选项卡中的其他帮助</span><span class="sxs-lookup"><span data-stu-id="ad757-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="ad757-136">将频道会议与团队的强大功能结合使用音频、视频、屏幕共享、录制和设备功能来管理日常会议</span><span class="sxs-lookup"><span data-stu-id="ad757-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="ad757-137">使用患者应用策展必须监控的高风险患者的列表，并从 EHR 系统中提取最新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ad757-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="ad757-138">患者应用本身将以下功能添加到 Microsoft 团队：</span><span class="sxs-lookup"><span data-stu-id="ad757-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="ad757-139">可以在单个频道中创建多个患者列表。</span><span class="sxs-lookup"><span data-stu-id="ad757-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="ad757-140">能够通过可配置的栏查看和排序患者显示的信息。</span><span class="sxs-lookup"><span data-stu-id="ad757-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="ad757-141">通过团队模板自动预配应用的功能。</span><span class="sxs-lookup"><span data-stu-id="ad757-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="ad757-142">适用于 iOS 和 Android 适用于 iOS 和 Android 的团队应用，适用于移动用户第一个医疗保健工作人员以及 Microsoft 团队 web 和桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="ad757-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="ad757-143">通过分析一致性语句支持 FHIR DSTU2 和 STU3 版本。</span><span class="sxs-lookup"><span data-stu-id="ad757-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="ad757-144">针对其用户界面上的所有视图和搜索操作的审核日志，以保护每个 HIPAA 准则的 PHI。</span><span class="sxs-lookup"><span data-stu-id="ad757-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="ad757-145">患者应用在团队扩展性平台上构建，并利用选项卡框架在频道内显示丰富的患者内容。</span><span class="sxs-lookup"><span data-stu-id="ad757-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="ad757-146">若要了解有关其他团队应用和平台本身的详细信息，请参阅[Microsoft 团队应用](/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="ad757-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="ad757-147">患者应用在私人预览版中，FHIR 界面位于 beta 中。</span><span class="sxs-lookup"><span data-stu-id="ad757-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="ad757-148">发布的版本不应向后兼容。</span><span class="sxs-lookup"><span data-stu-id="ad757-148">Released versions are not expected to be backward compatible.</span></span>

![桌面和移动设备上患者应用的屏幕截图](../../media/ehr-2.png)

<span data-ttu-id="ad757-150">有关实现的详细信息，请参阅将[电子医疗保健记录集成到 Microsoft 团队](patients-app.md)中。</span><span class="sxs-lookup"><span data-stu-id="ad757-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="ad757-151">Templates</span><span class="sxs-lookup"><span data-stu-id="ad757-151">Templates</span></span>

<span data-ttu-id="ad757-152">创建团队的新模板已开发为适用于医院的设置，并且预计会更多。</span><span class="sxs-lookup"><span data-stu-id="ad757-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="ad757-153">这使您可以更轻松地创建医疗保健工作者在各种部门或 wards 中协调病人的护理。</span><span class="sxs-lookup"><span data-stu-id="ad757-153">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="ad757-154">请参阅[面向医疗保健组织的团队模板入门](healthcare-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="ad757-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="ad757-155">团队可以为内部部门（如心脏病科）或用于护理 wards 的团队开始，并且更多模板位于开发中。</span><span class="sxs-lookup"><span data-stu-id="ad757-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="ad757-156">安全消息</span><span class="sxs-lookup"><span data-stu-id="ad757-156">Secure Messaging</span></span>

<span data-ttu-id="ad757-157">安全邮件支持在护理团队内进行协作，包括以下几项新功能：</span><span class="sxs-lookup"><span data-stu-id="ad757-157">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="ad757-158">邮件发件人可以为其邮件设置特殊优先级，以便收件人在阅读邮件之前反复收到通知。</span><span class="sxs-lookup"><span data-stu-id="ad757-158">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="ad757-159">邮件发件人可以请求已读回执，这样当邮件收件人阅读邮件时，会收到通知。</span><span class="sxs-lookup"><span data-stu-id="ad757-159">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="ad757-160">结合这些功能，可以更快地注意紧急邮件，并确保邮件已接收和阅读。</span><span class="sxs-lookup"><span data-stu-id="ad757-160">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="ad757-161">使用这些功能的新的护理团队可以在每个患者的基础上创建。</span><span class="sxs-lookup"><span data-stu-id="ad757-161">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="ad757-162">这些功能是基于策略的，可分配给个人或整个团队。</span><span class="sxs-lookup"><span data-stu-id="ad757-162">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="ad757-163">有关[医疗保健组织的安全邮件策略](messaging-policies-hc.md)的详细信息，请参阅入门。</span><span class="sxs-lookup"><span data-stu-id="ad757-163">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="ad757-164">同时与安全消息相关的功能是拥有受医疗保健组织联盟的其他租户，从而实现了更丰富的租户间通信。</span><span class="sxs-lookup"><span data-stu-id="ad757-164">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="ad757-165">（请参阅[管理 Microsoft 团队中的外部访问（联合）](../../manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ad757-165">(see [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="ad757-166">一线工作人员集成</span><span class="sxs-lookup"><span data-stu-id="ad757-166">Firstline Worker integration</span></span>

<span data-ttu-id="ad757-167">Microsoft 团队与一线工作人员集成，可用于协调倒班人员配备功能。</span><span class="sxs-lookup"><span data-stu-id="ad757-167">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="ad757-168">请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="ad757-168">See the following articles:</span></span>

- [<span data-ttu-id="ad757-169">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="ad757-169">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="ad757-170">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="ad757-170">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
