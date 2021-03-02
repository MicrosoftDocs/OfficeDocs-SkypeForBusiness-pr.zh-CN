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
description: 了解如何为组织中所有用户一次设置共存和升级设置，或者为贵组织的单个或一组用户设置共存和升级设置。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2dbeb4d93273aab848f1b4436b46e6b22e08e53
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397567"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>设置共存和升级设置


当你将 Skype for Business 用户升级为使用 Teams 时，你有几种选项可以帮助你为用户实现无缝过程。 可以选择一次为组织中所有用户进行共存和升级设置，也可以对组织中单个或一组用户进行设置更改。 请注意，较旧版本的 Skype for Business 客户端可能不会遵守这些设置。 有关 Skype for Business 客户端版本的信息，请转到 [Skype for Business 下载和更新页面](https://docs.microsoft.com/skypeforbusiness/software-updates)。 

通过阅读"了解 Microsoft Teams 和 [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 共存和互操作性"或"与 Skype for [Business](coexistence-chat-calls-presence.md)共存"，你可以更好地了解可用的模式。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>为组织中所有用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在 [Microsoft Teams 管理中心的](https://admin.teams.microsoft.com/)左侧导航栏中，转到 **组织范围的设置**  >  **Teams 升级**。 

2. 在 Teams 升级 **页面** 顶部，根据需要修改以下选项。
    - 设置 **共存** 模式。
        - **群岛** - 如果希望用户能够同时使用 Skype for Business 和 Teams，请使用此设置。
        - **仅 Skype for Business** - 如果希望用户仅使用 Skype for Business，请使用此设置。
        - **将 Skype for Business** 与 Teams 协作 - 如果希望用户除了使用 Teams 进行群组协作外，还希望使用 Skype for Business (使用) 。
        - **Skype for Business 与 Teams** 协作和会议 - 如果你希望用户除了使用 Teams 进行组协作外，还希望使用 Teams 进行群组协作和 teams 会议， (使用此设置) Teams 会议。
        - **仅 Teams** - 如果希望用户仅使用 Teams，请使用此设置。 请注意，即使使用此设置，用户仍然可以加入 Skype for Business 中托管的会议。
        
    - 设置 **通知 Skype for Business 用户 Teams 可供升级**。 如果启用此功能，它将告诉 Skype for Business 用户，他们将很快升级到 Teams 应用。
    - 设置 **用户加入 Skype for Business 会议的首选应用**。 此设置确定用于加入 Skype for Business 会议的应用，并且无论共存模式的值如何，都受支持。
      - **Skype 会议应用**
      - **功能受限的 Skype for Business**
    - 设置是否 **在后台为 Skype for Business 用户** 下载 Teams 应用。  此设置以无提示方式为在 Windows 上运行 Skype for Business 的用户下载 Teams 应用。 仅在用户共存模式为 Teams 或在 Skype for Business 中启用了等待升级通知时，才遵守此规则。
3. 进行更改 **后** 单击"保存"。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>为组织中单个用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **"用户**"，然后从列表中选择该用户。 
2. 在用户的 **"帐户**"选项卡上的 **Teams** 升级下，单击"编辑 **"。**
3. 可以设置 **共存模式**。 从以下选项中进行选择：
     - **使用组织范围的设置** - 如果希望用户使用组织范围的设置， **请使用** 此设置。 
     - **群岛** - 如果希望用户能够同时使用 Skype for Business 和 Teams，请使用此设置。 
     - **仅 Skype for Business** - 如果希望用户使用 Skype for Business，请使用此设置。
     - **将 Skype for Business** 与 Teams 协作 - 如果希望用户除了使用 Teams 进行群组协作外，还希望使用 Skype for Business (使用) 。
      - **Skype for Business 与 Teams** 协作和会议 - 如果希望用户除了使用 Teams 进行组协作外，还希望使用 Teams 进行群组协作和 teams 会议， (使用此设置) Teams 会议。
     - **仅 Teams** - 如果希望用户仅使用 Teams，请使用此设置。 用户仍可加入 Skype for Business 会议。
4. 如果选择除使用组织范围的设置外的任何共存模式，可以选择在即将升级到 Teams 的用户 Skype for Business 应用中启用通知。 可以通过打开"通知 Skype for Business 用户"选项 **为用户启用此** 通知。
5. 进行更改 **后** 单击"保存"。

### <a name="related-topics"></a>相关主题
[规划旅程](upgrade-plan-journey.md)

[了解 Skype for Business 和 Teams 的共存和升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)
