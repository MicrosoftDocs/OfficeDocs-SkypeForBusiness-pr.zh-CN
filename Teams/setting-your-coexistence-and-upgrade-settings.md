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
description: 了解如何同时为组织中的所有用户或组织中的单个或一组用户设置共存和升级设置。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474c5fc55476e664ba03b9dd82608d8c244b7982
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839183"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>设置共存和升级设置


将Skype for Business用户升级为使用Teams时，有多个选项可帮助用户实现无缝流程。 可以选择同时为组织中的所有用户创建共存和升级设置，也可以对组织中的单个或一组用户进行设置更改。 请注意，Skype for Business客户端的较旧版本可能不符合这些设置。 有关Skype for Business客户端版本的详细信息，请转到[Skype for Business下载和更新页面](/skypeforbusiness/software-updates)。 

可以通过阅读“[了解Microsoft Teams并Skype for Business共存、互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或[与Skype for Business共存](coexistence-chat-calls-presence.md)”来更好地了解可用的模式。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>为组织中的所有用户设置升级选项

 **使用 Microsoft Teams 管理中心**

1. 在 [Microsoft Teams管理中心](https://admin.teams.microsoft.com/)左侧导航栏中，转到 **Teams** >  **Teams升级设置**。 

2. 在 **Teams升级** 页的顶部，根据需要修改以下选项。

    - 设置 **共存** 模式。
        - **Islands** - 如果希望用户能够同时使用Skype for Business和Teams，请使用此设置。
        - **仅Skype for Business** - 如果希望用户仅使用Skype for Business，请使用此设置。
        - **Skype for Business Teams协作** - 如果希望用户使用Skype for Business，以及使用Teams进行组协作 (频道) ，请使用此设置。
        - **Skype for Business Teams协作和会议** - 如果希望用户使用Skype for Business，以及使用Teams进行组协作 (频道) 和Teams会议，请使用此设置。
        - **仅Teams** - 如果希望用户仅使用Teams，请使用此设置。 请注意，即使使用此设置，用户仍然可以加入托管在Skype for Business中的会议。

          > [!IMPORTANT]
          > 只有在完成以下两个步骤后，才能将 TeamsOnly 模式分配给整个租户：
          >  - 所有本地用户已移动到Teams仅使用本地工具集Skype for Business Server中的Move-CsUser。
          >  - 你已将任何Skype for Business DNS 记录更新为指向Microsoft 365。 
          >
          > 有关更多详细信息，请参阅[禁用混合配置以完成迁移到仅Teams](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。
        
    - 设置 **通知Skype for Business用户Teams可供升级**。 如果启用此功能，它会告诉Skype for Business用户他们将很快升级到Teams应用。

    - 设置 **用户加入Skype for Business会议的首选应用**。 此设置确定用于加入Skype for Business会议的应用，无论共存模式的价值如何，都会受到尊重。
      - **Skype会议应用**
      - **具有有限功能的Skype for Business**

    - 设置是否在 **后台为Skype for Business用户下载Teams应用**。 此设置以无提示方式下载Teams应用，供在Windows上运行Skype for Business的用户使用。 仅当仅Teams用户的共存模式，或者在Skype for Business中启用了挂起升级通知时，才会获得此功能。

3. 进行更改后单击 **“保存** ”。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>为组织中的单个用户设置升级选项

 **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **UsersManage** >  用户，然后从列表中选择用户。 
2. 在用户的 **“帐户”** 选项卡上，在 **Teams升级** 下，单击 **“编辑**”。
3. 可以设置 **共存模式**。 除Teams之外的模式只能应用于本地Skype for Business Server的用户，相反，只有云中托管的用户才能使用 TeamsOnly 模式。  从以下选项中选择：
     - **使用组织范围的设置** - 如果希望用户使用 **组织范围** 设置中的设置，请使用此设置。 
     - **Islands** - 如果希望用户能够同时使用Skype for Business和Teams，请使用此设置。 
     - **仅Skype for Business** - 如果希望用户使用Skype for Business，请使用此设置。
     - **Skype for Business Teams协作** - 如果希望用户使用Skype for Business，以及使用Teams进行组协作 (通道) ，请使用此设置。
      - **Skype for Business Teams协作和会议** - 如果希望用户使用Skype for Business，以及使用Teams进行组协作 (频道) 和Teams会议，请使用此设置。
     - **仅Teams** - 如果希望用户仅使用Teams，请使用此设置。 用户仍可以加入Skype for Business会议。
4. 如果选择除 **使用组织范围设置** 以外的任何 **共存模式**，则可以选择在即将升级到Teams的用户Skype for Business应用中启用通知。 可以通过打开“**通知Skype for Business用户**”选项为用户启用此通知。
5. 进行更改后单击 **“保存** ”。

### <a name="related-topics"></a>相关主题
[规划旅程](upgrade-plan-journey.md)

[了解Skype for Business和Teams的共存和升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[解除本地Skype for Business环境的授权](/skypeforbusiness/hybrid/decommission-on-prem-overview)
