---
title: Microsoft Teams 中特定于资源的同意
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解需要配置的设置，以控制组织中团队所有者是否可以同意应用。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815672"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams 中特定于资源的同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams 中特定于资源的同意可让团队所有者同意应用访问团队数据。 此类访问的示例包括读取频道消息、创建和删除频道以及创建和删除频道选项卡的功能。

作为管理员，你可以控制你的组织的团队所有者是否可以通过使用 Azure Active Directory (Azure AD) PowerShell 模块或 Azure 门户和 Microsoft Teams 管理中心配置的设置来表示同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>设置团队所有者是否可以许可应用

下面是必须设置以控制团队所有者是否可以许可应用的设置。 请务必查看以下所有设置。

### <a name="settings-in-azure-ad"></a>Azure AD 中的设置

以下两个设置确定团队所有者是否可以许可应用。

> [!IMPORTANT]
> 更改这些设置不会影响已授予许可的应用的数据访问。 例如，如果将这些设置配置为防止团队所有者表示许可，这些更改不会删除已授予的数据访问。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"用户可以同意应用代表他们访问公司数据"设置

此设置控制您的组织中的用户是否可以代表他们许可应用。 若要使团队所有者能够表示同意，必须将此设置设置为 **"是"。** 若要管理此设置，请执行下列操作：

1. 在 Azure 门户中，转到 **"企业应用程序**  >  **用户设置"。**
2. 在 **"企业应用程序**"**下，将"用户可以同意** 代表用户访问公司数据的应用"设置为"**否**"或"**是"。**

也可使用 PowerShell 管理此设置。 若要了解有关详细信息，请参阅"[为应用程序配置用户内容"。](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent"设置

此设置控制您的组织中的用户是否可以同意应用访问他们拥有组的公司数据。 必须启用此设置，团队所有者才能表示同意。 有关如何使用 PowerShell 管理此设置的步骤，请参阅"配置组所有者同意[访问组数据的应用"。](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的设置

除了 Azure AD 中的设置[](manage-apps.md#manage-org-wide-app-settings)外，"管理应用"页面上[](manage-apps.md)的组织范围应用设置、应用在"管理应用"页面上是[](manage-apps.md#allow-and-block-apps)被阻止还是允许，以及分配给团队所有者的应用权限策略决定了团队所有者是否可以同意。 [](teams-app-permission-policies.md)

> [!IMPORTANT]
> 更改这些设置不会影响已授予许可的应用的数据访问。 例如，如果在组织范围内禁用第三方应用，或者阻止特定应用以防止团队所有者同意，这些更改不会删除已授予的数据访问权限。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>组织范围应用设置中的"允许第三方应用"设置

此组织范围内的应用设置控制组织中的用户是否可以使用第三方应用。 必须启用此设置，团队所有者才能表示同意。 若要管理此设置，请执行下列操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用** 管理应用"，然后单击"  >  **组织范围的应用设置"。**
2. 在第 **三方应用下**，关闭或打开"允许 **第三方应用"。**

    !["允许 Teams 中的第三方应用"设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

最长可能需要等待 24 小时，更改才会生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>在组织级别允许或阻止应用

当你在"管理应用"页面上阻止或[](manage-apps.md#allow-and-block-apps)允许应用时，将阻止或允许组织中所有用户使用该应用。 如果允许应用，团队所有者只能同意应用。 若要在组织级别允许或阻止应用，请执行下列操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**
2. 在"管理应用"页面上，选择应用，然后单击"阻止"以阻止它 **或单击"** 允许"以允许它。

    ![组织范围内设置中阻止的应用的屏幕截图](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>分配给团队所有者的应用权限策略

团队所有者只能同意应用其应用权限策略允许其运行。 若要查看和管理分配给团队所有者的应用权限策略，请执行下列操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**用户"。**
2. 双击团队显示名称，然后单击"策略 **"。**
3. 分配给团队所有者的策略列在应用权限 **策略下**。
    - 若要分配其他策略，请单击"编辑"，然后选择要分配的策略。
    - 若要编辑分配给团队所有者的策略设置，请单击策略名称，然后进行想要的更改。  

## <a name="uploading-custom-apps"></a>上传自定义应用

将自定义应用 (也) 资源特定许可的旁加载应用时，应用必须来自它要安装到的租户。 换句话说，Azure AD 应用注册必须来自此租户。 全局管理员不受此限制限制，可以直接将自定义应用从任何租户上传到团队 (旁加载) 或租户应用目录。

## <a name="related-topics"></a>相关主题

- [可用的 RSC 权限](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
