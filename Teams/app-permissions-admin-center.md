---
title: 在 Microsoft Teams 管理中心查看应用权限并授予管理员许可
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何查看应用请求的权限，以及在 Microsoft Teams 管理中心的"管理应用"页面上向应用授予管理员许可。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6aafd5cbdd1ae44844f69b78234f10a54abe7b85
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824903"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心查看应用权限并授予管理员许可

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在 Microsoft Teams [管理](manage-apps.md) 中心内的"管理应用"页面，你可在其中查看和管理组织的所有 Teams 应用。 例如，你可以查看应用的组织级别状态和属性、批准或上传新的自定义应用、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。

在这里，也可向组织范围的管理员同意请求访问数据的应用，并查看应用的 (RSC) 用户。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>向组织范围的管理员同意应用

如果您是全局管理员，则可以审阅并授予这些应用，这些应用代表全部用户请求权限。 这样做是为了使用户不必审阅并接受应用在启动应用时所请求的权限。 此外，根据 Azure Active Directory (Azure AD) 的用户许可设置，可能不允许某些用户获得有关访问公司数据的应用的许可。 [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent)

应用请求的权限示例包括读取团队中存储的信息、阅读用户的配置文件以及代表用户发送电子邮件的能力。 若要了解详细信息，请参阅 Microsoft 身 [份平台终结点中的权限和许可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。 

**"权限**"列指示应用是否具有需要同意的权限。 你将看到在 Azure AD **中** 注册的每个应用的视图详细信息链接，该应用中包含需要许可的权限。 请记住这仅适用于自定义和第三方应用和应用。 您不会看到此链接，或者需要授予管理员许可，让 Microsoft 发布的应用使用。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用"页面上的"权限"列的屏幕截图":::

若要向应用授予组织范围许可，请按照以下步骤操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。
2. 执行下列操作之一：
    - 搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。
    - 按 **降序** 对"权限"列进行排序以查找应用程序，然后选择" **查看详细信息**"。 这样可以使你进入应用 **详细信息** 页面的"权限"选项卡。

3. 在**组织范围内的权限下**，选择 **"审阅"权限并同同。**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用程序的"权限"选项卡上组织范围的权限的屏幕截图":::

    只有全局管理员才能执行此操作。 Teams 服务管理员不能使用此选项。

4. 在 **"权限** "选项卡上，查看应用请求的权限。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > 向应用授予组织范围的同意可使应用访问你所在组织的数据。 在授予许可之前，仔细查看应用请求的权限。
5. 如果您相当意识到应用请求的权限 **，请单击"** 接受"以授予许可。 页面顶部暂时显示一个标题，可以让你知道已被请求的权限授予了该应用。 该应用现在具有针对组织中所有用户的指定资源的访问权限，而其他任何用户都不会提示您审阅权限。

接受权限后，你将在 **应用详细信息页面上的"组织** 范围"权限下看到一条消息，告诉你同意被授予。 要查看有关应用的权限的详细信息，请单击 Azure Active **Directory 链接** 以转到 Azure AD 门户中的应用页面。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="取确授予时显示的消息的屏幕截图":::

如果允许你授予同意，并且一个或多个用户同意特定应用同意，你还将看到同意消息，以通知你同意，并且 Azure AD 门户中该应用页面的 Azure Active Directory 链接。

> [!NOTE]
> 虽然 Teams **服务管理员** 无法使用"审阅"权限和同意选项，并且不能向应用授予组织范围的管理员同意，Teams 服务管理员可查看应用 **的"权限"** 选项卡上的内容。 例如，Teams 服务管理员可以单击 **Azure Active Directory 链接** 以在 Azure AD 门户中查看应用权限详细信息。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>查看应用的特定于资源的许可权限

RSC 权限允许团队所有者同意应用访问和修改工作组的数据。 RSC 权限是授予但特定于 Teams 的权限，用于定义应用在特定团队中可以执行的操作。 RSC 权限示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。 

RSC 权限在应用清单（而非 Azure AD）中定义。 当您向团队添加应用时，您授予对 RSC 权限的许可。 要了解详细信息，[请参阅特定于资源的同 () 。 ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

全局管理员和 Teams 服务管理员可在应用详细信息页的"权限 **"** 选项卡上查看应用的 RSC 权限。 

若要查看应用的 RSC 权限，请按照下列步骤操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。
2. 搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。
3. 在 **Microsoft Graph 资源 (特定的许) 可的) ，** 查看应用请求的 RSC 权限。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限的屏幕截图":::

## <a name="known-issues"></a>已知问题

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>"查看详细信息"链接未显示在请求权限的某些第三方应用的权限列中

目前，对于在 Azure AD 中注册了请求权限的所有第三方应用而来，审阅权限和授予许可功能不可访问。 您将在 **"权限"列** 中看到"查看 **--** 详细信息"列（而不是 **查看详细信息链接** ）。 我们正在使用 ISV 来为其应用启用此功能。

## <a name="related-topics"></a>相关主题

- [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
- [Microsoft 身份平台终结点中的权限和许可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams 中资源特定的一定](resource-specific-consent.md)
- [特定于资源的同 (RSC) ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


