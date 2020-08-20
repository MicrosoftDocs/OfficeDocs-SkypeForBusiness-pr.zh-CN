---
title: 在 Microsoft Teams 管理中心中管理应用
author: LanaChin
ms.author: v-lanac
manager: serdars
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
description: 了解如何在 Microsoft Teams 管理中心的"管理应用"页面上管理 Teams 应用
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 23ff7cc90d30dc931b0677ce5ec5aa8db98981fb
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818181"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心中管理应用
======================================================

作为管理员，你可以在 Microsoft Teams 管理中心查看和管理组织的所有 Teams 应用的位置。 此处，你可以看到应用的组织级别状态和属性、批准或上传新自定义应用、在组织级别批准或允许应用、购买第三方应用的服务以及管理组织范围内的应用设置。

"管理应用程序"页面向你提供所有可用应用，提供了用于决定在组织中允许或阻止哪些应用的相关信息。 然后，你可以[使用应用权限策略、应用](teams-app-permission-policies.md)[设置策略](teams-app-setup-policies.md)以及自定义[应用策略与设置](teams-custom-app-policies-and-settings.md)来为你组织中的特定用户配置应用体验。

在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。 只有全局管理员或 Teams 服务管理员才能访问该页面。

> [!NOTE]
> Microsoft 365 政政版社区云中尚不提供 Teams (GCC) 应用。

## <a name="view-apps"></a>查看应用

可以查看每个应用，包括有关每个应用的以下信息。

!["托管的应用"页面的屏幕截图](media/manage-apps.png)

- **名称**：应用名称。 单击应用名称可以查看有关该应用程序的详细信息。 这包括应用的描述，无论是否允许或阻止、版本、适用于应用的类别、认证状态、支持的功能和应用 ID。 下面是一个示例：

  ![应用的应用详细信息页面的屏幕截图](media/manage-apps-app-details.png)
  
- **认证：** 如果应用已通过认证，你将看到 **Microsoft 365 认** 证或 **发布者认证**。 单击该链接，查看应用的认证详细信息。 如果看 **--** 见"，我们没有应用的认证信息。 若要深入了解 Teams 中认证的应用，请 [阅读 Microsoft 365 应用认证计划](https://docs.microsoft.com/teams-app-certification/all-apps)。  
- **发布者**：发布者的名称。
- **发布状态**：发布自定义应用的状态。
- **状态**：位于组织级别的应用的状态，可能是以下方法之一：

    - **已允**许： 该应用面向您组织中的所有用户提供。
    
    - **已阻止**：应用被阻止，并且不可供你组织中的任何用户使用。
    
    - **阻止组织范围：应用**已在组织范围的应用设置中被阻止。
    
      请务必了解的是此列表示以前位于"组织范围设置"窗格上的应用的 **允许和阻止** 状态。 现在，你可以在"管理应用"页面上查看、阻止应用以及 **允许应用** 。 
- **许可证**：指示应用是否以服务形式作为服务 (购买) 提供软件。 此列仅适用于第三方应用。 每个第三方应用都将具有以下值之一：
    - **立即购买**：应用提供 SaaS 订阅，可供购买。  
    - **已购买**：应用提供 SaaS 订阅，你已为其购买了许可证。
    - **-**： 应用未提供 SaaS 订阅。
- **自定义应用**：应用是否是自定义应用。
- **类别：** 适用于应用的类别。
- **版本**：应用版本。

要在表格中查看所需的信息，请单击 **右** 上角的"编辑列"，在表格中添加或删除列。

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>将自定义应用发布到组织的应用商店

使用"管理应用"页面发布专为你的组织构建的应用。 在发布自定义应用后，它可供组织的应用商店中的用户使用。 有两种方法可以将自定义应用发布到组织的应用商店。 使用方式取决于获取应用的方式。

- [批准自定义应用](#approve-a-custom-app)：如果开发人员使用 Teams 应用提交 API 直接向"管理应用"页面提交应用，请使用此方法。 然后，你可以直接从 (详细信息页面查看并发布) 编辑或拒绝应用。
- [上载应用包](#upload-an-app-package)：如果开发人员以 .zip 格式向你发送应用包，请使用此方法。 通过上载应用包发布应用。

###  <a name="approve-a-custom-app"></a>审批自定义应用

" **管理应用"页面上的** 待定审批小组件会在开发人员使用 Teams 应用提交 API 提交应用时通知你。 会列出新提交的应用，其中**包含**已提交的发布状态和 **"被****Submitted****阻止状态**"。 转到应用详细信息页面以查看有关应用的详细信息，然后发布该应用，将 **"发布状态"设置为****"发布**"。

开发人员向自定义应用提交更新时，你也会收到通知。 然后，你可以在应用详细信息页面上 (查并发布或) 名称。 已对更新的应用执行所有应用权限策略和应用设置策略。

若要了解详细信息 [，请参阅发布通过 Teams 应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。

### <a name="upload-an-app-package"></a>上载应用包

开发人员使用 Teams 应用 Studio 创建 [Teams 应用包](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)，然后将其通过 .zip 格式发送给你。 如果你有应用包，可以将其上载到组织的应用商店。

要上载新的自定义应用，请选择" **上传** "以上载应用包。 应用在上载之后不突出显示，因此你将需要在"管理应用"页面上搜索应用列表，才能找到它。

若要在上载应用后进行更新，请在"管理应用"页面上的应用列表中单击应用名称，然后单击" **更新**"。 这样做将替换为已更新的应用，因此仍将实时使用现有的应用以及所有应用权限策略和应用设置策略。

若要了解详细信息，请参阅 [通过上载应用包发布自定义应用](upload-custom-apps.md)。

## <a name="allow-and-block-apps"></a>允许和阻止应用

在"管理应用"页中，你可以选择或阻止处于组织级别的单个应用。 它显示每个可用的应用及其当前的组织级应用状态。  ("阻止"并允许该组织级别的应用从 **组织范围内应用设置** 窗格移动到此处。) 

若要允许或阻止应用，请选择它，然后单击"允**许"或"阻止****"。** 当你阻止应用时，系统将禁用与该应用的所有交互，并且对于组织中的任何用户，该应用不会显示在 Teams 中。

当在"管理应用"页面上阻止或允许使用某个应用时，组织中的所有用户都会阻止或允许该应用。  在 Teams 应用权限策略中阻止或允许使用某个应用时，向分配该策略的用户阻止或允许该应用。 为了用户能够安装任意应用并与其进行交互，你必须允许该应用在"管理应用"页面上的"管理应用"页面和分配给用户的应用权限策略中。

 > [!NOTE]
 > 若要卸载应用，请右键单击应用，然后单击"卸载 **"或** 使用 **左侧的"更多** 应用程序"菜单。

## <a name="purchase-services-for-third-party-apps"></a>购买第三方应用的服务

可以直接从"管理应用"页面搜索和购买由第三方应用中用户提供的服务的许可证。 下 **表** 中的"许可证"列指示应用是否提供了付费的 SaaS 订阅。 单击 **"立即** 购买"即可查看用户的计划和定价信息和购买许可证。 若要了解详细信息， [请在 Microsoft Teams 管理中心中查看 Teams 第三方应用的购买服务](purchase-third-party-apps.md)。

## <a name="manage-org-wide-app-settings"></a>管理组织范围内的应用设置

使用组织范围的应用设置来控制用户是否可以安装第三方应用，以及用户是否可以在你的组织中上载自定义应用或与其进行交互。 组织范围的应用设置管理所有用户的行为，并覆盖分配给用户的任何其他应用权限策略。 你可以使用它们来控制存在音性或有问题的应用。

> [!NOTE]
> 若要了解如何在 Microsoft 365 政政版中使用组织范围的应用设置 - Teams 的 GCC 部署，请参阅 Teams 中的 ["管理应用权限策略](teams-app-permission-policies.md)"。

1. 在"管理应用"页面上， **选择组织范围内的应用设置**。 然后，您可以配置面板中所需的设置。

    ![组织范围的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. 在 **第三方应用下，关闭**或打开这些设置以控制对第三方应用的访问：

    - **允许第三方应用：** 此控制用户是否可以使用第三方应用。 如果关闭此设置，你的用户将不能安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为 **"** 受阻止"组织范围。

        > [!NOTE]
        > 关闭 **"允许的第三方应用"** 时，将禁用传出的 [Webhooks，](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 这意味着用户无法创建它们。 在此设置处于打开状态时，将为所有用户启用传出的 Webhookie，你可通过允许或阻止传出 Webhook 应用的应用权限策略来在用户 [级别控制它们](teams-app-permission-policies.md)。 <br><br>请注意，如果你拥有使用特定[app permission policies](teams-app-permission-policies.md)应用的 Microsoft 应用**的现有应用**权限策略 **，并阻止**其他所有设置，并且要为用户启用传出的 Webhookie，请将传出 Webhook 应用添加到列表中。
    - **允许默认发布到应用商店中的任何新**第三方应用：此控制发布到 Teams 应用商店的新第三方应用是否可在 Teams 中自动提供。 仅当允许第三方应用时，你仅可设置此选项。

3. 在 **"自定义应用**"下，关闭或打开" **允许与自定义应用进行交互**"。 此设置可控制用户是否可以与自定义应用交互。 若要了解详细信息，请参阅 ["管理自定义应用策略和 Teams 中的设置](teams-custom-app-policies-and-settings.md)"。
4. 单击 **"** 为组织范围的应用设置保存"以使生效。

## <a name="related-topics"></a>相关主题

- [Teams 中适用于应用的管理设置](admin-settings.md)