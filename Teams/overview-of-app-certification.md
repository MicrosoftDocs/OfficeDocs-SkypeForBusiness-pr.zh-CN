---
title: Microsoft 应用认证概述
ms.reviewer: ''
description: 了解 Teams 应用的应用证明和认证计划。
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
ms.openlocfilehash: 85277e9948dac1e083eb587f9bfc3787be3644a6
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137153"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>Microsoft 365 应用合规性计划，适用于第三方应用的安全性、合规性和隐私

Microsoft 合规性计划根据派生自领先的行业标准框架的控件检查和审核应用。 该计划演示了为保护客户数据而实施的功能强大的安全性和合规性做法。 计划包括以下阶段：

* 发布者验证。
* 发布者证明。
* Microsoft 365 认证。

## <a name="publisher-verification"></a>发布者验证

应用开发人员必须先进行验证，然后才能将其应用提交给 Microsoft。 发布者使用其 Microsoft 合作伙伴网络 (MPN) 帐户验证其标识，并将此 MPN 帐户与其应用注册相关联。 发布者验证可帮助管理员和最终用户了解应用程序开发人员的真实性。 发布者验证具有以下优势：

* 提高了客户的透明度和风险降低 - 此功能可帮助客户了解他们信任的开发人员发布的组织中使用的应用。
* 改进了品牌打造 - `verified` 徽章会显示在 Azure Active Directory 许可提示、企业应用页面以及最终用户和管理员使用的其他用户界面上。
* 更顺畅的企业采用 - 管理员可以配置用户同意策略，将发布者验证状态作为主要策略条件。

## <a name="publisher-attestation"></a>发布者证明

发布者证明是应用合规性计划的下一层。 经发布者证明的应用为管理员提供了有关应用安全性和合规性措施的可信度。 它还有助于缩短查看应用的此信息的时间。 该证明将针对 [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) 确定的 80 多个风险因素反映应用的安全性、数据处理和合规性实践。 发布者证明过程可以在发布者验证完成之前启动。

应用开发人员需要完成自我评估，其中包括客户和 IT 管理员经常提出的问题，以评估应用的安全性和合规性。 然后，Microsoft 会发布此信息，以便更轻松、更及时地进行评估。 若要了解详细信息，请参阅[证明指南](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)。

管理员可以通过三种不同的方式快速检查已发布且已证明的应用。

* 当收集有关应用的更多信息时，请访问位于 [Microsoft Teams 应用安全性和合规性](/microsoft-365-app-certification/teams/teams-apps) 的相应链接查看特定应用的详细信息。或者，可在 Teams 管理中心内选择发布者证明链接。

  :::image type="content" source="media/attested-app-tac3.png" alt-text="在 Teams 管理中心，单击发布者证明链接以查看应用证明的详细信息":::

* 在 Teams 管理中心，从“**管理应用**”页面检查应用的详细信息时，请查看应用详细信息页面横幅上的“发布者已证明”图标。

  :::image type="content" source="media/attested-app-tac1.png" alt-text="在 Teams 管理中心，“发布者已证明”图标显示在所有已证明的应用上。":::

* 在 Teams 管理中心内向应用授予权限时，应用名称前面的蓝色复选标记会指示应用是经过发布者证明的应用，还是经过 Microsoft 365 认证的应用。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 管理中心内用于授予权限的对话框上，蓝色复选标记指示这是经发布者证明的应用。":::

经证明或认证的应用的证明详细信息页会列出以下详细信息。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="为已证明应用提供的详细信息。":::

## <a name="microsoft-365-certification"></a>Microsoft 365 认证

应用认证通过以下方式实现：

* 由合格分析师进行评审。
* 对围绕应用安全性和合规性框架、流程和过程的综合评估进行审批。

我们将根据源自领先的行业标准框架的一系列安全控制措施对应用进行检查。

证书表明，当在组织中激活应用时，实施了强大的安全性和合规性实践来保护客户数据。 有关 Microsoft 365 认证对管理员和最终用户有用的详细信息，请参阅 [Microsoft 365 应用符合性计划](/microsoft-365-app-certification/docs/enterprise-app-certification-guide) 概述。

管理员可以通过以下方式快速检查Microsoft 365 认证应用。

* 在 Web 上收集有关应用的详细信息时，请参阅 Microsoft 文档中有关该应用的防护图标。

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="在有关应用的安全性和符合性的详细帮助文章中查看 Microsoft 365 认证信息":::

* 在 Teams 管理中心检查应用程序时，请使用“认证”列对应用列表进行排序。 请参阅图标，并可以选择链接以访问上面提到的特定于应用的页面。

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="在 Teams 管理中心查看应用的Microsoft 365 认证状态。" lightbox="media/m365cert-apps-list2.png":::

* 查看应用的详细信息时，请参阅应用横幅中的 Microsoft 365 认证图标。

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="在 Teams 管理中心管理特定应用时，查看应用横幅中的 Microsoft 365 认证信息":::

* 在 Teams 管理中心内向应用授予权限时，应用名称前面的蓝色复选标记会指示应用是经过发布者证明的应用，还是经过 Microsoft 365 认证的应用。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 管理中心的授予权限对话框中，管理员可以查看蓝色复选标记，确保应用已获得 Microsoft 365 证明":::

## <a name="view-security-compliance-and-privacy-information"></a>查看安全性、合规性、隐私信息

你可以在 Microsoft 文档和 Teams 管理中心找到有关受证明或认证的应用的安全性、隐私、合规性、行为的信息。

### <a name="microsoft-documentation"></a>Microsoft 文档

有关每个列出应用的安全性、隐私性、合规性等详细信息，请参阅 [Microsoft Teams 应用安全性和合规性](/microsoft-365-app-certification/teams/teams-apps)中链接的特定于应用的帮助文章。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="为接受 Microsoft 合规性计划的应用提供的详细信息。":::

### <a name="teams-admin-center"></a>Teams 管理中心

为组织评估应用时，可以使用独立的 Cloud Access Security Brokers (CASB)（如 Microsoft Cloud App Security (MCAS)）来查找有关应用的安全性和行为的信息。 Teams 管理中心包含 MCAS 中针对 Microsoft 365 认证应用的安全性和符合性的信息，可用于检查应用是否满足你的需求。

> [!NOTE]
> 无论你的组织是否有支持 MCAS 的许可证，此功能都可供所有管理员使用。

若要访问应用的 MCAS 信息，请执行以下操作：

1. 在 Teams 管理中心中，选择 **Teams 应用** 下的 **管理应用**。
1. 选择 **认证** 对应用进行排序，并将所有 Microsoft 365 认证应用推送到表的顶部。
1. 选择 Microsoft 365 认证应用。
1. 选择 **安全性和符合性** 选项卡。

   :::image type="content" source="media/mcas.png" alt-text="Teams 管理中心安全性和合规性选项卡的屏幕截图":::

   若要获取有关应用支持的功能的更多详细信息，请选择每个类别的下拉列表。

<!--- TBD: Move to the permissions article 

## View the granted Graph permissions in Azure Portal

Admins can grant permission to an app on behalf of all organization users. It helps avoid each user to individually request the permissions. Permissions granted of an admin are called delegated permissions in [Azure Portal](https://aad.portal.azure.com/).

Before you grant any permission to an app, review a list of requested permissions in the [Manage Apps](https://admin.teams.microsoft.com/policies/manage-apps) section of Teams admin center.

:::image type="content" source="media/attested-app-tac2.png" alt-text="In Teams admin center, on the dialog to grant permissions, admins can check the permissions requested by an app.":::

After admins grant the org-wide permissions to an app, they can review the Graph permissions in Azure Portal.

:::image type="content" source="media/tac-perms-in-aad-after-granting1.png" alt-text="Admins can see all the app permissions granted by users and admins in the Azure Portal." lightbox="media/tac-perms-in-aad-after-granting2.png":::
--->

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>查看应用的隐私策略和使用条款

在 Teams 管理中心内，每个应用页面都链接到应用的隐私声明和使用条款。

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="在 Teams 管理中心，管理员可以访问指向每个应用的隐私策略和使用条款的链接" lightbox="media/tac-app-tou-privacy-info2.png":::

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

- How to view the support information for an app in TAC?

- We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->

## <a name="see-also"></a>另请参阅

* [查看应用权限并授予管理员许可](app-permissions-admin-center.md)。
