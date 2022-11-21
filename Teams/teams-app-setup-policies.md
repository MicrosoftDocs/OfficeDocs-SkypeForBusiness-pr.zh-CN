---
title: 在 Microsoft Teams 中管理应用设置策略
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何创建、编辑和管理应用设置策略，以固定应用、安装应用以及允许用户上传自定义应用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4c94f0610535fa014b0f759b104dd1aef901e055
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131001"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>使用应用设置策略在 Teams 中固定和自动安装应用

作为管理员，可以使用应用设置策略来安装和固定应用，并控制哪些特定用户可以上传自定义应用。 固定有助于促进采用，并提供对组织中相关应用的快速访问。

* **[固定应用](#pin-apps)：** 应用设置策略允许你选择要固定的应用，设置应用在 Teams 应用栏或撰写消息区域中为用户显示的顺序。 管理员还可以控制最终用户是否可以固定自己的应用。

* **[安装应用](#install-apps)：** 应用设置策略允许用户在启动 Teams 时和会议期间代表用户安装允许的应用。

* **上传自定义应用：** 应用设置策略允许你控制哪些用户可以将自定义应用上传到 Teams。 请参阅 [上传自定义应用](teams-custom-app-policies-and-settings.md) 一文。

默认情况下，Microsoft Teams 管理中心提供以下内置应用设置策略：

* **全局（组织范围内的默认）**：此默认策略适用于组织中的所有用户，除非分配了其他策略。 编辑全局策略以固定对用户最重要的应用。

* **一线员工**：此策略适用于一线员工。 无法自定义策略。 可以将其分配给组织中的一线员工。

## <a name="pin-apps"></a>固定应用

固定应用会在 Teams 客户端的应用栏中显示该应用。 管理员可以固定应用，并且可以允许用户固定。 固定用于突出显示用户最需要的应用，并提升访问的便利性。 固定适用于 [Teams 中的所有类型的应用](deploy-apps-microsoft-teams-landing-page.md) - 核心应用、Microsoft 提供的应用、第三方应用以及组织内开发的自定义应用。

管理员可以通过应用设置策略固定应用。 管理员固定的应用会自动为允许应用的用户安装。 最终用户无法卸载此类应用。 使用应用设置策略可执行以下任务：

* 为最终用户自定义 Teams，以突出显示最重要的应用。 选择要固定的应用以及应用的显示顺序。
* 控制用户是否可以固定应用。

应用固定在 Teams 桌面客户端左侧和 Teams 移动客户端底部的应用栏上。 消息传递扩展位于撰写消息区域的底部。

|Teams 桌面客户端  |Teams 移动客户端 |
|---------|---------|
|![显示 Teams 桌面客户端中的应用栏的屏幕截图。](media/app-setup-policies-desktop-app-bar.png).  |   ![显示 Teams 移动客户端中的应用栏的屏幕截图。](media/mobile-app-ui.png)      |

要使用应用设置策略固定应用，请执行以下步骤：

1. 登录 Teams 管理中心并访问“**Teams 应用**” > **“[设置策略](https://admin.teams.microsoft.com/policies/app-setup)”**。

1. 选择“**添加**”。

1. 输入策略的名称和说明。

1. （可选）打开 **“用户固定** ”以允许用户固定应用并更改固定应用的顺序。

1. 在“**固定应用**”下，选择“**添加应用**”。

1. 在“**添加固定应用**”窗格中，搜索要添加的应用，然后选择“**添加**”。

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="屏幕截图显示如何在应用设置策略中添加固定的应用。" lightbox="media/add-pinned-apps-large.png":::

1. 选择“**添加**”。

1. 在 **“应用栏** ”或 **“消息传递扩展”** 下，按照你希望应用在 Teams 客户端中的显示顺序排列应用。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="安装策略中固定的应用和固定消息传送扩展的屏幕截图。":::

1. 选择“**保存**”。

> [!NOTE]
> 在 Teams 教育版中，默认情况下，“作业”应用固定在全局策略中，即使未看到其在全局策略中列出。

> [!NOTE]
> 对于组织中的一线员工，建议使用定制的一线应用体验。 此功能为拥有 [F 许可证](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline)的用户在 Teams 中固定最相关的应用。 若要了解详细信息，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

## <a name="install-apps"></a>安装应用

使用应用设置策略，管理员可以完成以下任务：

* 在其个人 Teams 环境中为最终用户安装应用。
* 为最终用户将应用安装为 [消息传递扩展](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)。

如果应用 [权限策略](teams-app-permission-policies.md) 允许他们安装应用，并且 Teams 管理员允许该应用，则最终用户可以自行安装应用。如果应用被阻止，最终用户可以 [请求管理员批准](user-requests-approve-apps.md)。

若要使用应用设置策略安装应用，请执行以下步骤：

1. 登录 Teams 管理中心并访问“**Teams 应用**” > **“[设置策略](https://admin.teams.microsoft.com/policies/app-setup)”**。

1. 选择“**添加**”。

1. 提供策略的名称和说明。

1. 在“**已安装的应用**”下，选择“**添加应用**”。

1. 在 **“添加已安装的应用** ”窗格中，搜索要为用户安装的应用。 还可以按应用权限策略筛选应用。

1. 选择“**添加**”。

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="通过应用策略安装应用的屏幕截图。":::

## <a name="manage-app-setup-policies"></a>管理应用设置策略

可在 Microsoft Teams 管理中心中管理应用设置策略。 使用全局（组织范围内的默认）策略或创建并分配自定义策略。 最终用户获得全局策略。 如果创建自定义策略，它将替代全局策略。 全局管理员或 Teams 服务管理员可以管理这些策略。

可以编辑全局策略中的设置，以包括所需的应用。 要为组织中的不同用户组自定义 Teams，请创建并分配一个或多个自定义策略。

:::image type="content" source="media/app-setup-policies-update.png" alt-text="显示应用设置策略页的屏幕截图，其中包含用于管理策略或添加新策略的选项。":::

### <a name="edit-an-app-setup-policy"></a>编辑应用设置策略

可以使用 Microsoft Teams 管理中心来编辑策略，包括已创建的全局（组织范围内的默认）策略和自定义策略。 编辑或分配策略后，更改可能需要几个小时才能生效。

1. 登录 Teams 管理中心并访问“**Teams 应用**” > **“[设置策略](https://admin.teams.microsoft.com/policies/app-setup)”**。

1. 选择要编辑的策略，然后选择“**编辑**”。

1. 进行所需更改。

1. 选择“**保存**”。

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>将应用设置策略中的自定义策略分配给用户和组

要了解如何将策略分配给最终用户和组，请参阅 [如何将策略指派给用户和组](assign-policies-users-and-groups.md)。

## <a name="considerations-and-limitations"></a>注意事项和限制

* 无法使用应用设置策略安装带有可配置选项卡的自定义应用。

* 最终用户无法卸载由管理员安装的应用。

* 如果策略中允许用户固定，则最终用户可以取消固定通过应用设置策略固定的应用。

* 如果启用了用户固定选项，则用户可以在 Teams 桌面和移动客户端上更改其固定应用的顺序。 用户无法更改其在 Teams Web 客户端上固定的应用顺序。

* 管理员固定始终优先。 如果启用了“用户固定”选项，则用户固定的应用将显示在管理员固定的应用下方。 如果关闭“用户固定”选项，则用户将丢失现有固定，并且应用栏中只有管理员固定的应用可用。

* Microsoft 365 政府社区云 (GCC) 环境中的 Teams 管理中心提供了用户固定设置， (GCC、GCC High 和 DoD) ，但不起作用。

* 在 Teams 教育版中，默认情况下，“作业”应用固定在全局策略中，即使未看到其在全局策略中列出。

* 可以添加到策略中的已固定应用的最大数量没有限制。 但是，必须至少有两个应用固定到 Teams 移动客户端（iOS 和 Android）。 如果策略具有的应用少于两个，移动客户端将不会反映策略设置，转而继续使用现有配置。

* 编辑或分配策略后，更改可能需要几个小时才能生效。

* 并非所有应用都可以通过应用设置策略固定到 Teams。 某些应用可能不支持此功能。 要查找可以固定的应用，请在“**添加固定的应用**”窗格中搜索应用。 具有个人作用域的选项卡（静态选项卡）和机器人可以固定到 Teams 桌面客户端，可在“**添加固定的应用**”窗格中找到这些应用。 而 Teams 应用商店会列出所有 Teams 应用。 “**添加固定的应用**”窗格仅包括可以通过策略固定到 Teams 的应用。

* 在Teams 教育版中，“通话”应用不可用。 在应用设置策略中创建新的自定义策略时，“呼叫”应用将显示在应用列表中。 然而，应用并没有固定到 Teams 客户端，Teams 教育版用户不会在 Teams 中看到“通话”应用程序。

## <a name="related-articles"></a>相关文章

* [Teams 中应用的管理设置](admin-settings.md)
* [将策略分配给 Teams 中的最终用户](assign-policies-users-and-groups.md)
