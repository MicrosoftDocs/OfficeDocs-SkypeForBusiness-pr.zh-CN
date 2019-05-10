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
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>将电子医疗记录集成到 Microsoft Teams 中

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

要参与专用预览，请参阅[在专用预览中的注册](#enroll-in-the-private-preview)。

本文适用于常规医疗保健 IT 开发人员感兴趣的医疗信息系统在使用 FHIR Api 连接到 Microsoft 团队。 这将使护理协调方案相匹配医疗保健组织的需要。

链接的文章文档的 Microsoft 团队患者应用程序，FHIR 接口规范和以下各节介绍什么是设置 FHIR 服务器和连接到您的开发环境或租户中的患者应用程序所必需的。 您需要熟悉的 FHIR 服务器选择，文档必须是受支持的选项之一：
- Datica （通过其[CMI](https://datica.com/compliant-managed-integration/)产品）
- 项 Cloverleaf （通过[项 FHIR 桥](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）
- Redox (通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/))
- Dapasoft （通过[Corolar FHIR 上](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> 此过程不包括使用 Microsoft 团队管理中心或 PowerShell cmdlet 启用功能的步骤。 FHIR 服务器/服务侧和患者应用程序客户端中，是完全完成配置。

下图展示了患者应用程序的体系结构：

![患者应用程序体系结构](../../media/patients-app-architecture.png)

以下各节介绍仅 FHIR 数据访问层患者应用程序的要求的 FHIR 服务器 （或 EHR 启用 FHIR Api） 必须满足才能集成患者应用程序，其中包括：

- 用户身份验证的期望值
- 集成界面的功能和技术要求
- 在性能和可靠性期望
- FHIR 资源的期望值患者应用程序支持
- 集成和预期的工作效率模型过程
- 如何注册您自己与您的客户在患者应用程序的专用预览
- 如何 FHIR 和一些常见面临患者 app 入门
- 将来下一步迭代患者应用程序的要求

> [!NOTE]
> 在以下各节，用于向任何第三方组织，可启用对患者应用程序通过 FHIR EHR 系统的集成和实现 FHIR 服务器以匹配列出的规范，请参阅 word"合作伙伴"互操作性合作伙伴"。

## <a name="functional-and-technical-requirements"></a>功能和技术要求  

### <a name="authentication"></a>身份验证  

即使 EHR 系统可能会实现用户级别授权，则应用程序级授权*用户级别授权不支持*是执行数据转换和公开 FHIR，通过 EHR 数据连接的更多常规支持的方法. 互操作服务 （合作伙伴） 获取提升到 EHR 数据，并公开相同的数据传递到互操作服务使用者 （患者应用程序） 没有授权上下文的相应 FHIR 资源的访问与互操作集成服务或平台。 患者应用程序不能强制实施用户级授权，但支持患者应用程序之间的互操作性合作伙伴的服务应用程序对应用程序身份验证。

下面介绍了应用程序对应用程序身份验证模型：

服务身份验证服务应通过 OAuth 2.0[客户端凭据流](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 合作伙伴服务需要提供以下信息：

1. 合作伙伴服务允许患者应用程序创建与合作伙伴，这样可使患者应用程序生成自己 client_id 和 client_secret，通过将伙伴的身份验证服务器上的身份验证注册门户管理帐户。
2. 合作伙伴服务拥有接受和验证的身份验证/授权系统、 （身份验证） 客户端凭据提供并提供了返回访问令牌与租户提示在范围内，如下所述。
3. 出于安全原因或在机密破坏的情况下，患者应用程序可以重新生成密钥和使无效或删除旧机密 （的相同示例位于 Azure 门户-AAD 应用程序注册）
4. 承载一致性的元数据终结点应未经身份验证，应不使用身份验证令牌的情况下可访问它。
5. 合作伙伴服务提供的令牌的终结点的患者应用程序请求使用客户端凭据流访问令牌。 按照授权服务器的令牌 url 应如以下示例所示的 FHIR 服务器上从元数据提取 FHIR 一致性声明 （功能） 语句的一部分：

![患者应用程序 5](../../media/Patient-app-5.png)

访问令牌的请求包括以下参数：

* * *

    POST /token HTTP/1.1 主机： 授权 server.com

    授予类型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx

* * *

合作伙伴服务提供 client_id 和 client_secret 患者应用程序，通过将伙伴的一侧的身份验证注册门户管理。 合作伙伴服务提供了到使用客户端凭据流请求访问令牌的终结点。 成功响应必须包括 token_type、 access_token 和 expires_in 参数。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>将映射 AAD 租户路由： 提供程序终结点

患者应用程序连接到合作伙伴服务通过一个终结点。 合作伙伴服务拥有并维护到各自医疗保健提供程序 （FHIR 服务器） 的合作伙伴服务正在使用的映射 (AAD 租户 ID) 的每个 Microsoft 客户的机制。

映射到提供程序的终结点 AAD 租户使用 AAD 租户 ID (GUID)。 患者应用程序将在范围中，租户 ID 传递时请求的每个请求访问令牌。 合作伙伴服务保留的租户 ID 映射到提供程序终结点，并将请求重定向到提供程序的终结点基于租户 id。 若要执行此操作，合作伙伴支持配置其端 （手动方式或通过门户的入职培训提供组织到其互操作平台的一部分）。

身份验证和路由工作流如下所示：

![患者应用程序 6](../../media/Patient-app-6.png)

1. 通过发送的应用程序访问令牌的请求：
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. 回复邮件中使用应用程序令牌：

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. 请求受保护的数据，使用访问令牌。
4. 授权消息： 选择要从范围内的租户 ID 路由到的适当 FHIR 服务器
5. 与应用程序令牌身份验证后，从授权 FHIR 服务器发送受保护的应用程序数据。

## <a name="interfaces"></a>接口

以下文章中记录了特定的呼叫和患者应用程序使用的字段。 选择适用于您 FHIR 服务器/FHIR Api 的接口。

- [DSTU2 接口规范](dstu2-interface.md)
- [STU3 接口规范](stu3-interface.md)

## <a name="performance-and-reliability"></a>性能和可靠性

在专用的预览患者应用程序时，有的端到端性能不保证能。 性能的因素包括参与工作流，在运行状况系统的环境中，EHR 从开始到互操作的合作伙伴的所有跃距的相对延迟及其基础结构，包括 FHIR 服务器并跨到 Office 365 生态系统和患者应用程序。

![互操作性合作伙伴](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>入门 FHIR  

如果您是新手 FHIR，并且需要轻松访问可以向 Microsoft 团队 EHR 集成界面来公开 FHIR 服务器，Microsoft 已打开源 FHIR 服务器可供所有开发人员使用。 请参阅[什么是对 Azure FHIR 服务器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)文章了解更多有关开源 FHIR 服务器可从 Microsoft 并将其部署的组织。

您可以使用 HSPC 打开沙盒 EHR 环境创建 EHR 还支持 open FHIR 服务器并用于播放使用患者应用程序。 我们建议您通读[HSPC 沙盒文档](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 不仅不会沙盒提供轻松、 面向用户界面，并且用户友好的创建、 添加和编辑患者的方式，它还为您提供了多个示例开始。  

## <a name="enroll-in-the-private-preview"></a>在专用预览中注册

创建开源 FHIR 服务器后，就真正容易连接到您的租户内部患者应用程序，按照下列步骤操作：

1. 初始详细信息[与我们联系](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview):  
    - 您的姓名
    - 您的位置
    - 公司或您的组织
    - 为什么您感兴趣 EHR 集成患者相关应用程序

    我们将回到您尽可能快地与多个问题，并指导您完成获取设置的专用预览的过程。

2. 确保该 sideloading 的自定义应用程序启用打算试用患者应用程序租户。 请参阅[应用程序的权限策略](../../admin-settings.md)，以了解如何开启这从团队管理中心您或您的客户的租户。

3. Sideload 患者应用程序清单 （在我们处理您的电子邮件向我们） 之后将获取来自 Microsoft 到要用于护理协调和患者舍入方案为租户中的工作组。 [上载到 Microsoft 团队应用程序包](/microsoftteams/platform/concepts/apps/apps-upload)中有周围如何端加载应用程序的详细的说明

4. 导航到作为团队所有者的常规通道，然后单击患者选项卡。您应看到就会显示两个首次运行的体验即选项 EHR 模式和手动模式。 请选择**EHR 模式**将 FHIR 服务器终结点 （即后更早版本与所有所需的数据和上方的规范每个资源只安装） 复制到链接字段并提供一个名称，也表示 FHIR 服务器的连接。 在连接上，单击和所有内容应准备就绪。

    ![患者 app 服务器设置](../../media/patients-server.png)

5. 开始使用应用程序患者从 FHIR 服务器/EHR 搜索和将它们添加到列表，请[为我们提供反馈](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)如果内容不起作用。 此外，建立患者应用程序的完全经过身份验证的版本-> FHIR 服务器流，请参与脱机对话框与 Microsoft 团队的医护人员产品工程、 通过电子邮件请求前面提到以阐明要求和我们将帮助您启用此每上述 FHIR 接口文档中的身份验证要求。  


