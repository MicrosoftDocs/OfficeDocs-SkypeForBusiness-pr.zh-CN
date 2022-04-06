---
title: Microsoft 提供的应用验证和应用测试概述
ms.reviewer: ''
description: 了解Teams应用的质量检查、应用验证和认证计划。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9accce27ded20f8ce78d4d5b80f6aff474213675
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64649012"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Microsoft 对Teams应用执行的检查和验证

Microsoft 要求所有应用在应用商店中列出最终用途之前，必须通过强制验证。 它适用于所有应用 (除了自定义应用) 发布在Teams应用商店。 此外，Microsoft 强烈建议应用开发人员参与应用的可选认证，以指示增强的合规性、安全和隐私控制。

所有应用都必须遵循 Microsoft 应用认证策略。 Teams应用商店团队执行 400 多个测试，以确保应用可用，并遵守高标准的隐私和安全性。

若要了解应用开发人员遵守的详细验证准则，请参阅 [面向开发人员的验证指南](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。

> [!NOTE]
> Microsoft 的验证和检查不适用于自定义应用，因为自定义应用是在组织内开发的，并且仅适用于组织成员。

<!--- TBD: Add the link later. 
To review the certification policies of any app, see [App certification policies]().
Is the link /microsoft-365-app-certification/teams/teams-apps
--->

## <a name="app-validation-and-testing"></a>应用验证和测试

在每个应用在 Teams 应用商店上可用之前，我们会对每个应用执行 400 多个测试用例。 测试可确保适当的功能、用户体验和安全性，并确保所有应用都符合公开列出的 CMO 策略。 以下是 Microsoft 应用验证团队在发布之前针对每个应用执行的一些测试：

* 确保应用请求的Graph权限确实是应用功能需要的权限，而不是任何额外的权限。 定期检查现有应用的Graph权限，以确保应用无需额外权限。
* 要求用户登录/登录的应用必须具有注销/注销选项。
* 所有应用发布者都会在 Microsoft 合作伙伴中心进行详细的验证过程。 验证包括电子邮件验证、业务验证等。 若要详细了解应用发布，请参阅 [开发人员如何创建合作伙伴中心帐户](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、 [面向开发人员的提交指南](/office/dev/store/add-in-submission-guide)以及 [开发人员如何发布应用](https://aka.ms/PublishToTeamsStore)。
* 只有经过验证的发布服务器的应用才能向最终用户寻求Graph权限。
* 任何应用都无法下载可执行文件。
* 测试应用不包含广告、其他应用的促销
* 测试应用是否适合使用任何攻击性语言、网络攻击机器人、垃圾邮件或诈骗内容。
* 应用中的所有链接都可正常运行，并且仅与应用产品/服务相关。
* 作为应用商店运行状况检查的一部分，我们会定期测试和评估所有已发布的Teams应用。
* 涵盖Teams应用的隐私策略和使用条款由 ISV 发布
* ISV 的联系人详细信息可在应用商店列表及其各自的[Publisher证明页面](/microsoft-365-app-certification/teams/teams-apps)上找到。

## <a name="publisher-verification"></a>Publisher验证

Publisher验证可帮助管理员和最终用户了解应用程序开发人员与Microsoft 标识平台集成的真实性。 拥有经过验证的发布者意味着发布者已使用其 Microsoft 合作伙伴网络 (MPN) 帐户验证其标识，并将此 MPN 帐户与其应用注册相关联。

Publisher验证提供以下优势：

* 提高客户的透明度和降低风险 - 此功能可帮助客户了解其组织中使用的应用由他们信任的开发人员发布。
* 改进了品牌打造 - `verified` Azure Active Directory许可提示、Enterprise应用页面以及最终用户和管理员使用的其他用户界面上显示徽章。
* 更平滑的企业采用 - 管理员可以配置用户同意策略，发布者验证状态作为主要策略条件。

此外，Microsoft 鼓励应用开发人员参与其合规性计划，这是一种严格的双层方法，可确保应用质量、安全性和符合性。 Teams应用商店包含数百个应用，这些应用超越了已详细的验证准则并符合这些程序。

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365应用符合性计划

Microsoft 合规性计划演示了针对派生自领先行业标准框架的控件对应用进行审查，并制定了强大的安全性和合规性做法来保护客户数据。 此程序有两个阶段：

* Publisher证明。
* Microsoft 365认证。

### <a name="publisher-attestation"></a>Publisher证明

应用开发人员需要完成自我评估，其中包括客户或 IT 管理员在评估应用的安全性和符合性时经常提出的问题。 然后，Microsoft 发布此信息，以便更轻松、更及时地进行评估。 这些信息包括有关在组织中激活应用时的数据处理、安全性、合规性和隐私的详细信息。

若要了解详细信息，请参阅 [发布证明指南](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)。

### <a name="microsoft-365-certification"></a>Microsoft 365认证

应用认证通过以应用的安全性和合规性框架、流程和过程为中心的全面评估的合格分析师评审和批准来实现。 应用将针对派生自领先行业标准框架的一系列安全控制进行审核。 该证书演示了在组织中激活应用时为保护客户数据而实施的强安全性和合规性做法。

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
