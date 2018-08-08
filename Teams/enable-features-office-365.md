---
title: 管理 Office 365 组织中的 Microsoft 团队功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 了解可以在你的 Office 365 组织中启用或禁用的所有 Microsoft Teams 功能，包括租户范围的设置、电子邮件集成、应用及云存储等。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50650d852e87cb885beae4403022464fafb57373
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "20265944"
---
<a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>管理 Office 365 组织中的 Microsoft 团队功能
======================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Teams 可以在 Office 365 租户级别启用或关闭多项设置。 与团队启用还启用团队的任何用户将继承从租户级别的设置。

下面是 Office 365 管理员可以在 Teams 中启用或禁用的功能列表。 

除非另有说明，否则选项的默认值为“开启”。

> [!NOTE] 
> 要管理 Teams 的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。 如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作： 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> Office 365 管理员可以随时通过 Office 365 管理中心关闭 Microsoft Teams。 请注意，即使你关闭 Microsoft Teams，具有 Teams 有效许可证的用户也能继续看到 Teams 应用磁贴。 有关如何从用户删除许可证的详细信息，请参阅[管理对 Microsoft Teams 许可证的用户访问](user-access.md)。 禁用 Teams 后，将阻止从 Teams 客户端进行访问，但仍可以通过其他客户端和服务获取数据，例如，通过 SharePoint 和 OneDrive 获取文件。 除非明确删除团队，否则所有数据保留在原处。

<a name="office-365-tenant-wide-settings"></a>Office 365 租户范围的设置 
---------------------

在**租户范围的设置**中，你可以开启或关闭“常规”、“电子邮件集成”、“应用”和“自定义云存储”中的选项。

要编辑 Teams 的**租户范围的设置**，请转到 Office 365 管理中心。 选择 **“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。

### <a name="general"></a>常规

在“常规”部分中可以为贵组织配置以下设置：

> ![租户范围的设置中的“常规”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **在个人资料中显示组织结构图：** 如果启用此设置，将在用户的联系人卡片中显示组织结构图图标，单击该图标后，将显示详细的组织结构图。

    ![用户的联系人卡片中的组织结构图图标屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![组织结构图屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  **对没有 Teams 的收件人使用 Skype for Business：** 如果启用此设置，对于未启用 Teams 的用户，Teams 对话将自动显示在 Skype for Business 中。  

-   **允许 T-Bot 主动发送帮助消息：** 如果启用此设置，T-Bot 将启动与用户的私人聊天会话以帮助他们使用 Teams。

    ![Teams 界面中的“T-Bot”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>电子邮件集成
-----------------

开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。 用户可以对属于其所属团队的任何频道执行此操作。 用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。 并且，即使用户无权创建频道电子邮件地址，如果有权限的用户创建了该地址，则用户可以从该频道的“**更多选项**”菜单访问该地址。

为贵组织配置以下“**电子邮件集成**”设置： 

   ![租户范围的设置中的“电子邮件集成”部分屏幕截图。](media/QS-edu-email-integration.png)


-   **允许用户向频道发送电子邮件：** 如果启用此设置，将启用邮件挂钩，用户可以通过向 Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。 

    要查找频道的电子邮件地址，请单击频道的“**更多选项**”菜单，然后选择“**获取电子邮件地址**”。 

-   **受限制的发件人列表：** 可以对发件人域做进一步限制，以确保仅允许的 SMTP 域可以向 Teams 频道发送电子邮件。

<a name="apps"></a>应用
----

应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。 可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。 通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。 

在 **“应用”** 下，可以为贵组织配置以下设置： 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **在 Microsoft Teams 中允许外部应用：** 如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **默认启用新的外部应用：** 打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。 如果你希望控制新应用，请关闭此开关。 当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。 

- **允许侧向加载外部应用：** 如果打开此开关，用户可以安装和启用自定义聊天机器人和选项卡。 

要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。 



<a name="custom-cloud-storage"></a>自定义云存储
--------------------

Teams 中的云存储选项当前包括 Box、Dropbox、Google Drive 和 ShareFile。 用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。 可打开贵组织要使用的云存储提供商对应的开关。 

![“自定义云存储”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="settings-by-userlicense-type"></a>设置用户/许可证类型
------------------------
设置时的 Microsoft 团队为您的组织最初，您可以使用**用户/许可证类型设置**下拉列表菜单选择许可证类型然后为该许可证类型的所有用户打开团队。

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

 用户/许可证类型的一些示例包括**企业**和**来宾**。 （如果您具有教育版 SKU 许可证，**教育-教职员工**或**培训-学生**都可用。）![设置用户许可证的控件](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)

您具有多个许可证类型中您的组织，例如，同时**企业**和**来宾**。 Microsoft 团队可以仅区分基于的许可证已分配给这些用户。 您可以打开或关闭**团队和频道**、**呼叫和会议**，以及**消息**中这些用户的选项。 如果您使用只有一个许可证类型，请考虑为租户范围的设置的设置。
> [!NOTE]
> 有关来宾访问的详细信息，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。

<a name="teams-and-channels"></a>团队和频道
------------------

团队用于将一群人集中在一起，以便这些人密切合作来完成事情。 对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的。 团队也可以是持续存在的，以反映贵组织的内部结构。

Office 365 租户可以拥有的最大团队数当前为 500,000。 全局管理员可以创建无限数量的团队。 用户可以创建 250 个团队。 团队所有者可以向团队添加 2500 个成员。

作为管理员，你可以通过使用 Office 365 管理中心中的“组”仪表板管理团队所有者和成员。 要了解详细信息，请单击“**团队和频道**”下的“**使用 Office 365 管理中心中的‘组’仪表板管理团队**”。

你可以控制贵组织中哪些用户可以在 Teams 中创建团队。 Office 365 组定义的相同创建设置适用于 Teams。 有关管理 Office 365 组的详细信息，请参阅[创建 Office 365 组](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)和[控制哪些人可以创建 Office 365 组](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

> [!NOTE]
> 无法从“组”仪表板创建团队。 必须使用 Teams 桌面客户端或 Web 应用创建团队。

默认情况下，所有用户都可以创建团队或组。 选择 Teams 客户端（桌面客户端或 Web 应用）中左侧的 **“团队”**，然后选择客户端底部的 **“创建并加入团队”**（在团队列表下方）。

![“按许可证的用户设置”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

频道是团队的子类别。 团队中的任何人都可以添加频道以及参与频道中的对话。 你可为活动或部门创建频道。 对话、文件和 Wiki 是特定于每个频道的，但团队的所有成员都可以查看它们。

## <a name="calls-and-meetings"></a>通话和会议

为贵组织配置以下“**通话和会议**”设置：

![“通话和会议”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

会议中的最大人数是 80。 私人聊天中可以有 20 个成员，包括创建聊天的用户。

-   **允许安排私人会议：** 如果启用此设置，用户可以安排不在任何频道中列出的私人会议。

-   **允许临时频道聚会**：打开此功能后，用户可以快速为专为紧急或特定目的而创建的频道快速启动会议。

-   **允许安排频道会议：** 如果启用此设置，用户可以为某个频道安排会议，所有频道成员只需单击一下即可轻松加入会议。

-   **在会议中允许视频：** 指定是否允许在会议中使用视频。

-   **允许在会议中共享屏幕：** 指定是否允许在会议中共享屏幕。

-   **允许专线通话：** 如果启用此设置，用户可以进行专线通话。

## <a name="messaging"></a>消息 

在“消息”部分中可以为贵组织配置以下设置：

![“消息”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **启用 Giphy 以便用户可以向对话添加 gif：** 如果启用此设置，用户可以在对话中使用动画图片。

-   **内容分级：** 如果启用动画图片，可以应用内容分级来限制可以在对话中显示的动画图片的类型。 可用的内容分级选项如下：

    -   无限制
    -   适中（默认值）
    -   严格

-   **启用用户可以编辑和添加到对话的 Meme：** 如果启用此设置，用户可以使用 Internet Meme 制作幽默的帖子。

-   **启用用户可以编辑和添加到对话的表情图片：** 如果启用此设置，用户可以发布包含可编辑文字的图片以引起频道成员的注意。

-   **允许所有者删除所有消息：** 如果启用此设置，频道所有者可以删除频道中的所有消息。

-   **允许用户编辑自己的消息：** 如果启用此设置，用户可以编辑自己的消息。

-   **允许用户删除自己的消息：** 如果启用此设置，用户可以删除自己的消息。

-   **允许用户私人聊天：** 如果启用此设置，用户可以参与仅聊天中的人员（而非团队中的所有人）可见的私人聊天。


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |决策点         |贵组织将启用 Microsoft Teams 的哪些设置？         |
|![后续步骤图标。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |后续步骤        |使用[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)中的表格记录这些决定。         |

