---
title: Microsoft 应用认证概述
description: 了解 Microsoft 365 应用合规性计划，包括第三方应用的安全性、合规性、隐私。
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 09/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e86f5e372bc1c03c2dc75b09f5e26b8fb5d98241
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677492"
---
# <a name="know-about-apps-that-undergo-app-compliance-program-for-security-data-handling-and-privacy"></a>了解通过应用合规性计划实现安全性、数据处理和隐私的应用

Microsoft 365 应用合规性计划针对派生自领先行业标准框架的控制来检查和审核应用。 该计划演示了为保护客户数据而实施的功能强大的安全性和合规性做法。 计划包括以下阶段：

* [发布者验证](#publisher-verification)。
* [发布者证明](#publisher-attestation)。
* [Microsoft 365 认证](#microsoft-365-certification)。

## <a name="publisher-verification"></a>发布者验证

应用开发人员必须先进行验证，然后才能将其应用提交给 Microsoft。 开发人员使用其 Microsoft 合作伙伴网络 (MPN) 帐户验证其标识，并将此 MPN 帐户与其应用注册相关联。 发布者验证可帮助管理员和最终用户了解应用程序开发人员的真实性。 发布者验证具有以下优势：

* 提高了客户的透明度和风险降低 - 此功能可帮助客户了解他们信任的开发人员发布的组织中使用的应用。
* 改进了品牌打造 - `verified` 徽章会显示在 Azure Active Directory 许可提示、企业应用页面以及最终用户和管理员使用的其他用户界面上。
* 更顺畅的企业采用 - 管理员可以配置用户同意策略，将发布者验证状态作为主要策略条件。

## <a name="publisher-attestation"></a>发布者证明

发布者证明是应用合规性计划的下一层。 经发布者证明的应用为管理员提供了有关应用安全性和合规性措施的可信度。 它还有助于缩短查看应用的此信息的时间。 该证明将针对 [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) 确定的 80 多个风险因素反映应用的安全性、数据处理和合规性实践。 发布者证明过程可以在发布者验证完成之前启动。

应用开发人员需要完成自我评估，其中包括客户和 IT 管理员经常提出的问题，以评估应用的安全性和合规性。 然后，Microsoft 会发布此信息，以便更轻松、更及时地进行评估。 若要了解详细信息，请参阅[证明指南](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)。

管理员可以通过三种不同的方式快速检查已发布且已证明的应用。

* 当收集有关应用的更多信息时，请在 [Microsoft Teams 应用安全性和合规性](/microsoft-365-app-certification/teams/teams-apps)处的相应链接中查看特定应用的详细信息。 或者，选择 [ Teams 管理中心](https://admin.teams.microsoft.com/) 中的 `Publisher attestation` 链接。

  :::image type="content" source="media/attested-app-tac3.png" alt-text="在 Teams 管理中心，选择发布者证明链接以查看应用证明的详细信息。":::

* 在 Teams 管理中心，从“**[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**”页面检查应用的详细信息时，请查看应用详细信息页面横幅上的“发布者已证明”图标。

  :::image type="content" source="media/attested-app-tac1.png" alt-text="在 Teams 管理中心，“发布者已证明”图标显示在所有已证明的应用上。":::

* 在 Teams 管理中心中，在 [向应用授予权限](app-permissions-admin-center.md)之前，应用名称前面的蓝色复选标记表示它是发布者证明的应用。 所有Microsoft 365 应用也会经过发布者证明，因此Microsoft 365 应用也会显示蓝色复选标记。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 管理中心内用于授予权限的对话框上，蓝色复选标记指示这是经发布者证明的应用。":::

经证明或认证的应用的证明详细信息页会列出以下详细信息。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="为已证明应用提供的详细信息。":::

## <a name="microsoft-365-certification"></a>Microsoft 365 认证

应用认证通过以下方式实现：

* 由合格分析师进行评审。
* 对围绕应用安全性和合规性框架、流程和过程的综合评估进行审批。

我们将根据源自领先的行业标准框架的一系列安全控制措施对应用进行检查。

证书表明，当在组织中使用应用时，实施了强大的安全性和合规性实践来保护客户数据。 有关管理员和最终用户如何从认证中受益的详细信息，请参阅 [ Microsoft 365 应用合规性计划概述](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)。

管理员可以通过以下方式快速检查Microsoft 365 认证应用。

* 在 Web 上收集有关应用的详细信息时，请参阅 [Microsoft 文档中有关该应用的防护图标](/microsoft-365-app-certification/teams/teams-apps)。

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="在有关应用的安全性和符合性的详细帮助文章中查看 Microsoft 365 认证信息":::

* 在 [Teams 管理中心](https://admin.teams.microsoft.com/policies/manage-apps) 检查应用程序时，请使用“认证”列对应用列表进行排序。 请参阅图标，并可以选择链接以访问上面提到的特定于应用的页面。

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="在 Teams 管理中心查看应用的Microsoft 365 认证状态。" lightbox="media/m365cert-apps-list2.png":::

* 查看应用的详细信息时，请参阅应用横幅中的 Microsoft 365 认证图标。

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="在 Teams 管理中心管理特定应用时，查看应用横幅中的 Microsoft 365 认证信息":::

* 在 Teams 管理中心中，在 [向应用授予权限](app-permissions-admin-center.md)之前，应用名称前面的蓝色复选标记表示它是发布者证明的应用。 所有Microsoft 365 应用也会经过发布者证明，因此Microsoft 365 应用也会显示蓝色复选标记。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 管理中心的授予权限对话框中，管理员可以查看蓝色复选标记，确保应用已获得 Microsoft 365 证明":::

## <a name="view-security-compliance-and-privacy-information"></a>查看安全性、合规性、隐私信息

你可以在 [Microsoft 文档](/microsoft-365-app-certification/teams/teams-apps) 和 [Teams 管理中心](https://admin.teams.microsoft.com/policies/manage-apps) 找到有关受证明或认证的应用的安全性、隐私、合规性、行为的信息。

### <a name="microsoft-documentation"></a>Microsoft 文档

有关每个列出应用的安全性、隐私性、合规性等详细信息，请参阅 [Microsoft Teams 应用安全性和合规性](/microsoft-365-app-certification/teams/teams-apps)中链接的特定于应用的帮助文章。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="为接受 Microsoft 合规性计划的应用提供的详细信息。":::

### <a name="teams-admin-center"></a>Teams 管理中心

估应用时，可以使用独立的 Cloud Access Security Brokers (CASB)（如 Microsoft Cloud App Security (MCAS)）来查找有关应用的安全性和行为的信息。 Teams 管理中心包含 MCAS 中针对 Microsoft 365 认证应用的安全性和符合性的信息。 在应用详细信息页中检查此信息，以验证应用是否满足你的安全需求。

> [!NOTE]
> 无论你的组织是否有支持 MCAS 的许可证，此功能都可供所有管理员使用。

若要访问应用的 MCAS 信息，请执行以下操作：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 选择 **认证** 对应用进行排序，并将所有 Microsoft 365 认证应用推送到表的顶部。

1. 选择 Microsoft 365 认证应用。

1. 选择 **安全性和符合性** 选项卡。

   :::image type="content" source="media/mcas.png" alt-text="Teams 管理中心安全性和合规性选项卡的屏幕截图。" lightbox="media/mcas.png":::

   若要获取有关应用支持的功能的更多详细信息，请选择每个类别的下拉列表。

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>查看应用的隐私策略和使用条款

在 Teams 管理中心内，每个应用页面都链接到应用的隐私声明和使用条款。

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="在 Teams 管理中心，管理员可以访问指向每个应用的隐私策略和使用条款的链接。" lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>相关文章

* [查看应用权限并授予管理员许可](app-permissions-admin-center.md)。
