---
title: Microsoft Teams 应用权限和考虑事项
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理员可以了解Microsoft Teams应用从其组织请求的数据和权限。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 925136660ef6adda6374fab1acccf10a2b9f1722
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190282"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

Microsoft Teams应用是将一个或多个功能聚合到可安装、升级和卸载的应用的一种方式。 应用功能包括：

* 机器人
* 消息传递扩展插件
* 选项卡
* 连接

作为管理员，你只管理应用。 但是，本文重点介绍功能级别的权限和注意事项，因为应用中的功能会影响应用所需的权限和风险配置文件。 对于使用情况，应用由用户同意，并由 IT 专业人员从策略角度进行管理。

例如`RECEIVE_MESSAGE``REPLYTO_MESSAGE`，下面大写字母中列出的权限仅用于说明和说明目的。 这些字符串或权限不会出现在[Microsoft Teams开发人员文档](/microsoftteams/platform/overview)或 [Microsoft Graph 权](/graph/permissions-reference)限的任何位置。

## <a name="global-app-permissions-and-considerations"></a>全局应用权限和注意事项

### <a name="required-permissions"></a>所需权限

无

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

* 应用必须披露其使用的数据及其使用条款和隐私策略链接中的数据用途。

* [特定于资源的许可](resource-specific-consent.md) 提供了一组应用可以请求的权限，这些权限显示在应用的安装屏幕上。 若要详细了解特定于资源的许可权限，请[参阅Graph权限参考](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

* 应用可能还需要资源特定许可权限以外的权限。 安装应用后，应用可以通过同意提示请求Graph权限。 若要了解详细信息，请参阅 [了解 Azure AD 应用程序同意体验](/azure/active-directory/develop/application-consent-experience)。 可以在Azure 门户中配置 API 权限和许可。 若要了解详细信息，请参阅[Azure Active Directory许可框架](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>机器人和消息传递扩展

### <a name="required-permissions"></a>所需权限

* RECEIVE_MESSAGE，REPLYTO_MESSAGE：机器人可以接收来自用户的消息并回复他们。<sup>1</sup>

* POST_MESSAGE_USER：用户向机器人发送消息后，机器人可以随时发送用户直接消息 (也称为 *主动消息* 。

* GET_CHANNEL_LIST：添加到团队的机器人可以获取团队中频道的名称和 ID 列表。

### <a name="optional-permissions"></a>可选权限

* 标识：在频道中使用时，应用的机器人可以访问团队成员的基本标识信息 (名字、姓氏、用户主体名称 [UPN]、电子邮件地址) 。 在个人或群组聊天中使用时，机器人可以访问这些用户的相同信息。

* POST_MESSAGE_TEAM：允许应用的机器人随时向团队成员发送直接 (主动) 消息，即使用户从未与机器人交互。

* 下面不是显式权限，但由RECEIVE_MESSAGE和REPLYTO_MESSAGE以及机器人可以使用的范围（在清单中声明）隐含：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* 下面不是显式权限，但由RECEIVE_MESSAGE和REPLYTO_MESSAGE以及机器人可以使用的范围（在清单中声明）隐含：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* SEND_FILES，RECEIVE_FILES：<sup>2</sup> 控制机器人是否可以发送和接收个人聊天中的文件 (尚不支持群聊或频道) 。

### <a name="considerations"></a>注意事项

* 机器人仅有权访问已添加到的团队或已安装它们的用户。

* 机器人仅接收用户明确提及的消息。 此数据离开公司网络。

* 机器人只能回复被提及的对话。

* 当用户与机器人交谈时，如果机器人存储用户的 ID，它可以随时发送用户直接消息。

* 从理论上讲，机器人消息可能包含网络钓鱼或恶意软件网站的链接。 但是，用户、租户管理员或 Microsoft 可以全局阻止机器人。 [应用验证和验证检查](overview-of-app-validation.md)可确保任何虚假应用在存储Teams不可用。

* 机器人可以检索 (，并可能为已添加应用的团队成员或个人或群聊中的单个用户存储) 基本标识信息。 若要获取有关这些用户的详细信息，机器人必须要求他们登录到Azure Active Directory (Azure AD) 。

* 机器人可以检索 (，并可能将) 频道列表存储在团队中;此数据离开公司网络。

* 默认情况下，机器人无法代表用户执行操作，但机器人可以要求用户登录;用户一登录，机器人就会有一个访问令牌，可以使用该令牌执行其他操作。 这些其他内容的确切内容取决于机器人以及用户登录的位置：机器人是注册到 https://apps.dev.microsoft.com/ 的 Azure AD 应用，可以具有自己的权限集。

* 将文件发送到机器人时，该文件将离开公司网络。 发送和接收文件需要用户批准每个文件。

* 默认情况下，机器人无法代表用户执行操作，但机器人可以要求用户登录;用户一登录，机器人就会有一个访问令牌，可以使用该令牌执行其他操作。 这些附加内容究竟取决于机器人以及用户登录的位置：机器人是在 [应用程序注册门户](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) 中注册的 Azure AD 应用，可以有自己的权限集。

* 每当向团队添加或删除用户时，都会通知机器人。

* 机器人看不到用户的 IP 地址或其他引用者信息。 所有信息都来自 Microsoft。  (有一个例外：如果机器人实现自己的登录体验，登录 UI 将看到用户的 IP 地址和引用者信息。) 

* 另一方面，消息传递扩展会看到用户的 IP 地址和引用者信息。

* 应用指南 (和 AppSource 审阅过程) 需要根据有效目的，通过POST_MESSAGE_TEAM权限) 向 (用户发布个人聊天消息时自行决定。 如果发生滥用，用户可以阻止机器人，租户管理员可以阻止应用，Microsoft 可以根据需要集中阻止机器人。

<sup>1</sup> 某些机器人仅发送消息 (POST_MESSAGE_USER) 。 它们被称为“仅通知”机器人，但该术语不指允许或不允许机器人执行的操作，这意味着机器人不想公开聊天体验。 Teams使用此字段禁用通常会启用的 UI 中的功能;与公开会话体验的机器人相比，机器人在允许执行的操作中不受限制。

<sup>2</sup> 受应用文件中 `manifest.json` 机器人对象上的 supportsFiles 布尔属性控制。

> [!NOTE]
> 如果机器人有自己的登录，则用户第一次登录时会有第二次不同的许可体验。
>
>目前，与Teams应用 (机器人、选项卡、连接器或消息传递扩展) 中的任何功能关联的 Azure AD 权限与此处列出的Teams权限完全分离。

## <a name="tabs"></a>选项卡

选项卡是Teams内运行的网站。

### <a name="required-permissions"></a>所需权限

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>可选权限

当前未 () 

### <a name="considerations"></a>注意事项

* 选项卡的风险配置文件几乎与在浏览器选项卡中运行的同一网站相同。

* 选项卡还会获取运行它的上下文，包括当前用户的登录名称和 UPN、当前用户的 Azure AD 对象 ID、Microsoft 365组的 ID（如果是团队) 、租户 ID 和用户的当前区域设置） (。 但是，若要将这些 ID 映射到用户的信息，该选项卡必须使用户登录到 Azure AD。

## <a name="connectors"></a>连接

当外部系统中发生事件时，连接器会将消息发布到通道。

### <a name="required-permissions"></a>所需权限

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>可选权限

REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持可操作消息，这些消息允许用户帖子针对连接器消息的答复，例如通过添加对GitHub问题的响应或将日期添加到 Trello 卡片。

### <a name="considerations"></a>注意事项

* 发布连接器消息的系统不知道它向谁发布或接收邮件的用户：未披露有关收件人的信息。  (Microsoft 是实际收件人，而不是租户;Microsoft 将实际帖子到 channel.) 

* 当连接器消息发布到频道时，没有数据离开公司网络。

* 支持可操作消息 (REPLYTO_CONNECTOR_MESSAGE权限) 连接器也看不到 IP 地址和引用者信息;此信息将发送到 Microsoft，然后路由到以前在连接器门户中注册到 Microsoft 的 HTTP 终结点。

* 每次为通道配置连接器时，都会为该连接器实例创建唯一 URL。 如果删除该连接器实例，则无法再使用该 URL。

* 连接器消息不能包含文件附件。

* 连接器实例 URL 应被视为机密/机密：任何具有该 URL 的用户都可以帖子该 URL，如电子邮件地址。 因此，存在一些垃圾邮件或网络钓鱼或恶意软件网站链接的风险。 如果发生这种情况，团队所有者可以删除连接器实例。

* 如果发送连接器消息的服务遭到入侵并开始发送垃圾邮件/网络钓鱼/恶意软件链接，则租户管理员可能会阻止创建新的连接器实例，并且 Microsoft 可以集中阻止它们。

> [!NOTE]
> 目前无法知道哪些连接器支持可操作消息 (REPLYTO_CONNECTOR_MESSAGE权限) 。

## <a name="outgoing-webhooks"></a>传出 Webhook

_传出 Webhook_ 由团队所有者或团队成员创建。 它们不是Teams应用的功能;此信息是为完整性而包含的。

### <a name="required-permissions"></a>所需权限

RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收来自用户的消息并回复他们。

### <a name="optional-permissions"></a>可选权限

无

### <a name="considerations"></a>注意事项

* 传出 Webhook 类似于机器人，但特权较少。 必须像机器人一样显式提及它们。

* 注册传出 Webhook 时，将生成一个机密，允许传出 Webhook 验证发件人是否Microsoft Teams而不是恶意攻击者。 此机密应保留机密;任何有权访问它的人都可以模拟Microsoft Teams。 如果机密遭到泄露，则可以删除和重新创建传出 Webhook，并生成新的机密。

* 虽然可以创建不验证机密的传出 Webhook，但我们建议不要使用它。

* 除了接收和答复消息之外，传出 Webhook 不能做太多操作：它们不能主动发送消息，无法发送或接收文件，他们无法执行机器人可以执行的任何其他操作，除了接收和答复消息。
