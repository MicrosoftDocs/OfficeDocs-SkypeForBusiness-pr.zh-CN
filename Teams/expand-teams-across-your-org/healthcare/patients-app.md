---
title: 患者应用概述
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
ms.reviewer: anach
description: 了解如何使用 FHIR Api 将电子医疗保健记录集成到 Microsoft 团队患者应用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29bb5b32cdd6e2f0d819adcc610639929921d078
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361382"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="3a0c5-103">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="3a0c5-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a0c5-104">**2020年10月15日，将弃用 "患者" 应用，并且用户将无法再从 "团队" 应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="3a0c5-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="3a0c5-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="3a0c5-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="3a0c5-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="3a0c5-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="3a0c5-109">使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="3a0c5-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="3a0c5-111">本文适用于使用 FHIR Api 在医疗信息系统上连接到 Microsoft 团队的一般医疗保健 IT 开发人员。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="3a0c5-112">这将启用符合医疗保健组织的需求的护理协调方案。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="3a0c5-113">链接的文章介绍 Microsoft 团队患者应用的 FHIR 界面规范，并且以下各节介绍了设置 FHIR 服务器以及连接到你的开发环境或租户中的患者应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="3a0c5-114">您还需要熟悉所选 FHIR 服务器的文档，该文档必须是受支持的选项之一：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="3a0c5-115">Datica (通过其 [CMI](https://datica.com/compliant-managed-integration/) 服务) </span><span class="sxs-lookup"><span data-stu-id="3a0c5-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="3a0c5-116">Infor Cloverleaf ([INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) </span><span class="sxs-lookup"><span data-stu-id="3a0c5-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="3a0c5-117">Redox (通过 [R ^ FHIR 服务器](https://www.redoxengine.com/fhir/)) </span><span class="sxs-lookup"><span data-stu-id="3a0c5-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="3a0c5-118">Dapasoft (通过 [Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) </span><span class="sxs-lookup"><span data-stu-id="3a0c5-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="3a0c5-119">此过程不包括使用 Microsoft 团队管理中心或 PowerShell cmdlet 启用功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="3a0c5-120">配置完全在 FHIR 服务器/服务端和患者应用客户端中完成。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="3a0c5-121">下面所示的是患者应用的体系结构：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-121">Illustrated below is the architecture of the Patients app:</span></span>

![患者应用体系结构图表](../../media/patients-app-architecture.png)

<span data-ttu-id="3a0c5-123">以下各部分介绍了 FHIR 服务器 (或 EHR 启用 FHIR Api) 必须满足才能与患者应用集成的患者应用的 "仅 FHIR 数据访问" 层的要求，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="3a0c5-124">有关用户身份验证的期望</span><span class="sxs-lookup"><span data-stu-id="3a0c5-124">Expectations around user authentication</span></span>
- <span data-ttu-id="3a0c5-125">集成界面的功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="3a0c5-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="3a0c5-126">关于性能和可靠性的期望值</span><span class="sxs-lookup"><span data-stu-id="3a0c5-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="3a0c5-127">患者应用支持的 FHIR 资源的期望值</span><span class="sxs-lookup"><span data-stu-id="3a0c5-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="3a0c5-128">用于集成的流程和预期的签约模型</span><span class="sxs-lookup"><span data-stu-id="3a0c5-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="3a0c5-129">如何开始使用 FHIR 和患者应用中的一些常见挑战</span><span class="sxs-lookup"><span data-stu-id="3a0c5-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="3a0c5-130">患者应用下一次迭代的未来要求</span><span class="sxs-lookup"><span data-stu-id="3a0c5-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="3a0c5-131">在以下部分中，"合作伙伴" 或 "互操作合作伙伴" 一词用于指可通过 FHIR 将患者应用集成到 EHR 系统的任何第三方组织，并实现 FHIR 服务器以匹配列出的规范。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="3a0c5-132">功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="3a0c5-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="3a0c5-133">身份验证</span><span class="sxs-lookup"><span data-stu-id="3a0c5-133">Authentication</span></span>  

<span data-ttu-id="3a0c5-134">*使用不支持用户级授权*的应用级授权是更常用的方法来执行数据转换并通过 FHIR 公开连接来 EHR 数据，即使 EHR 系统可能会实现用户级授权。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="3a0c5-135">互操作服务 (合作伙伴) 提升对 EHR 数据的访问权限，并且当它们公开与相应 FHIR 资源相同的数据时，不会将授权上下文传递到互操作服务使用者 (患者应用) 与互操作服务或平台集成。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="3a0c5-136">患者应用将不能强制实施用户级授权，但支持应用程序进行患者应用和互操作合作伙伴的服务之间的应用程序身份验证。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="3a0c5-137">应用程序身份验证模型如下所述：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="3a0c5-138">应通过 OAuth 2.0 [客户端凭据流](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)执行服务身份验证。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="3a0c5-139">合作伙伴服务需要提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="3a0c5-140">合作伙伴服务使患者应用可以创建合作伙伴的帐户，从而使患者应用能够生成并拥有 client_id 和 client_secret，通过合作伙伴身份验证服务器上的身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="3a0c5-141">合作伙伴服务拥有身份验证/授权系统，该系统接受和验证 (身份验证) 提供的客户端凭据，并在范围内向后提供租户提示的访问令牌，如下所述。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="3a0c5-142">出于安全原因或在机密遭到破坏的情况下，患者应用可以重新生成机密，从而使 Azure 门户中的 (（AAD 应用注册) 中提供相同的机密示例。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="3a0c5-143">托管一致性语句的元数据终结点应取消身份验证，它应该在没有身份验证令牌的情况下可以访问。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="3a0c5-144">合作伙伴服务提供患者应用的令牌终结点，以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="3a0c5-145">按授权服务器的令牌 url 应该是从 FHIR 服务器上的元数据中提取的 FHIR 一致性 (功能) 语句的一部分，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-145">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="3a0c5-146">{"resourceType"： "CapabilityStatement"，。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-146">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="3a0c5-147">.</span><span class="sxs-lookup"><span data-stu-id="3a0c5-147">.</span></span>
        <span data-ttu-id="3a0c5-148">.</span><span class="sxs-lookup"><span data-stu-id="3a0c5-148">.</span></span>
        <span data-ttu-id="3a0c5-149">"剩余"： [{"模式"： "服务器"，"安全性"： {"extension"： [{"extension"： [{"扩展名"： [{"" url "：" 标记 "，" valueUri "：" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token "}，{" url "：" 授权 "，" valueUri "：" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize "}]，" url "：" http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris "}]，" 服务 "： [{" 系统 "：" https://hl7.org/fhir/ValueSet/restful-security-service ""，"代码"： "OAuth"}]}]}。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-149">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="3a0c5-150">.</span><span class="sxs-lookup"><span data-stu-id="3a0c5-150">.</span></span>
                <span data-ttu-id="3a0c5-151">.</span><span class="sxs-lookup"><span data-stu-id="3a0c5-151">.</span></span>
            <span data-ttu-id="3a0c5-152">} ] }</span><span class="sxs-lookup"><span data-stu-id="3a0c5-152">} ] }</span></span>

* * *

<span data-ttu-id="3a0c5-153">访问令牌的请求包含以下参数：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-153">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="3a0c5-154">POST/token HTTP/1.1 主机： authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="3a0c5-154">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="3a0c5-155">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="3a0c5-155">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="3a0c5-156">合作伙伴服务提供患者应用的 client_id 和 client_secret，通过合作伙伴的身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-156">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="3a0c5-157">合作伙伴服务提供终结点以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-157">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="3a0c5-158">成功的响应必须包括 token_type、access_token 和 expires_in 参数。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-158">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="3a0c5-159">路由：将 AAD 租户映射到提供方终结点</span><span class="sxs-lookup"><span data-stu-id="3a0c5-159">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="3a0c5-160">患者应用通过单个终结点连接到合作伙伴服务。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-160">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="3a0c5-161">合作伙伴服务拥有和维护一种机制，可将每个 Microsoft 客户 (AAD 租户 ID) 映射到合作伙伴服务正在使用的 (FHIR server) 的各个健康服务提供商。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-161">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="3a0c5-162">将 AAD 租户映射到提供程序终结点将使用 AAD 租户 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-162">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="3a0c5-163">患者应用在范围内传递租户 ID，同时为每个请求请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-163">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="3a0c5-164">合作伙伴服务将租户 ID 的映射保留到提供方终结点，并根据租户 ID 将请求重定向到提供方终结点。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-164">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="3a0c5-165">为此，合作伙伴在将提供商组织加入到其互操作平台) 的过程中手动或通过门户来支持其最终 (的配置。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-165">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="3a0c5-166">身份验证和路由工作流如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-166">The Authentication and Routing workflow is shown below:</span></span>

![身份验证和路由工作流的图表](../../media/Patient-app-6.png)

1. <span data-ttu-id="3a0c5-168">通过发送以下内容请求应用访问令牌：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-168">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="3a0c5-169">使用应用令牌进行答复：</span><span class="sxs-lookup"><span data-stu-id="3a0c5-169">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="3a0c5-170">使用访问令牌请求受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-170">Request protected data with Access token.</span></span>
4. <span data-ttu-id="3a0c5-171">授权消息：选择要从作用域中的租户 ID 路由到的相应 FHIR 服务器</span><span class="sxs-lookup"><span data-stu-id="3a0c5-171">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="3a0c5-172">在对应用令牌进行身份验证后，从授权的 FHIR 服务器发送受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-172">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="3a0c5-173">交互</span><span class="sxs-lookup"><span data-stu-id="3a0c5-173">Interfaces</span></span>

<span data-ttu-id="3a0c5-174">以下文章中记录了患者应用所使用的特定通话和字段。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-174">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="3a0c5-175">选择适用于你的 FHIR server/FHIR Api 的接口。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-175">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="3a0c5-176">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="3a0c5-176">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="3a0c5-177">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="3a0c5-177">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="3a0c5-178">性能和可靠性</span><span class="sxs-lookup"><span data-stu-id="3a0c5-178">Performance and Reliability</span></span>

<span data-ttu-id="3a0c5-179">患者应用在私人预览版中，不能保证端到端的性能。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-179">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="3a0c5-180">性能方面的因素包括工作流中涉及的所有跃点的相对延迟，从运行状况系统环境中的 EHR 开始到互操作伙伴及其基础（包括 FHIR 服务器以及跨 Office 365 生态应用和患者应用）。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-180">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互操作合作伙伴性能的插图](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="3a0c5-182">FHIR 入门</span><span class="sxs-lookup"><span data-stu-id="3a0c5-182">Get started with FHIR</span></span>  

<span data-ttu-id="3a0c5-183">如果你是 FHIR 新手，并且需要轻松访问你可以向 Microsoft 团队 EHR 集成界面公开的 FHIR 服务器，Microsoft 有一个开放源代码 FHIR 服务器供所有开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-183">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="3a0c5-184">请参阅 [AZURE FHIR Server For Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 文章，了解有关 Microsoft 的 OPEN Source FHIR Server 的详细信息，并将其部署给你的组织。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-184">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="3a0c5-185">你还可以使用 HSPC 开放式沙盒 EHR 环境创建一个 EHR，该 EHR 还支持打开的 FHIR 服务器，并使用它来在患者应用中玩。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-185">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="3a0c5-186">我们建议你阅读 [HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-186">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="3a0c5-187">沙盒不仅提供了一种简单的 UI 和用户友好的创建、添加和编辑患者的方式，还提供了几个示例来开始使用。</span><span class="sxs-lookup"><span data-stu-id="3a0c5-187">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 