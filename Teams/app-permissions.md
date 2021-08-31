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
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理员可以了解应用从Microsoft Teams请求的数据和权限。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15892a4eb3996923f7a0129805e2bb542cdc8d7c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731781"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

Microsoft Teams应用是一种将一个或多个功能聚合到可安装、升级和卸载的应用包的方法。 这些功能包括：

- 机器人
- 消息传送扩展
- 选项卡
- 连接器

应用由用户许可，由 IT 从策略角度进行管理。 但是，大多数情况下，应用的权限和风险配置文件由应用包含的功能的权限和风险配置文件定义。 因此，本文重点介绍功能级别的权限和注意事项。

下面以大写字母列出的权限（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）不会显示在[Microsoft Teams](/microsoftteams/platform/overview)开发人员文档或[Microsoft](/graph/permissions-reference)Graph 中。 它们只是本文的描述性简写。


| 标题   | 描述    |
|-----------|------------|
| ![描述决策点的图标。](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>使用下表作为指南，了解正在调查的应用正在请求哪些权限。</li></ul> |
| ![一个描述下一步骤的图标。](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>研究应用或服务本身，确定是否允许在组织中访问它。 例如，机器人发送和接收来自用户的消息，并且（企业自定义机器人除外）位于符合性边界之外。 因此，包含机器人的任何应用都需要这些权限，并且至少具有该风险配置文件。 </li></ul>|

另请参阅["请求设备权限"选项卡 Microsoft Teams。](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>全局应用权限和注意事项

### <a name="required-permissions"></a>所需权限

无

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

- 应用必须在使用条款和隐私策略链接中披露它使用的数据以及数据的用途。

- [特定于资源的许可](resource-specific-consent.md) 提供应用可以请求的一组权限，显示在应用的安装屏幕上。 若要详细了解特定于资源的许可权限，请参阅Graph[引用](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

- 应用可能还需要除特定于资源的许可权限外的权限。 安装应用后，应用可以通过Graph请求权限。 有关详细信息，请参阅了解 [Azure AD 应用程序许可体验](/azure/active-directory/develop/application-consent-experience)。 可以在 Azure 门户中配置 API 权限和许可。 若要了解有关详细信息，请参阅Azure Active Directory[框架](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>机器人和消息传送扩展

### <a name="required-permissions"></a>所需权限

- RECEIVE_MESSAGE，REPLYTO_MESSAGE。 机器人可以接收来自用户的消息并回复它们。<sup>1</sup>

- POST_MESSAGE_USER。 在用户向机器人发送消息后，机器人可以发送用户直接消息 (也称 *主动* 消息。

- GET_CHANNEL_LIST。 添加到团队的机器人可以获取团队中频道的名称和 ID 列表。

### <a name="optional-permissions"></a>可选权限

- IDENTITY。 在通道中使用时，应用的机器人可以访问团队成员的基本标识信息 (名字、姓氏、用户主体名称 [UPN]、电子邮件地址) ;在个人聊天或群组聊天中使用时，机器人可以访问这些用户的相同信息。

- POST_MESSAGE_TEAM。 允许应用的机器人随时向任何团队成员 (主动) 消息，即使用户以前从未与机器人交谈。

- 以下不是显式权限，但由清单中声明RECEIVE_MESSAGE REPLYTO_MESSAGE以及可以使用机器人的范围所暗示：
 
    - RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

- SEND_FILES，RECEIVE_FILES。<sup>2</sup> 控制机器人是否可以在个人聊天中发送和接收文件 (尚不支持群组聊天或频道聊天) 。

### <a name="considerations"></a>注意事项

- 机器人只能访问已添加到的团队或已安装机器人的用户。

- 机器人仅接收用户明确提及它们的消息。 此数据离开企业网络。

- 机器人只能回复提及它们的对话。

- 用户与机器人聊天后，如果机器人存储该用户的 ID，则它随时都可以向该用户发送直接消息。

- 从理论上讲，机器人消息可以包含指向钓鱼或恶意软件网站的链接，但用户、租户管理员或 Microsoft 可以全局阻止机器人。

- 机器人可以检索 (，并) 应用添加到的团队成员或者个人或群组聊天中单个用户的非常基本的标识信息。 若要获取有关这些用户的进一步信息，机器人必须要求他们登录到 Azure Active Directory (Azure AD) 。

- 机器人可以检索 (，并) 团队中的频道列表;此数据会离开企业网络。

- 将文件发送到机器人时，该文件会离开企业网络。 发送和接收文件需要用户批准每个文件。 

- 默认情况下，机器人无法代表用户操作，但机器人可以请求用户登录;用户登录后，机器人将拥有一个访问令牌，可以使用该令牌执行其他操作。 这些附加内容完全取决于机器人以及用户登录位置：机器人是注册到 的 Azure AD 应用，可以有自己的权限 https://apps.dev.microsoft.com/ 集。

- 每当向团队添加或删除用户时，都会通知机器人。

- 机器人看不到用户的 IP 地址或其他引用网站信息。 所有信息都来自 Microsoft。  (有一个例外：如果机器人实现了自己的登录体验，则登录 UI 将看到用户的 IP 地址和引用网站信息。) 

- 另一方面，消息传送扩展会查看用户的 IP 地址和引用网站信息。

- 应用 (以及我们的 AppSource 评审) 需要自行决定是否出于有效目的 (用户POST_MESSAGE_TEAM) 个人聊天消息。 如果滥用，用户可以阻止机器人，租户管理员可以阻止应用，并且 Microsoft 可以在必要时集中阻止机器人。

<sup>1</sup> 某些机器人仅向 (POST_MESSAGE_USER) 。 它们称为"仅通知"机器人，但术语不是指允许或不允许机器人执行什么操作，这意味着机器人不希望公开聊天体验。 Teams此字段禁用通常启用的 UI 中的功能;与公开聊天体验的机器人相比，机器人在允许执行哪些操作方面没有限制。

<sup>2</sup> 由应用的文件上的机器人对象上的 supportsFiles 布尔manifest.js控制。

> [!NOTE]
> 如果机器人有其自己的登录，则用户首次登录时，会经历另一种不同的许可体验。
>
>目前，与 Teams 应用 (机器人、选项卡、连接器或消息扩展) 内的任何功能关联的 Azure AD 权限与此处列出的 Teams 权限完全分离。

## <a name="tabs"></a>选项卡

选项卡是在外部运行的网站Teams。

### <a name="required-permissions"></a>所需权限

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>可选权限

当前 (无) 

### <a name="considerations"></a>注意事项

- 选项卡的风险配置文件几乎与在浏览器选项卡中运行的同一网站相同。 

- 选项卡还会获取其运行上下文，包括当前用户的登录名和 UPN、当前用户的 Azure AD 对象 ID、Microsoft 365 组的 ID（如果是团队) ，则驻留在 (、租户 ID 和用户的当前区域设置）。 但是，若要将这些 ID 映射到用户的信息，该选项卡必须让用户登录到 Azure AD。

## <a name="connectors"></a>连接器

当外部系统中发生事件时，连接器将消息发送到通道。

### <a name="required-permissions"></a>所需权限

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>可选权限

REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持可操作的消息，允许用户向连接器消息发布定向回复，例如，通过将响应添加到 GitHub 问题或向 Trello 卡添加日期。

### <a name="considerations"></a>注意事项

- 发布连接器消息的系统不知道邮件的发布对象或接收者：不会披露有关收件人的信息。  (Microsoft 是实际收件人，而不是租户;Microsoft 向 channel.) 

- 将连接器消息发布至通道时，没有数据离开企业网络。

- 支持可操作消息的连接器 (REPLYTO_CONNECTOR_MESSAGE权限) 也看不到 IP 地址和引用者信息;此信息将发送到 Microsoft，然后路由到以前在连接器门户中向 Microsoft 注册的 HTTP 终结点。

- 每次为通道配置连接器时，会创建该连接器实例的唯一 URL。 如果删除该连接器实例，则无法再使用 URL。

- 连接器消息不能包含文件附件。

- 连接器实例 URL 应视为机密/机密：具有该 URL 的任何人都可以发布，例如电子邮件地址。 因此，存在垃圾邮件或指向网络钓鱼或恶意软件网站的链接的风险。 如果发生这种情况，团队所有者可以删除连接器实例。

- 如果发送连接器消息的服务遭到入侵并开始发送垃圾邮件/钓鱼/恶意软件链接，租户管理员可以阻止创建新的连接器实例，Microsoft 可以集中阻止它们。

> [!NOTE]
> 目前无法知道哪些连接器支持可操作消息 (REPLYTO_CONNECTOR_MESSAGE权限) 。

## <a name="outgoing-webhooks"></a>传出 Webhook

*传出 Webhook* 由团队所有者或团队成员进行创建。 它们不是应用Teams功能;为了完整，包含此信息。

### <a name="required-permissions"></a>所需权限

RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收来自用户的消息并回复他们。

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

- 传出 Webhook 类似于机器人，但权限较少。 必须明确提及它们，就像机器人一样。

- 注册传出 Webhook 时，会生成一个机密，该机密允许传出 Webhook 验证发送方是否Microsoft Teams恶意攻击者。 此机密应保留为机密;有权访问它的任何人都可以模拟Microsoft Teams。 如果机密泄露，可以删除并重新创建传出 Webhook，并生成新的机密。

- 虽然可以创建不验证机密的传出 Webhook，但建议不要这样做。

- 除了接收和答复消息外，传出 Webhook 无法执行许多操作：它们无法主动发送消息，无法发送或接收文件，除了接收和答复消息之外，他们无法执行机器人可以执行的其他操作。