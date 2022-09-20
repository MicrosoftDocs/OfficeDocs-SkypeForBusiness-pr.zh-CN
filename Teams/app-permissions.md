---
title: Microsoft Teams 应用权限和考虑事项
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理员可以了解 Microsoft Teams 应用从其组织请求的数据和权限。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 42044bf8f74c99b27db724e87ee35e700491aa8e
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837192"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

Microsoft Teams 应用是一种将一个或多个功能聚合到可安装、升级和卸载的应用中的方法。 应用的功能包括：

* 机器人
* 消息传递扩展
* 选项卡
* 连接器

作为管理员，你仅管理应用。 但是，本文重点介绍功能级别的权限和注意事项，因为应用中的功能会影响应用所需的权限和风险配置文件。 对于使用情况，应用由用户同意，并由 IT 专业人员从策略角度进行管理。

下面以大写字母列出的权限，例如`RECEIVE_MESSAGE`和 `REPLYTO_MESSAGE`仅用于说明和说明目的。 这些字符串或权限不会出现在 [Microsoft Teams 开发人员文档](/microsoftteams/platform/overview) 或 [Microsoft Graph权](/graph/permissions-reference)限中的任何位置。

## <a name="global-app-permissions-and-considerations"></a>全局应用权限和注意事项

### <a name="required-permissions"></a>所需权限

无

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

* 应用必须在其使用条款和隐私策略链接中披露它使用的数据以及数据的用途。

* [特定于资源的许可](resource-specific-consent.md) 提供应用可以请求的一组权限，这些权限显示在应用的安装屏幕上。 若要了解有关特定于资源的许可权限的详细信息，请参阅 [Graph 权限参考](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

* 应用可能还需要资源特定许可权限以外的权限。 安装应用后，应用可以通过同意提示请求 Graph 权限。 若要了解详细信息，请参阅 [了解Azure AD应用程序许可体验](/azure/active-directory/develop/application-consent-experience)。 可以在Azure 门户中配置 API 权限和许可。 若要了解详细信息，请 [参阅Azure Active Directory同意框架](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>机器人和消息传递扩展

### <a name="required-permissions"></a>所需权限

* RECEIVE_MESSAGE，REPLYTO_MESSAGE：机器人可以接收来自用户的消息并回复他们。<sup>1</sup>

* POST_MESSAGE_USER：用户向机器人发送消息后，机器人可以随时发送用户直接消息（也称为 *主动消息* ）。

* GET_CHANNEL_LIST：添加到团队的机器人可以获取团队中频道的名称和 ID 列表。

### <a name="optional-permissions"></a>可选权限

* 标识：在频道中使用时，应用的机器人可以访问团队成员的基本标识信息（名字、姓氏、用户主体名称 [UPN]、电子邮件地址）。 当在个人或群组聊天中使用它时，机器人可以访问这些用户的相同信息。

* POST_MESSAGE_TEAM：允许应用的机器人随时向团队成员发送直接（主动）消息，即使用户从未与机器人交互。

* 下面不是显式权限，但由RECEIVE_MESSAGE和REPLYTO_MESSAGE以及可以在其中使用机器人的范围（在清单中声明）隐含：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* 下面不是显式权限，但由RECEIVE_MESSAGE和REPLYTO_MESSAGE以及可以在其中使用机器人的范围（在清单中声明）隐含：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* SEND_FILES，RECEIVE_FILES：<sup>2</sup> 控制机器人是否可以在个人聊天中发送和接收文件（尚不支持群组聊天或频道）。

### <a name="considerations"></a>注意事项

* 机器人只能访问已添加到的团队或已安装它们的用户。

* 机器人仅接收用户显式提及的消息。 此数据离开公司网络。

* 机器人只能回复提及它们的对话。

* 当用户与机器人进行交互时，如果机器人存储用户的 ID，则它可以随时发送用户直接消息。

* 从理论上讲，机器人消息可能包含指向网络钓鱼或恶意软件站点的链接。 但是，用户、租户管理员或 Microsoft 可以全局阻止机器人。 [应用验证和验证检查](overview-of-app-validation.md) 可确保 Teams 应用商店中不提供任何虚假应用。

* 机器人可以检索（并可能存储）应用已添加到的团队成员的基本标识信息，或在个人或群组聊天中为单个用户检索基本标识信息。 若要获取有关这些用户的更多信息，机器人必须要求他们登录到Azure Active Directory（Azure AD）。

* 机器人可以检索（并可能存储）团队中的频道列表;此数据将离开公司网络。

* 默认情况下，机器人无法代表用户执行操作，但机器人可以要求用户登录;用户登录后，机器人将拥有一个访问令牌，可以使用该令牌执行其他操作。 这些其他内容的确切内容取决于机器人以及用户登录的位置：机器人是在 https://apps.dev.microsoft.com/ 注册的Azure AD应用，可以有自己的权限集。

* 将文件发送到机器人时，该文件将离开公司网络。 发送和接收文件需要用户批准每个文件。

* 每当向团队添加或删除用户时，都会通知机器人。

* 机器人看不到用户的 IP 地址或其他引用者信息。 所有信息都来自 Microsoft。 （有一个例外：如果机器人实现自己的登录体验，登录 UI 将看到用户的 IP 地址和引用者信息。）

* 另一方面，消息传递扩展会看到用户的 IP 地址和引用者信息。

* 出于有效目的，应用指南（和 AppSource 审核流程）要求在向用户发布个人聊天消息（通过POST_MESSAGE_TEAM权限）时自行决定。 如果滥用，用户可以阻止机器人，租户管理员可以阻止应用，Microsoft 可以根据需要集中阻止机器人。

<sup>1</sup> 某些机器人仅发送消息（POST_MESSAGE_USER）。 它们称为“仅通知”>机器人，但术语不指允许或不允许机器人执行的操作，这意味着机器人不希望公开对话体验。 Teams 使用此字段禁用通常会启用的 UI 中的功能;与公开对话体验的机器人相比，机器人在允许执行的操作方面不受限制。

<sup>2</sup> 受应用的 `manifest.json` 文件中机器人对象的 supportsFiles 布尔属性控制。

> [!NOTE]
> 如果机器人有自己的登录，则用户首次登录时会获得第二次同意体验。—different—consent experience。
>
>目前，与 Teams 应用中的任何功能（机器人、选项卡、连接器或消息传递扩展）关联的Azure AD权限与此处列出的 Teams 权限完全分开。

## <a name="tabs"></a>选项卡

选项卡是在 Teams 中运行的网站。

### <a name="required-permissions"></a>所需权限

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>可选权限

无（当前）

### <a name="considerations"></a>注意事项

* 选项卡的风险配置文件几乎与在浏览器选项卡中运行的同一网站相同。

* 选项卡还获取运行它的上下文，包括当前用户的登录名称和 UPN、当前用户的Azure AD对象 ID、它所在的Microsoft 365组的 ID（如果是团队）、租户 ID 和用户的当前区域设置。 但是，若要将这些 ID 映射到用户的信息，该选项卡必须使用户登录到Azure AD。

## <a name="connectors"></a>连接器

外部系统中发生事件时，连接器会将消息发布到通道。

### <a name="required-permissions"></a>所需权限

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>可选权限

REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持可操作邮件，允许用户将目标答复发布到连接器消息，例如通过添加对 GitHub 问题的响应或向 Trello 卡添加日期。

### <a name="considerations"></a>注意事项

* 发布连接器消息的系统不知道其发布到的人员或接收邮件的人员：不会披露有关收件人的信息。 （Microsoft 是实际收件人，而不是租户;Microsoft 会将实际帖子发布到频道。）

* 当连接器消息发布到通道时，公司网络中没有数据。

* 支持可操作消息（REPLYTO_CONNECTOR_MESSAGE权限）的连接器也看不到 IP 地址和引用者信息;此信息将发送到 Microsoft，然后路由到以前在连接器门户中向 Microsoft 注册的 HTTP 终结点。

* 每次为通道配置连接器时，都会创建该连接器实例的唯一 URL。 如果删除该连接器实例，则无法再使用该 URL。

* 连接器消息不能包含文件附件。

* 连接器实例 URL 应被视为机密/机密：具有该 URL 的任何人都可以发布到该 URL，如电子邮件地址。 因此，存在一些垃圾邮件或网络钓鱼或恶意软件网站链接的风险。 如果发生这种情况，则团队所有者可以删除连接器实例。

* 如果发送连接器消息的服务遭到入侵并开始发送垃圾邮件/网络钓鱼/恶意软件链接，租户管理员可以阻止创建新的连接器实例，Microsoft 可以集中阻止它们。

> [!NOTE]
> 目前无法知道哪些连接器支持可操作邮件（REPLYTO_CONNECTOR_MESSAGE权限）。

## <a name="outgoing-webhooks"></a>传出 webhook

_传出 Webhook_ 由团队所有者或团队成员创建。 它们不是 Teams 应用的功能;包含此信息是为了实现完整性。

### <a name="required-permissions"></a>所需权限

RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收来自用户的消息并回复他们。

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

* 传出 Webhook 类似于机器人，但特权较少。 必须像机器人一样显式提及它们。

* 注册传出 Webhook 时，将生成一个机密，允许传出 Webhook 验证发件人是否为 Microsoft Teams 而不是恶意攻击者。 此机密应保留为机密;有权访问它的任何人都可以模拟 Microsoft Teams。 如果机密遭到入侵，请删除并重新创建传出 Webhook 以生成新机密。

* 尽管可以创建不验证机密的传出 Webhook，但我们建议对其进行验证。

* 除了接收和答复邮件之外，传出 Webhook 无法执行很多操作：无法主动发送邮件、无法发送或接收文件、无法执行机器人可执行的任何其他操作（接收和答复邮件除外）。
