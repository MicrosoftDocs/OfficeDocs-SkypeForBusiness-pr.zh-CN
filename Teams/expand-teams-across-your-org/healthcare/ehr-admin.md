---
title: 用于虚拟访问的团队
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
description: 使用 Microsoft 团队设置你的虚拟访问系统
ms.openlocfilehash: 808d957cd86273852e7c2c98ec223b1988e5bd0d
ms.sourcegitcommit: cbf87fc914a19088af8ec08fb0976db9f838a45d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49355962"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="90a1c-103">与团队的虚拟访问-集成到 EHR</span><span class="sxs-lookup"><span data-stu-id="90a1c-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="90a1c-104">Microsoft 团队电子医疗记录 (EHR) 连接器使临床医生能够轻松地从 EHR 系统与团队中的另一个提供商发起虚拟患者访问或咨询。</span><span class="sxs-lookup"><span data-stu-id="90a1c-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="90a1c-105">Microsoft 团队基于 Microsoft 365 云构建，支持在支持 HIPAA、高科技认证等的单个集线器中使用聊天、视频、语音和医疗保健工具实现简单、安全的协作和通信。</span><span class="sxs-lookup"><span data-stu-id="90a1c-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="90a1c-106">团队的通信和协作平台使临床医生能够轻松地通过零散的系统进行混乱，以便他们可以花时间提供最佳护理。</span><span class="sxs-lookup"><span data-stu-id="90a1c-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="90a1c-107">Microsoft 团队电子医疗记录 (EHR) 连接器可以：</span><span class="sxs-lookup"><span data-stu-id="90a1c-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="90a1c-108">启动团队从提供商和患者门户进行虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="90a1c-109">在连接和断开连接事件上写回 EHR 元数据，以启用自动审核和记录保留。</span><span class="sxs-lookup"><span data-stu-id="90a1c-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="90a1c-110">集成到现有 clinician 和患者工作流，同时允许他们使用 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="90a1c-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="90a1c-111">观看有关如何从 EHR 门户管理虚拟访问的视频。</span><span class="sxs-lookup"><span data-stu-id="90a1c-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="90a1c-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="90a1c-112">Before you begin</span></span>

<span data-ttu-id="90a1c-113">在集成 EHR 连接器之前，你需要确保具有以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="90a1c-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="90a1c-114">适用于 Microsoft Cloud for 医疗保健的活动订阅或 Microsoft 团队订阅的 Microsoft 团队 EHR 连接器独立优惠。</span><span class="sxs-lookup"><span data-stu-id="90a1c-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="90a1c-115">用户必须具有相应的 Microsoft 365 或 Office 365 许可证，其中包含 Microsoft 团队会议。</span><span class="sxs-lookup"><span data-stu-id="90a1c-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="90a1c-116">应在组织内部采纳和使用 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="90a1c-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="90a1c-117">组织必须使用长篇版本2018或更高版本。</span><span class="sxs-lookup"><span data-stu-id="90a1c-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="90a1c-118">您的系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="90a1c-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="90a1c-119">你还需要来自组织中以下人员的信息：</span><span class="sxs-lookup"><span data-stu-id="90a1c-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="90a1c-120">Microsoft 365 管理员</span><span class="sxs-lookup"><span data-stu-id="90a1c-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="90a1c-121">长篇故事管理员</span><span class="sxs-lookup"><span data-stu-id="90a1c-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="90a1c-122">请求长篇故事管理员提供 Epic-Microsoft 的团队 Telehealth 集成指南，该指南在长篇故事市场中可用。</span><span class="sxs-lookup"><span data-stu-id="90a1c-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="90a1c-123">连接线设置</span><span class="sxs-lookup"><span data-stu-id="90a1c-123">Connector setup</span></span>

<span data-ttu-id="90a1c-124">连接器设置要求你：</span><span class="sxs-lookup"><span data-stu-id="90a1c-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="90a1c-125">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="90a1c-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="90a1c-126">配置提供商组织信息</span><span class="sxs-lookup"><span data-stu-id="90a1c-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="90a1c-127">验证和批准配置</span><span class="sxs-lookup"><span data-stu-id="90a1c-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="90a1c-128">查看和完成配置</span><span class="sxs-lookup"><span data-stu-id="90a1c-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="90a1c-129">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="90a1c-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="90a1c-130">通过启动 EHR 连接器配置门户，将你的医疗保健组织配置为启动与 Microsoft 团队的虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="90a1c-131">使用测试 URL 配置长篇测试环境的连接器。</span><span class="sxs-lookup"><span data-stu-id="90a1c-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="90a1c-132">准备好启用长篇制作环境时，请使用生产 URL。</span><span class="sxs-lookup"><span data-stu-id="90a1c-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="90a1c-133">测试环境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="90a1c-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="90a1c-134">生产环境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="90a1c-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="90a1c-135">您的组织中的 Microsoft 365 管理员和长篇故事管理员必须完成配置门户中的信息和集成步骤。</span><span class="sxs-lookup"><span data-stu-id="90a1c-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="90a1c-136">对于长篇故事配置步骤，请联系分配给你的组织的长篇故事资源。</span><span class="sxs-lookup"><span data-stu-id="90a1c-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="90a1c-137">配置提供商组织信息</span><span class="sxs-lookup"><span data-stu-id="90a1c-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="90a1c-138">此步骤将由 Microsoft 365 管理员完成。</span><span class="sxs-lookup"><span data-stu-id="90a1c-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="90a1c-139">Microsoft 365 管理员必须启动连接器配置门户并通过 Microsoft 凭据登录才能启动配置过程。</span><span class="sxs-lookup"><span data-stu-id="90a1c-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="90a1c-140">若要完成此步骤，Microsoft 365 管理员必须收到一个有效的快速运行状况互操作性资源 (FHIR 来自 Microsoft 365 管理员的) 基 URL，以及将审批配置的长篇管理员的用户名。</span><span class="sxs-lookup"><span data-stu-id="90a1c-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="90a1c-141">Microsoft 365 管理员必须启动连接器配置页面，并以 Microsoft 凭据登录才能启动配置过程。</span><span class="sxs-lookup"><span data-stu-id="90a1c-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="90a1c-142">FHIR 基 URL 是对应于服务器 FHIR API 终结点的静态地址。</span><span class="sxs-lookup"><span data-stu-id="90a1c-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="90a1c-143">示例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` 。</span><span class="sxs-lookup"><span data-stu-id="90a1c-143">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="90a1c-144">配置审批者名称是将负责审批配置的长篇故事系统管理员的名称。</span><span class="sxs-lookup"><span data-stu-id="90a1c-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![将从 EHR 连接器的列表中选择配置审核人的姓名。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="90a1c-146">验证和批准配置</span><span class="sxs-lookup"><span data-stu-id="90a1c-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="90a1c-147">作为审批者添加的医疗保健组织的长篇故事管理员必须现在使用同一 EHR 连接器 URL，以便使用其 Microsoft 365 凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="90a1c-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="90a1c-148">成功验证后，将要求审批者使用其长篇凭据进行登录以验证长篇故事组织。</span><span class="sxs-lookup"><span data-stu-id="90a1c-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="90a1c-149">组织中的 Microsoft 365 管理员和长篇故事管理员可以是同一个人。</span><span class="sxs-lookup"><span data-stu-id="90a1c-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="90a1c-150">在这种情况下，在第一步中添加您自己的用户名作为审批者。</span><span class="sxs-lookup"><span data-stu-id="90a1c-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="90a1c-151">您仍需登录长篇故事以验证您的访问权限。</span><span class="sxs-lookup"><span data-stu-id="90a1c-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="90a1c-152">长篇故事登录仅用于验证你的 FHIR 基本 URL。</span><span class="sxs-lookup"><span data-stu-id="90a1c-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="90a1c-153">Microsoft 不会使用此登录存储凭据或访问 EHR 数据。</span><span class="sxs-lookup"><span data-stu-id="90a1c-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![验证和批准凭据配置。](../../media/ehc-provider-2.png)

<span data-ttu-id="90a1c-155">成功长篇故事登录后，长篇故事管理员 **必须** 批准该配置。</span><span class="sxs-lookup"><span data-stu-id="90a1c-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="90a1c-156">如果配置不正确，Microsoft 365 管理员将能够通过再次登录 Microsoft EHR 连接器门户来修改原始配置。</span><span class="sxs-lookup"><span data-stu-id="90a1c-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![确认已配置 EHR 连接器，并选择更改配置。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="90a1c-158">查看和完成配置</span><span class="sxs-lookup"><span data-stu-id="90a1c-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="90a1c-159">当长篇管理员批准配置信息时，您将看到患者和提供商启动的集成记录。</span><span class="sxs-lookup"><span data-stu-id="90a1c-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="90a1c-160">这些记录是完成长篇故事中的虚拟访问配置所必需的。</span><span class="sxs-lookup"><span data-stu-id="90a1c-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="90a1c-161">有关详细信息，请参阅 Epic-Microsoft 的团队 Telehealth 集成指南。</span><span class="sxs-lookup"><span data-stu-id="90a1c-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="90a1c-162">Microsoft 365 或长篇故事管理员可以随时登录到配置门户以查看集成记录和修改组织配置（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="90a1c-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![显示集成信息。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="90a1c-164">启动团队虚拟访问</span><span class="sxs-lookup"><span data-stu-id="90a1c-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="90a1c-165">完成 EHR 连接器步骤和长篇配置后，你的组织已准备好支持 Microsoft 团队的视频访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="90a1c-166">虚拟就诊先决条件</span><span class="sxs-lookup"><span data-stu-id="90a1c-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="90a1c-167">您的系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="90a1c-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="90a1c-168">医疗保健组织必须已完成长篇企业和 Microsoft 365 组织之间的设置。</span><span class="sxs-lookup"><span data-stu-id="90a1c-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="90a1c-169">提供程序体验</span><span class="sxs-lookup"><span data-stu-id="90a1c-169">Provider experience</span></span>

<span data-ttu-id="90a1c-170">你的组织中的医疗保健提供商还可以通过其长篇提供商应用程序 (超空间、Haiku、Canto) 与 Microsoft 团队的虚拟访问进行联接。</span><span class="sxs-lookup"><span data-stu-id="90a1c-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="90a1c-171">" **开始虚拟访问** " 按钮嵌入在提供程序流中。</span><span class="sxs-lookup"><span data-stu-id="90a1c-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="90a1c-172">提供程序体验的关键功能：</span><span class="sxs-lookup"><span data-stu-id="90a1c-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="90a1c-173">提供程序可使用支持的浏览器或 Microsoft 团队应用程序加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="90a1c-174">当首次加入虚拟访问时，提供程序必须使用 Microsoft 365 帐户进行一次登录。</span><span class="sxs-lookup"><span data-stu-id="90a1c-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="90a1c-175">在一次性登录后，提供者将直接转到 Microsoft 团队中的虚拟约会。</span><span class="sxs-lookup"><span data-stu-id="90a1c-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="90a1c-176"> (提供商必须登录到 Microsoft 团队) 。</span><span class="sxs-lookup"><span data-stu-id="90a1c-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="90a1c-177">提供商可以查看为给定约会连接和断开连接的参与者的实时更新。</span><span class="sxs-lookup"><span data-stu-id="90a1c-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="90a1c-178">当患者连接到虚拟访问时，提供商可以看到。</span><span class="sxs-lookup"><span data-stu-id="90a1c-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![提供商体验与患者的虚拟访问](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="90a1c-180">患者体验</span><span class="sxs-lookup"><span data-stu-id="90a1c-180">Patient experience</span></span>

<span data-ttu-id="90a1c-181">该连接器支持患者通过 MyChart web 和手机加入虚拟走访。</span><span class="sxs-lookup"><span data-stu-id="90a1c-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="90a1c-182">在约会时，病人可以使用 " **开始虚拟访问** " 按钮从 MyChart 开始虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="90a1c-183">患者体验的关键功能：</span><span class="sxs-lookup"><span data-stu-id="90a1c-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="90a1c-184">在没有应用安装的情况下，患者可以从桌面和移动设备上的新式 web 浏览器中加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="90a1c-185">患者只需单击一次即可加入虚拟访问，无需其他帐户或登录。</span><span class="sxs-lookup"><span data-stu-id="90a1c-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="90a1c-186">不需要患者创建 Microsoft 帐户或登录以启动虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="90a1c-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="90a1c-187">患者将放在大厅，直到医疗保健提供商加入约会并将其准许到虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="90a1c-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="90a1c-188">在加入虚拟访问之前，可以在大厅中测试视频和麦克风。</span><span class="sxs-lookup"><span data-stu-id="90a1c-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![虚拟就诊的患者体验](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="90a1c-190">长篇故事、MyChart、Haiku 和 Canto 是长篇故事系统公司的商标。</span><span class="sxs-lookup"><span data-stu-id="90a1c-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="90a1c-191">数据的隐私和位置</span><span class="sxs-lookup"><span data-stu-id="90a1c-191">Privacy and location of data</span></span>

<span data-ttu-id="90a1c-192">团队集成到 EHR 系统可优化集成和虚拟访问流程期间正在使用和存储的数据量。</span><span class="sxs-lookup"><span data-stu-id="90a1c-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="90a1c-193">该解决方案遵循团队隐私中概述的整个团队隐私和数据管理原则和指南。</span><span class="sxs-lookup"><span data-stu-id="90a1c-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="90a1c-194">Microsoft 团队 EHR 连接器不会在 EHR 系统中存储和传输任何可识别的个人数据或患者或医疗保健提供商的任何健康记录。</span><span class="sxs-lookup"><span data-stu-id="90a1c-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="90a1c-195">EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在团队会议设置期间使用。</span><span class="sxs-lookup"><span data-stu-id="90a1c-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="90a1c-196">EHR 用户的唯一 ID 存储在 [存储 Microsoft 365 客户数据的位置](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 中所述的三个地理区域之一。</span><span class="sxs-lookup"><span data-stu-id="90a1c-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="90a1c-197">会议参与者向团队输入的所有聊天、录制和其他数据将根据现有的存储策略进行存储。</span><span class="sxs-lookup"><span data-stu-id="90a1c-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="90a1c-198">如果想要了解有关 Microsoft 团队中的数据位置的详细信息，请访问 [团队中的数据位置](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="90a1c-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
