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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何创建、编辑和管理应用设置策略，以固定应用、安装应用以及允许用户上传自定义应用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: c741bb8a1b6ab7e27ec064dc0f22226f69bc6e10
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655888"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用设置策略

管理员可以使用应用设置策略来安装和固定应用，并允许用户上传自定义应用。 固定有助于提升组织中相关应用的采用。

* **固定应用：** 应用设置策略允许选择要固定的应用，设置应用在 Teams 应用栏或撰写消息区域中为用户显示的顺序。 管理员还可以控制最终用户是否可以固定自己的应用。 查看 [固定应用](#pin-apps)。
* **安装应用：** 应用设置策略允许在用户启动 Teams 和会议期间代表用户安装允许的应用。 有关详细信息，请参阅 [安装应用](#install-apps)。
* **上传自定义应用：** 应用设置策略允许用户将自定义应用上传到 Teams。 有关详细信息，请参阅 [上传自定义应用](teams-custom-app-policies-and-settings.md)。

默认情况下，Microsoft Teams 管理中心提供以下内置应用设置策略：

* **全局（组织范围内的默认）**：此默认策略适用于组织中的所有用户，除非分配了其他策略。 编辑全局策略以固定对用户最重要的应用。

* **一线员工**：此策略适用于一线员工。 无法自定义策略。 可以将其分配给组织中的一线员工。

## <a name="pin-apps"></a>固定应用

固定应用可突出显示组织中用户最需要的应用。 固定适用于 Teams 中的所有类型的应用（核心应用、Microsoft 提供的应用、第三方应用以及组织内开发的自定义）。 如果用户允许应用，则通过应用设置策略固定应用也会安装它。 使用应用设置策略可执行以下任务：

* 为最终用户自定义 Microsoft Teams ，以突出显示最重要的应用。 选择要固定的应用以及应用的显示顺序。
* 控制用户是否可以固定应用。

应用固定在 Teams 桌面客户端左侧和 Teams 移动客户端底部的应用栏上。

|Teams 桌面客户端  |Teams 移动客户端 |
|---------|---------|
|![显示 Teams 桌面客户端中的应用栏的屏幕截图。](media/app-setup-policies-desktop-app-bar.png).  |   ![显示 Teams 移动客户端中的应用栏的屏幕截图。](media/mobile-app-ui.png)      |

消息传递扩展位于撰写消息区域的底部。

要使用应用设置策略固定应用，请执行以下步骤：

1. 登录 Teams 管理中心并访问“**Teams 应用**” > **“[设置策略](https://admin.teams.microsoft.com/policies/app-setup)”**。

1. 选择“**添加**”。

1. 输入策略的名称和说明。

1. 启用“**用户固定**”。

   > [!NOTE]
   > 在 Microsoft 365 政府社区云 (GCC) 环境（GCC、GCC High 和 DoD）中的 Teams 管理中心中提供“**用户固定**”设置，但没有效果。

1. 在“**固定应用**”下，选择“**添加应用**”。

1. 在“**添加固定应用**”窗格中，搜索要添加的应用，然后选择“**添加**”。 还可以按应用权限策略筛选应用。

1. 选择“**添加**”。

1. 在“**应用栏**”或“**消息传递扩展**”下，按希望应用在 Teams 中出现的顺序排列应用。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="“设置”策略中固定的应用和固定的消息传递扩展的屏幕截图。":::

1. 选择“**保存**”。

> [!NOTE]
> 在 Teams 教育版中，默认情况下，“作业”应用固定在全局策略中，即使未看到其在全局策略中列出。

> [!NOTE]
> 对于组织中的一线员工，建议使用定制的一线应用体验。 此功能为拥有 [F 许可证](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)的用户在 Teams 中固定最相关的应用。 若要了解详细信息，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

## <a name="install-apps"></a>安装应用

使用应用设置策略，管理员可以完成以下任务：

* 在其个人 Teams 环境中为最终用户安装应用。
* 为最终用户将应用安装为 [消息传递扩展](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)。

如果 [应用权限](teams-app-permission-policies.md) 策略允许应用并且 Teams 管理员允许应用，则最终用户可以自行安装应用。相反，如果为用户或组织阻止应用，则最终用户可以 [请求管理员批准](user-requests-approve-apps.md)。

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
* 通过应用设置策略固定的应用可以由用户取消固定（如果设置策略中允许用户固定）。
* 在 Teams 教育版中，默认情况下，“作业”应用固定在全局策略中，即使未看到其在全局策略中列出。
* 可以添加到策略中的已固定应用的最大数量没有限制。 但是，必须至少有两个应用固定到 Teams 移动客户端（iOS 和 Android）。 如果策略具有的应用少于两个，移动客户端将不会反映策略设置，转而继续使用现有配置。
* 编辑或分配策略后，更改可能需要几个小时才能生效。

## <a name="faqs"></a>常见问题解答

### <a name="working-with-app-setup-policies"></a>使用应用设置策略

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么在“添加固定的应用”窗格中找不到应用

并非所有应用都可以通过应用设置策略固定到 Teams。 某些应用可能不支持此功能。 要查找可以固定的应用，请在“**添加固定的应用**”窗格中搜索应用。 具有个人作用域的选项卡（静态选项卡）和机器人可以固定到 Teams 桌面客户端，可在“**添加固定的应用**”窗格中找到这些应用。

请记住，Teams 应用商店列出了所有 Teams 应用。 “**添加固定的应用**”窗格仅包括可以通过策略固定到 Teams 的应用。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是 Teams 教育版管理员。我需要了解 Teams 教育中的应用程序设置策略的什么内容

“通话”应用在 Teams 教育版中不可用。 在应用设置策略中创建新的自定义策略时，呼叫应用会显示在应用列表中。 然而，应用并没有固定到 Teams 客户端，Teams 教育版用户不会在 Teams 中看到“通话”应用程序。

### <a name="user-experience"></a>用户体验

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>用户如何才能在 Teams 中查看所有固定的应用

要查看为用户固定的所有应用，用户可能必须根据已安装的应用数及其 Teams 客户端窗口的大小执行以下操作。

|Teams 桌面客户端 |Teams 移动客户端 |
|---------|---------|
|在 Teams 一侧的应用栏中，选择“**... 更多应用**”。| 在 Teams 底部附近的应用栏中，向上轻扫。|
|![显示 Teams 桌面客户端中更多固定应用的屏幕截图。](media/app-setup-policies-desktop-more-apps.png)   |![显示 Teams 移动客户端中更多固定应用的屏幕截图](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>我需要了解哪些 Teams 移动体验内容

Teams 移动客户端（iOS 和 Android）支持带有静态选项卡的个人应用。 已固定到 Teams 桌面客户端的应用将出现在 Teams 移动客户端中。 个人机器人将出现在移动客户端的“聊天”中。

第三方应用（可从 Teams 应用商店下载）需要先获得批准，才能出现在手机上。 如果管理员固定未经 Microsoft 移动版批准的应用，它将显示在 Teams 桌面应用上，但不会显示在移动设备上。 有关详细信息，请参阅“[移动客户端](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients)”。

借助 Teams 移动客户端，用户将看到核心 Teams 应用，例如活动、聊天和 Teams，你可以固定一些 Microsoft 提供的应用。

#### <a name="order-of-apps-pinned-through-a-policy"></a>通过策略固定的应用顺序

如果启用了“**用户固定**”选项，用户可以更改其在 Teams 桌面和移动客户端上固定的应用顺序。 用户无法更改其在 Teams Web 客户端上固定的应用顺序。

#### <a name="does-user-pinning-take-precedence"></a>用户固定是否优先

管理员固定始终优先。 如果启用 **了“用户固定** ”选项，则用户固定的应用将显示在管理员固定的应用下面。 如果关闭 **“用户固定** ”选项，则用户将丢失现有引脚，并且只有管理员固定的应用才能在应用栏中使用。

### <a name="custom-teams-apps"></a>自定义 Teams 应用

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的组织构建了自定义 Teams 应用，并将其发布到 AppSource 或租户应用程序目录，但当应用固定到 Teams 中的应用栏时，应用图标不按预期显示。 如何解决这个问题？

在提交应用之前，请确保遵循徽标指南。 要了解更多信息，请参阅 [卖家面板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-articles"></a>相关文章

* [Teams 中应用的管理设置](admin-settings.md)
* [将策略分配给 Teams 中的最终用户](assign-policies-users-and-groups.md)
