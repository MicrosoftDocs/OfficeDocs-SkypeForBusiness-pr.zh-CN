---
title: 患者应用概述
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者应用 EHR 集成
ms.openlocfilehash: d2177e4201a1c7d7087a4c04ffffbbf52dd7366c
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548307"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="dfcbb-103">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="dfcbb-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

<span data-ttu-id="dfcbb-104">若要参与私人预览版, 请参阅[注册私人预览版](#enroll-in-the-private-preview)。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="dfcbb-105">本文适用于使用 FHIR Api 在医疗信息系统上连接到 Microsoft 团队的一般医疗保健 IT 开发人员。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="dfcbb-106">这将启用符合医疗保健组织的需求的护理协调方案。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="dfcbb-107">链接的文章介绍 Microsoft 团队患者应用的 FHIR 界面规范, 并且以下各节介绍了设置 FHIR 服务器以及连接到你的开发环境或租户中的患者应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="dfcbb-108">您还需要熟悉所选 FHIR 服务器的文档, 该文档必须是受支持的选项之一:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="dfcbb-109">Datica (通过其[CMI](https://datica.com/compliant-managed-integration/)产品)</span><span class="sxs-lookup"><span data-stu-id="dfcbb-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="dfcbb-110">Infor Cloverleaf (通过[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="dfcbb-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="dfcbb-111">Redox (通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="dfcbb-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="dfcbb-112">Dapasoft (通过[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="dfcbb-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="dfcbb-113">此过程不包括使用 Microsoft 团队管理中心或 PowerShell cmdlet 启用功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="dfcbb-114">配置完全在 FHIR 服务器/服务端和患者应用客户端中完成。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="dfcbb-115">下面所示的是患者应用的体系结构:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-115">Illustrated below is the architecture of the Patients app:</span></span>

![患者应用体系结构图表](../../media/patients-app-architecture.png)

<span data-ttu-id="dfcbb-117">以下各部分介绍了 FHIR 服务器 (或支持 EHR 的 FHIR Api) 为与患者应用集成的患者应用的 FHIR 数据访问层的要求, 其中包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="dfcbb-118">有关用户身份验证的期望</span><span class="sxs-lookup"><span data-stu-id="dfcbb-118">Expectations around user authentication</span></span>
- <span data-ttu-id="dfcbb-119">集成界面的功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="dfcbb-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="dfcbb-120">关于性能和可靠性的期望值</span><span class="sxs-lookup"><span data-stu-id="dfcbb-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="dfcbb-121">患者应用支持的 FHIR 资源的期望值</span><span class="sxs-lookup"><span data-stu-id="dfcbb-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="dfcbb-122">用于集成的流程和预期的签约模型</span><span class="sxs-lookup"><span data-stu-id="dfcbb-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="dfcbb-123">如何在患者应用的私人预览版中注册自己和你的客户</span><span class="sxs-lookup"><span data-stu-id="dfcbb-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="dfcbb-124">如何开始使用 FHIR 和患者应用中的一些常见挑战</span><span class="sxs-lookup"><span data-stu-id="dfcbb-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="dfcbb-125">患者应用下一次迭代的未来要求</span><span class="sxs-lookup"><span data-stu-id="dfcbb-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="dfcbb-126">在以下部分中, "合作伙伴" 或 "互操作合作伙伴" 一词用于指可通过 FHIR 将患者应用集成到 EHR 系统的任何第三方组织, 并实现 FHIR 服务器以匹配列出的规范。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="dfcbb-127">功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="dfcbb-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="dfcbb-128">身份验证</span><span class="sxs-lookup"><span data-stu-id="dfcbb-128">Authentication</span></span>  

<span data-ttu-id="dfcbb-129">*使用不支持用户级授权*的应用级授权是更常用的方法来执行数据转换并通过 FHIR 公开连接来 EHR 数据, 即使 EHR 系统可能会实现用户级授权.</span><span class="sxs-lookup"><span data-stu-id="dfcbb-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="dfcbb-130">互操作服务 (合作伙伴) 获取对 EHR 数据的提升访问权限, 并且当它们公开与相应的 FHIR 资源相同的数据时, 不会将授权上下文传递到与互操作集成的互操作服务使用者 (患者应用)服务或平台。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="dfcbb-131">患者应用将不能强制实施用户级授权, 但支持应用程序进行患者应用和互操作合作伙伴的服务之间的应用程序身份验证。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner’s service.</span></span>

<span data-ttu-id="dfcbb-132">应用程序身份验证模型如下所述:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="dfcbb-133">应通过 OAuth 2.0[客户端凭据流](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)执行服务身份验证。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="dfcbb-134">合作伙伴服务需要提供以下内容:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="dfcbb-135">合作伙伴服务使患者应用可以创建合作伙伴的帐户, 从而使患者应用能够生成并拥有自己的 client_id 和 client_secret, 通过合作伙伴身份验证服务器上的身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-135">The Partner service enables the Patients app to create an account with the Partner, which  enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner’s Authentication server.</span></span>
2. <span data-ttu-id="dfcbb-136">合作伙伴服务拥有身份验证/授权系统, 该系统接受和验证 (身份验证) 提供的客户端凭据, 并在范围内向后提供租户提示的访问令牌, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-136">The Partner service owns the Authentication/Authorization system, which   accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="dfcbb-137">出于安全原因或在机密遭到破坏的情况下, 患者应用可以重新生成机密并使旧机密无效 (在 Azure 门户中提供相同的示例-AAD 应用注册)</span><span class="sxs-lookup"><span data-stu-id="dfcbb-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (Example of the same is available in Azure Portal - AAD App Registration)</span></span>
4. <span data-ttu-id="dfcbb-138">托管一致性语句的元数据终结点应取消身份验证, 它应该在没有身份验证令牌的情况下可以访问。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="dfcbb-139">合作伙伴服务提供患者应用的令牌终结点, 以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="dfcbb-140">按授权服务器的令牌 url 应该是从 FHIR 服务器上的元数据中提取的 FHIR 一致性 (功能) 语句的一部分, 如下例所示:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

![代码示例中的令牌 URL 的屏幕截图](../../media/Patient-app-5.png)

<span data-ttu-id="dfcbb-142">访问令牌的请求包含以下参数:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-142">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="dfcbb-143">POST/token HTTP/1.1 主机: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="dfcbb-143">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="dfcbb-144">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="dfcbb-144">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="dfcbb-145">合作伙伴服务提供患者应用的 client_id 和 client_secret, 通过合作伙伴的身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-145">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner’s side.</span></span> <span data-ttu-id="dfcbb-146">合作伙伴服务提供终结点以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-146">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="dfcbb-147">成功的响应必须包括 token_type、access_token 和 expires_in 参数。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-147">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="dfcbb-148">路由: 将 AAD 租户映射到提供方终结点</span><span class="sxs-lookup"><span data-stu-id="dfcbb-148">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="dfcbb-149">患者应用通过单个终结点连接到合作伙伴服务。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-149">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="dfcbb-150">合作伙伴服务拥有和维护一种机制, 可将每个 Microsoft 客户 (AAD 租户 ID) 映射到合作伙伴服务所使用的相应医疗保健提供商 (FHIR 服务器)。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-150">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="dfcbb-151">将 AAD 租户映射到提供程序终结点将使用 AAD 租户 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-151">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="dfcbb-152">患者应用在范围内传递租户 ID, 同时为每个请求请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-152">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="dfcbb-153">合作伙伴服务将租户 ID 的映射保留到提供方终结点, 并根据租户 ID 将请求重定向到提供方终结点。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-153">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="dfcbb-154">为此, 合作伙伴在将提供商组织加入其互操作平台的过程中手动或通过门户支持配置。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-154">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="dfcbb-155">身份验证和路由工作流如下所示:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-155">The Authentication and Routing workflow is shown below:</span></span>

![身份验证和路由工作流的图表](../../media/Patient-app-6.png)

1. <span data-ttu-id="dfcbb-157">通过发送以下内容请求应用访问令牌:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-157">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="dfcbb-158">使用应用令牌进行答复:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-158">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="dfcbb-159">使用访问令牌请求受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-159">Request protected data with Access token.</span></span>
4. <span data-ttu-id="dfcbb-160">授权消息: 选择要从作用域中的租户 ID 路由到的相应 FHIR 服务器</span><span class="sxs-lookup"><span data-stu-id="dfcbb-160">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="dfcbb-161">在对应用令牌进行身份验证后, 从授权的 FHIR 服务器发送受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-161">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="dfcbb-162">交互</span><span class="sxs-lookup"><span data-stu-id="dfcbb-162">Interfaces</span></span>

<span data-ttu-id="dfcbb-163">以下文章中记录了患者应用所使用的特定通话和字段。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-163">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="dfcbb-164">选择适用于你的 FHIR server/FHIR Api 的接口。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-164">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="dfcbb-165">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="dfcbb-165">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="dfcbb-166">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="dfcbb-166">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="dfcbb-167">性能和可靠性</span><span class="sxs-lookup"><span data-stu-id="dfcbb-167">Performance and Reliability</span></span>

<span data-ttu-id="dfcbb-168">患者应用在私人预览版中, 不能保证端到端的性能。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-168">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="dfcbb-169">性能因素包括工作流中涉及的所有跃点的相对延迟, 从运行状况系统环境中的 EHR 开始到互操作伙伴及其基础 (包括 FHIR 服务器和跨 Office 365 生态系统)患者应用。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-169">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互操作合作伙伴性能的插图](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="dfcbb-171">FHIR 入门</span><span class="sxs-lookup"><span data-stu-id="dfcbb-171">Get started with FHIR</span></span>  

<span data-ttu-id="dfcbb-172">如果你是 FHIR 新手, 并且需要轻松访问你可以向 Microsoft 团队 EHR 集成界面公开的 FHIR 服务器, Microsoft 有一个开放源代码 FHIR 服务器供所有开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-172">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="dfcbb-173">请参阅[AZURE FHIR Server For Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)文章, 了解有关 Microsoft 的 OPEN Source FHIR Server 的详细信息, 并将其部署给你的组织。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-173">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="dfcbb-174">你还可以使用 HSPC 开放式沙盒 EHR 环境创建一个 EHR, 该 EHR 还支持打开的 FHIR 服务器, 并使用它来在患者应用中玩。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-174">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="dfcbb-175">我们建议你阅读[HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-175">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="dfcbb-176">沙盒不仅提供了一种简单的 UI 和用户友好的创建、添加和编辑患者的方式, 还提供了几个示例来开始使用。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-176">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="dfcbb-177">注册私人预览版</span><span class="sxs-lookup"><span data-stu-id="dfcbb-177">Enroll in the private preview</span></span>

<span data-ttu-id="dfcbb-178">创建开放源代码 FHIR 服务器后, 通过执行以下所述步骤, 在租户内部连接到患者应用非常简单:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-178">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="dfcbb-179">[请](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)通过以下初始详细信息与我们联系:</span><span class="sxs-lookup"><span data-stu-id="dfcbb-179">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="dfcbb-180">您的姓名</span><span class="sxs-lookup"><span data-stu-id="dfcbb-180">Your Name</span></span>
    - <span data-ttu-id="dfcbb-181">您的职位</span><span class="sxs-lookup"><span data-stu-id="dfcbb-181">Your Position</span></span>
    - <span data-ttu-id="dfcbb-182">您所代表的公司或组织</span><span class="sxs-lookup"><span data-stu-id="dfcbb-182">The company or organization you represent</span></span>
    - <span data-ttu-id="dfcbb-183">为什么你对用于 EHR 集成的患者应用感兴趣</span><span class="sxs-lookup"><span data-stu-id="dfcbb-183">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="dfcbb-184">我们将尽快向您提供更多问题, 并指导您完成设置个人预览版的过程。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-184">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="dfcbb-185">确保在你要尝试患者应用的租户中启用了自定义应用的旁加载。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-185">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="dfcbb-186">请参阅[应用权限策略](../../admin-settings.md), 了解如何从团队管理中心为您或您的客户的租户打开此功能。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-186">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="dfcbb-187">旁加载将从 Microsoft (将电子邮件处理到美国) 转到租户中的团队, 并将该清单应用到要用于护理和患者舍入方案的团队中。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-187">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="dfcbb-188">有关如何加载应用的详细说明, 请将[应用包上载到 Microsoft 团队](/microsoftteams/platform/concepts/apps/apps-upload)</span><span class="sxs-lookup"><span data-stu-id="dfcbb-188">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="dfcbb-189">导航到 "常规" 通道作为团队所有者, 然后单击 "患者" 选项卡。你应该看到首次运行体验, 它将显示两个选项, 即 EHR 模式和手动模式。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-189">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="dfcbb-190">请选择**EHR 模式**, 并复制 FHIR 服务器终结点 (您刚才使用上述规范的所有必需数据和资源) 到链接字段, 并为连接提供一个表示 FHIR 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-190">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="dfcbb-191">单击 "连接", 一切准备就绪即可开始。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-191">Click on Connect, and everything should be ready to go.</span></span>

    ![患者应用服务器设置的屏幕截图](../../media/patients-server.png)

5. <span data-ttu-id="dfcbb-193">开始使用应用从 FHIR 服务器/EHR 搜索病人, 并将其添加到列表中, 如果不起作用, 请[向我们提供反馈](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-193">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="dfcbb-194">此外, 若要建立患者应用 > FHIR 服务器流的经完全验证的版本, 请使用 Microsoft 团队 for 医疗保健产品工程与 Microsoft 团队进行脱机对话, 以明确要求, 我们将根据上述 FHIR 界面文档中所述的身份验证要求, 帮助为你启用此项。</span><span class="sxs-lookup"><span data-stu-id="dfcbb-194">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  


