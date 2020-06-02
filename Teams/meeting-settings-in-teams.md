---
title: 管理会议设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 了解如何管理用户在组织中安排的 Teams 会议的设置。
ms.openlocfilehash: 761504400639c8ed53c617f6c816dd7c4703a530
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489134"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理会议设置

作为管理员，你可以使用 Teams 会议设置来控制匿名用户是否可以加入 Teams 会议、自定义会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口范围。 这些设置适用于用户在组织中安排的所有 Teams 会议。 可以在 Microsoft Teams 管理中心的“**会议**” > “**会议设置**”中管理这些设置。

## <a name="allow-anonymous-users-to-join-meetings"></a>允许匿名用户加入会议

通过匿名加入，任何人都可以通过单击会议邀请中的链接以匿名用户的身份加入会议。 要了解更多信息，请参阅[在没有 Teams 帐户的情况下加入会议](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 转到管理中心 <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a> 。

2. 在左侧导航中，转到“**会议**” > “**会议设置**”。

3. 在“**参与者**”下，打开“**匿名用户可以加入会议**”。

    ![管理中心会议的参与者设置的屏幕截图](media/meeting-settings-participants.png "Microsoft Teams 管理中心 Teams 会议的参与者设置的屏幕截图")

> [!CAUTION]
> 如果不希望匿名用户加入组织中由用户安排的会议，请关闭此设置。

## <a name="customize-meeting-invitations"></a>自定义会议邀请

你可以自定义 Teams 会议邀请，以满足组织的需求。 可添加组织的徽标，并包含有用的信息，如支持网站的链接和法律免责声明，以及纯文本页脚。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>为会议邀请创建徽标的提示  

1. 创建一个不超过 188 像素宽 x 30 像素高（相当小）的图像。
2. 将图像保存为 JPG 或 PNG 格式。
3. 将图像存储在收到邀请的每个人都可以访问的位置，例如公共网站。

    现在，你可以将其添加到会议邀请。 查看后续步骤。

### <a name="customize-your-meeting-invitations"></a>自定义会议邀请

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。。
2. 在左侧导航中，转到“**会议**” > “**会议设置**”。
3. 在“**电子邮件邀请**”下，执行以下操作：

    ![可自定义的会议邀请设置的屏幕截图](media/meeting-settings-invitation.png "可以为 Teams 会议自定义的会议邀请设置的屏幕截图")

    - **徽标 URL** 输入存储徽标的 URL。
    - **法律 URL** 如果你的组织有一个法律网站，并且你希望其他人转至该网站了解任何法律问题，请在此处输入其 URL。
    - **帮助 URL** 如果你的组织有一个支持网站，并且你希望人们在遇到问题时转至该网站，请在此处输入其 URL。
    - **页脚**输入要作为页脚包含在内的文本。
4. 单击“**预览邀请**”可查看会议邀请的预览。
5. 完成时单击“**保存**”。
6. 等待一个小时左右，以便传播所作的更改。 然后，安排一次 Teams 会议，查看会议邀请的外观。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>设置你希望如何处理 Teams 会议的实时媒体流量

<a name="bknetwork"> </a>

如果要使用服务质量 [(QoS)](qos-in-teams.md) 确定网络流量的优先级，则可以启用 QoS 标记，并且可以设置每种媒体流量的端口范围。 为不同流量类型设置端口范围只是处理实时媒体的其中一个步骤；有关详细信息，请参阅 [Teams 中的服务质量 (QoS)](qos-in-teams.md)。

> [!IMPORTANT]
> 如果要在 Microsoft Teams 管理中心为 Microsoft Teams 服务启用 QoS 或更改设置，还需[向所有用户设备和所有内部网络设备应用匹配设置](QoS-in-Teams-clients.md)，以完全实施对 Teams 中的 QoS 所作的更改。

 ![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**
1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。
2. 在左侧导航中，转到“**会议**” > “**会议设置**”。
3. 在“**网络**”下，执行以下操作：

    ![管理中心会议的网络设置的屏幕截图](media/meeting-settings-network.png "Microsoft Teams 管理中心 Teams 会议的网络设置的屏幕截图")

    - 要允许对 QoS 使用 DSCP 标记，请打开**插入实时媒体流量的服务质量 (QoS) 标记**。 你只能选择是否使用标记；不能为每种流量类型设置自定义标记。 有关 DSCP 标记的更多信息，请参阅[选择 QoS 实施方法](QoS-in-Teams.md#select-a-qos-implementation-method)。
        > [!NOTE]
        > 打开**插入实时媒体流量的服务质量 (QoS) 标记**也将启用通过 UDP 端口 3479（音频）、3480（视频）和 3481（共享）与传输中继的流量。
    - 要指定端口范围，请在“**选择每种媒体实时流量的端口范围**”旁选择“**指定端口范围**”，然后输入音频、视频和屏幕共享的起始和结束端口。 要实施 QoS，必须选择此选项。
        > [!IMPORTANT]
        > 如果你选择了**自动使用任何可用的端口**，则将使用 1024 和 65535 之间的可用端口。 仅在未实施 QoS 的情况下使用此选项。
        >
        > 选择的端口范围过窄会导致通话中断或通话质量不佳。 下面的建议只是最低要求。

如果你不确定要在环境中使用的端口范围，不妨从以下设置开始。 要了解更多信息，请阅读[在 Microsoft Teams 中实施服务质量 (QoS)](QoS-in-Teams.md)。 以下是所需的 DSCP 标记和由 Teams 和 ExpressRoute 使用的建议相应媒体端口范围。

### <a name="port-ranges-and-dscp-markings"></a>端口范围和 DSCP 标记

媒体流量类型| 客户端源端口范围\* |协议|DSCP 值|DSCP 类|
|:---             |:---                         |:---    |:---      |:---      |
|音频            | 50,000–50,019               |TCP/UDP |46        |加速转发 (EF)|
|视频            | 50,020–50,039               |TCP/UDP |34        |保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059      |TCP/UDP |18        |保证转发 (AF21)|
| | | | |

\* 分配的端口范围不能重叠，必须彼此相邻。

在 QoS 使用过一段时间后，你将获得这三种工作负载中每一种的需求信息，并且可以根据特定需求选择要进行的更改。 [通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。
