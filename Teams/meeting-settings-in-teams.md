---
title: 管理会议设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理的用户安排在组织中的团队会议设置。
ms.openlocfilehash: 4ded26dae69b5afef1d9fafb4819a73475c44898
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231879"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理会议设置

作为一名管理员，您使用团队会议设置来控制是否匿名用户可以加入团队会议和自定义会议邀请，如果您想要启用服务质量 (QoS) 设置的实时通信的端口范围。 这些设置应用于所有团队会议在组织中的用户日程安排。 **会议**管理这些设置 > Microsoft 团队管理中心中的**会议设置**。

## <a name="allow-anonymous-users-to-join-meetings"></a>允许匿名用户加入会议

匿名加入与任何人都可以作为加入会议匿名用户通过单击会议邀请中的链接。

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议设置**。
2. 在**参与者**下启用**匿名用户可以加入会议**。

    ![会议-设置-participants.png](media/meeting-settings-participants.png "Microsoft 团队管理中心中的团队会议的参与者设置的屏幕截图")

如果您不希望匿名用户可以加入您的组织中的用户安排的会议，请关闭此设置。

## <a name="customize-meeting-invitations"></a>自定义会议邀请

您可以自定义团队会议邀请，以满足您组织的需求。 您可以添加贵组织的徽标和包括有用的信息，如技术支持网站和法律免责声明和纯文本页脚的链接。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>创建会议邀请的徽标的提示  

1. 创建不超过 188 像素宽 x 30 像素高 （它是非常小） 的图像。
2. 将图像保存为 JPG 格式。
3. 将图像存储在您的组织中的所有人都可以访问，如网络共享一个中心位置。

### <a name="customize-your-meeting-invitations"></a>自定义会议邀请

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议设置**。
2. 在**电子邮件邀请**，下执行以下操作：

    ![会议-设置-invitation.png](media/meeting-settings-invitation.png "会议的屏幕截图可以自定义团队会议的邀请设置")

    - **徽标 URL**输入您的徽标的存储位置的 URL。
    - **法律 URL**如果您的组织具有您想让用户转到的任何法律问题的法律网站，输入以下 URL。
    - **帮助 URL**如果您的组织具有您想让用户转到如果他们遇到问题的支持网站，，输入以下 URL。
    - **页脚**输入要作为页脚包含的文本。
3. 等待一小时或，更改将传播。 然后安排团队会议以查看会议邀请如下所示。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>设置您希望如何处理团队会议的实时的媒体流量

<a name="bknetwork"> </a>

如果您使用的服务质量[(QoS)](qos-in-teams.md)若要设置网络流量，可以启用 QoS 标记，并且您可以设置每种类型的媒体流量的端口范围。

 ![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议设置**。
2. 在**网络**下执行以下操作：

    ![会议-设置-network.png](media/meeting-settings-network.png "团队会议的 Microsoft 团队管理中心中的网络设置的屏幕截图")

    - 要允许 DSCP 标记，以用于 QoS，请打开**插入的服务质量 (QoS) 标记的实时的媒体流量**。 只有或不; 使用标记的选项不能设置为每种通信类型的自定义标记。 更多有关 DSCP 标记，请参阅[选择 QoS 实现方法](QoS-in-Teams.md#select-a-qos-implementation-method)。
    - 若要指定端口范围，旁边**选择每种类型的实时的媒体流量的端口范围**，请选择**指定端口范围**，，然后输入音频、 视频和屏幕共享的起始和结束端口。 选择此选项需要实现 QoS。
    > [!IMPORTANT]
    > 如果您选择**自动使用任何可用的端口**，1024年之间可用的端口，并使用 65535。 仅当不实现 QoS，请使用此选项。
    >
    > 选择太窄的端口范围会导致丢弃的呼叫和质量欠佳的呼叫质量。 下面的建议应最低。

 如果您不确定哪些端口范围，在您的环境中使用，以下设置都很好的起点。 若要了解详细信息，请阅读[实现的服务质量 (QoS) 中的 Microsoft 团队](QoS-in-Teams.md)。 这些是必需的 DSCP 标记和建议的相应媒体端口范围团队和 ExpressRoute 使用。

_端口范围和 DSCP 标记_

媒体通信类型| 客户端源端口范围\* |协议|DSCP 值|DSCP 类|
|:---             |:---                         |:---    |:---      |:---      |
|音频            | 50000 – 50,019               |TCP/UDP |46        |加速转发 (EF)|
|视频            | 50,020 – 50,039               |TCP/UDP |34        |保证转发 (AF41)|
|应用程序/屏幕共享| 50,040 – 50,059      |TCP/UDP |18        |保证转发 (AF21)|
| | | | |

\*分配的端口范围不能重叠，并且必须彼此相邻。

端口范围设置不同的通信类型是只有一个步骤中处理实时媒体;更多详细信息，请参阅[服务质量 (QoS) 中的团队](qos-in-teams.md)。 如果启用，或更改的 Microsoft 团队管理中心中的设置，您需要向[匹配将设置应用于所有用户设备](QoS-in-Teams-clients.md)和内部网络设备完全在工作组中实现对 QoS 的更改。

QoS 一直在使用后的一段时间，您必须按每个这些三个工作负荷，需使用情况的信息和您可以选择要进行更改基于您的特定需求。 [呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)将有用的。
