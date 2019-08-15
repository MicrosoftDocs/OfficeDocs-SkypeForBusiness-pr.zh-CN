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
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理组织中用户安排的团队会议的设置。
ms.openlocfilehash: b1513e80028137c909f5fc0f854666b1770299c8
ms.sourcegitcommit: c169b091a630ff78c233a2a2824da122184635d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2019
ms.locfileid: "36404599"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理会议设置

作为管理员, 你可以使用团队会议设置控制匿名用户是否可以加入团队会议、自定义会议邀请, 以及是否要启用服务质量 (QoS), 并为实时流量设置端口范围。 这些设置适用于用户在你的组织中安排的所有团队会议。 可在 Microsoft 团队管理中心**** > 的会议 "**会议设置**" 中管理这些设置。

## <a name="allow-anonymous-users-to-join-meetings"></a>允许匿名用户加入会议

通过匿名加入, 任何人都可以通过单击会议邀请中的链接以匿名用户身份加入会议。

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**会议** > **会议设置**"。
2. 在 "**参与者**" 下, 打开**匿名用户可以加入会议**。

    ![管理中心中的会议参与者设置的屏幕截图](media/meeting-settings-participants.png "Microsoft 团队管理中心中团队会议的参与者设置的屏幕截图")

如果您不希望匿名用户加入您的组织中的用户计划的会议, 请关闭此设置。

## <a name="customize-meeting-invitations"></a>自定义会议邀请

您可以自定义团队会议邀请以满足组织的需求。 你可以添加组织的徽标并包含有用的信息, 如指向支持网站和法律免责声明的链接, 以及纯文本页脚。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>为会议邀请创建徽标的提示  

1. 创建宽度不188超过30像素的图像 (相当小)。
2. 以 JPG 或 PNG 格式保存图像。
3. 将图像存储在你的组织中的每个人都可以访问的中心位置, 例如网络共享。

    现在, 您可以将其添加到会议邀请。 请参阅后续步骤。

### <a name="customize-your-meeting-invitations"></a>自定义会议邀请

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**会议** > **会议设置**"。
2. 在 "**电子邮件邀请**" 下, 执行下列操作:

    ![可自定义的会议邀请设置的屏幕截图](media/meeting-settings-invitation.png "可为团队会议自定义的会议邀请设置的屏幕截图")

    - **徽标 URL**输入存储徽标的 URL。
    - **合法 URL**如果你的组织拥有法律网站, 而你希望其他人出于任何法律问题而转到该网站, 请在此处输入 URL。
    - **帮助 URL**如果你的组织有支持网站, 而你希望用户在遇到问题时转到该网站, 请在此处输入 URL。
    - **页脚**输入要包含在页脚中的文本。
3. 等待一小时, 这样才能传播所做的更改。 然后安排团队会议以查看会议邀请的外观。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>设置你希望如何处理团队会议的实时媒体流量

<a name="bknetwork"> </a>

如果你使用 "服务质量[(QoS)](qos-in-teams.md) " 来设置网络流量的优先级, 则可以启用 QoS 标记, 并且可以为每种类型的媒体流量设置端口范围。 为不同的流量类型设置端口范围只是处理实时媒体的一个步骤;[在团队中查看服务质量 (QoS)](qos-in-teams.md) , 了解更多详细信息。

> [!IMPORTANT]
> 如果你在 microsoft 团队服务的 Microsoft 团队管理中心中启用 QoS 或更改设置, 你还需要[将匹配设置应用到所有用户设备](QoS-in-Teams-clients.md)和所有内部网络设备, 以完全实现团队中的 QoS 的更改。

 ![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**会议** > **会议设置**"。
2. 在 "**网络**" 下, 执行下列操作:

    ![管理中心中的会议的网络设置的屏幕截图](media/meeting-settings-network.png "Microsoft 团队管理中心中团队会议的网络设置的屏幕截图")

    - 若要允许对 QoS 使用 DSCP 标记, 请打开**实时媒体流量的 "插入服务质量 (QoS)" 标记**。 您只能选择使用标记, 也可以不选择。不能为每种流量类型设置自定义标记。 有关 DSCP 标记的详细信息, 请参阅[选择 QoS 实现方法](QoS-in-Teams.md#select-a-qos-implementation-method)。
    - 若要指定端口范围, 请在 "为**每种实时媒体流量选择端口范围**" 旁边, 选择 "**指定端口范围**", 然后输入音频、视频和屏幕共享的起始和结束端口。 若要实现 QoS, 选择此选项是必需的。
    > [!IMPORTANT]
    > 如果选择 "**自动使用任何可用端口**", 将使用1024和65535之间的可用端口。 仅在未实现 QoS 时使用此选项。
    >
    > 选择太窄的端口范围将导致呼叫中断和通话质量不佳。 下面的建议最少。

如果不确定要在环境中使用的端口范围, 以下设置是一个很好的起始点。 若要了解详细信息, 请参阅[Microsoft 团队中的实施服务质量 (QoS)](QoS-in-Teams.md)。 这些是所需的 DSCP 标记和建议的相应媒体端口范围 (由团队和 ExpressRoute 使用)。

_端口范围和 DSCP 标记_

媒体流量类型| 客户端源端口范围\* |协议|DSCP 值|DSCP 类|
|:---             |:---                         |:---    |:---      |:---      |
|音频            | 50000-50019               |TCP/UDP |46        |加速转发 (EF)|
|视频            | 50,020–50,039               |TCP/UDP |34        |保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059      |TCP/UDP |18        |有保证的转发 (AF21)|
| | | | |

\*您分配的端口范围不能重叠, 并且必须彼此相邻。

在 QoS 已使用过一段时间后, 你将在每个这三个工作负荷的需求上获得使用信息, 你可以根据特定需要选择要进行的更改。 [通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)将非常有用。
