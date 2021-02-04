---
title: Teams 虚拟访问
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 使用 Microsoft Teams 设置虚拟访问系统
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101330"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="4f682-103">使用 Teams 进行虚拟访问 - 集成到 EHR 中</span><span class="sxs-lookup"><span data-stu-id="4f682-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="4f682-104">借助 Microsoft Teams 电子健康记录 (EHR) Connector，医生可以轻松直接从 EHR 系统在 Teams 中启动虚拟患者访问或咨询其他提供商。</span><span class="sxs-lookup"><span data-stu-id="4f682-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="4f682-105">Microsoft Teams 在 Microsoft 365 云上构建，支持符合 HIPAA、HITECH 认证等要求，通过单个中心中的聊天、视频、语音和医疗保健工具实现简单、安全的协作和通信。</span><span class="sxs-lookup"><span data-stu-id="4f682-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="4f682-106">通过 Teams 的通信和协作平台，医生可以轻松解决系统碎片化问题，以便他们花时间提供最佳护理。</span><span class="sxs-lookup"><span data-stu-id="4f682-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="4f682-107">Microsoft Teams 电子运行状况记录 (EHR) 连接器可以：</span><span class="sxs-lookup"><span data-stu-id="4f682-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="4f682-108">从提供商和患者门户启动 Teams 虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="4f682-109">连接和断开连接事件时写回到 EHR 元数据，以启用自动审核和记录保留。</span><span class="sxs-lookup"><span data-stu-id="4f682-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="4f682-110">集成到现有医生和患者工作流中，同时允许他们使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4f682-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="4f682-111">观看如何从 EHR 门户管理虚拟访问的视频。</span><span class="sxs-lookup"><span data-stu-id="4f682-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="4f682-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="4f682-112">Before you begin</span></span>

<span data-ttu-id="4f682-113">在集成 EHR 连接器之前，需要确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="4f682-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="4f682-114">访问在 Epic 的应用应用商店中用于 Microsoft Teams [应用](https://apporchard.epic.com/Gallery?id=6153)。</span><span class="sxs-lookup"><span data-stu-id="4f682-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="4f682-115">Microsoft Cloud for Healthcare 的活动订阅或 Microsoft Teams EHR 连接器独立套餐 (仅在生产测试期间强制执行) 。</span><span class="sxs-lookup"><span data-stu-id="4f682-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="4f682-116">用户必须具有包含 Microsoft Teams 会议的适当 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="4f682-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="4f682-117">Microsoft Teams 应在组织内部采用和使用。</span><span class="sxs-lookup"><span data-stu-id="4f682-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="4f682-118">组织必须具有 2018 年 11 月版或更高版本的"长篇故事"版本。</span><span class="sxs-lookup"><span data-stu-id="4f682-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="4f682-119">系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="4f682-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="4f682-120">还需要组织中以下人员的信息：</span><span class="sxs-lookup"><span data-stu-id="4f682-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="4f682-121">Microsoft 365 管理员</span><span class="sxs-lookup"><span data-stu-id="4f682-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="4f682-122">长篇客户分析师</span><span class="sxs-lookup"><span data-stu-id="4f682-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="4f682-123">请请Epicic 技术专家提供 Epic-Microsoft Teams Telehealth 集成指南，该指南在长篇市场中提供。</span><span class="sxs-lookup"><span data-stu-id="4f682-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="4f682-124">连接器设置</span><span class="sxs-lookup"><span data-stu-id="4f682-124">Connector setup</span></span>

<span data-ttu-id="4f682-125">连接器设置要求：</span><span class="sxs-lookup"><span data-stu-id="4f682-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="4f682-126">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="4f682-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="4f682-127">配置信息</span><span class="sxs-lookup"><span data-stu-id="4f682-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="4f682-128">批准或查看配置</span><span class="sxs-lookup"><span data-stu-id="4f682-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="4f682-129">查看并完成配置</span><span class="sxs-lookup"><span data-stu-id="4f682-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="4f682-130">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="4f682-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="4f682-131">首先启动 EHR 连接器配置门户，将医疗保健组织配置为启动 Microsoft Teams 的虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="4f682-132">配置一个或多个组织以测试集成。</span><span class="sxs-lookup"><span data-stu-id="4f682-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="4f682-133">在配置门户中配置测试和生产 URL。</span><span class="sxs-lookup"><span data-stu-id="4f682-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="4f682-134">在迁移到生产环境之前，先从 Epic 的测试环境测试集成。</span><span class="sxs-lookup"><span data-stu-id="4f682-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="4f682-135">EHR 连接器配置 URL： [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4f682-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="4f682-136">组织的 Microsoft 365 管理员和长篇客户分析师必须在配置门户中完成信息和集成步骤。</span><span class="sxs-lookup"><span data-stu-id="4f682-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="4f682-137">有关"长篇大作"配置步骤，请联系分配给组织的"长篇故事"技术专家资源。</span><span class="sxs-lookup"><span data-stu-id="4f682-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="4f682-138">配置信息</span><span class="sxs-lookup"><span data-stu-id="4f682-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="4f682-139">此步骤由 **Microsoft 365 管理员完成**。</span><span class="sxs-lookup"><span data-stu-id="4f682-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="4f682-140">Microsoft 365 管理员必须启动连接器配置门户，然后使用 Microsoft 凭据登录才能启动配置过程。</span><span class="sxs-lookup"><span data-stu-id="4f682-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="4f682-141">若要完成此步骤，Microsoft 365 管理员必须收到来自一名 Epic 技术专家的有效快速运行状况互操作性资源 (FHIR) 基 URL，以及将批准配置的一名长篇客户分析师的用户名。</span><span class="sxs-lookup"><span data-stu-id="4f682-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="4f682-142">Microsoft 365 管理员必须启动连接器配置页，然后使用 Microsoft 凭据登录才能开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="4f682-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="4f682-143">FHIR 基 URL 是对应于服务器 FHIR API 终结点的静态地址。</span><span class="sxs-lookup"><span data-stu-id="4f682-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="4f682-144">示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` 。</span><span class="sxs-lookup"><span data-stu-id="4f682-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="4f682-145">配置审批者名称是负责在下一步中审批配置的"长篇客户"分析人员的名称。</span><span class="sxs-lookup"><span data-stu-id="4f682-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="4f682-146">"长篇故事"客户分析师是组织中具有对"长篇故事"的登录访问权限的人。</span><span class="sxs-lookup"><span data-stu-id="4f682-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![从 EHR 连接器中的列表中选择配置审批者的名称。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="4f682-148">批准或查看配置</span><span class="sxs-lookup"><span data-stu-id="4f682-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="4f682-149">作为审批者添加的医疗保健组织的"长篇客户"分析师现在必须使用上一步骤中的相同 EHR 连接器 URL，才能使用其 Microsoft 365 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="4f682-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="4f682-150">成功验证后，将要求审批者使用其"长篇"凭据登录以验证"长篇故事"组织。</span><span class="sxs-lookup"><span data-stu-id="4f682-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="4f682-151">你组织的 Microsoft 365 管理员和长篇客户分析师可以是同一个人。</span><span class="sxs-lookup"><span data-stu-id="4f682-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="4f682-152">在这种情况下，请添加自己的用户名作为审批者。</span><span class="sxs-lookup"><span data-stu-id="4f682-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="4f682-153">你仍然需要登录到"长篇大作"来验证你的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4f682-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="4f682-154">长篇登录仅用于验证 FHIR 基 URL。</span><span class="sxs-lookup"><span data-stu-id="4f682-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="4f682-155">Microsoft 不会通过此登录存储凭据或访问 EHR 数据。</span><span class="sxs-lookup"><span data-stu-id="4f682-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![验证并批准凭据配置。](../../media/approve-view-configuration.png)

<span data-ttu-id="4f682-157">成功登录"长篇故事"后，长篇客户 **分析师必须** 批准配置。</span><span class="sxs-lookup"><span data-stu-id="4f682-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="4f682-158">如果配置不正确，Microsoft 365 管理员将可以再次登录 Microsoft EHR 连接器门户来修改原始配置。</span><span class="sxs-lookup"><span data-stu-id="4f682-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![确认 EHR 连接器已配置，以及用于更改配置的选项。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="4f682-160">查看并完成配置</span><span class="sxs-lookup"><span data-stu-id="4f682-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="4f682-161">当配置信息由"长篇故事"管理员批准时，你将看到患者和提供者启动的集成记录。</span><span class="sxs-lookup"><span data-stu-id="4f682-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="4f682-162">这些记录是完成"长篇故事"中的虚拟访问配置所必需的。</span><span class="sxs-lookup"><span data-stu-id="4f682-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="4f682-163">有关详细信息，请参阅 Epic-Microsoft Teams Telehealth 集成指南。</span><span class="sxs-lookup"><span data-stu-id="4f682-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="4f682-164">Microsoft 365 或 Epic 客户分析师随时可登录配置门户，查看集成记录并根据需要修改组织配置。</span><span class="sxs-lookup"><span data-stu-id="4f682-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![将显示集成信息。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="4f682-166">之前由 Microsoft 管理员配置的每一个 FHIR URL 必须由 Epic 客户分析人员完成审批过程。</span><span class="sxs-lookup"><span data-stu-id="4f682-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![配置信息已获批准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="4f682-168">启动 Teams 虚拟访问</span><span class="sxs-lookup"><span data-stu-id="4f682-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="4f682-169">完成 EHR 连接器步骤和"长篇大作"配置后，组织即可使用 Microsoft Teams 支持视频访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="4f682-170">虚拟访问先决条件</span><span class="sxs-lookup"><span data-stu-id="4f682-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="4f682-171">系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="4f682-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="4f682-172">医疗保健组织必须已完成在 Epic 组织与 Microsoft 365 组织之间的设置。</span><span class="sxs-lookup"><span data-stu-id="4f682-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="4f682-173">提供商体验</span><span class="sxs-lookup"><span data-stu-id="4f682-173">Provider experience</span></span>

<span data-ttu-id="4f682-174">贵组织的医疗保健提供商还可以从 Hyperspace、Haiku、Canto (的"长篇"提供商应用程序加入 Microsoft Teams 的虚拟) 。</span><span class="sxs-lookup"><span data-stu-id="4f682-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="4f682-175">提供程序 **流中** 嵌入了"开始虚拟访问"按钮。</span><span class="sxs-lookup"><span data-stu-id="4f682-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="4f682-176">提供商体验的主要功能：</span><span class="sxs-lookup"><span data-stu-id="4f682-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="4f682-177">提供商可以使用支持的浏览器或 Microsoft Teams 应用程序加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="4f682-178">首次加入虚拟访问时，提供商必须使用其 Microsoft 365 帐户进行一次登录。</span><span class="sxs-lookup"><span data-stu-id="4f682-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="4f682-179">一次登录后，提供商将直接进入 Microsoft Teams 中的虚拟约会。</span><span class="sxs-lookup"><span data-stu-id="4f682-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="4f682-180"> (提供程序必须登录到 Microsoft Teams) 。</span><span class="sxs-lookup"><span data-stu-id="4f682-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="4f682-181">提供商可以看到给定约会的参与者连接和断开连接实时更新。</span><span class="sxs-lookup"><span data-stu-id="4f682-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="4f682-182">提供商可以看到患者何时连接到虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![与患者进行虚拟访问的提供商体验](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="4f682-184">患者体验</span><span class="sxs-lookup"><span data-stu-id="4f682-184">Patient experience</span></span>

<span data-ttu-id="4f682-185">此连接器支持患者通过 MyChart Web 和移动设备加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="4f682-186">预约时，患者可以使用"开始虚拟访问"按钮从 MyChart 开始 **虚拟** 访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="4f682-187">患者体验的主要功能：</span><span class="sxs-lookup"><span data-stu-id="4f682-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="4f682-188">患者无需安装应用即可从桌面和移动设备上的现代 Web 浏览器加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="4f682-189">患者只需单击一下即可加入虚拟访问，无需其他帐户或登录。</span><span class="sxs-lookup"><span data-stu-id="4f682-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="4f682-190">患者无需创建 Microsoft 帐户或登录以启动虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="4f682-191">患者将被放置在大厅中，直到医疗保健提供商加入预约并准许他们进行虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="4f682-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="4f682-192">加入虚拟访问之前，大厅中提供了视频和麦克风测试。</span><span class="sxs-lookup"><span data-stu-id="4f682-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![虚拟访问患者体验](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="4f682-194">Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商标。</span><span class="sxs-lookup"><span data-stu-id="4f682-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="4f682-195">数据的隐私和位置</span><span class="sxs-lookup"><span data-stu-id="4f682-195">Privacy and location of data</span></span>

<span data-ttu-id="4f682-196">Teams 与 EHR 系统的集成优化了集成和虚拟访问流期间使用和存储的数据量。</span><span class="sxs-lookup"><span data-stu-id="4f682-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="4f682-197">该解决方案遵循 Teams 隐私中概述的总体 Teams 隐私和数据管理原则与准则。</span><span class="sxs-lookup"><span data-stu-id="4f682-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="4f682-198">Microsoft Teams EHR 连接器不存储或传输任何可识别的个人数据，也不会从 EHR 系统传输患者或医疗保健提供者的任何健康记录。</span><span class="sxs-lookup"><span data-stu-id="4f682-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="4f682-199">EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在 Teams 会议设置期间使用。</span><span class="sxs-lookup"><span data-stu-id="4f682-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="4f682-200">EHR 用户的唯一 ID 存储在 [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)客户数据存储位置中所述的三个地理区域之一。</span><span class="sxs-lookup"><span data-stu-id="4f682-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="4f682-201">会议参与者输入到 Teams 的所有聊天、录制和其他数据都根据现有存储策略进行存储。</span><span class="sxs-lookup"><span data-stu-id="4f682-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="4f682-202">若要详细了解 Microsoft Teams 中数据的位置，请访问 [Teams 中数据的位置](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="4f682-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
