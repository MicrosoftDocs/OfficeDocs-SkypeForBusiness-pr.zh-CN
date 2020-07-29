---
title: Microsoft 团队中特定于资源的同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解需要配置以控制组织中的团队所有者是否可以同意应用的设置。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429374"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft 团队中特定于资源的同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft 团队中特定于资源的同意允许团队所有者同意访问团队数据的应用。 此类访问的示例包括读取通道消息、创建和删除信道以及创建和删除信道选项卡的功能。

作为管理员，你可以控制你的组织中的团队所有者是否可以通过使用 Azure Active Directory （Azure AD） PowerShell 模块或 Azure 门户和 Microsoft 团队管理中心配置的设置授予同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>设置团队所有者是否可以同意应用

以下是你必须设置的设置以控制团队所有者是否可以同意应用。 请务必查看以下所有设置。

### <a name="settings-in-azure-ad"></a>Azure AD 中的设置

以下两个设置确定团队所有者是否可以同意应用。

> [!IMPORTANT]
> 更改这些设置中的任何设置不会影响已授权的应用的数据访问。 例如，如果配置这些设置以防止团队所有者授予同意，这些更改不会删除已授予的数据访问权限。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"用户可以同意代表自己访问公司数据的应用" 设置

此设置控制你的组织中的用户是否可以代表他们同意应用。 若要使团队所有者能够授予同意，此设置必须设置为 **"是"**。 若要管理此设置，请执行下列操作：

1. 在 Azure 门户中，转到 "**企业应用程序**"  >  **用户设置**。
2. 在 "**企业应用程序**" 下，设置用户可以同意代表 "**否**" 或 **"是"****的应用访问公司数据**。

您也可以使用 PowerShell 管理此设置。 若要了解详细信息，请参阅[将用户内容配置到应用程序](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 设置

此设置控制你的组织中的用户是否可以同意访问其拥有的组的公司数据的应用。 必须为团队所有者启用此设置以授予同意。 有关如何使用 PowerShell 管理此设置的步骤，请参阅[配置团队所有者同意访问组数据的应用](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心中的设置

除了 Azure AD 中的设置外，"[管理应用](manage-apps.md)" 页面上的 "[组织范围内应用设置](manage-apps.md#manage-org-wide-app-settings)"、"[管理应用](manage-apps.md#allow-and-block-apps)" 页面上是否已阻止或允许应用，以及分配给团队所有者的[应用权限策略](teams-app-permission-policies.md)确定团队所有者是否授予同意。

> [!IMPORTANT]
> 更改这些设置中的任何设置不会影响已授权的应用的数据访问。 例如，如果您禁用了组织范围内的第三方应用或阻止了特定应用以防止团队所有者授予同意，则这些更改不会删除已授予的数据访问权限。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>组织范围的应用设置中的 "允许第三方应用" 设置

此组织范围内的应用设置控制你的组织中的用户是否可以使用第三方应用。 此设置必须为 "启用" 才能使团队所有者授予同意。 若要管理此设置，请执行下列操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"，然后单击 "**组织范围的应用设置**"。
2. 在 "**第三方应用**" 下，关闭或打开 "**允许第三方应用**"。

    !["允许团队中的第三方应用" 设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

最长可能需要等待 24 小时，更改才会生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>在组织级别允许或阻止应用

当你在 "[管理应用](manage-apps.md#allow-and-block-apps)" 页面上阻止或允许应用时，将阻止或允许组织中的所有用户使用该应用。 如果允许应用，团队所有者仅可向应用授予许可。 若要允许或阻止组织级别的应用，请执行下列操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 在 "管理应用" 页面上，选择应用，然后单击 "**阻止**" 以阻止它，或单击 "**允许**" 以允许它。

    ![组织范围设置中被阻止的应用的屏幕截图](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>分配给团队所有者的应用权限策略

团队所有者只能同意其应用权限策略允许其运行的应用。 若要查看和管理分配给团队所有者的应用权限策略，请执行下列操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。
2. 双击团队所有者的显示名称，然后单击 "**策略**"。
3. 分配给团队所有者的策略在 "**应用权限策略**" 下列出。
    - 若要分配其他策略，请单击 "**编辑**"，然后选择要分配的策略。
    - 若要编辑分配给团队所有者的策略的设置，请单击策略名称，然后进行所需的更改。  

## <a name="uploading-custom-apps"></a>上载自定义应用程序

当上载使用特定于资源的同意的自定义应用（也称为旁加载）时，应用必须来自要安装到的租户。 换言之，Azure AD 应用注册必须来自此租户。 全局管理员从此限制中免除，并且可以将自定义应用从任意租户直接上载到团队（旁加载）或租户应用目录。

## <a name="related-topics"></a>相关主题

- [可用的 RSC 权限](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [在 Microsoft 团队管理中心中管理你的应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
