---
title: Teams 虚拟就诊
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
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: 使用 Microsoft Teams 设置虚拟就诊系统
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705246"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="cd212-103">通过 Teams 进行虚拟就诊 - 集成到 EHR</span><span class="sxs-lookup"><span data-stu-id="cd212-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="cd212-104">Microsoft Teams借助 EHR (EHR) 连接器，医生可以轻松直接从 EHR 系统启动虚拟患者访问或咨询Teams提供商。</span><span class="sxs-lookup"><span data-stu-id="cd212-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="cd212-105">Microsoft Teams 基于 Microsoft 365 云进行构建，可在支持 HIPAA、HITECH 认证等合规性要求的单个中心内通过聊天、视频、语音和医疗保健工具，实现简单、安全的协作和沟通。</span><span class="sxs-lookup"><span data-stu-id="cd212-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="cd212-106">利用 Teams 的沟通和协作平台，临床医生可轻松解决零碎的体制问题，从而腾出更多时间提供最好的医治。</span><span class="sxs-lookup"><span data-stu-id="cd212-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="cd212-107">Microsoft TeamsEHR (EHR) 连接器可以：</span><span class="sxs-lookup"><span data-stu-id="cd212-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="cd212-108">启动Teams EHR 系统的虚拟访问和集成的医疗工作流。</span><span class="sxs-lookup"><span data-stu-id="cd212-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="cd212-109">使患者能够从患者Teams内加入虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="cd212-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="cd212-110">将有关虚拟访问的元数据写回到 EHR 系统Teams与会者连接和断开连接时进行记录，并启用自动审核和记录保留。</span><span class="sxs-lookup"><span data-stu-id="cd212-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="cd212-111">请观看此视频，了解如何从 EHR 门户管理虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="cd212-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="cd212-112">Before you begin</span></span>

<span data-ttu-id="cd212-113">在集成 EHR 连接器之前，需要确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="cd212-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="cd212-114">可以访问并使用 [Epic 的 App Orchard 商城](https://apporchard.epic.com/Gallery?id=6153)中的 Microsoft Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="cd212-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="cd212-115">活动订阅 Microsoft Cloud for Healthcare 或订阅 EHR 连接器Microsoft Teams产品/服务 (仅在生产测试期间) 。</span><span class="sxs-lookup"><span data-stu-id="cd212-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="cd212-116">用户必须具有包含 Microsoft Teams 会议的适当 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="cd212-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="cd212-117">组织内部应采用和使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="cd212-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="cd212-118">组织必须具有 2018 年 11 月或更高版本的 Epic 版本。</span><span class="sxs-lookup"><span data-stu-id="cd212-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="cd212-119">系统必须满足所有[软件和浏览器先决条件](../../hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="cd212-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="cd212-120">还需要组织中以下人员的信息：</span><span class="sxs-lookup"><span data-stu-id="cd212-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="cd212-121">Microsoft 365 管理员</span><span class="sxs-lookup"><span data-stu-id="cd212-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="cd212-122">Epic 客户分析员</span><span class="sxs-lookup"><span data-stu-id="cd212-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="cd212-123">与你的 Epic 技术专家一起查看 [Epic-Microsoft Teams 远程医疗集成指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。</span><span class="sxs-lookup"><span data-stu-id="cd212-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="cd212-124">请确保完成所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="cd212-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="cd212-125">连接器设置</span><span class="sxs-lookup"><span data-stu-id="cd212-125">Connector setup</span></span>

<span data-ttu-id="cd212-126">连接器设置要求你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cd212-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="cd212-127">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="cd212-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="cd212-128">配置信息</span><span class="sxs-lookup"><span data-stu-id="cd212-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="cd212-129">批准或查看配置</span><span class="sxs-lookup"><span data-stu-id="cd212-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="cd212-130">查看和完成配置</span><span class="sxs-lookup"><span data-stu-id="cd212-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="cd212-131">启动 EHR 连接器配置门户</span><span class="sxs-lookup"><span data-stu-id="cd212-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="cd212-132">通过启动 EHR 连接器配置门户，将医疗保健组织配置为Microsoft Teams虚拟访问。</span><span class="sxs-lookup"><span data-stu-id="cd212-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="cd212-133">可配置一个或多个组织来测试集成。</span><span class="sxs-lookup"><span data-stu-id="cd212-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="cd212-134">在配置门户中配置测试和生产 URL。</span><span class="sxs-lookup"><span data-stu-id="cd212-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="cd212-135">在投入生产之前，请从 Epic 的测试环境测试集成。</span><span class="sxs-lookup"><span data-stu-id="cd212-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="cd212-136">EHR 连接器配置 URL：[https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cd212-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="cd212-137">你组织的 Microsoft 365 管理员和 Epic 客户分析员必须完成配置门户中的信息和集成步骤。</span><span class="sxs-lookup"><span data-stu-id="cd212-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="cd212-138">有关 Epic 配置步骤，请联系指派给贵组织的 Epic 技术专家资源。</span><span class="sxs-lookup"><span data-stu-id="cd212-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="cd212-139">配置信息</span><span class="sxs-lookup"><span data-stu-id="cd212-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="cd212-140">此步骤应由 **Microsoft 365 管理员** 完成。</span><span class="sxs-lookup"><span data-stu-id="cd212-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="cd212-141">Microsoft 365 管理员必须启动连接器配置门户并使用 Microsoft 凭据登录才能开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="cd212-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="cd212-142">若要完成此步骤，Microsoft 365 管理员必须从 Epic 技术专员处获得有效的快速医疗保健互操作性资源 (FHIR) 基本 URL，并获得负责批准配置的 Epic 客户分析员的用户名。</span><span class="sxs-lookup"><span data-stu-id="cd212-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="cd212-143">Microsoft 365 管理员必须启动连接器配置页面并使用 Microsoft 凭据登录才能开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="cd212-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="cd212-144">FHIR 基本 URL 是与你的服务器 FHIR API 端点对应的静态地址。</span><span class="sxs-lookup"><span data-stu-id="cd212-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="cd212-145">示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。</span><span class="sxs-lookup"><span data-stu-id="cd212-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="cd212-146">配置审批者姓名是下一步j将负责审批配置的 Epic 客户分析员的姓名。</span><span class="sxs-lookup"><span data-stu-id="cd212-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="cd212-147">Epic 客户分析员是指你的组织中对 Epic 具有登录访问权限的人员。</span><span class="sxs-lookup"><span data-stu-id="cd212-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![将从 EHR 连接器中的列表中选择配置审批者的姓名。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="cd212-149">批准或查看配置</span><span class="sxs-lookup"><span data-stu-id="cd212-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="cd212-150">已添加为审批者医疗保健组织的 Epic 客户分析师现在必须使用上一步骤中的同一 EHR 连接器 URL 使用其 Microsoft 365 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cd212-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="cd212-151">验证成功后，审批者必须使用其 Epic 凭据登录以验证 Epic 组织。</span><span class="sxs-lookup"><span data-stu-id="cd212-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="cd212-152">你组织的 Microsoft 365 管理员和 Epic 客户分析员可以是同一个人。</span><span class="sxs-lookup"><span data-stu-id="cd212-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="cd212-153">在这种情况下，请将你自己的用户名添加为审批者。</span><span class="sxs-lookup"><span data-stu-id="cd212-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="cd212-154">你仍需要登录到 Epic 验证你的访问权限。</span><span class="sxs-lookup"><span data-stu-id="cd212-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="cd212-155">Epic 登录仅用于验证 FHIR 基本 URL。</span><span class="sxs-lookup"><span data-stu-id="cd212-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="cd212-156">Microsoft 不会通过此登录来存储凭据或访问 EHR 数据。</span><span class="sxs-lookup"><span data-stu-id="cd212-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![验证和审批凭据配置。](../../media/approve-view-configuration.png)

<span data-ttu-id="cd212-158">成功登录 Epic 后，Epic 客户分析员 **必须** 审批配置。</span><span class="sxs-lookup"><span data-stu-id="cd212-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="cd212-159">如果配置不正确，Microsoft 365 管理员能够再次登录到 Microsoft EHR 连接器门户来修改原始配置。</span><span class="sxs-lookup"><span data-stu-id="cd212-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![确认已配置 EHR 连接器以及更改配置的选项。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="cd212-161">查看和完成配置</span><span class="sxs-lookup"><span data-stu-id="cd212-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="cd212-162">在配置信息获得 Epic 管理员批准后，系统将为你提供用于患者和提供商启动的集成记录。</span><span class="sxs-lookup"><span data-stu-id="cd212-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="cd212-163">这些记录是完成 Azure 中的虚拟就诊配置所必需的。</span><span class="sxs-lookup"><span data-stu-id="cd212-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="cd212-164">有关更多详细信息，请参阅《Epic-Microsoft Teams 远程医疗集成指南》。</span><span class="sxs-lookup"><span data-stu-id="cd212-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="cd212-165">Microsoft 365 或 Epic 客户分析员可以随时登录配置门户来查看集成记录并根据需要修改组织配置。</span><span class="sxs-lookup"><span data-stu-id="cd212-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![将显示集成信息。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="cd212-167">Epic 客户分析员必须对 Microsoft 管理员之前配置的每个 FHIR URL 完成审批过程。</span><span class="sxs-lookup"><span data-stu-id="cd212-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![配置信息已获得批准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="cd212-169">启动 Teams 虚拟就诊</span><span class="sxs-lookup"><span data-stu-id="cd212-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="cd212-170">完成 EHR 连接器步骤和长篇大作配置后，组织已准备好使用 Microsoft Teams 支持视频访问。</span><span class="sxs-lookup"><span data-stu-id="cd212-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="cd212-171">虚拟就诊先决条件</span><span class="sxs-lookup"><span data-stu-id="cd212-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="cd212-172">系统必须满足所有[软件和浏览器先决条件](../../hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="cd212-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="cd212-173">医疗保健组织必须已完成 Epic 组织和 Microsoft 365 组织之间的设置。</span><span class="sxs-lookup"><span data-stu-id="cd212-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="cd212-174">提供商体验</span><span class="sxs-lookup"><span data-stu-id="cd212-174">Provider experience</span></span>

<span data-ttu-id="cd212-175">你组织的医疗保健提供商还可以从其 Epic 提供商应用程序（Hyperspace、Haiku、Canto）通过 Microsoft Teams 加入虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="cd212-176">提供商流中嵌入了“**开始虚拟就诊**”按钮。</span><span class="sxs-lookup"><span data-stu-id="cd212-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="cd212-177">提供商体验的主要功能：</span><span class="sxs-lookup"><span data-stu-id="cd212-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="cd212-178">提供商可以使用支持的浏览器或 Microsoft Teams 应用程序加入虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="cd212-179">在首次加入虚拟就诊时，提供商必须使用其 Microsoft 365 帐户进行一次性登录。</span><span class="sxs-lookup"><span data-stu-id="cd212-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="cd212-p114">一次登录后，提供商将直接进入 Microsoft Teams 中的虚拟约会。（提供上必须登录到 Microsoft Teams）。</span><span class="sxs-lookup"><span data-stu-id="cd212-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="cd212-182">提供商可以查看给定预约的参与者连接和断开连接实时更新。</span><span class="sxs-lookup"><span data-stu-id="cd212-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="cd212-183">提供商可以查看患者何时连接到虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![有患者的虚拟就诊提供商体验](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="cd212-185">患者体验</span><span class="sxs-lookup"><span data-stu-id="cd212-185">Patient experience</span></span>

<span data-ttu-id="cd212-186">连接器支持患者通过 MyChart 网页版和移动版加入虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="cd212-187">预约时，患者可以使用“**开始虚拟就诊**”按钮从 MyChart 开始虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="cd212-188">患者体验的主要功能：</span><span class="sxs-lookup"><span data-stu-id="cd212-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="cd212-189">患者无需安装应用，可通过台式机和移动设备上的新式 Web 浏览器加入虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="cd212-190">患者只需单击一下即可加入虚拟就诊，无需其他帐户或登录。</span><span class="sxs-lookup"><span data-stu-id="cd212-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="cd212-191">患者无需创建 Microsoft 帐户或登录即可启动虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="cd212-192">患者将被置于大厅中，直到医疗保健提供商加入预约并准许患者进行虚拟就诊。</span><span class="sxs-lookup"><span data-stu-id="cd212-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="cd212-193">加入虚拟就诊之前，可在大厅中测试视频和麦克风。</span><span class="sxs-lookup"><span data-stu-id="cd212-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![虚拟就诊患者体验](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="cd212-195">Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商标。</span><span class="sxs-lookup"><span data-stu-id="cd212-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="cd212-196">隐私和数据位置</span><span class="sxs-lookup"><span data-stu-id="cd212-196">Privacy and location of data</span></span>

<span data-ttu-id="cd212-197">Teams 与 EHR 系统集成可优化集成和虚拟就诊流期间正在使用和存储的数据量。</span><span class="sxs-lookup"><span data-stu-id="cd212-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="cd212-198">该解决方案遵循“Teams 隐私”中概述的总体 Teams 隐私和数据管理原则和准则。</span><span class="sxs-lookup"><span data-stu-id="cd212-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="cd212-199">Microsoft Teams EHR 连接器不会存储或传输来自 EHR 系统的任何可识别个人数据或者患者或医疗保健提供商的任何健康记录。</span><span class="sxs-lookup"><span data-stu-id="cd212-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="cd212-200">EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在 Teams 会议设置期间使用。</span><span class="sxs-lookup"><span data-stu-id="cd212-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="cd212-201">EHR 用户的唯一 ID 存储在“[Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)”中所述的三个地理区域之一。</span><span class="sxs-lookup"><span data-stu-id="cd212-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="cd212-202">会议参与者在 Teams 中输入的所有聊天、记录和其他数据都将根据现有的存储策略进行存储。</span><span class="sxs-lookup"><span data-stu-id="cd212-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="cd212-203">如需了解有关 Microsoft Teams 中的数据位置的更多信息，请访问 [Teams 中的数据位置](../../location-of-data-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cd212-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd212-204">相关主题</span><span class="sxs-lookup"><span data-stu-id="cd212-204">Related topics</span></span>

[<span data-ttu-id="cd212-205">Teams虚拟访问</span><span class="sxs-lookup"><span data-stu-id="cd212-205">Teams virtual visits</span></span>](ehr-admin-reports.md)