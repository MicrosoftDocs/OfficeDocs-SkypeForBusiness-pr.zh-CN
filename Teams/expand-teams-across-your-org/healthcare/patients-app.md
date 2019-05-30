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
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>将电子医疗记录集成到 Microsoft Teams 中

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

若要参与私人预览版, 请参阅[注册私人预览版](#enroll-in-the-private-preview)。

本文适用于使用 FHIR Api 在医疗信息系统上连接到 Microsoft 团队的一般医疗保健 IT 开发人员。 这将启用符合医疗保健组织的需求的护理协调方案。

链接的文章介绍 Microsoft 团队患者应用的 FHIR 界面规范, 并且以下各节介绍了设置 FHIR 服务器以及连接到你的开发环境或租户中的患者应用所需的内容。 您还需要熟悉所选 FHIR 服务器的文档, 该文档必须是受支持的选项之一:
- Datica (通过其[CMI](https://datica.com/compliant-managed-integration/)产品)
- Infor Cloverleaf (通过[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/))
- Dapasoft (通过[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> 此过程不包括使用 Microsoft 团队管理中心或 PowerShell cmdlet 启用功能的步骤。 配置完全在 FHIR 服务器/服务端和患者应用客户端中完成。

下面所示的是患者应用的体系结构:

![患者应用体系结构图表](../../media/patients-app-architecture.png)

以下各部分介绍了 FHIR 服务器 (或支持 EHR 的 FHIR Api) 为与患者应用集成的患者应用的 FHIR 数据访问层的要求, 其中包括以下内容:

- 有关用户身份验证的期望
- 集成界面的功能和技术要求
- 关于性能和可靠性的期望值
- 患者应用支持的 FHIR 资源的期望值
- 用于集成的流程和预期的签约模型
- 如何在患者应用的私人预览版中注册自己和你的客户
- 如何开始使用 FHIR 和患者应用中的一些常见挑战
- 患者应用下一次迭代的未来要求

> [!NOTE]
> 在以下部分中, "合作伙伴" 或 "互操作合作伙伴" 一词用于指可通过 FHIR 将患者应用集成到 EHR 系统的任何第三方组织, 并实现 FHIR 服务器以匹配列出的规范。

## <a name="functional-and-technical-requirements"></a>功能和技术要求  

### <a name="authentication"></a>身份验证  

*使用不支持用户级授权*的应用级授权是更常用的方法来执行数据转换并通过 FHIR 公开连接来 EHR 数据, 即使 EHR 系统可能会实现用户级授权. 互操作服务 (合作伙伴) 获取对 EHR 数据的提升访问权限, 并且当它们公开与相应的 FHIR 资源相同的数据时, 不会将授权上下文传递到与互操作集成的互操作服务使用者 (患者应用)服务或平台。 患者应用将不能强制实施用户级授权, 但支持应用程序进行患者应用和互操作合作伙伴的服务之间的应用程序身份验证。

应用程序身份验证模型如下所述:

应通过 OAuth 2.0[客户端凭据流](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)执行服务身份验证。 合作伙伴服务需要提供以下内容:

1. 合作伙伴服务使患者应用可以创建合作伙伴的帐户, 从而使患者应用能够生成并拥有自己的 client_id 和 client_secret, 通过合作伙伴身份验证服务器上的身份验证注册门户进行管理。
2. 合作伙伴服务拥有身份验证/授权系统, 该系统接受和验证 (身份验证) 提供的客户端凭据, 并在范围内向后提供租户提示的访问令牌, 如下所述。
3. 出于安全原因或在机密遭到破坏的情况下, 患者应用可以重新生成机密并使旧机密无效 (在 Azure 门户中提供相同的示例-AAD 应用注册)
4. 托管一致性语句的元数据终结点应取消身份验证, 它应该在没有身份验证令牌的情况下可以访问。
5. 合作伙伴服务提供患者应用的令牌终结点, 以使用客户端凭据流请求访问令牌。 按授权服务器的令牌 url 应该是从 FHIR 服务器上的元数据中提取的 FHIR 一致性 (功能) 语句的一部分, 如下例所示:

![代码示例中的令牌 URL 的屏幕截图](../../media/Patient-app-5.png)

访问令牌的请求包含以下参数:

* * *

    POST/token HTTP/1.1 主机: authorization-server.com

    grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx

* * *

合作伙伴服务提供患者应用的 client_id 和 client_secret, 通过合作伙伴的身份验证注册门户进行管理。 合作伙伴服务提供终结点以使用客户端凭据流请求访问令牌。 成功的响应必须包括 token_type、access_token 和 expires_in 参数。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>路由: 将 AAD 租户映射到提供方终结点

患者应用通过单个终结点连接到合作伙伴服务。 合作伙伴服务拥有和维护一种机制, 可将每个 Microsoft 客户 (AAD 租户 ID) 映射到合作伙伴服务所使用的相应医疗保健提供商 (FHIR 服务器)。

将 AAD 租户映射到提供程序终结点将使用 AAD 租户 ID (GUID)。 患者应用在范围内传递租户 ID, 同时为每个请求请求访问令牌。 合作伙伴服务将租户 ID 的映射保留到提供方终结点, 并根据租户 ID 将请求重定向到提供方终结点。 为此, 合作伙伴在将提供商组织加入其互操作平台的过程中手动或通过门户支持配置。

身份验证和路由工作流如下所示:

![身份验证和路由工作流的图表](../../media/Patient-app-6.png)

1. 通过发送以下内容请求应用访问令牌:
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. 使用应用令牌进行答复:

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. 使用访问令牌请求受保护的数据。
4. 授权消息: 选择要从作用域中的租户 ID 路由到的相应 FHIR 服务器
5. 在对应用令牌进行身份验证后, 从授权的 FHIR 服务器发送受保护的数据。

## <a name="interfaces"></a>交互

以下文章中记录了患者应用所使用的特定通话和字段。 选择适用于你的 FHIR server/FHIR Api 的接口。

- [DSTU2 接口规范](dstu2-interface.md)
- [STU3 接口规范](stu3-interface.md)

## <a name="performance-and-reliability"></a>性能和可靠性

患者应用在私人预览版中, 不能保证端到端的性能。 性能因素包括工作流中涉及的所有跃点的相对延迟, 从运行状况系统环境中的 EHR 开始到互操作伙伴及其基础 (包括 FHIR 服务器和跨 Office 365 生态系统)患者应用。

![互操作合作伙伴性能的插图](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR 入门  

如果你是 FHIR 新手, 并且需要轻松访问你可以向 Microsoft 团队 EHR 集成界面公开的 FHIR 服务器, Microsoft 有一个开放源代码 FHIR 服务器供所有开发人员使用。 请参阅[AZURE FHIR Server For Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)文章, 了解有关 Microsoft 的 OPEN Source FHIR Server 的详细信息, 并将其部署给你的组织。

你还可以使用 HSPC 开放式沙盒 EHR 环境创建一个 EHR, 该 EHR 还支持打开的 FHIR 服务器, 并使用它来在患者应用中玩。 我们建议你阅读[HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 沙盒不仅提供了一种简单的 UI 和用户友好的创建、添加和编辑患者的方式, 还提供了几个示例来开始使用。  

## <a name="enroll-in-the-private-preview"></a>注册私人预览版

创建开放源代码 FHIR 服务器后, 通过执行以下所述步骤, 在租户内部连接到患者应用非常简单:

1. [请](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)通过以下初始详细信息与我们联系:  
    - 您的姓名
    - 您的职位
    - 您所代表的公司或组织
    - 为什么你对用于 EHR 集成的患者应用感兴趣

    我们将尽快向您提供更多问题, 并指导您完成设置个人预览版的过程。

2. 确保在你要尝试患者应用的租户中启用了自定义应用的旁加载。 请参阅[应用权限策略](../../admin-settings.md), 了解如何从团队管理中心为您或您的客户的租户打开此功能。

3. 旁加载将从 Microsoft (将电子邮件处理到美国) 转到租户中的团队, 并将该清单应用到要用于护理和患者舍入方案的团队中。 有关如何加载应用的详细说明, 请将[应用包上载到 Microsoft 团队](/microsoftteams/platform/concepts/apps/apps-upload)

4. 导航到 "常规" 通道作为团队所有者, 然后单击 "患者" 选项卡。你应该看到首次运行体验, 它将显示两个选项, 即 EHR 模式和手动模式。 请选择**EHR 模式**, 并复制 FHIR 服务器终结点 (您刚才使用上述规范的所有必需数据和资源) 到链接字段, 并为连接提供一个表示 FHIR 服务器的名称。 单击 "连接", 一切准备就绪即可开始。

    ![患者应用服务器设置的屏幕截图](../../media/patients-server.png)

5. 开始使用应用从 FHIR 服务器/EHR 搜索病人, 并将其添加到列表中, 如果不起作用, 请[向我们提供反馈](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)。 此外, 若要建立患者应用 > FHIR 服务器流的经完全验证的版本, 请使用 Microsoft 团队 for 医疗保健产品工程与 Microsoft 团队进行脱机对话, 以明确要求, 我们将根据上述 FHIR 界面文档中所述的身份验证要求, 帮助为你启用此项。  


