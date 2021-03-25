---
title: 设置共存和升级设置
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 了解如何同时为组织中所有用户或组织中单个或一组用户设置共存和升级设置。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52e035f3940237309a1a8bab0211ccaad243b004
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117070"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>设置共存和升级设置


当你将 Skype for Business 用户升级为使用 Teams 时，你有几种选项可以帮助你为用户实现无缝过程。 可以选择一次为组织中所有用户进行共存和升级设置，也可以对组织中单个或一组用户进行设置更改。 请注意，较旧版本的 Skype for Business 客户端可能不会遵守这些设置。 有关 Skype for Business 客户端版本的信息，请转到 [Skype for Business 下载和更新页面](/skypeforbusiness/software-updates)。 

通过阅读了解 Microsoft Teams 和 [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 共存和互操作性或与 Skype for Business 共存，你可以更好地了解可用的 [模式](coexistence-chat-calls-presence.md)。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>为组织中所有用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在 [Microsoft Teams 管理中心的](https://admin.teams.microsoft.com/)左侧导航栏中，转到 **"组织范围的** 设置""Teams  >  **升级"。** 

2. 在 Teams 升级 **页的顶部** ，根据需要修改以下选项。
    - 设置 **共存** 模式。
        - **群岛** - 如果希望用户能够同时使用 Skype for Business 和 Teams，请使用此设置。
        - **仅 Skype for Business** - 如果希望用户仅使用 Skype for Business，请使用此设置。
        - **将 Skype for Business** 与 Teams 协作 - 如果希望用户使用 Skype for Business，以及使用 Teams 进行群组协作和频道协作， (此设置) 。
        - **Skype for Business 与 Teams** 协作和会议 - 如果希望用户使用 Skype for Business 以及使用 Teams 进行组协作， (频道和 Teams 会议) 此设置。
        - **仅 Teams** - 如果希望用户仅使用 Teams，请使用此设置。 请注意，即使使用此设置，用户仍然可以加入 Skype for Business 中托管的会议。
        
    - 设置 **"通知 Skype for Business 用户 Teams 可供升级"。** 如果启用此功能，它将告诉 Skype for Business 用户他们即将升级到 Teams 应用。
    - 为用户 **设置"首选应用"以加入 Skype for Business 会议**。 此设置确定用于加入 Skype for Business 会议的应用，并且无论共存模式的价值如何，都受遵守。
      - **Skype 会议应用**
      - **功能受限的 Skype for Business**
    - 设置是否 **在后台为 Skype for Business 用户下载 Teams 应用**。  此设置以无提示方式为在 Windows 上运行 Skype for Business 的用户下载 Teams 应用。 只有当用户的共存模式为"仅 Teams"或在 Skype for Business 中启用了等待升级通知时，才遵守此规则。
3. 进行更改 **后** ，单击"保存"。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>为组织中单个用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **"用户"，** 然后从列表中选择用户。 
2. 在用户的 **"帐户**"选项卡上的 **"Teams 升级"下**，单击"**编辑"。**
3. 可以设置 **共存模式**。 从以下选项中进行选择：
     - **使用组织范围的设置** - 如果希望用户使用组织范围的设置， **请使用** 此设置。 
     - **群岛** - 如果希望用户能够同时使用 Skype for Business 和 Teams，请使用此设置。 
     - **仅 Skype for Business** - 如果希望用户使用 Skype for Business，请使用此设置。
     - **将 Skype for Business** 与 Teams 协作 - 如果希望用户使用 Skype for Business，以及使用 (Teams 进行组协作和频道协作，) 。
      - **Skype for Business 与 Teams** 协作和会议 - 如果希望用户使用 Skype for Business 以及使用 Teams 进行组协作， (频道和 Teams 会议) 此设置。
     - **仅 Teams** - 如果希望用户仅使用 Teams，请使用此设置。 用户仍可加入 Skype for Business 会议。
4. 如果选择"使用 **组织** 范围的设置"外的任何共存模式，可以选择在即将升级到 Teams 的用户 Skype for Business 应用中启用通知。 您可以通过打开"通知 Skype for Business 用户"选项 **为用户启用此** 通知。
5. 进行更改 **后** ，单击"保存"。

### <a name="related-topics"></a>相关主题
[规划旅程](upgrade-plan-journey.md)

[了解 Skype for Business 和 Teams 的共存和升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)