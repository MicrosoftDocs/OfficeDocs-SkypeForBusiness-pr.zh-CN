---
title: 在管理中心查看应用权限Microsoft Teams管理员许可
author: cichur
ms.author: v-mahoffman
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在管理中心的"管理应用"页面上查看应用请求的权限并授予Microsoft Teams许可。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5076c80edfff8e4b36b53ad79c3b17805f4d6df
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775992"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在管理中心查看应用权限Microsoft Teams管理员许可

管理[中心](manage-apps.md)中的"Microsoft Teams"页面是查看和管理组织Teams应用的地方。 例如，可以看到应用的组织级状态和属性、批准新的自定义应用或将其上载到组织的应用商店、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。

在此处，还可以向请求访问数据和查看资源特定许可权限的应用授予组织范围的管理员许可， (RSC) 权限。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>向应用授予组织范围的管理员许可

如果你是全局管理员，你可以查看并许可代表组织中所有用户请求权限的应用。 你这样做，以便用户不必在启动应用时查看并接受应用请求的权限。 此外，根据用户在应用程序中[的同意](/azure/active-directory/manage-apps/configure-user-consent)Azure Active Directory (Azure AD) ，可能不允许某些用户向访问公司数据的应用授予许可。

应用请求的权限示例包括读取团队中存储的信息、读取用户的个人资料以及代表用户发送电子邮件的能力。 有关详细信息，请参阅终结点 中[的权限Microsoft 标识平台许可](/azure/active-directory/develop/v2-permissions-and-consent)。 

" **权限"** 列指示应用是否具有需要许可的权限。 你将看到 **在具有需要** 许可的权限的 Azure AD中注册的每个应用的"查看详细信息"链接。 请记住，这仅适用于自定义和第三方应用。 你不会看到此链接，也不需要为 Microsoft 发布的应用授予管理员许可。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用"页面上"权限"列的屏幕截图。":::

若要向应用授予组织范围许可，请执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 执行下列操作之一：
    - 搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。
    - 按降 **序对**"权限"列进行排序以查找应用，然后选择"**查看详细信息"。** 执行此操作会你将访问 **应用详细信息页** 的"权限"选项卡。

3. 在 **"组织范围的权限"下**，选择 **"审阅权限和同意"。**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用"权限"选项卡上组织范围内权限的屏幕截图。":::

    只有全局管理员才能这样做。 此选项对服务管理员Teams可用。

4. 在 **"权限"** 选项卡上，查看应用请求的权限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图。":::

    > [!IMPORTANT]
    > 向应用授予组织范围同意允许应用访问组织的数据。 在授予许可之前，请仔细查看应用请求的权限。
5. 如果你同意应用请求的权限，请单击"接受 **"以授予** 同意。 页面顶部临时显示一个横幅，告知你已授予应用所请求的权限。 应用现在有权访问组织中所有用户的指定资源，系统不会提示任何其他用户查看权限。

接受权限后，应用详细信息页面上的" **组织** 范围权限"下会显示一条消息，告知你已授予许可。 若要查看有关应用权限的详细信息，请单击Azure Active Directory链接以转到应用门户中的应用Azure AD页面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="授予许可时显示的消息的屏幕截图。":::

如果允许您的组织中的用户授予许可，并且如果一个或多个用户授予了对特定应用的同意，则还将看到相同的消息，告知你已授予许可，以及 Azure AD 门户中应用的 Azure Active Directory 链接。

> [!NOTE]
> 尽管"审阅权限和许可"选项不可用于 Teams 服务管理员，并且他们无法向应用授予组织范围的管理员许可，但 Teams 服务管理员可以在应用的"权限"选项卡上查看内容。  例如，Teams服务管理员可以单击"Azure Active Directory"链接，在门户中查看应用Azure AD详细信息。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看应用的资源特定许可权限

RSC 权限允许团队所有者授予应用访问和修改团队数据的许可。 RSC 权限是Teams特定权限，用于定义应用可在特定团队中执行哪些操作。 RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。 

RSC 权限在应用清单中定义，而不是在Azure AD。 将应用添加到团队时，需要授予对 RSC 权限的许可。 若要了解有关详细信息，请参阅[RSC (资源特定的) 。 ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

全局管理员Teams服务管理员可以在应用详细信息页的"权限"选项卡上查看应用的 RSC权限。 

若要查看应用的 RSC 权限，请执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。
3. 在 **"Microsoft Graph RSC** (许可) 下，查看应用请求的 RSC 权限。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="应用的 RSC 权限屏幕截图。":::

## <a name="known-issues"></a>已知问题

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>某些请求权限的第三方应用的"权限"列中不显示"查看详细信息"链接

目前，在请求权限的应用中注册的所有第三方应用Azure AD权限和授予许可。 你将在 **"权限"** 列中看到，而不是" **--** 查看 **详细信息"** 链接。 我们正在与 ISV 合作，为应用启用此功能。

## <a name="related-topics"></a>相关主题

- [在管理中心内Microsoft Teams应用](manage-apps.md)
- [终结点中的权限Microsoft 标识平台许可](/azure/active-directory/develop/v2-permissions-and-consent)
- [应用程序内特定于资源Teams](resource-specific-consent.md)
- [RSC (特定于资源) ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [在](https://aka.ms/PR132)Ignite 2020 Teams应用中导航 (生命周期) 