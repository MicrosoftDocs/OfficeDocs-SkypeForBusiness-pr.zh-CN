---
title: Microsoft Teams 应用权限和考虑事项
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: lehewe
description: 了解贵组织要求的数据和权限应用。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2618f4ad5a09e6fff33580f9e9085d6d282797a6
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569639"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 应用权限和考虑事项

通过 Microsoft Teams 应用可以将一项或多项功能汇聚到一个可以安装、升级和卸载的_应用包_。 这些功能包括：

-   聊天机器人
-   消息传递扩展
-   选项卡
-   连接器

从策略角度来看，应用由用户许可并由 IT 管理。 但是，大多数情况下，应用的权限和风险配置文件由其包含的功能的权限和风险配置文件定义。 因此，本文主要介绍功能级别的权限和考虑事项。

下文所列大写字母的权限（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）未出现在 [Microsoft Teams 开发人员文档](https://aka.ms/teamsdevdocs)或 [Microsoft Graph 的权限](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中的任何地方。 使用它们只是为了在本文中进行简要说明。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>请使用下面各表来指导你了解你调查的应用需要的权限。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>研究应用或服务本身来确定是否允许在贵组织中对其进行访问。 例如，聊天机器人向用户发送消息以及接收来自用户的消息，并且它们在合规边界之外（企业业务线聊天机器人除外）。 因此，包含聊天机器人的任何应用至少需要这些权限以及具有相应风险配置文件。 </li></ul>|

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE、REPLYTO_MESSAGE。 聊天机器人可以接收来自用户的消息以及回复用户。<sup>1</sup></li><li>POST_MESSAGE_USER。 用户向聊天机器人发送消息后，聊天机器人可以随时向用户发送私信（也称为<em>主动消息</em>）。</li><li>GET_CHANNEL_LIST。 添加到团队的聊天机器人可以获取团队中的频道的名称和 ID 列表。</li></ul></td>
    <td valign="top"><ul><li>IDENTITY。 当 it& #39; s 中使用的通道，app& #39; s 自动程序可以访问的工作组成员 （名字、 姓氏、 用户主体名称 [UPN]、 电子邮件地址）; 基本标识信息当 it& #39; s 用于个人或群聊、 自动程序可以访问这些用户相同的信息。</li><li> POST_MESSAGE_TEAM。 允许 app& #39; s bot 直接 （主动） 将邮件发送到任何团队成员在任何时候，即使用户具有从不讨论到 bot 之前。</li><li>以下权限不是显式权限，而是 RECEIVE_MESSAGE、REPLYTO_MESSAGE 以及可以使用聊天机器人的范围隐含的权限，并在 manifest 中声明： <ul><li>RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES、RECEIVE_FILES。<sup>3</sup> 控制聊天机器人是否可以在个人聊天中发送和接收文件（在群组聊天和频道中还不支持）。</li></ul></td>
    <td valign="top"><ul><li>自动程序仅有权访问哪些 they& #39; 团队 ve 已添加了或到已安装它们的用户。</li><li>自动程序仅哪些 they& #39 接收消息; re 明确提到用户。 此数据将离开公司网络。</li><li>    自动程序可以仅答复对话的 they& #39; re 提到。</li><li>后用户具有与自动程序、 conversed，如果 bot 存储该 user& #39; s ID，它可以发送该用户直接邮件在任何时间。 </li><li>从理论上来说，聊天机器人消息可能包含钓鱼站点或恶意软件站点的链接，但用户或租户管理员可以阻止聊天机器人，Microsoft 也可以全局阻止聊天机器人。 </li><li>聊天机器人可以检索（并可能存储）添加了该应用的团队成员或者个人聊天或群组聊天中各个用户的最基本身份信息。 要获取这些用户的更多信息，聊天机器人必须要求其登录 Azure Active Directory (Azure AD)。 </li><li>聊天机器人可以检索（并可能存储）团队中的频道列表；此数据将离开公司网络。 </li><li>向聊天机器人发送文件后，该文件将离开公司网络。 发送和接收文件时需要用户对每个文件进行批准。 </li><li>默认情况下自动程序 don& #39; t 能够代表用户，但 bot 可以要求用户登录;只要用户登录时，自动程序将具有访问令牌与它可以执行其他操作。 具体哪些其他操作取决于聊天机器人和用户登录位置：聊天机器人是在 <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> 上注册的 Azure AD 应用，因此可以拥有自己的一组权限。</li><li>每当在团队中添加或删除用户时，聊天机器人都会收到通知。</li><li>Bot don& #39; t，请参阅 users& #39;IP 地址或其他引用网站信息。 所有信息均来自 Microsoft。 (还有一个例外： 登录 UI 如果 bot 实现自己登录体验，将看到 users& #39;IP 地址和引用网站信息。）</li><li>消息扩展，另一方面，看 users& #39;IP 地址和引用网站信息。</li><li>应用准则（以及我们的 AppSource 审阅过程）要求自行决定向用户发布个人聊天消息（通过 POST_MESSAGE_TEAM 权限）以达到有效目的。 如果发生滥用，用户可以阻止聊天机器人，租户管理员可以阻止应用，并且如果需要，Microsoft 可以集中阻止聊天机器人。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">一些聊天机器人仅发送消息 (POST_MESSAGE_USER)。 They& #39; re 称为&quot;仅通知&quot;bot，但术语 doesn& #39; t 涉及哪些 bot 是允许或不允许执行，它是指 bot doesn& #39; t 想要公开交谈体验。 团队使用此字段禁用通常会启用; 在 UI 中的功能bot isn& #39; t 在哪些 it& #39 限制; 允许执行相比不要公开交谈体验的 bot s。</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">当前处于开发人员预览版中。</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">为由<code>supportsFiles</code>上的应用程序 manifest.json 文件中的自动程序对象的布尔值属性。</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>如果自动程序有自己登录，则第二个 — 不同 — 的同意体验第一次用户登录。</li><li>目前，与任何 （自动程序、 选项卡、 连接器或消息扩展） 中的团队应用程序内的功能关联的 Azure AD 权限是从此处列出的团队权限完全独立。</li></ul>


## <a name="tabs"></a>选项卡

Tab 是团队内运行的网站。

<table>
  <tr>
    <th width="25%">所需的权限</th>
    <th width="25%">可选的权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">（当前） 无。</td>
    <td valign="top"><ul><li>选项卡的风险配置文件是与浏览器选项卡中运行该相同网站几乎完全相同。 </li><li>选项卡还获取的上下文中的 it& #39; s 运行，包括登录名和当前用户的 UPN Azure AD 对象 ID 为当前用户的 ID 的 Office 365 组所在 （如果它是团队）租户 ID，并且用户的当前区域设置。 但是，以将这些 Id 映射到 user& #39; s 信息、 选项卡将需要使用户登录到 Azure AD。</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>连接器

外部系统中的事件发生时，连接器发布到频道的邮件。

  <table>
  <tr>
    <th width="25%">所需的权限</th>
    <th width="25%">可选的权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持<em>可操作的消息</em>，使用户可以通过添加响应的 GitHub 问题或日期向 Trello 卡片例如张贴目标的答复连接器邮件。</td>
    <td valign="top"><ul><li>系统的文章连接器消息 doesn& #39; t 知道谁 it& #39; s 为发布或用户接收邮件： 披露关于该收件人无信息。 （Microsoft 是实际的收件人，租户;Microsoft 执行的实际发布到该频道。）</li><li>没有数据离开企业网络时连接器邮件发布到通道。</li><li>此外支持可操作的消息 （REPLYTO_CONNECTOR_MESSAGE 权限），则会 don& #39 连接器; t，请参阅 IP 地址和引用网站信息;此信息发送给 Microsoft，然后路由至已 Microsoft 连接器门户中的 HTTP 终结点。</li><li>连接器配置通道，每次创建该连接器实例的唯一的 URL。 如果删除该连接器实例，则可以不再使用的 URL。</li><li>连接器消息 can& #39; t 包含附件的文件。</li><li>URL 应视为机密/机密的连接器实例： 任何人都 URL 可以发布，喜欢的电子邮件地址。 因此，there& #39; s 一些风险的垃圾邮件或网络钓鱼或恶意软件的网站的链接。 如果的发生，团队所有者可以删除的连接器实例。</li><li>如果发送连接器邮件已泄露和开始发送恶意软件垃圾邮件/网络钓鱼链接的服务，租户管理员可以阻止新连接器实例创建，可以通过 Microsoft 集中阻止。</li></ul></td>
  </tr>
</table>

> [!Note]
> 不是当前可以知道哪些连接线支持可操作的消息 （REPLYTO_CONNECTOR_MESSAGE 权限）。


## <a name="outgoing-webhooks"></a>传出 webhooks

_传出 webhooks_创建动态团队所有者或团队成员如果 sideloading 启用租户。 它们不是团队应用程序; 的功能完整性包含此信息。

<table>
  <tr>
    <th width="25%">所需的权限</th>
    <th width="25%">可选的权限</th>
    <th width="50%">考虑事项</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收来自用户邮件和答复。</td>
    <td valign="top">无</td>
    <td valign="top"><ul><li>传出 webhooks 类似于 bot 但具有更少的权限。 它们必须是明确提到，就像 bot。</li><li>传出 webhook 注册时，会生成<em>密码</em>，此程序允许传出 webhook 验证发件人，而不是恶意攻击者是 Microsoft 团队。 此密钥应保持机密;有权访问它的任何人都可以模拟的 Microsoft 团队。 如果密钥被泄露，传出 webhook 可以删除和重新创建，并将生成新密码。</li><li>尽管 it& #39; s 可以创建传出 webhook 该 doesn& #39; t 验证机密，我们建议不要它。</li><li>接收和答复邮件，传出 webhooks can& #39; 之外 t 执行何： 它们 can& #39; t 主动发送的邮件，它们 can& #39; t 发送或接收文件，它们 can& #39; t 执行其他任何接收并答复，可以执行除外 bot邮件。</li></ul></td>
  </tr>
</table>
