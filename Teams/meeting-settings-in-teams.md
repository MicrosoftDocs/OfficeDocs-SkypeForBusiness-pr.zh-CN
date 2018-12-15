---
title: 在 Microsoft Teams 中管理会议设置
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
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: 了解如何管理的用户安排在组织中的团队会议设置。
ms.openlocfilehash: 1e3415b1fd17a863e14a79fcc66b32e6749b39e7
ms.sourcegitcommit: a51d357069765b7d0956880da2ffd041533cfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2018
ms.locfileid: "27283546"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理会议设置

作为一名管理员，您使用团队会议设置来控制是否匿名用户可以加入团队会议和自定义会议邀请，如果您想要启用服务质量 (QoS) 设置的实时通信的端口。 这些设置应用于所有团队会议在组织中的用户日程安排。 **会议**管理这些设置 > 中的 Microsoft 团队业务管理中心的 Skype**会议设置**。 

## <a name="allow-anonymous-users-to-join-meetings"></a>允许匿名用户加入会议

匿名加入与任何人都可以作为加入会议匿名用户通过单击会议邀请中的链接。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) 使用 Microsoft 团队 Skype 业务管理中心的
1. 在左侧导航窗格中，转到**会议** > **会议设置**。 
2. 在**参与者**下启用**匿名用户可以加入会议**。 

    ![会议-设置-participants.png](media/meeting-settings-participants.png "团队中的 Microsoft 团队业务管理中心的 Skype 的会议的参与者设置的屏幕截图")

如果您不希望匿名用户可以加入您的组织中的用户安排的会议，请关闭此设置。 
## <a name="customize-meeting-invitations"></a>自定义会议邀请

您可以自定义团队会议邀请，以满足您组织的需求。 您可以添加贵组织的徽标和包括有用的信息，如技术支持网站和法律免责声明和纯文本页脚的链接。 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>创建会议邀请的徽标的提示  

1. 创建不超过 188 像素宽 x 30 像素高 （它是非常小） 的图像。 
2. 将图像保存为 JPG 格式。 
3. 将图像存储在您的组织中的所有人都可以访问，如网络共享一个中心位置。 

### <a name="customize-your-meeting-invitations"></a>自定义会议邀请

![团队-徽标-30x30.png](media/teams-logo-30x30.png) 使用 Microsoft 团队 Skype 业务管理中心的

1. 在左侧导航窗格中，转到**会议** > **会议设置**。
2. 在**电子邮件邀请**，下执行以下操作： 

    ![会议-设置-invitation.png](media/meeting-settings-invitation.png "会议的屏幕截图可以自定义团队会议的邀请设置") 

    - **徽标 URL**输入您的徽标的存储位置的 URL。 
    - **法律 URL**如果您的组织具有您想让用户转到的任何法律问题的法律网站，输入以下 URL。 
    - **帮助 URL**如果您的组织具有您想让用户转到如果他们遇到问题的支持网站，，输入以下 URL。
    - **页脚**输入要作为页脚包含的文本。 
3. 等待一小时或，更改将传播。 然后安排团队会议以查看会议邀请如下所示。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>设置您希望如何处理团队会议的实时的媒体流量
如果您使用的服务质量 (QoS) 若要设置网络流量，可以启用 QoS 标记，并且您可以设置每种类型的媒体流量的端口范围。 

 ![团队-徽标-30x30.png](media/teams-logo-30x30.png) 使用 Microsoft 团队 Skype 业务管理中心的

1. 在左侧导航窗格中，转到**会议** > **会议设置**。 
2. 在**网络**下执行以下操作：

    ![会议-设置-network.png](media/meeting-settings-network.png "团队会议中的 Microsoft 团队业务管理中心的 Skype 的网络设置的屏幕截图")

    - 若要启用 QoS 标记，打开**插入的服务质量 (QoS) 标记的实时的媒体流量**。
    - 若要指定端口范围，旁边**选择每种类型的实时的媒体流量的端口范围**，请选择**指定端口范围**，，然后输入音频、 视频和屏幕共享的起始和结束端口。 
    
        如果您选择**自动使用任何可用的端口**，1024年之间可用的端口，并使用 65535。 

 ### <a name="related-topics"></a>相关主题
- [服务质量 (QoS 中的团队)](qos-in-teams.md)

