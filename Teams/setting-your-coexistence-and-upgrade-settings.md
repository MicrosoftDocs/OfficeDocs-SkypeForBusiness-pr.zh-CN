---
title: 设置共存和升级设置
author: dstrome
ms.author: dstrome
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
ms.openlocfilehash: e7559b5376f6b386132e7814b88b6fcce3f5b378
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282719"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>设置共存和升级设置


升级用户Skype for Business以使用Teams时，可以使用多个选项来帮助用户实现无缝过程。 可以选择一次为组织中所有用户进行共存和升级设置，也可以对组织中单个或一组用户进行设置更改。 请注意，较旧版本的 Skype for Business客户端可能不会遵守这些设置。 有关客户端版本Skype for Business，请转到"Skype for Business[和更新"页](/skypeforbusiness/software-updates)。 

可以通过阅读了解 Microsoft Teams 和 Microsoft Teams 共存Skype for Business[互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或共存，更好地了解可用的[Skype for Business。](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>为组织中所有用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在 [Microsoft Teams管理中心的](https://admin.teams.microsoft.com/)左侧导航栏中，转到"**组织范围的** 设置"Teams  >  **升级"**。 

2. 在升级页 **Teams，** 根据需要修改以下选项。
    - 设置 **共存** 模式。
        - **群岛**- 如果希望用户能够同时使用Skype for Business和Teams设置。
        - **Skype for Business** - 如果希望用户仅使用 Skype for Business，请使用Skype for Business。
        - **Skype for Business Teams** 协作 - 如果希望用户使用 Skype for Business，以及将 Teams 用于组协作 (频道，) 。
        - **Skype for Business** Teams 协作和会议 - 如果希望用户使用 Skype for Business，除了使用 Teams (进行组协作，) 和 Teams 会议，请使用此设置。
        - **Teams -** 如果希望用户仅使用 Teams，请使用Teams。 请注意，即使使用此设置，用户仍然可以加入在 Skype for Business 中托管的会议。
        
    - 将 **"Skype for Business通知Teams可用于升级的用户**。 如果启用此功能，它会告知Skype for Business用户他们即将升级到 Teams 应用。
    - 设置用户 **加入会议的首选Skype for Business应用**。 此设置确定哪个应用用于Skype for Business会议，并且无论共存模式的值如何，都受到遵守。
      - **Skype会议应用**
      - **Skype for Business功能受限的**
    - 设置是否 **在后台为Teams用户下载 Skype for Business 应用**。  此设置以无提示方式为Teams运行 Skype for Business 的用户Windows。 只有在用户共存模式为"仅启用"Teams或"正在升级"通知已启用时，才Skype for Business。
3. 进行更改 **后** ，单击"保存"。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>为组织中单个用户设置升级选项

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **"用户"，** 然后从列表中选择用户。 
2. 在用户的 **"帐户**"选项卡上的 **"Teams"下**，单击"**编辑"。**
3. 可以设置 **共存模式**。 从以下选项中进行选择：
     - **使用组织范围的设置** - 如果希望用户使用组织范围的设置， **请使用** 此设置。 
     - **群岛**- 如果希望用户能够同时使用 Skype for Business 和 Teams。 
     - **Skype for Business -** 如果希望用户使用此设置，请使用Skype for Business。
     - **Skype for Business Teams** 协作 - 如果希望用户使用 Skype for Business，以及将 Teams 用于组协作 (频道，) 。
      - **Skype for Business** Teams 协作和会议 - 如果希望用户使用 Skype for Business，则除了将 Teams 用于组协作 (频道) 会议Teams请使用此设置。
     - **Teams** - 如果希望用户仅使用 Teams，请使用Teams。 用户仍可加入Skype for Business会议。
4. 如果选择"使用 **组织** 范围的设置"外的任何共存模式，可以选择在即将升级到 Teams 的用户的 Skype for Business 应用中启用通知。 可以通过打开"通知用户"选项为用户 **Skype for Business通知**。
5. 进行更改 **后** ，单击"保存"。

### <a name="related-topics"></a>相关主题
[规划旅程](upgrade-plan-journey.md)

[了解Skype for Business和Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)