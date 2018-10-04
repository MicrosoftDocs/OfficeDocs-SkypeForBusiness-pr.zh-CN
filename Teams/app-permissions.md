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
ms.openlocfilehash: f3ea7aaa57f6784487d662174554ec0086a87346
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375745"
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
    <td valign="top"><ul><li>IDENTITY。 当 = #39; 渠道、 应用程序和 #39; 中使用的 s s 自动程序可以访问的工作组成员 （名字、 姓氏、 用户主体名称 [UPN]、 电子邮件地址）; 基本标识信息当 = #39; s 用于个人或群聊、 自动程序可以访问这些用户相同的信息。</li><li> POST_MESSAGE_TEAM。 允许应用程序和 #39; s bot 直接 （主动） 将邮件发送到任何团队成员在任何时候，即使用户具有从不讨论到 bot 之前。</li><li>以下权限不是显式权限，而是 RECEIVE_MESSAGE、REPLYTO_MESSAGE 以及可以使用聊天机器人的范围隐含的权限，并在 manifest 中声明： <ul><li>RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES、RECEIVE_FILES。<sup>3</sup> 控制聊天机器人是否可以在个人聊天中发送和接收文件（在群组聊天和频道中还不支持）。</li></ul></td>
    <td valign="top"><ul><li>自动程序仅有权访问该团队它们 = #39; ve 已添加了或到已安装它们的用户。</li><li>自动程序仅在其中接收邮件它们 = #39; re 明确提到的用户。 此数据将离开公司网络。</li><li>    自动程序仅答复顺序对话它们 = #39; re 提到。</li><li>Bot 存储该用户和 #39; 如果用户具有与自动程序、 conversed 后 s ID，它可以发送该用户直接消息在任何时间。 </li><li>从理论上来说，聊天机器人消息可能包含钓鱼站点或恶意软件站点的链接，但用户或租户管理员可以阻止聊天机器人，Microsoft 也可以全局阻止聊天机器人。 </li><li>聊天机器人可以检索（并可能存储）添加了该应用的团队成员或者个人聊天或群组聊天中各个用户的最基本身份信息。 要获取这些用户的更多信息，聊天机器人必须要求其登录 Azure Active Directory (Azure AD)。 </li><li>聊天机器人可以检索（并可能存储）团队中的频道列表；此数据将离开公司网络。 </li><li>向聊天机器人发送文件后，该文件将离开公司网络。 发送和接收文件时需要用户对每个文件进行批准。 </li><li>通过默认、 bot don 测验 t 能够代表用户，但 bot 可以要求用户登录;只要用户登录时，自动程序将具有访问令牌与它可以执行其他操作。 具体哪些其他操作取决于聊天机器人和用户登录位置：聊天机器人是在 <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> 上注册的 Azure AD 应用，因此可以拥有自己的一组权限。</li><li>每当在团队中添加或删除用户时，聊天机器人都会收到通知。</li><li>Bot don #39; 请参阅用户 t & #39;IP 地址或其他引用网站信息。 所有信息均来自 Microsoft。 (还有一个例外： 如果 bot 实现自己登录体验，用户和 #39; 将看到登录 UIIP 地址和引用网站信息。）</li><li>消息扩展，另一方面，看用户和 #39;IP 地址和引用网站信息。</li><li>应用准则（以及我们的 AppSource 审阅过程）要求自行决定向用户发布个人聊天消息（通过 POST_MESSAGE_TEAM 权限）以达到有效目的。 如果发生滥用，用户可以阻止聊天机器人，租户管理员可以阻止应用，并且如果需要，Microsoft 可以集中阻止聊天机器人。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">一些聊天机器人仅发送消息 (POST_MESSAGE_USER)。 他们 = #39; re 调用&quot;仅通知&quot;bot，但术语不测验 t 引用允许或不允许执行哪些自动程序，它意味着，自动程序不测验 t 想要公开交谈体验。 团队使用此字段禁用通常会启用; 在 UI 中的功能自动程序不是 & #39; 在什么受限制的 t = #39; s 允许执行相比不要公开交谈体验的 bot。</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">当前处于开发人员预览版中。</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">当前处于开发人员预览版中。 由应用的 manifest.json 文件中聊天机器人对象的 <code>supportsFiles</code> 布尔属性控制。</td>
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
    <td valign="top"><ul><li>选项卡的风险配置文件与浏览器选项卡中运行的同一网站几乎相同。 </li><li>选项卡还在其中获取的上下文 = #39; s 运行当前用户的 Azure AD 对象 ID，包括登录名和当前用户的 UPN 其所在，租户 ID 的 Office 365 组 （工作组） ID和用户的当前区域设置。 但是，要映射到用户 #39 这些 Id; s 信息、 选项卡将需要使用户登录到 Azure AD。</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持<em>可操作消息</em>，即允许用户发布针对连接器消息的目标回复，例如，向 GitHub 问题添加响应，或向 Trello 卡添加日期。</td>
    <td valign="top"><ul><li>系统的文章连接器消息不 = #39; t 知道谁 = #39; s 为发布或接收邮件的用户： 披露关于该收件人无信息。 （Microsoft 是实际接收人，而不是租户；Microsoft 向频道实际发布消息。）</li><li>向频道发布连接器消息时，没有任何数据离开公司网络。</li><li>Don = #39 还支持可操作的消息 （REPLYTO_CONNECTOR_MESSAGE 权限） 的连接器; t，请参阅 IP 地址和引用网站信息;此信息发送给 Microsoft，然后路由至已 Microsoft 连接器门户中的 HTTP 终结点。</li><li>每当为连接器配置频道时，都会为该连接器实例创建一个唯一的 URL。 如果删除了该连接器实例，则不能再使用该 URL。</li><li>连接器消息可以 & #39; t 包含附件的文件。</li><li>连接器实例 URL 应视为机密/保密信息：拥有该 URL 的任何人可以向其发布消息，就像电子邮件地址一样。 因此，那里 & #39; s 一些风险的垃圾邮件或网络钓鱼或恶意软件的网站的链接。 如果出现这种情况，团队所有者可以删除连接器实例。</li><li>如果发送连接器消息的服务受到破坏并开始发送垃圾消息/钓鱼链接/恶意软件链接，租户管理员可以阻止创建新的连接器实例，并且 Microsoft 可以集中阻止它们。</li></ul></td>
  </tr>
</table>

> [!Note]
> 当前，无法知道哪些连接器支持可操作消息（REPLYTO_CONNECTOR_MESSAGE 权限）。


## <a name="outgoing-webhooks"></a>传出 Webhook

_传出 Webhook_ 由团队所有者或团队成员动态创建（如果为租户启用了旁加载）。 它们不是 Teams 应用的功能；提供此信息是为了内容的完整性。

<table>
  <tr>
    <th width="25%">所需权限</th>
    <th width="25%">可选权限</th>
    <th width="50%">考虑事项</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE、REPLYTO_MESSAGE。 可以接收来自用户的消息以及回复用户。</td>
    <td valign="top">无</td>
    <td valign="top"><ul><li>传出 Webhook 与聊天机器人类似，但权限更少。 必须明确提及它们，就像聊天机器人一样。</li><li>注册传出 Webhook 后，将生成一个<em>密码</em>，用于允许传出 Webhook 验证发送者是 Microsoft Teams，而不是恶意攻击者。 此密码应保密；有权访问该密码的任何人都可以模拟 Microsoft Teams。 如果此密码泄露，可以删除并重新创建传出 Webhook，并将生成新密码。</li><li>尽管 = #39; s 可以创建传出 webhook，这并不 = #39; t 验证机密，我们建议不要它。</li><li>接收和答复邮件、 传出 webhooks 可以和 #39; 之外 t 执行何： 他们可以 & #39; t 主动发送的邮件，它们可以 & #39; t 发送或接收文件，它们可以 & #39; t 进行任何其他接收并答复，可以执行除外自动程序的操作邮件。</li></ul></td>
  </tr>
</table>