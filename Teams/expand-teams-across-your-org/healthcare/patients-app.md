---
title: 患者应用程序概述
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
description: Microsoft 团队患者 app EHR 集成
ms.openlocfilehash: f157061666dc72a8420b9b9331387b42d6918cea
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865035"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="a50fd-103">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="a50fd-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

<span data-ttu-id="a50fd-104">要参与专用预览，请参阅[在专用预览中的注册](#enroll-in-the-private-preview)。</span><span class="sxs-lookup"><span data-stu-id="a50fd-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="a50fd-105">本文适用于常规医疗保健 IT 开发人员感兴趣的医疗信息系统在使用 FHIR Api 连接到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="a50fd-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="a50fd-106">这将使护理协调方案相匹配医疗保健组织的需要。</span><span class="sxs-lookup"><span data-stu-id="a50fd-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="a50fd-107">链接的文章文档的 Microsoft 团队患者应用程序，FHIR 接口规范和以下各节介绍什么是设置 FHIR 服务器和连接到您的开发环境或租户中的患者应用程序所必需的。</span><span class="sxs-lookup"><span data-stu-id="a50fd-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="a50fd-108">您需要熟悉的 FHIR 服务器选择，文档必须是受支持的选项之一：</span><span class="sxs-lookup"><span data-stu-id="a50fd-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="a50fd-109">Datica （通过其[CMI](https://datica.com/compliant-managed-integration/)产品）</span><span class="sxs-lookup"><span data-stu-id="a50fd-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="a50fd-110">项 Cloverleaf （通过[项 FHIR 桥](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）</span><span class="sxs-lookup"><span data-stu-id="a50fd-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="a50fd-111">Redox (通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="a50fd-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="a50fd-112">Dapasoft （通过[Corolar FHIR 上](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="a50fd-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="a50fd-113">此过程不包括使用 Microsoft 团队管理中心或 PowerShell cmdlet 启用功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="a50fd-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="a50fd-114">FHIR 服务器/服务侧和患者应用程序客户端中，是完全完成配置。</span><span class="sxs-lookup"><span data-stu-id="a50fd-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="a50fd-115">下图展示了患者应用程序的体系结构：</span><span class="sxs-lookup"><span data-stu-id="a50fd-115">Illustrated below is the architecture of the Patients app:</span></span>

![患者应用程序体系结构](../../media/patients-app-architecture.png)

<span data-ttu-id="a50fd-117">以下各节介绍仅 FHIR 数据访问层患者应用程序的要求的 FHIR 服务器 （或 EHR 启用 FHIR Api） 必须满足才能集成患者应用程序，其中包括：</span><span class="sxs-lookup"><span data-stu-id="a50fd-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="a50fd-118">用户身份验证的期望值</span><span class="sxs-lookup"><span data-stu-id="a50fd-118">Expectations around user authentication</span></span>
- <span data-ttu-id="a50fd-119">集成界面的功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="a50fd-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="a50fd-120">在性能和可靠性期望</span><span class="sxs-lookup"><span data-stu-id="a50fd-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="a50fd-121">FHIR 资源的期望值患者应用程序支持</span><span class="sxs-lookup"><span data-stu-id="a50fd-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="a50fd-122">集成和预期的工作效率模型过程</span><span class="sxs-lookup"><span data-stu-id="a50fd-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="a50fd-123">如何注册您自己与您的客户在患者应用程序的专用预览</span><span class="sxs-lookup"><span data-stu-id="a50fd-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="a50fd-124">如何 FHIR 和一些常见面临患者 app 入门</span><span class="sxs-lookup"><span data-stu-id="a50fd-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="a50fd-125">将来下一步迭代患者应用程序的要求</span><span class="sxs-lookup"><span data-stu-id="a50fd-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="a50fd-126">在以下各节，用于向任何第三方组织，可启用对患者应用程序通过 FHIR EHR 系统的集成和实现 FHIR 服务器以匹配列出的规范，请参阅 word"合作伙伴"互操作性合作伙伴"。</span><span class="sxs-lookup"><span data-stu-id="a50fd-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="a50fd-127">功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="a50fd-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="a50fd-128">身份验证</span><span class="sxs-lookup"><span data-stu-id="a50fd-128">Authentication</span></span>  

<span data-ttu-id="a50fd-129">即使 EHR 系统可能会实现用户级别授权，则应用程序级授权*用户级别授权不支持*是执行数据转换和公开 FHIR，通过 EHR 数据连接的更多常规支持的方法.</span><span class="sxs-lookup"><span data-stu-id="a50fd-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="a50fd-130">互操作服务 （合作伙伴） 获取提升到 EHR 数据，并公开相同的数据传递到互操作服务使用者 （患者应用程序） 没有授权上下文的相应 FHIR 资源的访问与互操作集成服务或平台。</span><span class="sxs-lookup"><span data-stu-id="a50fd-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="a50fd-131">患者应用程序不能强制实施用户级授权，但支持患者应用程序之间的互操作性合作伙伴的服务应用程序对应用程序身份验证。</span><span class="sxs-lookup"><span data-stu-id="a50fd-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner’s service.</span></span>

<span data-ttu-id="a50fd-132">下面介绍了应用程序对应用程序身份验证模型：</span><span class="sxs-lookup"><span data-stu-id="a50fd-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="a50fd-133">服务身份验证服务应通过 OAuth 2.0[客户端凭据流](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="a50fd-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="a50fd-134">合作伙伴服务需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="a50fd-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="a50fd-135">合作伙伴服务允许患者应用程序创建与合作伙伴，这样可使患者应用程序生成自己 client_id 和 client_secret，通过将伙伴的身份验证服务器上的身份验证注册门户管理帐户。</span><span class="sxs-lookup"><span data-stu-id="a50fd-135">The Partner service enables the Patients app to create an account with the Partner, which  enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner’s Authentication server.</span></span>
2. <span data-ttu-id="a50fd-136">合作伙伴服务拥有接受和验证的身份验证/授权系统、 （身份验证） 客户端凭据提供并提供了返回访问令牌与租户提示在范围内，如下所述。</span><span class="sxs-lookup"><span data-stu-id="a50fd-136">The Partner service owns the Authentication/Authorization system, which   accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="a50fd-137">出于安全原因或在机密破坏的情况下，患者应用程序可以重新生成密钥和使无效或删除旧机密 （的相同示例位于 Azure 门户-AAD 应用程序注册）</span><span class="sxs-lookup"><span data-stu-id="a50fd-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (Example of the same is available in Azure Portal - AAD App Registration)</span></span>
4. <span data-ttu-id="a50fd-138">承载一致性的元数据终结点应未经身份验证，应不使用身份验证令牌的情况下可访问它。</span><span class="sxs-lookup"><span data-stu-id="a50fd-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="a50fd-139">合作伙伴服务提供的令牌的终结点的患者应用程序请求使用客户端凭据流访问令牌。</span><span class="sxs-lookup"><span data-stu-id="a50fd-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="a50fd-140">按照授权服务器的令牌 url 应如以下示例所示的 FHIR 服务器上从元数据提取 FHIR 一致性声明 （功能） 语句的一部分：</span><span class="sxs-lookup"><span data-stu-id="a50fd-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

![患者应用程序 5](../../media/Patient-app-5.png)

<span data-ttu-id="a50fd-142">访问令牌的请求包括以下参数：</span><span class="sxs-lookup"><span data-stu-id="a50fd-142">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="a50fd-143">POST /token HTTP/1.1 主机： 授权 server.com</span><span class="sxs-lookup"><span data-stu-id="a50fd-143">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="a50fd-144">授予类型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="a50fd-144">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="a50fd-145">合作伙伴服务提供 client_id 和 client_secret 患者应用程序，通过将伙伴的一侧的身份验证注册门户管理。</span><span class="sxs-lookup"><span data-stu-id="a50fd-145">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner’s side.</span></span> <span data-ttu-id="a50fd-146">合作伙伴服务提供了到使用客户端凭据流请求访问令牌的终结点。</span><span class="sxs-lookup"><span data-stu-id="a50fd-146">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="a50fd-147">成功响应必须包括 token_type、 access_token 和 expires_in 参数。</span><span class="sxs-lookup"><span data-stu-id="a50fd-147">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="a50fd-148">将映射 AAD 租户路由： 提供程序终结点</span><span class="sxs-lookup"><span data-stu-id="a50fd-148">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="a50fd-149">患者应用程序连接到合作伙伴服务通过一个终结点。</span><span class="sxs-lookup"><span data-stu-id="a50fd-149">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="a50fd-150">合作伙伴服务拥有并维护到各自医疗保健提供程序 （FHIR 服务器） 的合作伙伴服务正在使用的映射 (AAD 租户 ID) 的每个 Microsoft 客户的机制。</span><span class="sxs-lookup"><span data-stu-id="a50fd-150">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="a50fd-151">映射到提供程序的终结点 AAD 租户使用 AAD 租户 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="a50fd-151">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="a50fd-152">患者应用程序将在范围中，租户 ID 传递时请求的每个请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="a50fd-152">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="a50fd-153">合作伙伴服务保留的租户 ID 映射到提供程序终结点，并将请求重定向到提供程序的终结点基于租户 id。</span><span class="sxs-lookup"><span data-stu-id="a50fd-153">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="a50fd-154">若要执行此操作，合作伙伴支持配置其端 （手动方式或通过门户的入职培训提供组织到其互操作平台的一部分）。</span><span class="sxs-lookup"><span data-stu-id="a50fd-154">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="a50fd-155">身份验证和路由工作流如下所示：</span><span class="sxs-lookup"><span data-stu-id="a50fd-155">The Authentication and Routing workflow is shown below:</span></span>

![患者应用程序 6](../../media/Patient-app-6.png)

1. <span data-ttu-id="a50fd-157">通过发送的应用程序访问令牌的请求：</span><span class="sxs-lookup"><span data-stu-id="a50fd-157">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="a50fd-158">回复邮件中使用应用程序令牌：</span><span class="sxs-lookup"><span data-stu-id="a50fd-158">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="a50fd-159">请求受保护的数据，使用访问令牌。</span><span class="sxs-lookup"><span data-stu-id="a50fd-159">Request protected data with Access token.</span></span>
4. <span data-ttu-id="a50fd-160">授权消息： 选择要从范围内的租户 ID 路由到的适当 FHIR 服务器</span><span class="sxs-lookup"><span data-stu-id="a50fd-160">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="a50fd-161">与应用程序令牌身份验证后，从授权 FHIR 服务器发送受保护的应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="a50fd-161">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="a50fd-162">接口</span><span class="sxs-lookup"><span data-stu-id="a50fd-162">Interfaces</span></span>

<span data-ttu-id="a50fd-163">以下文章中记录了特定的呼叫和患者应用程序使用的字段。</span><span class="sxs-lookup"><span data-stu-id="a50fd-163">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="a50fd-164">选择适用于您 FHIR 服务器/FHIR Api 的接口。</span><span class="sxs-lookup"><span data-stu-id="a50fd-164">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="a50fd-165">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="a50fd-165">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="a50fd-166">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="a50fd-166">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="a50fd-167">性能和可靠性</span><span class="sxs-lookup"><span data-stu-id="a50fd-167">Performance and Reliability</span></span>

<span data-ttu-id="a50fd-168">在专用的预览患者应用程序时，有的端到端性能不保证能。</span><span class="sxs-lookup"><span data-stu-id="a50fd-168">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="a50fd-169">性能的因素包括参与工作流，在运行状况系统的环境中，EHR 从开始到互操作的合作伙伴的所有跃距的相对延迟及其基础结构，包括 FHIR 服务器并跨到 Office 365 生态系统和患者应用程序。</span><span class="sxs-lookup"><span data-stu-id="a50fd-169">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互操作性合作伙伴](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="a50fd-171">入门 FHIR</span><span class="sxs-lookup"><span data-stu-id="a50fd-171">Get started with FHIR</span></span>  

<span data-ttu-id="a50fd-172">如果您是新手 FHIR，并且需要轻松访问可以向 Microsoft 团队 EHR 集成界面来公开 FHIR 服务器，Microsoft 已打开源 FHIR 服务器可供所有开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="a50fd-172">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="a50fd-173">请参阅[什么是对 Azure FHIR 服务器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)文章了解更多有关开源 FHIR 服务器可从 Microsoft 并将其部署的组织。</span><span class="sxs-lookup"><span data-stu-id="a50fd-173">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="a50fd-174">您可以使用 HSPC 打开沙盒 EHR 环境创建 EHR 还支持 open FHIR 服务器并用于播放使用患者应用程序。</span><span class="sxs-lookup"><span data-stu-id="a50fd-174">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="a50fd-175">我们建议您通读[HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="a50fd-175">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="a50fd-176">不仅不会沙盒提供轻松、 面向用户界面，并且用户友好的创建、 添加和编辑患者的方式，它还为您提供了多个示例开始。</span><span class="sxs-lookup"><span data-stu-id="a50fd-176">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="a50fd-177">在专用预览中注册</span><span class="sxs-lookup"><span data-stu-id="a50fd-177">Enroll in the private preview</span></span>

<span data-ttu-id="a50fd-178">创建开源 FHIR 服务器后，就真正容易连接到您的租户内部患者应用程序，按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a50fd-178">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="a50fd-179">初始详细信息[与我们联系](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview):</span><span class="sxs-lookup"><span data-stu-id="a50fd-179">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="a50fd-180">您的姓名</span><span class="sxs-lookup"><span data-stu-id="a50fd-180">Your Name</span></span>
    - <span data-ttu-id="a50fd-181">您的位置</span><span class="sxs-lookup"><span data-stu-id="a50fd-181">Your Position</span></span>
    - <span data-ttu-id="a50fd-182">公司或您的组织</span><span class="sxs-lookup"><span data-stu-id="a50fd-182">The company or organization you represent</span></span>
    - <span data-ttu-id="a50fd-183">为什么您感兴趣 EHR 集成患者相关应用程序</span><span class="sxs-lookup"><span data-stu-id="a50fd-183">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="a50fd-184">我们将回到您尽可能快地与多个问题，并指导您完成获取设置的专用预览的过程。</span><span class="sxs-lookup"><span data-stu-id="a50fd-184">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="a50fd-185">确保该 sideloading 的自定义应用程序启用打算试用患者应用程序租户。</span><span class="sxs-lookup"><span data-stu-id="a50fd-185">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="a50fd-186">请参阅[应用程序的权限策略](../../admin-settings.md)，以了解如何开启这从团队管理中心您或您的客户的租户。</span><span class="sxs-lookup"><span data-stu-id="a50fd-186">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="a50fd-187">Sideload 患者应用程序清单 （在我们处理您的电子邮件向我们） 之后将获取来自 Microsoft 到要用于护理协调和患者舍入方案为租户中的工作组。</span><span class="sxs-lookup"><span data-stu-id="a50fd-187">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="a50fd-188">[上载到 Microsoft 团队应用程序包](/microsoftteams/platform/concepts/apps/apps-upload)中有周围如何端加载应用程序的详细的说明</span><span class="sxs-lookup"><span data-stu-id="a50fd-188">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="a50fd-189">导航到作为团队所有者的常规通道，然后单击患者选项卡。您应看到就会显示两个首次运行的体验即选项 EHR 模式和手动模式。</span><span class="sxs-lookup"><span data-stu-id="a50fd-189">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="a50fd-190">请选择**EHR 模式**将 FHIR 服务器终结点 （即后更早版本与所有所需的数据和上方的规范每个资源只安装） 复制到链接字段并提供一个名称，也表示 FHIR 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="a50fd-190">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="a50fd-191">在连接上，单击和所有内容应准备就绪。</span><span class="sxs-lookup"><span data-stu-id="a50fd-191">Click on Connect, and everything should be ready to go.</span></span>

    ![患者 app 服务器设置](../../media/patients-server.png)

5. <span data-ttu-id="a50fd-193">开始使用应用程序患者从 FHIR 服务器/EHR 搜索和将它们添加到列表，请[为我们提供反馈](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)如果内容不起作用。</span><span class="sxs-lookup"><span data-stu-id="a50fd-193">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="a50fd-194">此外，建立患者应用程序的完全经过身份验证的版本-> FHIR 服务器流，请参与脱机对话框与 Microsoft 团队的医护人员产品工程、 通过电子邮件请求前面提到以阐明要求和我们将帮助您启用此每上述 FHIR 接口文档中的身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="a50fd-194">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  


