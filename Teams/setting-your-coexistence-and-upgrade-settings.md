---
title: 设置您的共存和升级设置
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文将帮助您选择的共存模式和设置其他共存。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28d5cd4a967245f1df18530d58ed1c2679e910e3
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531859"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>设置您的共存和升级设置

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

升级业务用户来使用团队您 Skype 时，您具有多个选项可帮助您让您的用户的无缝过程。 您可以选择使共存和升级的同时，组织中的用户的所有设置，或您可以为一个或一组用户设置更改您的组织中。 请注意，旧版本的 Skype 业务客户端无法服从这些设置。 业务客户端版本的 Skype 的详细信息，请转到[for Business 的 Skype 下载和更新页面](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)。 

您可以获得更好地了解可供您通过阅读[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)模式的类型。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>设置为在组织中的所有用户的的升级选项

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队业务管理中心的 Skype**

1. 在左侧导航窗格中，转到**组织范围的设置** > **团队升级**。 

2. 在**工作组升级**页的顶部，进行以下更改，如果他们将为您的工作。
    - 将**共存**模式设置。
        - **群岛**-使用此设置，如果您希望用户能够同时使用这两个 Skype 业务和团队。
        - **Skype for Business 仅**-使用此设置，如果您希望仅对用户 for Business 使用 Skype。
        - **仅团队**（在某些组织 preview)-使用此设置，如果您希望用户使用仅团队。 请注意，即使使用此设置，用户仍可以加入 Skype for Business 中托管的会议。
    - 设置**通知的业务用户可用于升级团队的 Skype**。 如果您关闭此功能，它将告知业务用户的 Skype 他们会很快将升级到团队应用程序。
    - 设置**首选应用程序的用户可以加入 Skype 业务会议**。 此设置确定哪个应用程序用于业务会议加入 Skype，采用无论共存模式的值。
      - **Skype 会议应用程序**
      - **Skype for Business 使用有限的功能**
    - 设置为**下载适用于业务用户的 Skype 的背景中的团队应用程序**。  此设置以无提示方式下载 Windows 上运行 for Business 的 Skype 用户团队相关应用程序。 它被有效只有当用户的共存模式仅为团队或 Skype for Business 中启用的挂起升级通知。
3. 进行更改后，请单击**保存**。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>设置您的组织中的单个用户的升级选项

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队业务管理中心的 Skype**

1. 在左侧导航窗格中，转到**用户**，，然后从列表中选择用户。 
2. 在用户，在**升级团队**、 下的**帐户**选项卡上单击**编辑**。
3. 您可以设置**共存模式**。 选择以下选项：
     - **使用组织范围的设置**-使用此设置，如果您希望用户使用**组织范围**的设置中的设置。 
     - **群岛**-使用此设置，如果您希望用户能够使用这两个 Skype 业务和团队。 
     - **Skype for Business 仅**-使用此设置，如果您希望用户 for Business 使用 Skype。 
     - 仅团队**团队仅**-使用此设置，如果您希望用户使用。 用户仍可以加入 Skype 业务会议。
4. 如果您选择任何**共存模式**以外**使用组织范围的设置**，必须启用中用户的 Skype 的通知的业务应用程序升级到团队即将提供的选项。 您可以通过打开**Notify 业务用户 Skype**选项启用此通知用户。
5. 进行更改后，请单击**保存**。

### <a name="related-topics"></a>相关主题
[规划迁移](upgrade-plan-journey.md)

[了解共存和升级的 Skype 旅程，业务和团队](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[使用团队一起 Skype for Business 的组织的迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)
