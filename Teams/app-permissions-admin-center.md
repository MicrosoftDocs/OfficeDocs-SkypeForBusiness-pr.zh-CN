---
title: 在 Microsoft Teams 管理中心中查看应用权限并授予管理员同意
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心的“管理应用”页上查看应用请求的权限并向应用授予管理员同意。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ec44990728feac5982641ce80ff15442bcaf7d
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396483"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心中查看应用权限并授予管理员同意

管理员从 Teams 管理中心的“管理应用”页查看和管理所有 Teams 应用。 可以管理在组织内创建的、仅对最终用户可用的自定义应用，并管理 Teams 应用商店中可用的第三方。 例如，可以看到应用的组织级状态和属性，批准或将新的自定义应用上传到组织的应用商店，允许在组织级别或单个最终用户使用应用。

可以在此处向请求访问数据和查看应用的资源特定许可 (RSC) 的应用授予组织范围的管理员同意。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>向应用授予组织范围的管理员同意

如果你是全局管理员，则可以查看并同意代表组织中的所有用户请求权限的应用。 执行此操作后，用户无需在启动应用时查看并接受应用请求的权限。 此外，根据用户在 Azure Active Directory (Azure AD) 中的 [同意设置](/azure/active-directory/manage-apps/configure-user-consent)，可能不允许某些用户向访问公司数据的应用授予同意。

应用请求的权限示例包括读取存储在团队中的信息、读取用户配置文件和代表用户发送电子邮件的功能。 要了解详细信息，请参阅 [Microsoft 标识平台终结点中的权限和同意](/azure/active-directory/develop/v2-permissions-and-consent)。

“**权限**”列指示应用是否具有需要同意的权限。 你将看到适用于在 Azure AD 中注册的每个应用的 **查看详细信息** 链接，这些应用具有需要同意的权限。 请记住，这仅适用于自定义和第三方应用。 此链接不适用于 Microsoft 提供的应用。 此外，管理员不必为此类应用授予许可。

要向应用授予组织范围的同意，请按照以下步骤操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > **“[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)”**。

1. 执行下列操作之一：
    * 搜索所需的应用，选择要转到应用详细信息页的应用名称，然后选择“ **权限”** 选项卡。
    * 按降序对“**权限**”列进行排序以查找应用，然后选择“**查看详细信息**”。 执行此操作将你访问 **应用程序详细信息** 页的"权限"选项卡。

1. 在“**组织范围权限**”下，选择“**查看权限和同意**”。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用“权限”选项卡上组织范围权限的屏幕截图。":::

    必须是全局管理员才能执行此操作。 此选项对 Teams 服务管理员不可用。

1. 在“**权限**”选项卡上，查看应用请求的权限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图。":::

    > [!IMPORTANT]
    > 向应用授予组织范围的同意将允许应用访问组织的数据。 在授予同意之前，请仔细查看应用请求的权限。

1. 如果同意应用请求的权限，请选择 **“接受** ”以授予同意。 在页面顶部将临时显示一个横幅，以告知你已向应用授予请求的权限。 应用现在有权访问组织中所有用户的指定资源，系统不会提示其他人查看权限。

接受权限后，你将在应用详细信息页上“**组织范围权限**”下看到消息，告知你已授予许可。 若要查看有关应用权限的详细信息，请选择 **Azure Active Directory** 链接以转到 Azure AD 门户中的应用页面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="授予同意时显示的消息的屏幕截图。":::

如果允许组织中的用户授予许可，并且一个或多个用户已向特定应用授予许可，则你还将看到相同的消息，告知你已授予许可，以及指向 Azure AD 门户中应用页的 Azure Active Directory 链接。

> [!NOTE]
> 尽管“**查看权限和同意选项**”不可用于 Teams 服务管理员，因此他们无法向应用授予组织范围的管理员同意，但 Teams 服务管理员可以查看应用的“**权限**”选项卡上的内容。 例如，Teams 服务管理员可以单击“**Azure Active Directory**”链接，以在 Azure AD 门户中查看应用权限详细信息。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看应用的资源特定同意权限

借助 RSC 权限，团队所有者可以向应用授予访问和修改团队数据的许可。 RSC 权限是特定于 Teams 的精细权限，用于定义应用可在特定团队中执行的操作。 RSC 权限的示例包括创建和删除频道、获取团队设置，以及创建和删除频道选项卡的功能。

RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。 将应用添加到团队时，可授予对 RSC 权限的许可。 要了解详细信息，请参阅 [资源特定许可 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

全局管理员和 Teams 服务管理员可以在应用详细信息页的“**权限**”选项卡上查看应用的 RSC 权限。

要查看应用的 RSC 权限，请执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
1. 搜索所需的应用，选择要转到应用详细信息页的应用名称，然后选择“ **权限”** 选项卡。
1. 在“**Microsoft Graph 资源特定许可 (RSC) 权限**”下，查看应用请求的 RSC 权限。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="应用的 RSC 权限的屏幕截图。":::

## <a name="known-issues"></a>已知问题

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>对于某些请求权限的第三方应用，“查看详细信息”链接将不会显示在“权限”列中

查看权限和授予同意的功能不适用于所有第三方应用。 通常，当应用请求权限时，第三方应用会在 Azure Active Directory 中注册。 你将在“权限”列中看到 **`--`**，而不是“**查看详细信息**”链接。

## <a name="related-articles"></a>相关文章

* [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
* [Microsoft 标识平台终结点中的权限和同意](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams 中的资源特定许可](resource-specific-consent.md)
* [资源特定许可 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [导航 Teams 应用生命周期](https://aka.ms/PR132)（Ignite 2020 大会）
