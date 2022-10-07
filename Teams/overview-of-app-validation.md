---
title: Microsoft 提供的应用验证和应用测试概述
description: 了解基于市场认证策略的 Teams 应用验证指南。 了解 Microsoft 如何确保 Teams 应用遵守隐私和安全的高标准。
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 08/11/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eeb0c49dcf560b858b8723f813cc86b6b51c1daa
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377550"
---
# <a name="testing-and-validation-done-by-microsoft-for-all-teams-apps"></a>Microsoft 针对所有 Teams 应用执行的测试和验证

Microsoft 要求所有应用在应用商店中上架以供最终使用之前通过强制的验证。 它适用于 Teams 应用商店上发布的所有应用（自定义应用除外）。 此外，Microsoft 强烈建议应用开发人员参与应用的可选认证，以指示增强的合规性、安全、隐私控制。

所有应用都需要遵守 Microsoft 应用认证策略。 Teams 应用商店团队会执行 400 多个测试，以确保应用可用，并遵守高隐私和安全标准。

若要了解应用开发人员遵守的详细验证准则，请参阅[开发人员的验证指南](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。 本指南基于 [Teams 应用的认证策略](/legal/marketplace/certification-policies#1140-teams)。

> [!NOTE]
> Microsoft 的验证和检查不适用于自定义应用，因为它是在你的组织内开发的，并且仅对组织的成员可用。

## <a name="app-validation-and-testing"></a>应用验证和测试

在 Teams 应用商店上提供每个应用之前，我们会为它们执行 400 多项测试用例。 这些测试可确保适当的功能、用户体验、安全性，并确保所有应用都符合公开列出的 CMO 策略。 以下是 Microsoft 应用验证团队在发布之前针对每个应用执行的一些测试：

* 确保应用请求的 Graph 权限确实是应用功能需要的权限，而不是任何额外权限。 定期检查现有应用的图形权限，以确保应用无需额外权限。
* 要求用户登录的应用具有注销选项。
* 所有应用的开发人员都会在 Microsoft 合作伙伴中心进行详细的验证过程。 验证包括电子邮件验证、业务验证等。 若要详细了解应用发布，请参阅[开发人员如何创建合作伙伴中心帐户](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、[面向开发人员的提交指南](/office/dev/store/add-in-submission-guide)、[开发人员如何发布应用](https://aka.ms/PublishToTeamsStore)。
* 只有来自经过验证的开发人员的应用才能向最终用户寻求 Graph 权限。
* 没有应用可以下载可执行文件。
* 测试应用是否不包含广告、其他应用的促销。
* 应用程序经过测试，符合工作需要，没有攻击性语言、网络攻击机器人、垃圾邮件或诈骗内容。
* 应用中的所有链接都可正常运行，并且仅与应用产品相关。
* 作为应用商店运行状况检查的一部分，我们会定期测试和评估所有发布的 Teams 应用。
* 涵盖 Teams 应用的隐私策略和使用条款由应用开发人员提供。
* 应用开发人员的联系详细信息可在应用商店一览及其各自的[发布者证明页面](/microsoft-365-app-certification/teams/teams-apps)上找到。

此外，Microsoft 鼓励应用开发人员参与其合规性计划，这是一种严格的双层方法，可确保应用质量、安全性、合规性。 Teams 应用商店中有数百个超越了已经很详尽的验证准则并符合这些计划的应用。

## <a name="related-article"></a>相关文章

* [Microsoft 365 应用合规性计划的管理员概述](overview-of-app-certification.md)
