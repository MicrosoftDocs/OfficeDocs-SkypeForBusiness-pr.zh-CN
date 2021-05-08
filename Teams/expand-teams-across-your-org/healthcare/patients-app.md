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
description: 了解如何使用 FHIR API 将电子医疗保健记录Microsoft Teams患者应用。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096206"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="0ffa5-103">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="0ffa5-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="0ffa5-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="0ffa5-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="0ffa5-106">与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="0ffa5-107">用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="0ffa5-108">借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="0ffa5-109">查看列表的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="0ffa5-110">若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="0ffa5-111">本文面向对在医疗信息系统顶层使用 FHIR API 连接到医疗信息系统的一般医疗保健 IT 开发人员Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="0ffa5-112">这样可实现符合医疗保健组织需求的护理协调方案。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="0ffa5-113">链接的文章介绍了 Microsoft Teams Patients 应用的 FHIR 接口规范，以下部分介绍了在开发环境或租户中设置 FHIR 服务器并连接到 Patients 应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="0ffa5-114">还需要熟悉所选 FHIR 服务器的文档，这必须是受支持的选项之一：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="0ffa5-115">Datica ([CMI](https://datica.com/compliant-managed-integration/) 产品/服务) </span><span class="sxs-lookup"><span data-stu-id="0ffa5-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="0ffa5-116">Infor Cloverleaf ([Infor FHIR Bridge) ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="0ffa5-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="0ffa5-117">Redox ([R^FHIR 服务器) ](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="0ffa5-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="0ffa5-118">Dapasoft ([Corolar on FHIR) ](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="0ffa5-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="0ffa5-119">此过程不包括使用 Microsoft Teams 或 PowerShell cmdlet 启用功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="0ffa5-120">配置完全在 FHIR 服务器/服务端和 Patients 应用客户端中完成。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="0ffa5-121">下面演示了 Patients 应用的体系结构：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-121">Illustrated below is the architecture of the Patients app:</span></span>

![患者应用体系结构示意图](../../media/patients-app-architecture.png)

<span data-ttu-id="0ffa5-123">以下部分介绍 FHIR 服务器 (或启用了 EHR 的 FHIR API) 与 Patients 应用集成必须满足的仅 FHIR 数据访问层的要求，包括：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="0ffa5-124">有关用户身份验证的预期</span><span class="sxs-lookup"><span data-stu-id="0ffa5-124">Expectations around user authentication</span></span>
- <span data-ttu-id="0ffa5-125">集成接口的功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="0ffa5-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="0ffa5-126">有关性能和可靠性的预期</span><span class="sxs-lookup"><span data-stu-id="0ffa5-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="0ffa5-127">患者应用对 FHIR 资源的支持预期</span><span class="sxs-lookup"><span data-stu-id="0ffa5-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="0ffa5-128">集成过程和预期的参与模型</span><span class="sxs-lookup"><span data-stu-id="0ffa5-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="0ffa5-129">如何开始使用 FHIR 以及患者应用面临的一些常见挑战</span><span class="sxs-lookup"><span data-stu-id="0ffa5-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="0ffa5-130">患者应用下一次迭代的未来要求</span><span class="sxs-lookup"><span data-stu-id="0ffa5-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="0ffa5-131">在下列部分中，"合作伙伴"或"互操作合作伙伴"一词用于指代任何通过 FHIR 集成到患者应用的 EHR 系统的第三方组织，并且实施 FHIR 服务器以匹配列出的规范。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="0ffa5-132">功能和技术要求</span><span class="sxs-lookup"><span data-stu-id="0ffa5-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="0ffa5-133">身份验证</span><span class="sxs-lookup"><span data-stu-id="0ffa5-133">Authentication</span></span>  

<span data-ttu-id="0ffa5-134">应用级 *授权* （不支持用户级授权）是更常见的支持方法，用于通过 FHIR 执行数据转换和公开与 EHR 数据的连接，即使 EHR 系统可能实现用户级授权。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="0ffa5-135">互操作服务 (合作伙伴) 提升对 EHR 数据的访问权限，并且当它们公开与相应 FHIR 资源相同的数据时，不会将授权上下文传递给互操作服务使用者 (Patients 应用) 与互操作服务或平台集成。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="0ffa5-136">Patients 应用无法强制执行用户级授权，但支持在 Patients 应用与互操作合作伙伴的服务之间对应用程序进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="0ffa5-137">下面描述了应用程序到应用程序的身份验证模型：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="0ffa5-138">服务到服务身份验证应该通过 OAuth 2.0 [客户端凭据流 完成](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="0ffa5-139">合作伙伴服务需要提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="0ffa5-140">合作伙伴服务使患者应用能够与合作伙伴一起创建帐户，使患者应用能够生成并拥有 client_id 和 client_secret，通过合作伙伴的身份验证服务器上身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="0ffa5-141">合作伙伴服务拥有身份验证/授权系统，该系统接受并验证 (身份验证) 提供的客户端凭据，并返回范围中具有租户提示的访问令牌，如下所述。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="0ffa5-142">出于安全原因或发生机密违规时，Patients 应用可以重新生成机密，使旧机密失效或删除 (Azure 门户 - AAD 应用注册门户中提供了相同的示例) 。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="0ffa5-143">托管一致性语句的元数据终结点应该未经身份验证，并且应该可以在没有身份验证令牌的情况下访问。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="0ffa5-144">合作伙伴服务为 Patients 应用提供令牌终结点，以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="0ffa5-145">根据授权服务器，令牌 URL 应是 FHIR (功能) 从 FHIR 服务器上元数据提取的语句的一部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="0ffa5-146">访问令牌的请求由以下参数组成：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="0ffa5-147">合作伙伴服务为患者client_id client_secret服务，通过合作伙伴一侧的身份验证注册门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="0ffa5-148">合作伙伴服务提供终结点，以使用客户端凭据流请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="0ffa5-149">成功的响应必须包含token_type、access_token expires_in参数。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="0ffa5-150">路由：将 AAD 租户映射到提供程序终结点</span><span class="sxs-lookup"><span data-stu-id="0ffa5-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="0ffa5-151">Patients 应用通过单个终结点连接到合作伙伴服务。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="0ffa5-152">合作伙伴服务拥有并维护一种机制，将每个 Microsoft 客户 (AAD 租户 ID) 映射到合作伙伴服务正使用 (FHIR 服务器) 。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="0ffa5-153">将 AAD 租户映射到提供程序终结点使用 AAD 租户 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="0ffa5-154">Patients 应用在范围中传递租户 ID，同时请求每个请求的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="0ffa5-155">合作伙伴服务保留租户 ID 到提供程序终结点的映射，并基于租户 ID 将请求重定向到提供程序终结点。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="0ffa5-156">为此，合作伙伴支持在将提供商组织加入其互操作平台服务 (通过门户在最终用户端配置) 。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="0ffa5-157">身份验证和路由工作流如下所示：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-157">The Authentication and Routing workflow is shown below:</span></span>

![身份验证和路由工作流示意图](../../media/Patient-app-6.png)

1. <span data-ttu-id="0ffa5-159">通过发送：请求应用访问令牌：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="0ffa5-160">使用应用令牌答复：</span><span class="sxs-lookup"><span data-stu-id="0ffa5-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="0ffa5-161">使用访问令牌请求受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="0ffa5-162">授权消息：选择要从范围中的租户 ID 路由到的适当 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="0ffa5-163">使用应用令牌进行身份验证后，从授权的 FHIR 服务器发送应用保护的数据。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="0ffa5-164">接口</span><span class="sxs-lookup"><span data-stu-id="0ffa5-164">Interfaces</span></span>

<span data-ttu-id="0ffa5-165">以下文章介绍了患者应用使用的特定调用和字段。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="0ffa5-166">选择适用于 FHIR 服务器/FHIR API 的接口。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="0ffa5-167">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="0ffa5-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="0ffa5-168">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="0ffa5-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="0ffa5-169">性能和可靠性</span><span class="sxs-lookup"><span data-stu-id="0ffa5-169">Performance and Reliability</span></span>

<span data-ttu-id="0ffa5-170">虽然 Patients 应用为个人预览版，但无法保证端到端性能。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="0ffa5-171">性能因素包括工作流中涉及的所有跃点的相对延迟，从运行状况系统环境的 EHR 到互操作合作伙伴及其基础结构（包括 FHIR 服务器）以及 Office 365 生态系统和患者应用。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互操作合作伙伴性能插图](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="0ffa5-173">FHIR 入门</span><span class="sxs-lookup"><span data-stu-id="0ffa5-173">Get started with FHIR</span></span>  

<span data-ttu-id="0ffa5-174">如果对 FHIR 很了解，并且需要轻松访问 FHIR Server，并且该服务器可以公开给 Microsoft Teams EHR 集成接口，则 Microsoft 具有可供所有开发人员使用的开源 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="0ffa5-175">请参阅 [什么是适用于 Azure 的 FHIR 服务器](/azure/healthcare-apis/overview-open-source-server) 一文，详细了解 Microsoft 提供的开源 FHIR 服务器，并针对组织部署它。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-175">Please see the [What is FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="0ffa5-176">您还可以使用 HSPC Open 沙盒 EHR 环境创建一个 EHR，该 EHR 还支持打开的 FHIR Server，并使用它来与 Patients 应用一起玩。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="0ffa5-177">建议通读 [HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="0ffa5-178">沙盒不仅提供了一种简单、面向 UI 且用户友好的创建、添加和编辑患者的方式，还为你提供了几个入门示例。</span><span class="sxs-lookup"><span data-stu-id="0ffa5-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>