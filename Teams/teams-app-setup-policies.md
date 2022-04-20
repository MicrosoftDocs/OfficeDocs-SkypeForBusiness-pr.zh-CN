---
title: 在 Microsoft Teams 中管理应用设置策略
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何为组织中的用户使用和管理Microsoft Teams中的应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 328f2676ccec6cd1450166d7032877e176d5f1cd
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910818"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用设置策略

作为管理员，可以使用应用设置策略来安装和固定应用，以推广组织中最常用的应用，并确定是否希望用户将自定义应用上传到Teams。

- **固定应用：** 应用设置策略允许你选择要固定的应用，设置它们在Teams应用栏或撰写消息区域中为用户显示的顺序，并控制用户是否可以固定自己的应用。 有关详细信息，请参阅 [Pin 应用](#pin-apps)。
- **安装应用：** 应用设置策略允许你在用户开始Teams和会议期间代表用户安装应用。 有关详细信息，请参阅 [“安装应用](#install-apps)”。
- **Upload自定义应用：** 应用设置策略允许用户将自定义应用上传到Teams。 有关详细信息，请参阅[Upload自定义应用](#upload-custom-apps)。

## <a name="pin-apps"></a>固定应用

> [!NOTE]
> 对于组织中的一线员工，我们建议使用定制的一线应用体验。 此功能为拥有 [F 许可证](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)的用户固定Teams中最相关的应用。 若要了解详细信息，请参阅[为一线员工Teams应用](pin-teams-apps-based-on-license.md)。

固定应用可让你展示组织中用户需要的应用，包括由第三方或组织中的开发人员生成的应用。

使用应用设置策略可以执行以下任务：

- 自定义 Teams 以突出显示对用户最为重要的应用。 选择要固定的应用并设置它们显示的顺序。
- 控制用户是否可以将应用固定到 Teams。

应用固定到应用栏，应用栏是Teams桌面客户端左侧的栏，位于 iOS 和 Android)  (Teams移动客户端底部。

|Teams 桌面客户端  |Teams 移动客户端 |
|---------|---------|
|![Teams桌面客户端。](media/app-setup-policies-desktop-app-bar.png).  |   ![Teams移动客户端](media/mobile-app-ui.png)      |

消息传递扩展插件在撰写消息区域的底部可用。

> [!NOTE]
> 如果已Teams 教育版，请务必知道工作分配应用默认固定在全局策略中，即使当前未在全局策略中列出。

若要创建用于固定应用的应用设置策略，请执行以下步骤：

1. 登录到[Microsoft Teams管理中心](https://admin.teams.microsoft.com)。

1. 在左窗格中，转到 **Teams** **appsSetup** >  策略。

1. 选择“**添加**”。

1. 输入策略的名称和说明。

1. 启用 **用户固定**。

   > [!NOTE]
   > 用户 **固定** 设置在 (GCC、GCC高和 DoD) Microsoft 365 政府社区云 (GCC) 环境中的Teams管理中心中可用，但目前不起作用。

1. 在 **固定应用** 下，选择 **“添加应用**”。

1. 在 **“添加固定应用** ”窗格中，搜索要添加的应用，然后选择 **“添加**”。 还可以按应用权限策略筛选应用。

1. 选择“**添加**”。

1. 在 **“应用栏**”或 **“消息传递”扩展** 名下，按希望应用在Teams中显示的顺序排列应用。

   ![固定应用部分。](media/pin-messaging-extensions.png)

1. 选择“**保存**”。

## <a name="install-apps"></a>安装应用

你可以选择默认情况下为用户在其个人Teams环境中安装的应用、将应用安装为[消息传递扩展](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)，以及指定要在会议中安装的应用。

使用应用设置策略可以执行以下任务：

- 在其个人Teams环境中为用户安装应用
- 为用户安装应用作为消息传递扩展
- 在会议组织者的会议中安装应用

> [!NOTE]
> 如果分配给他们的 [应用权限策略](teams-app-permission-policies.md) 允许，用户仍然可以自行安装应用。

若要创建应用安装策略以安装应用，请执行以下步骤：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams** **appsSetup** >  策略。

2. 选择“**添加**”。

3. 输入策略的名称和说明。

4. 在 **“已安装的应用**”下，选择 **“添加应用**”。

5. 在 **“添加已安装的应用** ”窗格中，搜索要为用户自动安装的应用。 还可以按应用权限策略筛选应用。

6. 选择“**添加**”。

![安装应用策略。](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> 用户无法卸载管理员安装的应用。

## <a name="upload-custom-apps"></a>Upload自定义应用

可以使用Microsoft Teams管理中心创建允许用户将自定义应用上传到Teams的自定义策略。

若要创建应用设置策略以允许用户将自定义应用上传到Teams，请执行以下步骤：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams** **appsSetup** >  策略。

2. 选择“**添加**”。

3. 输入策略的名称和说明。

4. 打开或关闭 **Upload自定义应用**，具体取决于是否允许用户将自定义应用上传到Teams。

> [!NOTE]
> 如果在 [组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)中关闭 **第三方应用**，则无法更改此设置。

## <a name="manage-app-setup-policies"></a>管理应用设置策略

在Microsoft Teams管理中心管理应用设置策略。 使用全局 (组织范围的默认) 策略或创建和分配自定义策略。  除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

编辑全局策略中的设置以包含所需的应用。 若要自定义组织中不同用户组的Teams，请创建并分配一个或多个自定义策略。

![“应用设置策略”页。](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>编辑应用设置策略

可以使用Microsoft Teams管理中心编辑策略，包括创建的全局 (组织范围的默认) 策略和自定义策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams** **appsSetup** >  策略。

2. 选择要编辑的策略，然后选择 **“编辑**”。

3. 进行所需的更改。

4. 选择“**保存**”。

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>向用户和组分配自定义应用设置策略

有关向用户和组分配策略的详细信息，请参阅 [为用户和组分配策略](assign-policies-users-and-groups.md)。

## <a name="faq"></a>常见问题

### <a name="working-with-app-setup-policies"></a>使用应用设置策略

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理中心包含哪些内置应用设置策略

- **全局 (组织范围的默认)**：此默认策略适用于组织中的所有用户，除非你分配了另一个策略。 编辑全局策略以固定对用户最重要的应用。

- **前线工人**：这项政策适用于一线工人。 可以将其分配给组织中的一线工作者。 请务必知道，与创建的自定义策略一样，必须将策略分配给用户才能使设置处于活动状态。 有关详细信息，请转到本文的“ [向用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users-and-groups) ”部分。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么在“添加固定应用”窗格中找不到应用

并非所有应用都可以通过应用设置策略固定到Teams。 某些应用可能不支持此功能。 若要查找可固定的应用，请在 **“添加固定应用** ”窗格中搜索应用。 具有个人作用域 (静态选项卡) 和机器人的选项卡可以固定到Teams桌面客户端，这些应用在 **“添加固定应用**”窗格中可用。

请记住，Teams应用商店列出了所有Teams应用。 **“添加固定应用**”窗格仅包含可通过策略固定到Teams的应用。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是Teams 教育版管理员在Teams 教育版中，我需要了解哪些应用设置策略

通话应用在Teams 教育版中不可用。 创建新的自定义应用设置策略时，呼叫应用会显示在应用列表中。 但是，应用不会固定到Teams客户端，Teams 教育版用户不会在Teams中看到“呼叫”应用。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>可将多少个固定应用添加到策略

 (iOS 和 Android) ，至少必须将两个应用固定到Teams移动客户端。 如果策略的应用少于两个，则移动客户端不会反映策略设置，而是将继续使用现有配置。

可以添加到策略的固定应用数量没有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>策略更改生效需要多长时间

编辑或分配策略后，更改可能需要几个小时才能生效。

### <a name="user-experience"></a>用户体验

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>用户如何在Teams中查看其所有固定应用

若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装应用的数量及其Teams客户端窗口的大小。

|Teams 桌面客户端 |Teams 移动客户端 |
|---------|---------|
|在Teams侧的应用栏中，选择 **...更多应用**。| 在Teams底部附近的应用栏中，向上轻扫。|
|![Teams桌面客户端中的更多应用。](media/app-setup-policies-desktop-more-apps.png)   |![Teams移动客户端中的更多应用](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>我需要了解哪些关于Teams移动体验的信息

Teams移动客户端 (iOS 和 Android) 使用静态选项卡支持个人应用。 固定到Teams桌面客户端的应用将显示在Teams移动客户端中。 个人机器人将显示在移动客户端上的聊天中。

第三方应用 (可从Teams应用商店下载) 需要获得批准，然后才能在移动设备上显示。 如果管理员固定了 Microsoft for Mobile 未批准的应用，它将显示在Teams桌面上，但不会显示在移动设备上。 有关详细信息，请参阅 [移动客户](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 端。

借助Teams移动客户端，用户将看到活动、聊天和Teams等核心Teams应用，并且可以固定 Microsoft 的一些第一方应用，如 Shifts。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>用户是否可以更改通过策略固定的应用的顺序

如果打开“**用户固定**”选项，则用户可以在Teams桌面和移动客户端上更改其固定应用的顺序。 用户无法更改其固定应用在Teams Web 客户端上的顺序。

#### <a name="does-user-pinning-take-precedence"></a>用户固定是否优先

管理员引脚始终优先。 如果启用 **了“用户固定** ”选项，则用户会将其固定的应用保留在管理员固定应用下面。 如果“ **用户固定** ”选项被关闭，则用户将丢失其预先存在的引脚，并且应用栏中将仅存在管理员固定的应用。

### <a name="custom-teams-apps"></a>自定义Teams应用

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的组织生成了自定义Teams应用并将其发布到 AppSource 或租户应用目录，但当应用固定到Teams中的应用栏时，应用图标不会按预期显示。 如何实现修复它？

提交应用之前，请确保遵循徽标准则。 若要了解详细信息，请参阅 [卖家仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-articles"></a>相关文章

[Teams 中应用的管理设置](admin-settings.md)

[向 Teams 中的用户分配策略](assign-policies-users-and-groups.md)
