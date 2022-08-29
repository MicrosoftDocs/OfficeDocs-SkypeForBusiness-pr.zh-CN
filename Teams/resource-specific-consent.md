---
title: Microsoft Teams 中的资源特定同意
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解需要配置的设置，以控制组织中的团队所有者是否可以向应用表示同意。
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb96b6130ce87d8d1453f6ea4ee40af2bb84050d
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396463"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams 中的资源特定同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams 中的资源特定同意使团队所有者能够同意应用访问团队数据。 此类访问的示例包括读取频道消息、创建和删除频道以及创建和删除频道选项卡的功能。

作为管理员，你可以控制组织中的团队所有者是否可以通过你使用 Azure AD (Azure AD) PowerShell 模块或 Azure 门户和 Microsoft Teams 管理中心配置的设置来表示同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>设置团队所有者是否可以向应用表示同意

下面是必须设置的设置，以控制团队所有者是否可以向应用表示同意。 请务必查看以下所有设置。

### <a name="settings-in-azure-active-directory-portal"></a>Azure Active Directory 门户中的设置

以下两个设置确定团队所有者是否可以向应用表示同意。

> [!IMPORTANT]
> 更改上述任何设置不会影响已获得同意的应用的数据访问。 例如，如果配置这些设置来防止团队所有者表示同意，则这些更改不会删除已授予的数据访问权限。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>“用户可以同意应用代表他们访问公司数据”设置

此设置控制组织中的用户是否可以同意应用代表其进行访问。 若要使团队所有者能够表示同意，必须将此设置设置为“**是**”。 若要管理此设置，请执行以下操作：

1. 在 Azure 门户中，转到“**企业应用程序**” > “**用户设置**”。
2. 在“**企业应用程序**”下，将“**用户可以同意应用代表他们访问公司数据**”设置为“**否**”或“**是**”。

还可以使用 PowerShell 管理此设置。 若要了解详细信息，请参阅[配置应用程序的用户同意](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>“EnableGroupSpecificConsent”设置

此设置控制组织中的用户是否可以同意应用访问他们拥有的组的公司数据。 必须启用此设置，团队所有者才能表示同意。 有关如何使用 PowerShell 管理此设置的步骤，请参阅[配置组所有者对应用程序的同意](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的设置

除了 Azure AD 中的设置、“[管理应用](manage-apps.md)”页面上[组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)，无论是在“[管理应用](manage-apps.md#allow-and-block-apps)”页面上阻止还是允许应用，分配给团队所有者的[应用权限策略](teams-app-permission-policies.md)都决定团队所有者是否可以表示同意。

> [!IMPORTANT]
> 更改上述任何设置不会影响已获得同意的应用的数据访问。 例如，如果在组织范围内禁用第三方应用，或者阻止特定应用以阻止团队所有者表示同意，则这些更改不会删除已授予的数据访问权限。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>组织范围应用设置中的“允许第三方应用”设置

此组织范围的应用设置控制组织中的用户是否可以使用第三方应用。 必须启用此设置，团队所有者才能表示同意。 若要管理此设置，请执行以下操作：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 选择 **组织范围的应用设置** ，在第 **三方应用** 下，关闭或打开 **“允许第三方应用**”。

    ![Teams 中的“允许第三方应用”设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

最长可能需要等待 24 小时，更改才会生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>在组织级别允许或阻止应用

在“[管理应用](manage-apps.md#allow-and-block-apps)”页面上阻止或允许应用时，将对组织中的所有用户阻止或允许该应用。 仅当允许应用时，团队所有者才能对应用表示同意。 若要在组织级别允许或阻止应用，请执行以下操作：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 在“管理应用”页上，选择应用，然后选择 **“阻止** ”以阻止它或选择 **“允许** ”以允许它。

    ![组织范围设置中被阻止的应用的屏幕截图。](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>分配给团队所有者的应用权限策略

团队所有者只能对其应用权限策略允许运行的应用表示同意。 若要查看和管理分配给团队所有者的应用权限策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**用户**”。
1. 双击团队所有者的显示名称，然后选择 **“策略**”。
1. 分配给团队所有者的策略在“**应用权限策略**”下列出。
    - 若要分配其他策略，请选择 **“编辑**”，然后选择要分配的策略。
    - 若要编辑分配给团队所有者的策略设置，请选择策略名称，然后进行所需的更改。  

## <a name="upload-custom-apps"></a>上传自定义应用

上传使用资源特定同意的自定义应用（也称为旁加载）时，应用必须来自要安装到的租户。 换句话说，Azure AD 应用必须从此租户注册。 全局管理员不受此限制，可以直接将自定义应用从任何租户上传到团队（旁加载）或租户应用目录。

## <a name="related-articles"></a>相关文章

- [可用的 RSC 权限](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
