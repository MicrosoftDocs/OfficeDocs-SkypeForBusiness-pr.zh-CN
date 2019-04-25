---
title: 在 Microsoft Teams 中管理自定义应用策略和设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理自定义应用程序策略和设置以控制哪些人在组织中可以上载的 Microsoft 团队中的自定义应用程序。
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224611"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理自定义应用策略和设置

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

作为一名管理员，您可以使用自定义应用程序策略和设置以控制哪些人在您的组织可以将自定义应用程序上载到 Microsoft 团队。 管理员决定哪些用户可以上载自定义应用程序，并 admins 和团队所有者可以确定组织中的特定小组是否允许向它们添加自定义应用程序。  

## <a name="overview-of-custom-apps"></a>自定义应用程序的概述

用户可以通过直接向团队或个人上下文中上载应用程序包 （.zip 文件） 中的，向工作组添加自定义应用程序。 这一点不同于通过团队应用程序商店添加应用程序的方式。 添加自定义应用程序上载应用程序包，也称为 sideloading，允许您测试应用程序，如它正在开发的已准备好广泛之前。 它还允许您构建仅供内部使用应用程序，并将其与您的团队共享不提交给团队应用程序存储区中的团队应用程序目录。

![上载自定义应用程序](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>自定义应用程序策略和设置

三个组件确定用户是否可以上载自定义的应用程序到团队，这样就可以精细控制可以添加到团队的自定义应用程序，并可以将其团队需要自定义应用程序添加到：

- [用户自定义应用程序策略](#user-custom-app-policy)
- [团队自定义应用程序设置](#team-custom-app-setting)
- [组织范围内自定义应用程序设置](#org-wide-custom-app-setting)

这些设置不会影响阻止第三方应用程序的能力。  

### <a name="user-custom-app-policy"></a>用户自定义应用程序策略

作为[应用程序设置策略](teams-app-setup-policies.md)的一部分，管理员可以使用策略设置，**允许上载自定义应用程序**，来控制用户可以将自定义应用程序上载到团队是否。
 
如果此设置处于关闭状态：

- 用户不能将自定义应用程序上载到任何工作组在您的组织或个人上下文中。
- 用户可以使用自定义应用程序，具体取决于组织范围内自定义应用程序设置进行交互。

如果启用此设置：

- 用户可以上载自定义应用程序，到允许其团队和它们所所有者，具体取决于组织范围内自定义应用程序设置的团队。
- 用户可以将自定义应用程序上载到个人上下文。 
- 用户可以使用自定义应用程序，具体取决于组织范围内自定义应用程序设置进行交互。

您可以编辑中的全局应用程序设置策略的设置，以包含所需的应用程序。 如果您想要自定义为不同的组织中用户组的团队，创建并分配一个或多个自定义应用程序设置策略。

#### <a name="set-a-user-custom-app-policy"></a>设置用户自定义应用程序策略

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **设置策略**。
2. 选择**新策略**。
3. 打开或关闭**允许上载自定义应用程序**。
4. 选择您要为策略的任何其他设置。
5. 单击“**保存**”。

### <a name="team-custom-app-setting"></a>团队自定义应用程序设置

管理员和团队所有者可以控制团队是否允许向其添加自定义应用程序。 此设置，**允许成员，才能上载自定义应用程序**，以及用户的自定义应用程序策略确定谁可以将自定义应用程序添加到特定的团队。
 
如果此设置处于关闭状态：

- 团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许。
- 团队成员不团队所有者无法将自定义应用程序添加到团队。

如果启用此设置：

- 团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许为其。
- 团队成员不团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许为其。

#### <a name="configure-the-team-custom-app-setting"></a>配置团队自定义应用程序设置

1. 在工作组，转至组中，单击**多个选项 ˙˙˙** > **管理团队**。
2. 单击**设置**，然后展开**成员权限**。
3. 选中或清除**允许成员，才能上载自定义应用程序**复选框。

    ![团队自定义应用程序设置](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>组织范围内自定义应用程序设置

组织范围内自定义应用程序设置，**与自定义应用程序允许进行交互**，适用于您的组织中的所有人，并控制是否可以上载或自定义应用程序与之交互。 此设置将覆盖用户和团队自定义应用程序策略和设置。 它具有适用用作安全事件期间切换开关主控形状。

#### <a name="configure-the-org-wide-custom-app-setting"></a>配置组织范围内自定义应用程序设置

1. 在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **权限策略**。
2. 单击**组织范围的应用程序设置**。
3. 在**自定义应用程序**，下打开或关闭**与自定义应用程序允许进行交互**。

    ![组织范围内自定义应用程序设置](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>如何自定义应用程序策略和设置协同工作

此表总结了自定义应用程序策略和设置、 如何协同工作的以及其对控制您的组织中的谁可以将自定义应用程序上载到团队的组合的影响。

例如，假设您想要允许仅将自定义应用程序上载到特定的团队团队所有者。 您可设置以下各项：
- 打开 Microsoft 团队管理中心中**允许交互自定义应用程序**设置。
- 关闭您想要限制访问每个团队**允许成员，才能上载自定义应用程序**。
- 创建和自定义应用程序安装程序在分配策略的 Microsoft 团队管理中心使用开启，**用户可以上载自定义应用程序**设置并将其分配给团队所有者。

|组织范围内自定义应用程序设置 |团队自定义应用程序设置 |用户自定义应用程序策略 |效果  |
|---------|---------|---------|---------|
| 关    | 关    | 关     |为您的组织，与所有自定义应用程序交互而被阻止。 自定义应用程序无法上载的任何人。 您可以使用 PowerShell 删除自定义应用程序。   |
| 关     | 关     | 开        |为您的组织，与所有自定义应用程序交互而被阻止。 自定义应用程序无法上载的任何人。 您可以使用 PowerShell 删除自定义应用程序。         |
| 关    | 开        | 关        |为您的组织，与所有自定义应用程序交互而被阻止。 自定义应用程序无法上载的任何人。 您可以使用 Windows PowerShell 删除自定义应用程序。         |
| 关    | 开      | 开       |为您的组织，与所有自定义应用程序交互而被阻止。 自定义应用程序无法上载的任何人。 您可以使用 PowerShell 删除自定义应用程序。         |
| 开    | 关       | 关         |  用户无法上载自定义应用程序。      |
| 开     | 关       | 开         | 如果用户是团队所有者，它们可以将自定义应用程序上载到团队。 如果用户不是团队所有者，他们不能将自定义应用程序上载到团队。 用户可以上载个人上下文中的自定义应用程序。     |
| 开     | 开     | 关         | 用户无法上载自定义应用程序。       |
| 开    | 开        | 开        | 用户可以将自定义应用程序上载到团队，而不管用户是否团队所有者。 用户可以上载个人上下文中的自定义应用程序。       |

 ## <a name="related-topics"></a>相关主题
- [Teams 中适用于应用的管理设置](admin-settings.md)
- [在 Microsoft Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [在 Microsoft Teams 中管理应用权限策略](teams-app-permission-policies.md)
