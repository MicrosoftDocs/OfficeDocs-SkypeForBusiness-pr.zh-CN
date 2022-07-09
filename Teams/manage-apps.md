---
title: 在 Microsoft Teams 管理中心管理应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何管理 Teams 应用。 了解如何允许或阻止应用、检查组织级别状态和应用属性、上传自定义应用和管理应用设置。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: f9bf05364ae990930da89a64643fa86b2b0467c4
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695065"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理 Teams 应用

在 Teams 管理中心门户的 **Teams 应用** 页中管理组织的应用。 使用“管理应用”页面查看和管理组织应用目录中的所有 Teams 应用。

:::image type="content" source="media/manage-apps.png" alt-text="“管理应用”页的屏幕截图。" lightbox="media/manage-apps.png":::

若要使用 Teams 管理中心，必须具有全局管理员或 Teams 管理员角色。 有关详细信息，请参阅以下帮助文章：

* [Teams 管理员角色](./using-admin-roles.md)。
* [Microsoft 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)

若要管理应用，请使用策略来控制用户的权限、应用安装以及在组织中创建的自定义应用的上传。 若要了解策略，请参阅 [应用策略概述](app-policies.md)。

> [!NOTE]
> Microsoft 365 政府社区云高 (GCCH) 或国防部 (DoD) Teams 部署中不提供“管理应用”页面。

在创建应用期间，开发人员会创建应用 ID 并将其添加到清单文件。 启用列设置中的列 `External app ID` 后，可以在“管理应用”页上查看此外部应用 ID。 还可以在自定义应用的应用详细信息页上查看它。 该 ID 仅适用于自定义应用。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>应用管理用例和可用接口

Teams 管理中心提供了用于完成大多数应用管理用例的选项。 此外，其他门户中还提供了一些选项。

| 应用管理用例 | 指向接口的链接 | 文档 |
|:----|:----|:----|
| **在 Teams 管理中心** | | |
| 通过允许和阻止应用来控制组织中用户可用的应用。 还可以上传和批准自定义应用。 在此页面上管理应用后，可以使用应用权限和应用设置策略来配置组织应用商店中特定用户可用的应用。 | [在 Teams 管理中心管理应用](https://admin.teams.microsoft.com/policies/manage-apps) | 当前文章 |
| 应用权限策略控制要向组织中的 Teams 用户提供哪些应用。 可以使用全局 (组织范围的) 默认策略并对其进行自定义，也可以创建一个或多个策略来满足组织的需求。 | [权限策略](https://admin.teams.microsoft.com/policies/app-permission) | [管理应用权限策略](teams-app-permission-policies.md) |
| 应用设置策略控制如何使用 Teams 应用向用户提供应用。 使用全局 (组织范围的默认) 策略并对其进行自定义或创建自定义策略，并将其分配给一组用户。 | [设置策略](https://admin.teams.microsoft.com/policies/app-setup) | [管理应用设置策略](teams-app-setup-policies.md) |
| 可以开发和上传自定义应用作为应用包，并使其在组织的应用存储中可用。 | [管理](https://admin.teams.microsoft.com/policies/manage-apps)应用中的组织范围应用设置 | [管理自定义应用策略](teams-custom-app-policies-and-settings.md) |
| 可以使用组织的徽标、自定义背景或颜色自定义 Teams 应用商店。 | [自定义存储区](https://admin.teams.microsoft.com/policies/customize-appstore) | [自定义组织的应用商店](customize-your-app-store.md) |
| Teams 应用使用情况报告提供有关正在使用的应用、活动用户和其他应用使用情况信息的信息。 | [使用情况报告](https://admin.teams.microsoft.com/analytics/reports) | [Teams 应用使用情况报告](teams-analytics-and-reports/app-usage-report.md) |
| 用户在主持会议或与来宾聊天时可以添加应用。 他们还可以使用来宾在加入外部托管的会议或聊天时共享的应用。 将应用托管用户组织的数据策略以及该用户组织共享的任何第三方应用的数据共享做法。 | [外部访问](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [应用行为取决于用户类型](non-standard-users.md) |
| 通过来宾访问，可以向组织外部的人员提供对应用程序和其他 Teams 功能的访问权限，同时保持对公司数据的控制。 | [来宾访问](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams 中的来宾访问](guest-access.md) |
| 更新策略用于管理 Teams 和 Office 预览版用户，这些用户将在 Teams 应用中看到预发布或预览功能。  | [Teams 更新策略](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams 公共预览版](public-preview-doc-updates.md) |
| **Teams 管理中心外部** | | |
| 在Microsoft 365 管理中心中管理第三方应用的许可证和订阅 | [Microsoft 365 管理中心](https://admin.microsoft.com/#/licenses) | [管理第三方应用订阅](/microsoft-365/commerce/manage-saas-apps) |
| 审核 Microsoft Purview 合规门户 上的 Teams 应用事件。 | [审计](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams 活动](audit-app-management-activities.md) |
| 可以通过三种方法向应用程序授予对组织及其数据的权限：管理员同意所有用户的应用程序、用户向应用程序授予许可，或管理员集成应用程序并启用自助服务访问或将用户直接分配给应用程序。 验证应用的 Graph 权限。 验证用户提供的权限或管理员委托的权限。 | [Azure AD 门户](https://aad.portal.azure.com/) | [查看授予应用程序的权限](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>将自定义应用发布到组织的应用商店

使用“管理应用”页面发布专门为组织构建的应用。 发布自定义应用后，它可供组织应用商店中的用户使用。 有两种方法可以将自定义应用发布到组织的应用商店。 使用方式取决于获取应用的方式。

* [批准自定义应用](#approve-a-custom-app)：如果开发人员使用 Teams 应用提交 API 将应用直接提交到“管理应用”页面，请使用此方法。 然后，可以直接从应用详细信息页查看和发布 (或拒绝) 应用。
* [上传应用包](#upload-an-app-package)：如果开发人员以.zip格式向你发送应用包，请使用此方法。 可以通过上传应用包来发布应用。

### <a name="approve-a-custom-app"></a>批准自定义应用

“管理应用”页上的 **“挂起审批** ”小组件在开发人员使用 Teams 应用提交 API 提交应用时通知你。 新提交的应用列出了 **发布状态** 为 **“已提交**”和“**已阻止****状态**”。 转到应用详细信息页，查看有关应用的详细信息，然后将其发布，将 **发布状态** 设置为 **“发布**”。

开发人员将更新提交到自定义应用时，也会收到通知。 然后，可以在应用详细信息页上查看和发布 (或拒绝) 更新。 所有应用权限策略和应用设置策略仍会针对更新后的应用强制实施。

若要了解详细信息，请参阅 [发布通过 Teams 应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。

### <a name="upload-an-app-package"></a>上传应用包

开发人员使用 [Teams App Studio 创建 Teams 应用](/microsoftteams/platform/get-started/get-started-app-studio)包，然后以.zip格式将其发送给你。 拥有应用包后，可以将其上传到组织的应用商店。

若要上传新的自定义应用，请选择 **“上传** ”以上传应用包。 应用上传后不会突出显示，因此需要在“管理应用”页上搜索应用列表才能找到它。

若要在上传应用后更新应用，请在“管理应用”页上的应用列表中选择应用名称，然后选择 **“更新**”。 执行更新将替换现有应用，并且所有应用权限策略和应用设置策略仍会针对更新后的应用强制执行。

若要了解详细信息，请参阅 [通过上传应用包发布自定义应用](upload-custom-apps.md)。

## <a name="allow-and-block-apps"></a>允许和阻止应用

“管理应用”页是允许或阻止组织级别的单个应用的位置。 它显示每个可用的应用及其当前组织级别的应用状态。

若要允许或阻止应用，请执行以下操作：

1. 转到 Teams 管理中心> Teams 应用>管理应用。
1. 从应用列表中选择应用。
1. 选择 **“允许** ”或 **“阻止**”。

在“管理应用”页上阻止或允许应用时，会阻止或允许组织中的所有用户使用该应用。  在 Teams 应用权限策略中阻止或允许应用时，系统会阻止或允许分配该策略的用户使用该应用。 若要使用户能够安装任何应用并与之交互，必须在“管理应用”页上的组织级别以及分配给用户的应用权限策略中允许该应用。

 > [!NOTE]
 > 若要卸载应用，请右键单击应用，然后单击 **“卸载** ”或使用左侧的 **“更多应用** ”菜单。

## <a name="manage-user-requests-to-unblock-apps"></a>管理用户请求以取消阻止应用

可以查看请求以使受阻止的应用可供使用。 请求将发送给 IT 管理员，他们可以在 Teams 管理中心查看和管理用户请求。

  :::image type="content" source="media/user-request.png" alt-text="发出请求以进行阻止的应用审批":::

### <a name="view-a-request"></a>查看请求

 1. 登录 Teams 管理中心并选择 [“管理应用”](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="最终用户对被阻止应用的请求将显示在 Teams 管理中心标题为“用户请求”的列中。" lightbox="media/requested-apps.png":::

 1. 若要查看和检查每个应用的请求数，请 **按用户列对“请求** ”列中的请求进行排序。
 1. 选择要取消阻止的应用的名称，并打开应用详细信息页。
 1. 选择 **“管理请求** ”并完成弹出对话框中显示的步骤。 批准应用的步骤因用于阻止应用的方法而异。

    * 如果使用权限策略阻止应用，请通过修改 [权限策略](teams-app-permission-policies.md)来允许应用。
    * 如果所有用户都阻止应用， [请允许应用](#allow-and-block-apps)。
    * 如果所有用户都阻止了所有应用，请修改 [组织范围的设置](#manage-org-wide-app-settings)。

 如果管理员允许应用，则不会通知最终用户其请求已执行。 用户必须访问应用商店中的应用，以检查应用是否已解除阻止。

### <a name="dismiss-a-user-request"></a>消除用户请求

 1. 选择要为其消除用户请求的应用的名称。
 1. 选择 **“管理请求** ”，然后选择“关闭”对话框上 **的所有请求** 。
 1. 当请求被驳回时，它会将用户请求重置为零。

  :::image type="content" source="media/reject.png" alt-text="阻止的应用拒绝。"border="true":::

如果管理员驳回了请求，则不会通知最终用户其请求已执行。 用户必须访问应用商店中的应用，以检查应用是否已解除阻止。

## <a name="apps-blocked-by-publishers"></a>被发布者阻止的应用

当 ISV 将应用发布到全局应用商店时，他们可能需要管理员来配置或自定义应用体验。 管理员可以在设置应用时将其提供给最终用户。

例如，Contoso 电子版是一个 ISV，它为 Microsoft Teams 创建了一个技术支持。 Contoso Electronics 希望其客户设置应用的某些属性，以便当用户与应用交互时，它按预期运行。 在管理员允许或阻止应用程序之前，它将在 Teams 管理中心显示为 **“被发布者阻止** ”，并且默认情况下会对最终用户隐藏。 按照发布者的指南设置应用后，可以通过将状态更改为 **“允许**”来使其可供用户使用，或者通过将状态更改为 **“已阻止**”来阻止用户使用该应用。

<!--- 
![Screenshot of blocked by publisher status in teams admin center.](media/blocked-by-publisher.png)
--->

## <a name="add-an-app-to-a-team"></a>将应用添加到团队

使用 **“添加到团队** ”按钮将应用安装到团队。 此选项仅适用于可在团队范围内安装的应用。 此选项不适用于只能安装在个人范围内的应用。

1. 按应用名称搜索应用，然后选择该应用。 请勿打开应用详细信息页。
1. 选择 **“添加到团队**”。

   :::image type="content" source="media/manage-apps-add-app-team-trimmed.png" alt-text="可添加到团队范围的应用的“添加到团队”选项的屏幕截图。":::

1. 在 **“添加到团队** ”窗格中，搜索要将应用添加到的团队，选择团队，然后选择 **“应用**”。

## <a name="customize-an-app"></a>自定义应用

现在可以自定义应用，以便根据组织的需求包含特定的外观。 请参阅 [Teams 中的自定义应用](customize-apps.md)。

## <a name="purchase-services-for-third-party-apps"></a>购买第三方应用的服务

可以直接从“管理应用”页搜索并购买组织中用户的第三方应用提供的服务许可证。 表中的 **“许可证”** 列指示应用是否提供付费 SaaS 订阅。 **立即选择“购买**”以查看计划和定价信息，并为用户购买许可证。 若要了解详细信息，请参阅 [Microsoft Teams 管理中心中 Teams 第三方应用的购买服务](purchase-third-party-apps.md)。

## <a name="grant-permissions-and-consent-to-apps-to-use-end-user-information"></a>向应用授予使用最终用户信息的权限和许可

可以代表组织中的所有用户对请求权限的应用进行评审并授予许可。 为此，用户无需在启动应用时查看和接受应用请求的权限。 “ **权限** ”列指示应用是否具有需要同意的权限。 你将看到 Azure AD 中注册的每个应用的 **视图详细信息** 链接，该链接具有需要同意的权限。 若要了解详细信息，请参阅 [Microsoft Teams 管理中心中的“查看应用权限”并授予管理员许可](app-permissions-admin-center.md)。

## <a name="view-resource-specific-consent-permissions"></a>查看特定于资源的许可权限

特定于资源的许可 (RSC) 权限允许团队所有者授予应用访问和修改团队数据的许可。 RSC 权限是精细的、特定于 Teams 的权限，用于定义应用在特定团队中可以执行的操作。 可以在应用详细信息页的“ **权限** ”选项卡上查看 RSC 权限。 若要了解详细信息，请参阅 [Microsoft Teams 管理中心中的“查看应用权限”并授予管理员许可](app-permissions-admin-center.md)。

## <a name="manage-org-wide-app-settings"></a>管理组织范围的应用设置

使用组织范围的应用设置来控制拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) 的用户是否获得定制的一线应用体验、用户是否可以安装第三方应用，以及用户是否可以上传或与组织中的自定义应用交互。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 你可以使用它们控制恶意应用或有问题的应用。

> [!NOTE]
> 若要了解如何在 Microsoft 365 政府版 - 政府社区云高 GCCH 和国防部 (DoD) 部署 Teams 中使用组织范围的应用设置，请参阅 [Teams 中的“管理应用权限策略](teams-app-permission-policies.md)”。

1. 在“管理应用”页上，选择 **组织范围的应用设置**。 然后，可以在窗格中配置所需的设置。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="“管理应用”页上“组织范围的应用设置”窗格的屏幕截图":::

1. 在 **“定制应用**”下，关闭或打开 **“显示定制应用**”。 启用此设置时，具有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) 的用户可获得定制的一线应用体验。 此体验为一线员工固定 Teams 中最相关的应用。 若要了解详细信息，请参阅 [一线员工的裁缝 Teams 应用](pin-teams-apps-based-on-license.md)。

    此功能适用于 F 许可证。 将来将支持其他许可证类型。
1. 在“**第三方应用**”下，关闭或打开这些设置以控制对第三方应用的访问权限：

    * **允许第三方应用**：控制用户是否可以使用第三方应用。 如果关闭此设置，用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为 **“已阻止的组织范围** ”。

        > [!NOTE]
        > **当允许第三方应用** 关闭时，仍会为所有用户启用 [传出 Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)，但可以通过应用权 [限策略](teams-app-permission-policies.md)允许或阻止传出 Webhook 应用在用户级别控制它们。 请注意，如果现有 [Microsoft 应用的应用权限策略](teams-app-permission-policies.md)使用 **“允许特定应用”并阻止所有其他** 设置，并且要为用户启用传出 Webhook，请将传出 Webhook 应用添加到列表中。

        > [!NOTE]
        > 主持会议或与来自其他组织的人员聊天时，Teams 用户可以添加应用。 当他们加入由其他组织主持的会议或聊天时，也可以使用由这些组织的人共享的应用。 将应用主持用户组织的数据策略，以及该用户组织共享的任何第三方应用的数据共享实践。

    * **默认情况下，允许发布到应用商店的所有新的第三方应用**：控制发布到 Teams 应用商店的新第三方应用是否在 Teams 中自动可用。 仅在允许第三方应用时才能设置此选项。

1. 在 **“自定义应用**”下，关闭或启用 **允许与自定义应用的交互**。 此设置控制用户是否可以与自定义应用交互。 要了解详细信息，请参阅[在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。
1. 选择 **“保存** ”以实现组织范围的应用设置。

## <a name="see-also"></a>另请参阅

* [在从Skype for Business管理中心过渡期间管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
