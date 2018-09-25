---
title: Microsoft Teams 应用权限和考虑事项
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: 了解贵组织要求的数据和权限应用。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 960f54f27b7019d15d287c637c7c58f73dfdef0f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014184"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

Microsoft 团队应用程序是一种方法，以聚合到可安装、 升级和卸载_应用程序包_的一个或多个功能。 功能包括：

-   聊天机器人
-   消息传递扩展
-   选项卡
-   连接器

应用程序是由用户同意和由 IT 从策略角度。 但是，大多数情况下，应用程序的权限和风险配置文件由定义的权限和风险配置文件，它包含的功能。 因此，本文重点介绍权限和功能级别的注意事项。

以大写字母形式，例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE，下面列出的权限不出现在[Microsoft 团队开发人员文档](https://aka.ms/teamsdevdocs)或[Microsoft Graph 权限](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)的任何位置。 它们只需描述性简写出于本文目的。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>请使用下面各表来指导你了解你调查的应用需要的权限。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>研究应用程序或服务本身来确定您是否要允许组织内的对其进行访问。 例如，bot 发送和接收来自用户，邮件和 — 企业业务线 bot 除外 — 合规性边界外，它们位于。 因此，包括 bot 任何应用程序需要这些权限，并且至少具有风险的配置文件。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>全局应用权限和考虑事项

<table>
  <tr>
    <th width="25%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">无</td>
    <td valign="top">无</td>
    <td valign="top">应用必须在其使用条款和隐私策略链接中公开其使用的数据和数据用途。</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>聊天机器人和消息传递扩展

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE，REPLYTO_MESSAGE。 自动程序可以接收来自用户邮件和答复。<sup>1</sup></li><li>POST_MESSAGE_USER。 用户已向 bot 发送一条消息后，bot 可以发送用户直接邮件 （也称为_预防性消息_） 在任何时间。</li><li>GET_CHANNEL_LIST。 自动程序添加到团队可以获取团队中的名称和 Id 的通道的列表。</li></ul></td>
    <td valign="top"><ul><li>标识。 应用程序的自动程序在频道使用它时，可以访问工作组成员 （名字、 姓氏、 用户主体名称 [UPN]、 电子邮件地址）; 基本标识的信息个人或组聊天中使用它时，自动程序可以访问这些用户相同的信息。</li><li> POST_MESSAGE_TEAM。 允许应用程序的自动程序在任何时候，将直接 （主动） 邮件发送到任何团队成员即使用户具有从不讨论到 bot 之前。</li><li>以下权限不是显式权限，而是 RECEIVE_MESSAGE、REPLYTO_MESSAGE 以及可以使用聊天机器人的范围隐含的权限，并在 manifest 中声明： <ul><li>RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES、RECEIVE_FILES。<sup>3</sup> 控制聊天机器人是否可以在个人聊天中发送和接收文件（在群组聊天和频道中还不支持）。</li></ul></td>
    <td valign="top"><ul><li>聊天机器人只能访问添加了它们的团队或安装了它们的用户。</li><li>自动程序仅接收顺序它们明确提到用户的消息。 此数据离开企业网络。</li><li>    聊天机器人只能回复提及它们的对话。</li><li>用户与聊天机器人交谈后，如果聊天机器人存储了该用户的 ID，它随时可以向该用户发送私信。 </li><li>从理论上来说，聊天机器人消息可能包含钓鱼站点或恶意软件站点的链接，但用户或租户管理员可以阻止聊天机器人，Microsoft 也可以全局阻止聊天机器人。 </li><li>自动程序可以检索 （和可能存储） 应用程序已添加到，工作组成员或单个用户的个人或组聊天非常基本标识信息。 以获取更多有关这些用户的信息，自动程序必须要求其登录到 Azure Active Directory (Azure AD)。 </li><li>聊天机器人可以检索（并可能存储）团队中的频道列表；此数据将离开公司网络。 </li><li>当文件发送到自动程序时，该文件离开企业网络。 发送和接收文件的每个文件需要用户审批。 </li><li>默认情况下自动程序没有能够代表用户，但 bot 可以要求用户登录;只要用户登录时，自动程序将具有访问令牌与它可以执行其他操作。 完全内容这些其他事项取决于 bot 和用户登录： 自动程序是在注册 Azure AD 应用程序<a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a>并且可以具有自己的权限集。</li><li>每当在团队中添加或删除用户时，聊天机器人都会收到通知。</li><li>Bot 看不到用户的 IP 地址或其他引用网站信息。 来自 Microsoft 的所有信息。 (还有一个例外： 如果 bot 实现自己登录体验，登录 UI 看到用户的 IP 地址和引用网站信息。)</li><li>从另一方面来看，消息传递扩展会看到用户的 IP 地址和其他引用网站信息。</li><li>应用程序准则 （和 AppSource 审阅过程） 需要出于有效目的而 （通过 POST_MESSAGE_TEAM 权限中） 向用户发布个人聊天消息中的决定。 发生滥用，用户可以阻止 bot，租户管理员可以阻止该应用程序，以及 Microsoft 可以根据需要集中阻止自动程序。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">某些 bot 只能发送消息 (POST_MESSAGE_USER)。 其称作"仅限通知"自动程序，但术语不涉及哪些 bot 是允许或不允许执行，这意味着 bot 不想要公开交谈体验。 团队使用此字段禁用通常会启用; 在 UI 中的功能在什么它已允许执行不要公开交谈体验的 bot 相比，bot 不受限制。</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">当前处于开发人员预览版中。</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">正在开发人员预览。 为由<code>supportsFiles</code>上的应用程序 manifest.json 文件中的自动程序对象的布尔值属性。</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>如果聊天机器人自己登录，则用户首次登录时会有另一种不同的许可体验。</li><li>当前，与 Teams 应用中的任何功能（聊天机器人、选项卡、连接器或消息传递扩展）关联的 Azure AD 权限与此处所列的 Teams 权限完全分开。</li></ul>


## <a name="tabs"></a>选项卡

选项卡是 Teams 中运行的网站。

<table>
  <tr>
    <th width="25%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">无（当前）。</td>
    <td valign="top"><ul><li>选项卡的风险配置文件与浏览器选项卡中运行的同一网站几乎相同。 </li><li>选项卡还获取的上下文中运行，包括登录名和 UPN 当前用户 Azure AD 对象的当前用户的 ID 的 Office 365 组 （工作组） 其所在，租户 ID，并且用户的当前区域设置 ID。 但是，若要将这些 Id 映射到用户的信息，选项卡将必须使用户登录到 Azure AD。</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>连接器

连接器在外部系统发生事件时向频道发布消息。

  <table>
  <tr>
    <th width="25%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持_可操作的消息_，使用户可以通过添加响应的 GitHub 问题或日期向 Trello 卡片例如张贴目标的答复连接器邮件。</td>
    <td valign="top"><ul><li>文章连接器邮件系统不知道其发布到或接收邮件的用户： 披露关于该收件人无信息。 （Microsoft 是实际的收件人，租户;Microsoft 执行的实际发布到该频道。）</li><li>向频道发布连接器消息时，没有任何数据离开公司网络。</li><li>支持可操作消息（REPLYTO_CONNECTOR_MESSAGE 权限）的连接器也不会看到 IP 地址和引用网站信息；此信息将发送给 Microsoft，然后路由到以前在连接器门户中向 Microsoft 注册的 HTTP 终结点。</li><li>连接器配置通道，每次创建该连接器实例的唯一的 URL。 如果删除该连接器实例，则可以不再使用的 URL。</li><li>连接器消息不能包含文件附件。</li><li>URL 应视为机密/机密的连接器实例： 任何人都 URL 可以发布，喜欢的电子邮件地址。 因此，是一些风险的垃圾邮件或网络钓鱼或恶意软件的网站的链接。 如果的发生，团队所有者可以删除的连接器实例。</li><li>如果发送连接器消息的服务受到破坏并开始发送垃圾消息/钓鱼链接/恶意软件链接，租户管理员可以阻止创建新的连接器实例，并且 Microsoft 可以集中阻止它们。</li></ul></td>
  </tr>
</table>

> [!Note]
> 当前，无法知道哪些连接器支持可操作消息（REPLYTO_CONNECTOR_MESSAGE 权限）。


## <a name="outgoing-webhooks"></a>传出 Webhook

_传出 webhooks_创建动态团队所有者或团队成员如果 sideloading 启用租户。 它们不是团队应用程序; 的功能完整性包含此信息。

<table>
  <tr>
    <th width="25%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收来自用户邮件和答复。</td>
    <td valign="top">无</td>
    <td valign="top"><ul><li>传出 webhooks 类似于 bot 但具有更少的权限。 它们必须是明确提到，就像 bot。</li><li>传出 webhook 注册时，会生成_密码_，此程序允许传出 webhook 验证发件人，而不是恶意攻击者是 Microsoft 团队。 此密钥应保持机密;有权访问它的任何人都可以模拟的 Microsoft 团队。 如果密钥被泄露，传出 webhook 可以删除和重新创建，并将生成新密码。</li><li>尽管可以创建不验证密码的传出 Webhook，但建议不要这样做。</li><li>除了接收和回复消息外，传出 Webhook 不能执行其他操作：不能主动发送消息，不能发送和接收文件，不能执行聊天机器人可以执行的任何其他操作（接收和回复消息除外）。</li></ul></td>
  </tr>
</table>