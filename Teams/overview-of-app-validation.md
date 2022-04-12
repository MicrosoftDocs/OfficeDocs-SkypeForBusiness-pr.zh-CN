---
title: Microsoft 提供的应用验证和应用测试概述
ms.reviewer: ''
description: 了解为 Teams 应用完成的质量检查和应用验证。
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
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756988"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Microsoft 对所有 Teams 应用执行的验证

Microsoft 要求所有应用在应用商店中上架以供最终使用之前通过强制的验证。 它适用于 Teams 应用商店上发布的所有应用（自定义应用除外）。 此外，Microsoft 强烈建议应用开发人员参与应用的可选认证，以指示增强的合规性、安全、隐私控制。

所有应用都需要遵守 Microsoft 应用认证策略。 Teams 应用商店团队会执行 400 多个测试，以确保应用可用，并遵守高隐私和安全标准。

若要了解应用开发人员遵守的详细验证准则，请参阅[开发人员的验证指南](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。 本指南基于 [Teams 应用的认证策略](/legal/marketplace/certification-policies#1140-teams)。

> [!NOTE]
> Microsoft 的验证和检查不适用于自定义应用，因为它是在你的组织内开发的，并且仅对组织的成员可用。

## <a name="app-validation-and-testing"></a>应用验证和测试

在 Teams 应用商店上提供每个应用之前，我们会为它们执行 400 多项测试用例。 这些测试可确保适当的功能、用户体验、安全性，并确保所有应用都符合公开列出的 CMO 策略。 以下是 Microsoft 应用验证团队在发布之前针对每个应用执行的一些测试：

* 确保应用请求的 Graph 权限确实是应用功能需要的权限，而不是任何额外权限。 定期检查现有应用的图形权限，以确保应用无需额外权限。
* 要求用户登录的应用具有注销选项。
* 所有应用发布者都会在 Microsoft 合作伙伴中心上进行详细验证过程。 验证包括电子邮件验证、业务验证等。 若要详细了解应用发布，请参阅[开发人员如何创建合作伙伴中心帐户](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、[面向开发人员的提交指南](/office/dev/store/add-in-submission-guide)、[开发人员如何发布应用](https://aka.ms/PublishToTeamsStore)。
* 只有来自已验证发布服务器的应用可以从最终用户寻求 Graph 权限。
* 没有应用可以下载可执行文件。
* 测试应用是否不包含广告、其他应用的促销
* 应用程序经过测试，符合工作需要，没有攻击性语言、网络攻击机器人、垃圾邮件或诈骗内容。
* 应用中的所有链接都可正常运行，并且仅与应用产品相关。
* 作为应用商店运行状况检查的一部分，我们会定期测试和评估所有发布的 Teams 应用。
* 涵盖 Teams 应用的隐私策略和使用条款由 ISV 发布
* ISV 的联系人详细信息可在应用商店一览及其各自的[发布者证明页面](/microsoft-365-app-certification/teams/teams-apps)上找到。

此外，Microsoft 鼓励应用开发人员参与其合规性计划，这是一种严格的双层方法，可确保应用质量、安全性、合规性。 Teams 应用商店中有数百个超越了已经很详尽的验证准则并符合这些计划的应用。

## <a name="publisher-verification"></a>发布者验证

应用开发人员必须先进行验证，然后才能将其应用提交给 Microsoft。 发布者使用其 Microsoft 合作伙伴网络 (MPN) 帐户验证其身份，并将此 MPN 帐户与其应用注册相关联。 发布者验证可帮助管理员和终端用户了解到与 Microsoft 标识平台集成的应用开发人员的真实性。 发布者验证具有以下优势：

* 提高了客户的透明度和风险降低 - 此功能可帮助客户了解他们信任的开发人员发布的组织中使用的应用。
* 改进了品牌打造 - `verified` 徽章会显示在 Azure Active Directory 许可提示、企业应用页面以及最终用户和管理员使用的其他用户界面上。
* 更顺畅的企业采用 - 管理员可以配置用户同意策略，将发布者验证状态作为主要策略条件。

## <a name="see-also"></a>另请参阅

* [Microsoft 365 应用合规性计划的管理员概述](overview-of-app-certification.md)
