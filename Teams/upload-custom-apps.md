---
title: 在Microsoft Teams管理中心Upload自定义应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke, vaibhava
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在Microsoft Teams管理中心将自定义应用上传到组织的应用商店。
ms.openlocfilehash: 33f2a1234c041029b44f63f42f224784cc487fdc
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124347"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>通过上传应用包发布自定义应用

> [!NOTE]
> 发布自定义Teams应用时，组织应用商店中的用户可以使用它。 发布自定义应用有两种方法，使用方式取决于获取应用的方式。 **本文重点介绍如何通过上传应用包 (来发布自定义应用，.zip格式) 开发人员发送给你**。 当开发人员通过Teams应用提交 API 将应用直接提交到[“管理应用](manage-apps.md)”页面时，将使用另一种方法（批准自定义应用）。 若要了解有关该方法的详细信息，请参阅[发布通过Teams应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。

本文提供从开发到部署到发现Teams应用的端到端指南。 本指南重点介绍应用的Teams方面，适用于管理员和 IT 专业人员。 有关开发Teams应用的详细信息，请参阅[Teams开发人员文档](/microsoftteams/platform/)。

![从开发到部署的应用概述。](media/upload-custom-apps.png)

## <a name="create-your-app"></a>创建应用

Microsoft Teams开发人员平台使开发人员能够轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，并围绕现有内容和工作流创建协作。 基于Teams平台构建的应用是Teams客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。 有关详细信息，请转到[Teams开发人员文档](/microsoftteams/platform/)。

## <a name="validate"></a>验证

### <a name="get-the-app-package"></a>获取应用包

当应用准备好在生产环境中使用时，开发人员将生成一个应用包。 他们可以为此使用 [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) 。 他们将以.zip格式向你发送文件。

Teams应用商店中的所有应用都通过强制[应用验证](overview-of-app-validation.md)，以符合全球Teams应用商店的质量和安全标准。 此外，Microsoft 强烈鼓励应用开发人员参与可选 [应用符合性计划，该计划](overview-of-app-certification.md) 指示增强的合规性、安全和隐私控制。 有关详细信息，请参阅[Teams应用验证指南](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允许受信任的用户上传自定义应用

若要验证应用是否在生产租户中正常工作，需要允许自己和/或受信任的用户在生产租户中上传自定义应用。 可以使用 [应用设置策略](teams-app-setup-policies.md) 来执行此操作。

> [!NOTE]
> 如果你对将应用上传到生产租户进行验证感到不自在，即使是你自己或受信任的用户，也可以跳过此步骤，按照[Upload](#upload)中的步骤操作，[并设置和管理](#set-up-and-manage)部分，将未验证的应用发布到组织的应用商店。 然后，将该应用的访问权限限制为仅限你自己和你信任的用户。 然后，这些用户可以从组织的应用商店获取应用以执行验证。 验证应用后，使用相同的权限策略打开访问权限，并推出应用以供生产使用。

若要允许受信任的用户上传自定义应用，请执行以下步骤：

1. 启用 **允许与自定义应用** 组织范围应用设置的交互。 要执行此操作：

    1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **管理应用**，然后单击 **组织范围的应用设置**。
    
    2. 在 **“自定义应用**”下，打开 **“允许与自定义应用交互**”，然后单击“ **保存**”。
    
1. 在全局应用设置策略中关闭 **Upload自定义应用** 设置。 要执行此操作：

    1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **设置策略**，然后单击 **全局 (组织范围的默认)** 策略。
    
    2. 关闭 **Upload自定义应用**，然后单击 **“保存**”。
    
1. 创建允许上传自定义应用并将其分配给受信任用户集的新应用设置策略。 要执行此操作：

    1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **设置策略**，然后单击 **“添加**”。 为新策略提供名称和说明，打开 **Upload自定义应用**，然后单击 **“保存**”。
    
    2. 选择创建的新策略，然后单击 **“管理用户**”。 搜索用户，单击 **“添加**”，然后单击“ **应用**”。 重复此步骤，将策略分配给所有受信任的用户。

       ![“添加应用设置策略”页的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

这些用户现在可以上传应用清单，以验证应用是否在生产租户中正常工作。

## <a name="upload"></a>Upload

若要使应用可供组织应用商店中的用户使用，请上传该应用。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 选择 **Upload**，单击 **Upload**，选择从开发人员处收到的应用包，然后选择 **“打开**”。

   ![在管理中心上传应用的屏幕截图。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。 若要限制和控制谁有权使用应用，可以创建和分配应用权限策略。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用供用户发现

默认情况下，用户若要查找应用，他们必须转到组织的应用商店并浏览或搜索它。 为了方便用户访问应用，可以将应用固定到Teams中的应用栏。 为此，请创建应用设置策略并将其分配给用户。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

### <a name="search-the-audit-log-for-teams-app-events"></a>在审核日志中搜索Teams应用事件

可以搜索审核日志以查看组织中的Teams应用活动。 若要详细了解如何搜索审核日志，以及查看在审核日志中记录的Teams活动的列表，请[参阅“在审核日志中搜索Teams中的事件](audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://sip.protection.office.com/homepage)中用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="discover-and-adopt"></a>发现和采用

拥有应用权限的最终用户可以在组织的应用商店中找到它。 转到“应用”页上的“**为 *组织名称* 生成**”，查找组织的自定义应用。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Teams应用商店的屏幕截图，其中显示了为组织发布的自定义应用" lightbox="media/custom-app-lifecycle-discovery.png":::

如果创建并分配了应用设置策略，则应用将固定到Teams中的应用栏，以便为分配策略的用户轻松访问。

## <a name="update"></a>更新

若要更新应用，开发人员将按照 [“创建应用](#create-your-app) ”和 [“验证”](#validate) 部分中的步骤操作。

可以在Microsoft Teams管理中心的“管理应用”页上更新应用。 为此，请在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **管理应用**。 单击应用名称，然后单击 **“更新**”。 执行此操作将替换现有应用，并且所有应用权限策略和应用设置策略仍会针对更新后的应用强制执行。

### <a name="end-user-update-experience"></a>最终用户更新体验

在大多数情况下，完成应用更新后，会自动为最终用户显示新版本。 有关详细信息，请参阅 [最终用户更新体验](apps-update-experience.md)。

## <a name="related-topics"></a>相关主题

* [发布通过Teams应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)
* [在Microsoft Teams管理中心管理应用](manage-apps.md)
* [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
* [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
* [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
