---
title: 查看应用权限并授予 Microsoft 团队管理中心的管理员同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何查看应用请求的权限，并向 Microsoft 团队管理中心的 "管理应用" 页面上的应用授予管理员同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50a9abbd7e5872229c09d7d80c00c5d432723da1
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433045"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>查看应用权限并授予 Microsoft 团队管理中心的管理员同意

Microsoft 团队管理中心中的 " [管理应用](manage-apps.md) " 页面是你查看和管理你的组织的所有团队应用的位置。 例如，你可以查看应用的组织级别状态和属性、批准或将新的自定义应用上载到你的组织的应用商店、阻止或允许组织级别的应用，以及管理组织范围内的应用设置。

在此处，你还可以授予组织范围内管理员同意请求访问数据的权限的应用，并查看特定于资源的同意 (RSC) 应用的权限。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>向应用程序授予组织范围内管理员许可

如果您是全局管理员，您可以查看并同意代表您组织中的所有用户请求权限的应用。 这样做的目的是，用户在启动应用时不必查看和接受应用请求的权限。 此外，根据用户在 Azure Active Directory (Azure AD) 中的 [同意设置](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) ，某些用户可能不允许向访问公司数据的应用授予许可。

应用程序请求的权限的示例包括读取存储在团队中的信息、读取用户的配置文件以及代表用户发送电子邮件的功能。 若要了解详细信息，请参阅 [Microsoft 标识平台终结点中的权限和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。 

" **权限** " 列指示应用是否具有需要同意的权限。 你将看到在 Azure AD 中注册的每个应用的 " **查看详细信息** " 链接，该链接具有需要同意的权限。 请记住，这仅适用于自定义应用程序和第三方应用程序。 您将看不到此链接，也不需要授予由 Microsoft 发布的应用的管理员同意。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用" 页面上的 "权限" 列的屏幕截图":::

若要向应用授予组织范围内同意，请按照下列步骤操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 执行下列操作之一：
    - 搜索所需的应用，单击应用名称转到 "应用详细信息" 页面，然后选择 " **权限** " 选项卡。
    - 按降序对 " **权限** " 列进行排序以查找应用，然后选择 " **查看详细信息**"。 执行此操作将转到 "应用详细信息" 页面的 " **权限** " 选项卡。

3. 在 " **组织范围的权限**" 下，选择 " **审阅权限和同意**"。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用的 "权限" 选项卡上组织范围权限的屏幕截图":::

    只有全局管理员才能执行此操作。 团队服务管理员无法使用此选项。

4. 在 " **权限** " 选项卡上，查看应用请求的权限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > 授予应用的组织范围同意允许应用访问你的组织的数据。 在授予同意之前，请仔细查看该应用请求的权限。
5. 如果你同意应用请求的权限，请单击 " **接受** " 以授予同意。 标题会暂时显示在页面顶部，让你知道所请求的权限已被授予应用。 应用现在可以访问组织中所有用户的指定资源，并且不会提示任何其他人查看权限。

接受权限后，你将在 "应用详细信息" 页面上的 " **组织范围的权限** " 下看到一条消息，告知已授予同意。 若要查看有关应用权限的详细信息，请单击 **Azure Active Directory** 链接以转到 Azure AD 门户中的应用页面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="已授予同意时显示的消息的屏幕截图":::

如果你的组织中的用户允许授予同意，并且如果一个或多个用户授予了特定应用的同意，你还将看到相同的消息，告知你同意已授予同意，并且 Azure Active Directory 链接指向 Azure AD 门户中的应用页面。

> [!NOTE]
> 尽管 " **审阅权限和同意** " 选项对于团队服务管理员不可用，并且不能授予组织范围内管理员同意应用的权限，但团队服务管理员可以查看应用的 " **权限** " 选项卡上的内容。 例如，团队服务管理员可以单击 **Azure Active Directory** 链接以在 azure AD 门户中查看应用权限详细信息。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看应用的特定于资源的同意权限

RSC 权限允许团队所有者授予应用访问和修改团队数据的同意。 RSC 权限是特定于团队的权限，用于定义应用在特定团队中可以执行的操作。 RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。 

RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。 将应用添加到团队时，应授予对 RSC 权限的同意。 若要了解详细信息，请参阅 [特定于资源的同意 (RSC) ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全局管理员和团队服务管理员可以在应用详细信息页面的 " **权限** " 选项卡上查看应用的 RSC 权限。 

若要查看应用的 RSC 权限，请按照下列步骤操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 搜索所需的应用，单击应用名称转到 "应用详细信息" 页面，然后选择 " **权限** " 选项卡。
3. 在 " **Microsoft Graph 特定于资源的同意" (RSC) 权限**中，查看应用请求的 RSC 权限。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限的屏幕截图":::

## <a name="known-issues"></a>已知问题

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>在请求权限的某些第三方应用的 "权限" 列中不显示 "查看详细信息" 链接

目前，在 Azure AD 中注册权限的所有第三方应用都无法使用查看权限和授权许可的功能。 您将在 "权限" 列中看到，而不是 "**查看详细信息**" 链接 **--** **Permissions** 。 我们正在使用 Isv 为其应用启用此功能。

## <a name="related-topics"></a>相关主题

- [在 Microsoft 团队管理中心中管理你的应用](manage-apps.md)
- [Microsoft 标识平台终结点中的权限和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [团队中特定于资源的同意](resource-specific-consent.md)
- [特定于资源的同意 (RSC) ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [导航团队应用生命周期](https://aka.ms/PR132) (Ignite 2020 会话) 


