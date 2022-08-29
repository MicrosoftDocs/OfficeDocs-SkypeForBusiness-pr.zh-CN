---
title: 在 Microsoft Teams 管理中心上传自定义应用
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心将自定义应用上传到组织的应用商店。
ms.openlocfilehash: d95635546da7337c9c18ee0fddf7b40a5bf061c3
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397113"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>通过上载应用包来发布自定义应用

> [!NOTE]
> 发布自定义 Teams 应用时，组织应用商店中的用户可以使用它。 发布自定义应用有两种方法，使用的方式取决于获取应用的方式。 **本文重点介绍如何通过上传开发人员发送给你的应用包（采用.zip格式）来发布自定义应用**。 当开发人员通过 Teams 应用提交 API 将应用直接提交到 [“管理应用](manage-apps.md) ”页面时，将使用另一种方法批准自定义应用。 若要了解有关该方法的详细信息，请参阅 [发布通过 Teams 应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。

本文提供有关如何将 Teams 应用从开发到部署到发现的过程的端到端指导。 本指南重点介绍应用的 Teams 方面，适用于管理员和 IT 专业人员。 有关开发 Teams 应用的详细信息，请参阅 [Teams 开发人员文档](/microsoftteams/platform/)。

![从开发到部署的应用概述。](media/upload-custom-apps.png)

## <a name="create-your-app"></a>创建应用

借助 Microsoft Teams 开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，并围绕现有内容和工作流创建协作。 基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。 有关详细信息，请转到 [Teams 开发人员文档](/microsoftteams/platform/)。

## <a name="validate"></a>验证

### <a name="get-the-app-package"></a>获取应用包

当应用准备好在生产环境中使用时，开发人员应生成应用包。 他们可以使用 [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview)。 他们将以.zip格式向你发送文件。

Teams 应用商店中的所有应用都通过强制 [应用验证](overview-of-app-validation.md) ，以符合全球 Teams 应用商店的质量和安全标准。 此外，Microsoft 强烈鼓励应用开发人员参与可选 [的应用合规性计划，该计划](overview-of-app-certification.md) 指示增强的合规性、安全和隐私控制。 有关详细信息，请参阅 [Teams 应用验证指南](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允许受信任的用户上传自定义应用

若要验证应用是否在生产租户中正常工作，需要允许自己和/或受信任的用户在生产租户中上传自定义应用。 可以使用 [应用设置策略](teams-app-setup-policies.md) 来执行此操作。

> [!NOTE]
> 如果你对将应用上传到生产租户进行验证（即使是你自己或受信任的用户）感到不快，则可以跳过此步骤，按照 [“上传](#upload) ”和 [“设置和管理](#set-up-and-manage) ”部分中的步骤将未验证的应用发布到组织的应用商店。 然后，将该应用的访问权限限制为仅限你自己和你信任的用户。 然后，这些用户可以从组织的应用商店获取应用以执行验证。 验证应用后，使用相同的权限策略打开访问权限并推出应用以供生产使用。

若要允许受信任的用户上传自定义应用，请执行以下步骤：

1. 打开 **“允许与自定义应用** 组织范围的应用交互”设置。 要执行此操作：

    1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **Teams 应用** > **管理应用**，然后选择 **组织范围的应用设置**。

    1. 在 **“自定义应用**”下，打开 **“允许与自定义应用交互**”，然后选择 **“保存**”。

1. 关闭全局应用设置策略中的 **“上传自定义应用** ”设置。 要执行此操作：

    1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **Teams 应用** > **设置策略**，然后选择 **全局 (组织范围的默认)** 策略。

    1. 关闭 **“上传自定义应用**”，然后选择 **“保存**”。

1. 创建允许上传自定义应用并将其分配给受信任用户集的新应用设置策略。 要执行此操作：

    1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **Teams 应用** > **设置策略**，然后选择 **“添加**”。 为新策略提供名称和说明，打开 **“上传自定义应用**”，然后选择 **“保存**”。

    1. 选择创建的新策略，然后选择 **“管理用户**”。 搜索用户，选择 **“添加**”，然后选择 **“应用**”。 重复此步骤，将策略分配给所有受信任的用户。

       :::image type="content" source="media/manage-your-lob-apps-new-app-setup-policy.png" alt-text="“添加应用设置策略”页的屏幕截图。":::

这些用户现在可以上传应用清单，以验证应用是否在生产租户中正常工作。

## <a name="upload"></a>上传

若要使应用可供组织应用商店中的用户使用，请上传该应用。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“管理** 应用” > Teams **[应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 选择 **“上传**”，选择 **“上传**”，选择从开发人员处收到的应用包，然后选择 **“打开**”。

   ![管理中心内自定义应用上传的屏幕截图。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。 若要限制和控制谁有权使用应用，可以创建和分配应用权限策略。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用供用户发现

默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索它。 为了方便用户访问应用，可以将应用固定到 Teams 中的应用栏。 若要固定应用，请创建应用设置策略并将其分配给用户。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜索 Teams 应用事件的审核日志

可以搜索审核日志以查看组织中的 Teams 应用活动。 若要了解有关审核 Teams 活动的详细信息，请参阅 [在审核日志中搜索 Teams 中的事件](audit-app-management-activities.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://sip.protection.office.com/homepage)中用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="discover-and-adopt"></a>发现和采用

拥有应用权限的最终用户可以在组织的应用商店中找到它。 转到“应用”页面上的“ **为 *组织名称* 生成** ”，查找组织的自定义应用。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="显示为组织发布的自定义应用的 Teams 应用商店的屏幕截图" lightbox="media/custom-app-lifecycle-discovery.png":::

如果创建并分配了应用设置策略，应用将固定到 Teams 中的应用栏，以便为分配了策略的用户轻松访问。

## <a name="update-a-custom-app"></a>更新自定义应用

若要更新应用，开发人员请按照“ [创建应用](#create-your-app) ”和 [“验证”](#validate) 部分中的步骤操作。

你可以在 Microsoft Teams 管理中心的“管理应用”页上更新应用。 若要更新应用，请在 Microsoft Teams 管理中心的左侧导航中转到 **Teams 应用** > **管理应用**。 选择应用名称，然后选择 **“更新**”。 更新应用将替换现有应用，并且所有应用权限策略和应用设置策略仍会针对更新后的应用强制实施。

### <a name="end-user-update-experience"></a>最终用户更新体验

在大多数情况下，完成应用更新后，会自动为最终用户显示新版本。 有关详细信息，请参阅 [最终用户更新体验](apps-update-experience.md)。

## <a name="remove-a-custom-app-from-your-organizations-store"></a>从组织的存储中删除自定义应用

若要删除应用，请执行以下步骤：

1. 登录到 Teams 管理中心。
1. “访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)** ”页面。
1. 单击应用的名称以打开应用详细信息页。
1. 在应用横幅旁边，选择“**删除****操作** > ”。
1. 在对话框中，选择 **“删除**”。

## <a name="related-articles"></a>相关文章

* [发布通过 Teams 应用提交 API 所提交的自定义应用](submit-approve-custom-apps.md)
* [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
* [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
* [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
* [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
