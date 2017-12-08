---
title: "在你的 Office 365 组织中启用 Microsoft Teams 功能 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解可以在你的 Office 365 组织中启用的所有 Microsoft Teams 功能，包括租户范围的设置、电子邮件集成、应用及云存储等。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c785e554034cd87fd27f5137f206c8dc0e5f972a
ms.sourcegitcommit: e8b96ddf6a6eaea4598b116f1e33c71911b337bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a>在你的 Office 365 组织中启用 Microsoft Teams 功能
======================================================

Microsoft Teams 具有多个可以在租户级别启用或禁用的设置。 如果为租户启用了 Teams，同样启用了 Teams 的任何用户都将从租户级别继承设置。

下面是 Office 365 管理员可以选择在 Teams 中启用或禁用的功能列表。

除非另有说明，否则选项的默认值为“开启”。

> [!NOTE]
> Office 365 管理员可以随时通过 Office 365 管理中心关闭 Microsoft Teams。 请注意，即使你关闭 Microsoft Teams，具有 Teams 有效许可证的用户也能继续看到 Teams 应用磁贴。 有关如何从用户删除许可证的详细信息，请参阅[管理对 Microsoft Teams 许可证的用户访问](user-access.md)。 禁用 Teams 后，将阻止从 Teams 客户端进行访问，但仍可以通过其他客户端和服务获取数据，例如，通过 SharePoint 和 OneDrive 获取文件。 除非明确删除团队，否则所有数据保留在原处。

<a name="tenant-wide-settings"></a>租户范围的设置 
---------------------

在**租户范围的设置**中，你可以开启或关闭“常规”、“电子邮件集成”、“应用”和“自定义云存储”中的选项。

### <a name="general"></a>常规

在“常规”部分中可以为贵组织配置以下设置：

> ![租户范围的设置中的“常规”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **在个人资料中显示组织结构图：** 如果启用此设置，将在用户的联系人卡片中显示组织结构图图标，单击该图标时，将显示详细的组织结构图。

    ![用户的联系人卡片中的组织结构图图标屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![组织结构图屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **对没有 Microsoft Teams 的收件人使用 Skype for Business：** 如果启用此设置，将允许 Microsoft Teams 用户通过 Skype for Business 联系组织中未启用 Microsoft Teams 的其他用户。

-   **允许 T-Bot 主动帮助消息：** 如果启用此设置，T-Bot 将启动与用户的私人聊天会话以指导他们使用 Microsoft Teams。

    ![Microsoft Teams 界面中的“T-Bot”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>电子邮件集成
-----------------

开启此功能，以便用户可以使用频道电子邮件地址向 Microsoft Teams 中的频道发送电子邮件。 用户可以对属于其所属团队的任何频道执行此操作。 用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。 并且，即使用户无权创建频道电子邮件地址，如果有权限的用户创建了该地址，则用户可以从该频道的\<更多图标\>菜单访问该地址。

在“电子邮件集成”部分中可以为贵组织配置以下设置：

   ![租户范围的设置中的“电子邮件集成”部分屏幕截图。](media/QS-edu-email-integration.png)

-   **允许用户向频道发送电子邮件：** 如果启用此设置，将启用邮件挂钩，用户可以通过向 Microsoft Teams 频道的电子邮件地址发送电子邮件来向频道发布消息。

> 要查找频道的电子邮件地址，请单击频道名称旁边的**“更多选项”**，然后选择**“获取电子邮件地址”**。

-   **受限制的发件人列表：** 可以对发件人域做进一步限制，以确保仅允许的 SMTP 域可以向 Microsoft Teams 频道发送电子邮件。

<a name="apps"></a>应用
----

Microsoft Teams 中的应用是将你的团队关注的工具和服务正确集成到任何频道或聊天中的绝佳方式。

在**“应用”**部分中可以为贵组织配置以下设置：

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **在 Microsoft Teams 中允许外部应用：** 如果启用此设置，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。
![“应用”部分中的允许外部应用控制屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **允许侧向加载外部应用：** 如果启用此设置，用户可以安装和启用自定义聊天机器人和选项卡。

<a name="custom-cloud-storage"></a>自定义云存储
--------------------

Microsoft Teams 中的云存储选项当前包括 Box、Dropbox、Google Drive 和 ShareFile。 用户可以在 Microsoft Teams 频道和聊天中从云存储服务上载和共享文件。 可单击或点击贵组织要使用的云存储提供程序旁边的切换开关。

![“自定义云存储”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>按许可证的用户设置
------------------------

在**“按许可证的用户设置”**中，可以开启或关闭“团队和频道”、“通话和会议”以及“消息”中的选项。

<a name="teams-and-channels"></a>团队和频道
------------------

团队用于将一群人集中在一起，以便这些人密切合作来完成事情。 对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的。 团队也可以是持续存在的，以反映贵组织的内部结构。

作为管理员，你可以通过使用 Office 365 管理中心门户中的“组”仪表板管理团队所有者和成员。 在“团队和频道”部分中，单击**使用 Office 365 管理中心中的“组”仪表板管理团队**链接。

你可以控制贵组织中哪些用户可以在 Microsoft Teams 中创建团队。 Office 365 组定义的相同创建设置适用于 Microsoft Teams。 有关管理 Office 365 组的详细信息，请参阅[创建 Office 365 组](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)和[控制哪些人可以创建 Office 365 组](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

注意：无法从“组”仪表板创建团队。 必须使用 Microsoft Teams 桌面客户端或 Web 应用创建团队。

默认情况下，所有用户都可以创建团队或组。 用户可以选择 Microsoft Teams 客户端（桌面客户端或 Web 应用）中左侧的“团队”，然后选择客户端底部的“创建团队”（在团队列表下方），来创建团队。

Office 365 租户可以包含的默认最大团队数当前为 500,000。 全局管理员可以创建无限数量的团队。 用户可以创建 250 个团队。 团队所有者可以向团队添加 2500 个成员。

![“按许可证的用户设置”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

频道是团队的子类别。 团队中的任何人都可以添加频道以及参与频道中的对话。 你可为活动或部门创建频道。 对话、文件和 Wiki 是特定于每个频道的，但团队的所有成员都可以查看它们。

### <a name="calls-and-meetings"></a>通话和会议

在**“通话和会议”**部分中可以为贵组织配置以下设置：

> ![“通话和会议”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **允许安排私人会议：** 如果启用此设置，用户可以安排不在任何频道中列出的私人会议。

-   **允许临时频道聚会：**

-   **允许安排频道会议：** 如果启用此设置，用户可以为某个频道安排会议，所有频道成员只需单击一下即可轻松加入会议。

-   **在会议中允许视频：** 指定是否允许在会议中使用视频。

-   **允许在会议中共享屏幕：** 指定是否允许在会议中共享屏幕。

-   **允许专线通话：** 如果启用此设置，用户可以进行专线通话。

会议中的最大人数是 80。 私人聊天中可以有 20 个成员，包括创建聊天的用户。

### <a name="messaging"></a>消息 

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

