---
title: Microsoft Teams 应用权限和考虑事项
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 了解贵组织要求的数据和权限应用。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e841943a4a6bf5f6fcc242d83f4a02d4ca1aa06
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241969"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

通过 Microsoft Teams 应用可以将一项或多项功能汇聚到一个可以安装、升级和卸载的_应用包_。 这些功能包括：

- 聊天机器人
- 消息传递扩展
- 选项卡
- 连接器

从策略角度来看，应用由用户许可并由 IT 管理。 但是, 大多数情况下, 应用的权限和风险配置文件由应用所包含功能的权限和风险配置文件定义。 因此，本文主要介绍功能级别的权限和考虑事项。

下文所列大写字母的权限（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）未出现在 [Microsoft Teams 开发人员文档](https://aka.ms/teamsdevdocs)或 [Microsoft Graph 的权限](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中的任何地方。 使用它们只是为了在本文中进行简要说明。


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>使用下表作为指南, 了解正在调查的应用所请求的权限。</li></ul> |
| ![描述下一步的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>研究应用或服务本身, 确定是否希望允许在组织内访问它。 例如, bot 从用户发送和接收消息, 除了企业业务线机器人外, 它们还位于合规性边界之外。 因此, 任何包含机器人的应用都需要这些权限, 并且至少具有该风险配置文件。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>全局应用权限和注意事项

### <a name="required-permissions"></a>所需权限

无

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>考虑事项

应用必须公开它所使用的数据以及数据在其使用条款和隐私策略链接中的用途。</td>

## <a name="bots-and-messaging-extensions"></a>机器人和消息扩展

### <a name="required-permissions"></a>所需权限

- RECEIVE_MESSAGE、REPLYTO_MESSAGE。 聊天机器人可以接收来自用户的消息以及回复用户。<sup>1</sup>

- POST_MESSAGE_USER。 用户将消息发送到 bot 后, 机器人可以随时发送用户直接消息 (也称为*主动消息*)。

- GET_CHANNEL_LIST。 添加到团队的聊天机器人可以获取团队中的频道的名称和 ID 列表。

### <a name="optional-permissions"></a>可选权限

- 3x3. 当它在频道中使用时, 应用的智能机器人可以访问团队成员的基本标识信息 (名字、姓氏、用户主体名称 [UPN]、电子邮件地址);在个人或群组聊天中使用时, 机器人可以访问这些用户的相同信息。

- POST_MESSAGE_TEAM. 允许应用的 bot 随时向任何团队成员发送 (主动) 消息, 即使用户以前从未与 bot 聊天。

- 以下内容不是显式权限, 而是由 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用机器人的范围 (在清单中声明) 中隐含的。
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES.<sup>2</sup>控制机器人是否可以在个人聊天中发送和接收文件 (对于群组聊天或频道尚不支持)。

### <a name="considerations"></a>考虑事项

- Bot 只能访问已添加的团队或已安装他们的用户。

- Bot 仅接收用户明确提及的消息。 此数据将离开公司网络。

- 机器人只能回复所提及的对话。

- 在用户使用机器人 conversed 后, 如果 bot 存储该用户的 ID, 它可以随时发送该用户直接消息。

- 从理论上讲, bot 邮件包含指向网络钓鱼或恶意网站的链接, 但用户可以通过 Microsoft、租户管理员或由 Microsoft 全局阻止。

- Bot 可以为应用添加到的团队成员或个人或群组聊天中的单个用户检索和存储非常基本的标识信息。 若要获取有关这些用户的详细信息, 机器人必须要求他们登录到 Azure Active Directory (Azure AD)

- 机器人可以检索团队中的频道列表, 并可以存储这些频道的列表;此数据将离开公司网络。

- 将文件发送到机器人时, 该文件将离开公司网络。 发送和接收文件需要对每个文件进行用户审批。 

- 默认情况下, bot 无法代表用户执行操作, 但机器人可以让用户登录;一旦用户登录, bot 将拥有一个访问令牌, 它可以执行其他操作。 这些附加内容的具体内容取决于 bot 和用户登录的位置: bot 是注册的 Azure AD 应用https://apps.dev.microsoft.com/ , 并且可以拥有自己的权限集。

- 只要向团队中添加或删除用户, 就会通知机器人。

- Bot 看不到用户的 IP 地址或其他引用信息。 所有信息均来自 Microsoft。 (有一个例外: 如果机器人实现自己的登录体验, 登录用户界面将看到用户的 IP 地址和引用信息。)

- 另一方面, 邮件扩展功能请参阅用户的 IP 地址和引用信息。

- 应用指南 (和我们的 AppSource 审查流程) 需要在向用户 (通过 POST_MESSAGE_TEAM 权限) 发布个人聊天消息时决定是否有效。 在滥用的情况下, 用户可以阻止机器人, 租户管理员可以阻止该应用, 并且 Microsoft 可以在必要时集中阻止机器人。

<sup>1</sup>某些机器人仅发送邮件 (POST_MESSAGE_USER)。 它们称为 "仅通知" 功能人员, 但术语没有指允许或不允许机器人执行的操作, 这意味着机器人不希望公开会话体验。 团队使用此字段在 UI 中禁用通常启用的功能;与确实公开会话体验的 bot 相比, 机器人不受允许的功能。

<sup>2</sup>由应用程序的 supportsFiles 文件中的 bot 对象上的布尔属性控制。

> [!NOTE]
> 如果机器人有自己的登录, 则在用户第一次登录时有另一种不同的同意体验。
>
>目前, 与团队应用 (机器人、选项卡、连接器或消息扩展) 内的任何功能相关联的 Azure AD 权限完全独立于此处列出的团队权限。

## <a name="tabs"></a>选项卡

选项卡是在团队内运行的网站。

### <a name="required-permissions"></a>所需权限

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>可选权限

无 (当前)

### <a name="considerations"></a>考虑事项

- 选项卡的风险配置文件与在浏览器选项卡中运行的同一网站几乎完全相同。 

- 选项卡还获取正在运行的上下文, 包括当前用户的登录名和 UPN、当前用户的 Azure AD 对象 ID、它所在的 Office 365 组的 ID (如果它是团队), 租户 ID以及用户的当前区域设置。 但是, 若要将这些 Id 映射到用户的信息, 选项卡将必须使用户登录到 Azure AD。

## <a name="connectors"></a>接口

当发生外部系统中的事件时, 连接器将消息发送到频道。

### <a name="required-permissions"></a>所需权限

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>可选权限

REPLYTO_CONNECTOR_MESSAGE. 某些连接器支持可操作的消息, 这些消息允许用户将目标回复发布到连接器消息, 例如, 将响应添加到 GitHub 问题或将日期添加到 Trello 卡。

### <a name="considerations"></a>考虑事项

- 发布连接器消息的系统不知道它的发件人或接收邮件的人员: 不透露有关该收件人的任何信息。 (Microsoft 是实际的收件人, 而不是租户;Microsoft 会向该频道发送实际帖子。)

- 将连接器消息发送到频道时, 任何数据都不会离开公司网络。

- 支持可操作消息 (REPLYTO_CONNECTOR_MESSAGE 权限) 的连接器也看不到 IP 地址和引用信息;此信息将发送到 Microsoft, 然后路由到以前在连接器门户中注册到 Microsoft 的 HTTP 终结点。

- 每次为通道配置连接器时, 都会创建该连接器实例的唯一 URL。 如果该连接器实例已删除, 则无法再使用该 URL。

- 连接器消息不能包含文件附件。

- 连接器实例 URL 应视为机密/机密: 拥有该 URL 的任何人都可以发布到该 url, 例如电子邮件地址。 因此, 存在垃圾邮件或链接到网络钓鱼或恶意软件站点的风险。 如果发生这种情况, 团队所有者可以删除连接器实例。

- 如果发送连接器消息的服务遭到破坏并开始发送垃圾邮件/网络钓鱼/恶意软件链接, 租户管理员可以阻止创建新的连接器实例, 并且 Microsoft 可以集中阻止它们。

> [!NOTE]
> 目前不能知道哪些连接器支持可操作的消息 (REPLYTO_CONNECTOR_MESSAGE 权限)。

## <a name="outgoing-webhooks"></a>传出 webhooks

如果为租户启用旁加载, 则由团队所有者或团队成员实时创建*传出 webhooks* 。 它们不是团队应用的功能;包含此信息是为了实现完整性。

### <a name="required-permissions"></a>所需权限

RECEIVE_MESSAGE, REPLYTO_MESSAGE. 可接收来自用户的消息并答复他们。

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>考虑事项

- 传出 webhooks 类似于 bot, 但权限较少。 它们必须明确提及, 就像机器人一样。

- 注册传出 webhook 后, 将生成一个机密, 它允许传出 webhook 验证发件人是否为 Microsoft 团队, 而不是恶意攻击者。 此机密应保密;有权访问的任何人都可以模仿 Microsoft 团队。 如果机密遭到破坏, 则可以删除并重新创建传出 webhook, 并且将生成新的密码。

- 尽管可以创建不验证机密的传出 webhook, 但我们建议您不要使用它。

- 除了接收和答复邮件之外, 传出 webhooks 无法主动发送邮件、无法发送或接收文件, 他们也无法执行除接收和答复邮件之外的任何其他机器人功能。
