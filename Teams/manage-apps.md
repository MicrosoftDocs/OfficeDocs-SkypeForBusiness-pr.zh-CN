---
title: 在管理中心内Microsoft Teams应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何在 Teams 管理中心的"管理应用"页上管理Microsoft Teams应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 96acf3151c2b805fead94979010669520b7a000f
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442288"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>在管理中心内Microsoft Teams应用

作为管理员，可以查看和管理组织Teams应用。 在管理中心的"管理Teams页面上，可以：

- [在组织级别允许或阻止应用](#allow-and-block-apps)
- [发布者阻止的应用](#apps-blocked-by-publishers)
- [将应用添加到团队](#add-an-app-to-a-team)
- [批准新的自定义应用或将其上传到组织的应用商店](#publish-a-custom-app-to-your-organizations-app-store)
- [查看应用请求的权限](#view-resource-specific-consent-permissions)
- [向应用授予许可](#grant-admin-consent-to-apps)
- [第三方应用的购买服务](#purchase-services-for-third-party-apps)
- [请参阅应用组织级状态和属性](#view-apps)
- [管理组织范围内的应用设置](#manage-org-wide-app-settings)
- [查看认证应用的安全Microsoft 365信息](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

"管理应用"页面提供所有可用应用的视图，为你提供确定在整个组织中允许或阻止哪些应用时需要的信息。 然后，可以使用 [应用权限策略](teams-app-permission-policies.md)、 [应用设置](teams-app-setup-policies.md)策略、自定义应用策略 [和](teams-custom-app-policies-and-settings.md) 设置为组织中特定用户配置应用体验。

在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。 必须是全局管理员或Teams管理员才能访问页面。

!["托管应用"页的屏幕截图。](media/manage-apps.png)

> [!NOTE]
> "管理应用"页在 Microsoft 365 政府社区云 High (GCCH) 或国防部 (DoD) 部署中Teams。

## <a name="view-apps"></a>查看应用

你可以查看每个应用，包括有关每个应用的以下信息。

![应用的应用详细信息页的屏幕截图。](media/app-detail-page.jpg)

- **名称**：应用名称。 选择应用名称以转到应用详细信息页以查看有关该应用的详细信息。 这包括应用的说明，无论是允许还是阻止应用、版本、隐私策略、使用条款、适用于应用的类别、认证状态、支持的功能和应用 ID。
- **认证**：如果应用已通过认证，你将看到 **Microsoft 365认证Publisher****认证**。 选择链接以查看应用的认证详细信息。 如果看到 `--`，则我们没有应用的认证信息。 若要详细了解应用中的认证Teams，请阅读Microsoft 365[认证计划](/microsoft-365-app-certification/overview)。
- **Publisher**：发布者的名称。
- **发布状态**：自定义应用的发布状态。
- **状态**：组织级别的应用状态，可以是下列其中一项：
  - **允许**：该应用可供你组织的所有用户使用。
  - **已** 阻止：应用被阻止，并且对组织的任何用户不可用。
  - **发布者阻止**：应用被发布者阻止，默认情况下对最终用户隐藏。 使用发布者的指导设置应用后，可以允许或阻止该应用，使其可供最终用户使用。
  - **阻止组织范围**：应用在组织范围内的应用设置中受阻。
      必须知道，此列表示以前位于" **组织** 范围的设置"窗格的应用的允许和阻止状态。 现在，您可以在"管理应用"页面上的组织范围内查看、阻止和 **允许应用** 。
- **许可证**：指示应用是否提供软件即服务 (SaaS) 订阅进行购买。 此列仅适用于第三方应用。 每个第三方应用将具有以下值之一：
  - **购买**：该应用提供 SaaS 订阅，可供购买。  
  - **已** 购买：该应用提供 SaaS 订阅，并且你已购买其许可证。
  - **- -**：应用未提供 SaaS 订阅。
- **自定义应用**：应用是否是自定义应用。
- **权限**：指示在应用程序中注册的第三方或自定义Azure Active Directory (Azure AD) 是否具有需要许可的权限。 会看到以下值之一：
  - **查看详细信息**：应用具有需要许可才能访问数据的权限。
  - **- -**：应用没有需要许可的权限。
- **类别**：适用于应用的类别。
- **版本**：应用版本。
- **管理员可以在会议中安装**：指示管理员是否可以在团队会议中安装应用。 [了解更多信息](teams-app-setup-policies.md#install-apps)

若要在表中查看信息，请选择右上角的"编辑列"，向表中添加或删除列。

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>将自定义应用发布到组织的应用商店

使用"管理应用"页发布专为组织构建的应用。 发布自定义应用后，该应用可供组织应用商店中的用户使用。 有两种方法将自定义应用发布到组织的应用商店。 你使用的方式取决于你获取应用的方式。

- [批准自定义应用](#approve-a-custom-app)：如果开发人员使用应用提交 API 将应用直接提交到"管理应用"Teams使用此方法。 然后，你可以直接从应用 (查看) 或拒绝应用。
- [Upload应用包](#upload-an-app-package)：如果开发人员以其他格式将应用包发送给你，.zip方法。 通过上传应用包发布应用。

### <a name="approve-a-custom-app"></a>批准自定义应用

当 **开发人员使用** 应用提交 API 提交应用时，"管理应用"页面上的"待Teams小组件会通知你。 新提交的应用将列出，其发布 **状态为****"已提交**"，"**状态"为**"已 **阻止"**。 转到应用详细信息页以查看有关应用的详细信息，然后发布它，将"发布状态" **设置为** "发布 **"**。

开发人员将更新提交到自定义应用时，也会收到通知。 然后，可以在应用详细信息 (查看) 或拒绝更新。 对于更新的应用，所有应用权限策略和应用设置策略仍然强制实施。

若要了解有关详细信息，请参阅[发布通过应用提交 API Teams提交的自定义应用](submit-approve-custom-apps.md)。

### <a name="upload-an-app-package"></a>Upload应用包

开发人员使用 Teams [App Studio](/microsoftteams/platform/get-started/get-started-app-studio) 创建Teams应用包，然后以 .zip 格式发送给你。 当你拥有应用包时，你可以将其上传到组织的应用商店。

若要上传新的自定义应用，请选择 **Upload应用包**。 应用上传后不会突出显示，因此你需要在"管理应用"页面上搜索应用列表以找到它。

若要在应用上传后更新应用，请在"管理应用"页面上的应用列表中，选择应用名称，然后选择"更新 **"**。 执行此操作会替换现有应用，并且所有应用权限策略和应用设置策略仍对更新的应用强制实施。

有关详细信息，请参阅通过 [上传应用包发布自定义应用](upload-custom-apps.md)。

## <a name="allow-and-block-apps"></a>允许和阻止应用

"管理应用"页面是组织级别允许或阻止单个应用的地方。 它显示每个可用的应用及其当前的组织级应用状态。  (组织级别的阻止和允许应用已从" **组织范围** 应用设置"窗格移动到此处。) 

若要允许或阻止应用，请选择它，然后选择"允许 **"或** "阻止 **"**。 当你阻止应用时，将禁用与该应用的所有交互，并且该应用不会Teams用户显示在应用中。

在"管理应用"页面上阻止或允许应用时，将阻止或允许组织中所有用户使用该应用。  当你在应用权限策略中阻止或Teams应用时，会阻止或允许分配有该策略的用户使用。 若要使用户能够安装任何应用并与之交互，必须在"管理应用"页面和分配给用户的应用权限策略中允许组织级别的应用。

 > [!NOTE]
 > 若要卸载应用，请右键单击该应用，然后单击左侧的"卸载或使用更多应用"菜单。

## <a name="apps-blocked-by-publishers"></a>发布者阻止的应用

当 ISV 将应用发布到全局应用商店时，可能需要管理员来配置或自定义应用体验。 完全设置应用后，管理员可以使其可供最终用户使用。

例如，Contoso Electronics 是一个 ISV，它构建了适用于 Microsoft Teams 的帮助Microsoft Teams。 Contoso Electronics 希望其客户设置应用的某些属性，以便当用户与应用交互时，它可以如期运行。 在管理员允许或阻止应用程序之前，该应用程序在 Teams 管理中心中将显示为"被发布者阻止"，并且默认情况下会向最终用户隐藏。 按照发布者的指导设置应用后，可以通过将状态更改为"允许"来使其可供用户使用，或者通过将状态更改为"已阻止"来阻止 **用户使用该应用**。

![Teams 管理中心中按发布者状态阻止的屏幕截图。](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>向团队添加应用

使用" **添加到团队"** 按钮将应用安装到团队。 请记住，这仅适用于可在团队范围内安装的应用。 " **添加到团队** "按钮不适用于只能在个人范围内安装的应用。

!["添加到团队"按钮的屏幕截图。](media/manage-apps-add-app-team.png)

1. 搜索你需要的应用，然后单击应用名称左侧选择该应用。
2. 选择 **"添加到团队"**。
3. 在 **"添加到团队"** 窗格中，搜索要添加应用的团队，选择团队，然后选择"应用 **"**。

## <a name="customize-an-app"></a>自定义应用

现在，你可以自定义应用以根据组织需求包含特定的外观。 请参阅[自定义应用中Teams](customize-apps.md)。

## <a name="purchase-services-for-third-party-apps"></a>购买第三方应用的服务

可以直接从"管理应用"页面搜索并购买第三方应用为组织用户提供的服务的许可证。 表中的 **"** 许可证"列指示应用是否提供付费 SaaS 订阅。 选择 **"立即** 购买"，查看计划和定价信息，并购买用户的许可证。 有关详细信息，请参阅在 Teams 管理中心购买第三方[Microsoft Teams服务](purchase-third-party-apps.md)。

## <a name="grant-admin-consent-to-apps"></a>向应用授予管理员许可

可以代表组织中所有用户查看并授予对请求权限的应用的许可。 你这样做，以便用户不必在启动应用时查看并接受应用请求的权限。 " **权限"** 列指示应用是否具有需要许可的权限。 你将看到 **在具有需要** 许可的权限的 Azure AD中注册的每个应用的"查看详细信息"链接。 有关详细信息，请参阅在管理[中心内查看](app-permissions-admin-center.md)应用权限Microsoft Teams管理员许可。

## <a name="view-resource-specific-consent-permissions"></a>查看特定于资源的许可权限

RSC (资源) 权限允许团队所有者授予应用访问和修改团队数据的许可。 RSC 权限是Teams特定权限，用于定义应用可在特定团队中执行哪些操作。 可以在应用详细信息页面的"权限"选项卡上查看 RSC 权限。 有关详细信息，请参阅在管理[中心内查看](app-permissions-admin-center.md)应用权限Microsoft Teams管理员许可。

## <a name="manage-org-wide-app-settings"></a>管理组织范围内的应用设置

使用组织范围的应用设置，根据) 即将推出许可证 (、用户是否可以安装第三方应用，以及用户是否可以上载或与组织中的自定义应用进行交互，来控制用户是否获得定制的应用体验。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 你可以使用它们控制恶意应用或有问题的应用。

> [!NOTE]
> 若要了解如何使用 Microsoft 365 政府 - 政府社区云 高 GCCH 和国防部 (DoD) Teams 部署中的组织范围应用设置，请参阅在 [Teams 中管理应用权限策略](teams-app-permission-policies.md)。

1. 在"管理应用"页上，选择 **"组织范围的应用设置"**。 然后，你可以在面板中配置所需的设置。

1.  (即将推出) "自定义 **应用**"下，关闭或打开"显示基于许可证 **的定制应用"**。 启用此设置后，用户获得基于其许可证固定应用的体验。 有关详细信息，请参阅[根据许可证Teams自定义应用](pin-teams-apps-based-on-license.md)。

    此功能适用于 F 许可证。 将来将支持其他许可证类型。
1. 在“**第三方应用**”下，关闭或打开这些设置以控制对第三方应用的访问权限：

    - **允许第三方应用**：控制用户是否可以使用第三方应用。 如果关闭此设置，用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为"阻止组织范围"。

        > [!NOTE]
        > 当 **"** 允许第三方应用"关闭时，仍为所有用户启用传出 [Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，但可以通过应用权限策略允许或阻止传出 Webhook 应用，在用户级别控制 [它们](teams-app-permission-policies.md)。 请注意，如果 Microsoft 应用的现有应用权限策略使用"允许特定应用并阻止所有其他应用"设置，并且希望为用户启用传出 Webhook，则向列表添加传出 Webhook 应用。[](teams-app-permission-policies.md)

        > [!NOTE]
        > 主持会议或与来自其他组织的人员聊天时，Teams 用户可以添加应用。 当他们加入由其他组织主持的会议或聊天时，也可以使用由这些组织的人共享的应用。 将应用主持用户组织的数据策略，以及该用户组织共享的任何第三方应用的数据共享实践。

    - **默认情况下，允许发布到应用商店的所有新的第三方应用**：控制发布到 Teams 应用商店的新第三方应用是否在 Teams 中自动可用。 仅在允许第三方应用时才能设置此选项。

1. 在 **"自定义应用**"下，关闭或打开" **允许与自定义应用交互"**。 此设置控制用户是否可以与自定义应用交互。 要了解详细信息，请参阅[在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。
1. 选择 **"保存** "，使组织范围内的应用设置生效。

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>查看认证应用的安全Microsoft 365信息

为组织评估应用时，管理员可以使用独立的云访问安全代理 (CASB) （例如 Microsoft Cloud App Security (MCAS) ）来查找有关应用安全性和行为的信息。 Teams管理中心包含来自 MCAS 的安全和合规性信息Microsoft 365认证应用，以便你了解有关应用是否满足你需求的信息。

> [!NOTE]
> 此功能可供所有管理员使用，无论你的组织是否具有支持 MCAS 的许可证。

若要访问 MCAS 信息，请执行以下步骤：

1. 在 Teams 管理中心，选择 **"管理应用"下的**"**Teams应用"**。
1. 选择 **"** 认证"以对应用进行排序，Microsoft 365认证应用推送到表格顶部。
1. 选择一Microsoft 365认证应用。
1. 选择" **安全性和符合性"** 选项卡。

!["管理Teams"选项卡的屏幕截图。](media/mcas.png)

在此选项卡上，可找到有关安全性、符合性和数据保护的信息。 还可以展开每个下拉列表，获取有关所选应用程序支持哪些功能的更多详细信息。

## <a name="related-topics"></a>相关主题

- [Teams 中应用的管理设置](admin-settings.md)
