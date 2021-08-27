---
title: 小型企业设置 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 小型企业设置 Teams 可允许用户通过聊天和文件共享进行协作、安排并参加大小型会议及通过视频和语音相互交流。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e15a8a327d40ea11412229205fca6e856e9f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596316"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>小型企业设置 Microsoft Teams

自定义 Teams 的方法很多。 以下章节将说明如何设置各 Teams 工作负载：**聊天、团队和频道**；**会话和电话会议**；以及 **云语音**。 设置各工作负载的顺序可自行决定。 我们建议先设置聊天、团队和频道工作负载，但也可从会话和电话会议、甚至云语音开始设置。 选择权在你。

> [!NOTE]
> 若尚未进行部署，强烈建议通过试点开始 Teams 部署。 试点将允许你和一些早期采用者在规划和推出之前熟悉 Teams 及其功能。若要详细了解如何开始进行试点，请参阅[Microsoft Teams 入门指南](get-started-with-teams-quick-start.md)。

在大范围推出 Teams 之前，请参阅[确保你已准备就绪](get-started-with-teams-quick-start.md#make-sure-youre-ready)中的项目确保组织已做好准备。

跳转到感兴趣的章节：

- [工作负载](#workloads)
  - [聊天、团队和频道](#chat-teams-and-channels)
  - [会话和电话会议](#meetings-and-conferencing)
  - [商务语音](#business-voice)
- [部署客户端](#deploy-clients)
- [培训](#training)

## <a name="workloads"></a>工作负载
### <a name="chat-teams-and-channels"></a>聊天、团队和频道

聊天、团队和频道是 Teams 的基础。 **聊天** 允许一个或多个用户相互讨论、共享文件及私下会面。 **团队** 可对组织中的所有人员可见，或仅对团队成员可见。其允许相关人员在任何任务或场合，无论是长期运行的项目还是计划生日聚会中团结协作。 **团队** 的频道可以细分主题、项目、部门或其他对团队有意义的内容。 有关聊天、团队和频道的详细信息，请参阅[团队和频道概述](teams-channels-overview.md)。

> [!TIP]
> 完成 Microsoft Learn 中的 [管理 Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) 模块，了解如何管理团队角色、访问权限和消息传递策略。

在考虑推出团队和频道时，需决定负责创建的人员，以及组织外的来宾是否可进行访问等等。 [Microsoft Teams 聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)一文包含许多有关规划聊天、团队和频道的信息，但其以下重要内容需加以关注。 若要了解更多信息，请选择“决定”。

| 决定 | 说明 |
|--|--|
| [谁应该成为 Teams 管理员？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | 管理员角色可帮助向希望管理 Teams 的人员授予特定权限。 在小型企业中，同一人员可能负责 Teams 的方方面面，因此，这些额外角色可能没有必要。 之后，你始终可添加或删除管理员。<br><br>[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md) |
| [谁应该成为团队所有者和成员？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | 团队所有者负责管控能够访问团队及其频道的人员。 他们可以决定团队或频道是（对组织）公开还是私密，也可以制定是否应审核频道等策略。 成员可访问团队及其频道（除非频道设为私密，且他们不是该频道成员），也可被指定为审核员。<br><br>[在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md) |
| [是否应该启用来宾访问？](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |来宾访问允许组织内部人员邀请外部人员访问团队和频道。 来宾访问通常用于与组织外部人员进行协作，他们一般和你无正式关系。 例如，你可邀请项目规划员临时负责项目。<br>来宾访问不同于外部访问。 来宾访问邀请特定人员进行访问，与组织内部人员进行交互。  <br>默认情况下会 **关闭** 来宾访问。 <br><br>[启用或禁用 Microsoft Teams 的来宾访问](set-up-guests.md)  |

你无需进行任何其他操作，用户即可开始使用聊天、团队和频道。 不过，仍然有许多选项可用于控制 Teams 使用情况。 你可现在更改，也可等待，在观看用户如何使用 Teams 后再进行更改。 有关详细信息，请参阅以下文章：

- [在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)
- [Teams 设置](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>会话和电话会议

会话和电话会议允许组织内部人员相互会面，或与组织外部人员会面。 任何拥有 Teams 或 Skype for Business 客户端的人员受邀后即可加入 **会议**。 参与者可通过设备的麦克风、照相机和屏幕，无需手机便可加入对话。 参与者可使用电脑或移动设备彼此沟通、发起语音呼叫及共享视频和应用。

**音频会议** 允许参与者拨打会议电话号码并输入会议 ID 后，便可通过常规电话加入会议。 当参与者的 Internet 连接差、会议为仅语音会议或某些其他情况不允许他们通过 Teams 客户端加入会议时，音频会议便非常有用。

> [!TIP]
> 完成 Microsoft Learn 中的[使用 Microsoft Teams 管理会议、电话会议和事件](/learn/modules/m365-teams-collab-manage-meetings)模块，进一步熟悉相关内容。

Teams 默认启用会议，不过你仍然可控制组织者和参与者的会议体验。 你还可制定策略，规定会议前和会议期间相关人员可做和不可做的行为。 有关详细信息，请参阅以下文章：

- [管理员快速入门 - Microsoft Teams 中的会议和实时事件](quick-start-meetings-live-events.md)
- [中小型企业设置音频会议](audio-conferencing-smb.md)

### <a name="business-voice"></a>商务语音

[Microsoft 365 商务语音](business-voice/whats-business-voice.md) 作为优秀的解决方案，适用于用户数少于 300 的企业，可提供办公室电话系统的所有功能。 商务语音包括语音邮件、呼叫方 ID、电话系统菜单、免费电话号码等，无需管理复杂、昂贵的本地电话系统。

商务语音以 Microsoft 365 电话系统为基础，通过捆绑电话系统功能和外接程序、提供易于遵循的电话系统设置向导，简化了向组织添加语音的过程。 若组织所在的国家或地区支持[商务语音](business-voice/country-region-availability.md)，可将电话号码转至 Microsoft 365，让我们为你管理电话系统。

将 Microsoft 365 用作电话系统，便可在设备上安装 Teams 客户端，将任何设备转换为手机。 或者，若你希望使用传统台式电话或会议电话，可从多个经 Teams 认证的设备中任意选择。 无论使用哪种方法，呼叫始终将路由到你所在的位置，而由你发起的呼叫始终将包含你的办公室电话号码。

若有兴趣使用商务语音，请参阅[若要使用 Microsoft 365 商务语音，需要购买什么？](business-voice/what-to-buy.md)。

## <a name="deploy-clients"></a>部署客户端

在准备好允许用户开始使用 Teams 后，他们便可在 Windows、Mac、Linux PC 或 Android、iOS 设备上安装 Teams 客户端。 用户可直接从<https://teams.microsoft.com/downloads>下载 Teams 客户端。

请确保所有使用 Teams 的人员拥有 Teams 许可证。 有关分配 Teams 许可证的详细信息，请参阅[管理 Teams 用户访问权限](user-access.md#using-the-microsoft-365-admin-center)。

> [!TIP]
> 完成 Microsoft Learn 中的[部署 Microsoft Teams 客户端](/learn/modules/m365-teams-collab-deploy-clients/)模块，获得相关部署计划建议。

若组织通过 Microsoft Endpoint Configuration Manager、组策略或第三方分配机制将软件部署到用户计算机，请参阅[使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams](msi-deployment.md)。

若需部署 Teams 客户端的详细信息，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。

## <a name="training"></a>培训

若要了解如何培训用户使用 Teams，请参阅[ Microsoft Teams 培训](training-microsoft-teams-landing-page.md)。