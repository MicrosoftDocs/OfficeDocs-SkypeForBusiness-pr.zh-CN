---
title: 设置共存和升级设置
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文将帮助你选择共存模式并设置其他共存设置。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b398a9e70d650ad2afd70c60250076f1ab9fc2
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344191"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>设置共存和升级设置

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

将 Skype for Business 用户升级为使用团队时, 有多个选项可帮助你为你的用户设置无缝流程。 你可以选择同时为组织中的所有用户创建共存和升级设置, 也可以为组织中的单个或一组用户更改设置。 请注意, 旧版本的 Skype for Business 客户端可能无法接受这些设置。 有关 Skype for business 客户端版本的详细信息, 请转到[skype for business 下载和更新页面](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)。 

通过阅读[了解 Microsoft 团队和 skype for business 共存以及](teams-and-skypeforbusiness-coexistence-and-interoperability.md)[与 skype for](coexistence-chat-calls-presence.md)business 的互操作性或共存, 你可以更好地了解可供你使用的模式类型。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>为组织中的所有用户设置升级选项

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**组织范围的设置** > **团队升级**"。 

2. 在 "**团队升级**" 页面上, 进行以下更改 (如果它们将适合你)。
    - 设置**共存**模式。
        - **岛**-如果你希望用户能够同时使用 Skype for Business 和团队, 请使用此设置。
        - **仅限 Skype for** business-如果你希望你的用户仅使用 Skype for business, 请使用此设置。
        - **仅限团队**(在预览中对于某些组织)-如果希望用户仅使用团队, 请使用此设置。 请注意, 即使采用此设置, 用户仍然可以加入 Skype for Business 中托管的会议。
    - 设置**可供团队升级的 Skype for business 用户的通知**。 如果启用此操作, 它将通知 Skype for Business 用户即将升级到团队应用。
    - **为用户设置用于加入 Skype For business 会议的首选应用**。 此设置确定哪种应用用于加入 Skype for Business 会议, 并且无论共存模式的价值如何都有效。
      - **Skype 会议应用**
      - **具有有限功能的 Skype for business**
    - 设置是否**在 Skype for business 用户的后台下载团队应用**。  此设置将为运行 Windows 版 Skype for Business 的用户自动下载 "团队" 应用。 仅当用户的共存模式是 "仅限团队" 或 "在 Skype for Business 中启用了待升级通知" 时, 才会接受此功能。
3. 进行更改后, 单击 "**保存**"。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>为组织中的单个用户设置升级选项

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**用户**", 然后从列表中选择用户。 
2. 在用户的 "**帐户**" 选项卡上的 "**团队升级**" 下, 单击 "**编辑**"。
3. 你可以设置**共存模式**。 从以下选项中进行选择:
     - **使用组织范围的设置**-如果希望用户使用**组织范围**设置中的设置, 请使用此设置。 
     - **群岛**-如果您希望用户能够使用 Skype for Business 和团队, 请使用此设置。 
     - **仅限 Skype** for business-如果希望用户使用 Skype for business, 请使用此设置。 
     - **仅限团队**-如果你希望用户仅使用团队, 请使用此设置。 用户仍将能够加入 Skype for Business 会议。
4. 如果你选择除 "**使用组织范围外的设置**" 之外的任何**共存模式**, 你可以选择在用户的 Skype for business 应用中启用通知, 即将推出升级到团队的应用。 你可以通过打开 "**通知 Skype for business 用户**" 选项为用户启用此通知。
5. 进行更改后, 单击 "**保存**"。

### <a name="related-topics"></a>相关主题
[规划旅程](upgrade-plan-journey.md)

[了解 Skype for business 和团队的共存和升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)
