---
title: Microsoft Teams中特定于资源的许可
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解需要配置的设置，以控制组织中的团队所有者是否可以同意应用。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190493"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams中特定于资源的许可

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams中的资源特定许可允许团队所有者同意应用访问团队数据。 此类访问的示例包括读取频道消息、创建和删除通道以及创建和删除频道选项卡的功能。

作为管理员，你可以控制组织中的团队所有者是否可以通过使用 Azure Active Directory (Azure AD) PowerShell 模块或Azure 门户和Microsoft Teams管理中心配置的设置来表示同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>设置团队所有者是否可以同意应用

下面是必须设置的设置，以控制团队所有者是否可以同意应用。 请务必查看以下所有设置。

### <a name="settings-in-azure-ad"></a>Azure AD 中的设置

以下两个设置确定团队所有者是否可以同意应用。

> [!IMPORTANT]
> 更改上述任何设置不会影响已获得许可的应用的数据访问。 例如，如果配置这些设置以防止团队所有者同意，则这些更改不会删除已授予的数据访问权限。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>“用户可以同意应用代表其访问公司数据”设置

此设置控制组织中的用户是否可以代表其同意应用。 若要使团队所有者能够表示同意，必须将此设置设置为 **“是**”。 若要管理此设置，请执行以下操作：

1. 在Azure 门户中，转到 **Enterprise应用程序** > **用户设置**。
2. 在 **Enterprise应用程序** 下，设置 **用户可以同意应用代表其访问公司数据** 的 **“否**”或 **“是**”。

还可以使用 PowerShell 管理此设置。 若要了解详细信息，请参阅为 [应用程序配置用户内容](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>“EnableGroupSpecificConsent”设置

此设置控制组织中的用户是否可以同意应用访问他们拥有的组的公司数据。 必须启用此设置，团队所有者才能表示同意。 有关如何使用 PowerShell 管理此设置的步骤，请参阅 [配置组所有者对访问组数据的应用的许可](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理中心中的设置

除了 Azure AD 中的设置、[“管理应用](manage-apps.md)”页上的组织[范围应用设置](manage-apps.md#manage-org-wide-app-settings)外，“[管理应用](manage-apps.md#allow-and-block-apps)”页上是否阻止或允许应用，分配给团队所有者的[应用权限策略](teams-app-permission-policies.md)还决定团队所有者是否可以同意。

> [!IMPORTANT]
> 更改上述任何设置不会影响已获得许可的应用的数据访问。 例如，如果在组织范围内禁用第三方应用，或者阻止特定应用阻止团队所有者同意，则这些更改不会删除已授予的数据访问权限。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>组织范围应用设置中的“允许第三方应用”设置

此组织范围的应用设置控制组织中的用户是否可以使用第三方应用。 必须启用此设置才能让团队所有者同意。 若要管理此设置，请执行以下操作：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams应用** > **管理应用**，然后单击 **组织范围的应用设置**。
2. 在第 **三方应用** 下，关闭或打开 **允许第三方应用**。

    ![“允许Teams中的第三方应用”设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

最长可能需要等待 24 小时，更改才会生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>允许或阻止组织级别的应用

在 [“管理应用](manage-apps.md#allow-and-block-apps) ”页上阻止或允许应用时，会阻止或允许组织中的所有用户使用该应用。 仅当允许应用时，团队所有者才能同意应用。 若要允许或阻止组织级别的应用，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在“管理应用”页上，选择应用，然后单击 **“阻止** ”以阻止它或单击 **“允许** ”以允许它。

    ![组织范围设置中被阻止的应用的屏幕截图。](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>分配给团队所有者的应用权限策略

团队所有者只能同意应用的应用权限策略允许他们运行。 若要查看和管理分配给团队所有者的应用权限策略，请执行以下操作：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **“用户**”。
2. 双击团队所有者的显示名称，然后单击“ **策略**”。
3. 分配给团队所有者的策略在 **应用权限策略** 下列出。
    - 若要分配其他策略，请单击 **“编辑**”，然后选择要分配的策略。
    - 若要编辑分配给团队所有者的策略设置，请单击策略名称，然后进行所需的更改。  

## <a name="uploading-custom-apps"></a>上传自定义应用

上传自定义应用 (使用特定于资源的许可的已知旁加载) 时，应用必须来自要安装到的租户。 换句话说，Azure AD 应用注册必须来自此租户。 全局管理员不受此限制，可以直接将自定义应用从任何租户上传到团队 (旁加载) 或租户应用目录。

## <a name="related-topics"></a>相关主题

- [可用的 RSC 权限](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [在Microsoft Teams管理中心管理应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
