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
description: 了解如何使用 FHIR API 将电子医疗保健记录集成到 Microsoft Teams 患者应用中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096206"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>将电子医疗记录集成到 Microsoft Teams 中

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

本文面向对在医疗信息系统顶层使用 FHIR API 连接到 Microsoft Teams 感兴趣的一般医疗保健 IT 开发人员。 这样可实现符合医疗保健组织需求的护理协调方案。

链接的文章介绍了 Microsoft Teams Patients 应用的 FHIR 接口规范，以下部分介绍了在开发环境或租户中设置 FHIR 服务器并连接到 Patients 应用所需的内容。 还需要熟悉所选 FHIR 服务器的文档，这必须是受支持的选项之一：

- Datica ([CMI](https://datica.com/compliant-managed-integration/) 产品/服务) 
- Infor Cloverleaf ([Infor FHIR Bridge) ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox ([R^FHIR 服务器) ](https://www.redoxengine.com/fhir/)
- Dapasoft ([Corolar on FHIR) ](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> 此过程不包括使用 Microsoft Teams 管理中心或 PowerShell cmdlet 启用功能的步骤。 配置完全在 FHIR 服务器/服务端和 Patients 应用客户端中完成。

下面演示了 Patients 应用的体系结构：

![患者应用体系结构示意图](../../media/patients-app-architecture.png)

以下部分介绍 FHIR 服务器 (或启用了 EHR 的 FHIR API) 与 Patients 应用集成必须满足的仅 FHIR 数据访问层的要求，包括：

- 有关用户身份验证的预期
- 集成接口的功能和技术要求
- 有关性能和可靠性的预期
- 患者应用对 FHIR 资源的支持预期
- 集成过程和预期的参与模型
- 如何开始使用 FHIR 以及患者应用面临的一些常见挑战
- 患者应用下一次迭代的未来要求

> [!NOTE]
> 在下列部分中，"合作伙伴"或"互操作合作伙伴"一词用于指代任何通过 FHIR 集成到患者应用的 EHR 系统的第三方组织，并且实施 FHIR 服务器以匹配列出的规范。

## <a name="functional-and-technical-requirements"></a>功能和技术要求  

### <a name="authentication"></a>身份验证  

应用级 *授权* （不支持用户级授权）是更常见的支持方法，用于通过 FHIR 执行数据转换和公开与 EHR 数据的连接，即使 EHR 系统可能实现用户级授权。 互操作服务 (合作伙伴) 提升对 EHR 数据的访问权限，并且当它们公开与相应 FHIR 资源相同的数据时，不会将授权上下文传递给互操作服务使用者 (Patients 应用) 与互操作服务或平台集成。 Patients 应用无法强制执行用户级授权，但支持在 Patients 应用与互操作合作伙伴的服务之间对应用程序进行身份验证。

下面描述了应用程序到应用程序的身份验证模型：

服务到服务身份验证应该通过 OAuth 2.0 [客户端凭据流 完成](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 合作伙伴服务需要提供以下内容：

1. 合作伙伴服务使患者应用能够与合作伙伴一起创建帐户，使患者应用能够生成并拥有 client_id 和 client_secret，通过合作伙伴的身份验证服务器上身份验证注册门户进行管理。

2. 合作伙伴服务拥有身份验证/授权系统，该系统接受并验证 (身份验证) 提供的客户端凭据，并返回范围中具有租户提示的访问令牌，如下所述。

3. 出于安全原因或发生机密违规时，Patients 应用可以重新生成机密，使旧机密失效或删除 (Azure 门户 - AAD 应用注册门户中提供了相同的示例) 。

4. 托管一致性语句的元数据终结点应该未经身份验证，并且应该可以在没有身份验证令牌的情况下访问。

5. 合作伙伴服务为 Patients 应用提供令牌终结点，以使用客户端凭据流请求访问令牌。 根据授权服务器，令牌 URL 应是 FHIR (功能) 从 FHIR 服务器上元数据提取的语句的一部分，如以下示例所示：

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

访问令牌的请求由以下参数组成：

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

合作伙伴服务为患者client_id client_secret服务，通过合作伙伴一侧的身份验证注册门户进行管理。 合作伙伴服务提供终结点，以使用客户端凭据流请求访问令牌。 成功的响应必须包含token_type、access_token expires_in参数。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>路由：将 AAD 租户映射到提供程序终结点

Patients 应用通过单个终结点连接到合作伙伴服务。 合作伙伴服务拥有并维护一种机制，将每个 Microsoft 客户 (AAD 租户 ID) 映射到合作伙伴服务正使用 (FHIR 服务器) 。

将 AAD 租户映射到提供程序终结点使用 AAD 租户 ID (GUID) 。 Patients 应用在范围中传递租户 ID，同时请求每个请求的访问令牌。 合作伙伴服务保留租户 ID 到提供程序终结点的映射，并基于租户 ID 将请求重定向到提供程序终结点。 为此，合作伙伴支持在将提供商组织加入其互操作平台服务 (通过门户在最终用户端配置) 。

身份验证和路由工作流如下所示：

![身份验证和路由工作流示意图](../../media/Patient-app-6.png)

1. 通过发送：请求应用访问令牌：
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. 使用应用令牌答复：

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. 使用访问令牌请求受保护的数据。

4. 授权消息：选择要从范围中的租户 ID 路由到的适当 FHIR 服务器。

5. 使用应用令牌进行身份验证后，从授权的 FHIR 服务器发送应用保护的数据。

## <a name="interfaces"></a>接口

以下文章介绍了患者应用使用的特定调用和字段。 选择适用于 FHIR 服务器/FHIR API 的接口。

- [DSTU2 接口规范](dstu2-interface.md)
- [STU3 接口规范](stu3-interface.md)

## <a name="performance-and-reliability"></a>性能和可靠性

虽然 Patients 应用为个人预览版，但无法保证端到端性能。 性能因素包括工作流中涉及的所有跃点的相对延迟，从运行状况系统环境的 EHR 到互操作合作伙伴及其基础结构（包括 FHIR 服务器）以及 Office 365 生态系统和患者应用。

![互操作合作伙伴性能插图](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR 入门  

如果你是 FHIR 的新用户，并且需要轻松访问可以公开给 Microsoft Teams EHR 集成接口的 FHIR Server，则 Microsoft 具有可供所有开发人员使用的开源 FHIR 服务器。 请参阅 [什么是适用于 Azure 的 FHIR 服务器](/azure/healthcare-apis/overview-open-source-server) 一文，详细了解 Microsoft 提供的开源 FHIR 服务器，并针对组织部署它。

您还可以使用 HSPC Open 沙盒 EHR 环境创建一个 EHR，该 EHR 还支持打开的 FHIR Server，并使用它来与 Patients 应用一起玩。 建议通读 [HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 沙盒不仅提供了一种简单、面向 UI 且用户友好的创建、添加和编辑患者的方式，还为你提供了几个入门示例。