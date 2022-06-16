---
title: 在Microsoft Teams管理中心查看应用权限并授予管理员同意
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何查看应用请求的权限，以及如何在Microsoft Teams管理中心的“管理应用”页上向应用授予管理员许可。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e81b15b700cf2b62c93e5acd784a6303458280aa
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124437"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在Microsoft Teams管理中心查看应用权限并授予管理员同意

Microsoft Teams管理中心中的“[管理应用](manage-apps.md)”页是查看和管理组织的所有Teams应用的位置。 例如，可以看到应用的组织级状态和属性，批准或上传新的自定义应用到组织的应用商店，阻止或允许组织级别的应用，以及管理组织范围的应用设置。

在这里，还可以向请求访问数据权限的应用授予组织范围的管理员许可，并查看特定于资源的许可 (RSC) 应用的权限。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>向应用授予组织范围的管理员许可

如果你是全局管理员，则可以查看并授予代表组织中所有用户请求权限的应用的许可。 为此，用户无需在启动应用时查看和接受应用请求的权限。 此外，根据Azure Active Directory (Azure AD) 中的用户[同意设置](/azure/active-directory/manage-apps/configure-user-consent)，可能不允许某些用户向访问公司数据的应用授予许可。

应用请求的权限示例包括能够读取团队中存储的信息、读取用户的个人资料，以及代表用户发送电子邮件。 若要了解详细信息，请[参阅Microsoft 标识平台终结点中的权限和同意](/azure/active-directory/develop/v2-permissions-and-consent)。

“ **权限** ”列指示应用是否具有需要同意的权限。 你将看到 Azure AD 中注册的每个应用的 **视图详细信息** 链接，该链接具有需要同意的权限。 请记住，这仅适用于自定义和第三方应用。 此链接不适用于 Microsoft 提供的应用。 此外，管理员不必为此类应用授予许可。

若要向应用授予组织范围的许可，请执行以下步骤：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 执行下列操作之一：
    * 搜索所需的应用，单击应用名称转到应用详细信息页，然后选择“ **权限”** 选项卡。
    * 按降序对 **“权限”** 列进行排序以查找应用，然后选择 **“查看详细信息**”。 执行此操作可转到应用详细信息页的“ **权限** ”选项卡。

1. 在 **组织范围的权限** 下，选择 **“审阅权限”和“同意**”。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用的“权限”选项卡上的组织范围权限的屏幕截图。":::

    必须是全局管理员才能执行此操作。 此选项不适用于Teams服务管理员。

1. 在“ **权限”** 选项卡上，查看应用请求的权限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图。":::

    > [!IMPORTANT]
    > 向应用授予组织范围的许可允许应用访问组织的数据。 在授予同意之前，请仔细查看应用请求的权限。

1. 如果同意应用请求的权限，请单击 **“接受** ”以授予同意。 页面顶部会暂时显示一条横幅，让你知道已为应用授予请求的权限。 现在，该应用有权访问组织中所有用户的指定资源，并且不会提示其他人查看权限。

接受这些权限后，你将在应用详细信息页的 **组织范围** 权限下看到一条消息，告知已授予同意。 若要查看有关应用权限的详细信息，请单击 **Azure Active Directory** 链接，转到 Azure AD 门户中的应用页面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="授予同意时显示的消息的屏幕截图。":::

如果允许组织中的用户授予同意，并且一个或多个用户向特定应用授予许可，你还将看到相同的消息，告知你已授予许可，以及 Azure AD 门户中应用页面的Azure Active Directory链接。

> [!NOTE]
> 尽管“**审阅权限和同意**”选项不适用于Teams服务管理员，并且他们无法向应用授予组织范围的管理员许可，但Teams服务管理员可以在应用 **的“权限**”选项卡上查看内容。 例如，Teams服务管理员可以单击 **Azure Active Directory** 链接，在 Azure AD 门户中查看应用权限详细信息。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看应用的特定于资源的许可权限

RSC 权限允许团队所有者授予应用访问和修改团队数据的许可。 RSC 权限是精细的、特定于Teams的权限，用于定义应用在特定团队中可以执行的操作。 RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。

RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。 将应用添加到团队时，将授予对 RSC 权限的许可。 若要了解详细信息，请参阅 [特定于资源的许可 (RSC) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全局管理员和Teams服务管理员可以在应用详细信息页的“**权限**”选项卡上查看应用的 RSC 权限。

若要查看应用的 RSC 权限，请执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
1. 搜索所需的应用，单击应用名称转到应用详细信息页，然后选择“ **权限”** 选项卡。
1. 根据 **Microsoft Graph特定于资源的许可 (RSC) 权限**，查看应用请求的 RSC 权限。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="应用的 RSC 权限的屏幕截图。":::

## <a name="known-issues"></a>已知问题

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>“查看详细信息”链接不会显示在请求权限的某些第三方应用的“权限”列中

目前，在 Azure AD 中注册的所有请求权限的第三方应用都无法查看权限和授予许可。 你将在“**权限**”列中看到 **--**“**视图详细信息”链接，而不是“视图详细信息**”链接。 我们正在使用 ISV 为其应用启用此功能。

## <a name="related-topics"></a>相关主题

* [在Microsoft Teams管理中心管理应用](manage-apps.md)
* [Microsoft 标识平台终结点中的权限和同意](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams中特定于资源的许可](resource-specific-consent.md)
* [特定于资源的许可 (RSC) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* 在 Ignite 2020 会话 (导航[Teams应用生命周期](https://aka.ms/PR132)) 
