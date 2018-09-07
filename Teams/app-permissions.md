---
title: Microsoft 团队应用程序权限和注意事项
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: 了解请求从您的组织数据和权限的应用程序。
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: f35620c1778bbe12f7d98f1a326e47a58804680b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870170"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft 团队应用程序权限和注意事项

Microsoft 团队应用程序是一种方法，以聚合到可安装、 升级和卸载_应用程序包_的一个或多个功能。 功能包括：

-   自动程序
-   消息扩展
-   选项卡
-   连接器

应用程序是由用户同意和由 IT 从策略角度。 但是，大多数情况下，应用程序的权限和风险配置文件由定义的权限和风险配置文件，它包含的功能。 因此，本文重点介绍权限和功能级别的注意事项。

以大写字母形式，例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE，下面列出的权限不出现在[Microsoft 团队开发人员文档](https://aka.ms/teamsdevdocs)或[Microsoft Graph 权限](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)的任何位置。 它们只需描述性简写出于本文目的。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>使用下的表作为指南来了解您正在调查的应用程序正在请求的权限。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>下一步|<ul><li>研究应用程序或服务本身来确定您是否要允许组织内的对其进行访问。 例如，bot 发送和接收来自用户，邮件和 — 企业业务线 bot 除外 — 合规性边界外，它们位于。 因此，包括 bot 任何应用程序需要这些权限，并且至少具有风险的配置文件。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>全局应用程序权限和注意事项

<table>
  <tr>
    <th width="25%">所需的权限</th>
    <th width="25%">可选的权限</th>
    <th width="50%">考虑事项</th>
  </tr>
  <tr>
    <td valign="top">无</td>
    <td valign="top">无</td>
    <td valign="top">应用程序必须公开其使用哪些数据和数据用于在其术语中的使用和隐私策略链接。</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bot 和消息扩展

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">所需的权限</th>
    <th width="25%">可选的权限</th>
    <th width="50%">考虑事项</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE，REPLYTO_MESSAGE。 自动程序可以接收来自用户邮件和答复。<sup>1</sup></li><li>POST_MESSAGE_USER。 用户已向 bot 发送一条消息后，bot 可以发送用户直接邮件 （也称为_预防性消息_） 在任何时间。</li><li>GET_CHANNEL_LIST。 自动程序添加到团队可以获取团队中的名称和 Id 的通道的列表。</li></ul></td>
    <td valign="top"><ul><li>标识。 应用程序的自动程序在频道使用它时，可以访问工作组成员 （名字、 姓氏、 用户主体名称 [UPN]、 电子邮件地址）; 基本标识的信息个人或组聊天中使用它时，自动程序可以访问这些用户相同的信息。</li><li> POST_MESSAGE_TEAM。 允许应用程序的自动程序在任何时候，将直接 （主动） 邮件发送到任何团队成员即使用户具有从不讨论到 bot 之前。</li><li>以下不显式权限，但隐含 RECEIVE_MESSAGE REPLYTO_MESSAGE 并向其中自动程序可以使用，在清单中声明的范围： <ul><li>RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT、 REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES，RECEIVE_FILES。<sup>3</sup>自动程序是否可以发送和接收文件 （尚未支持群聊或通道） 的个人聊天中的控件。</li></ul></td>
    <td valign="top"><ul><li>自动程序仅有权访问团队其他们已被添加到或已安装它们的用户。</li><li>自动程序仅接收顺序它们明确提到用户的消息。 此数据离开企业网络。</li><li>    自动程序可以仅答复提到这些的对话。</li><li>用户具有与自动程序、 conversed，如果 bot 存储该用户的 ID 后，它可以发送该用户直接消息在任何时间。 </li><li>理论上可以 bot 邮件包含指向网络钓鱼或恶意软件的网站，但由用户，租户管理员，或全局由 Microsoft 会阻止自动程序。 </li><li>自动程序可以检索 （和可能存储） 应用程序已添加到，工作组成员或单个用户的个人或组聊天非常基本标识信息。 以获取更多有关这些用户的信息，自动程序必须要求其登录到 Azure Active Directory (Azure AD)。 </li><li>自动程序可以检索 （并可能存储） 通道团队; 中的列表此数据离开企业网络。 </li><li>当文件发送到自动程序时，该文件离开企业网络。 发送和接收文件的每个文件需要用户审批。 </li><li>默认情况下自动程序没有能够代表用户，但 bot 可以要求用户登录;只要用户登录时，自动程序将具有访问令牌与它可以执行其他操作。 完全内容这些其他事项取决于 bot 和用户登录： 自动程序是在注册 Azure AD 应用程序<a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a>并且可以具有自己的权限集。</li><li>只要用户添加或删除从团队，就明智 bot。</li><li>Bot 看不到用户的 IP 地址或其他引用网站信息。 来自 Microsoft 的所有信息。 (还有一个例外： 如果 bot 实现自己登录体验，登录 UI 看到用户的 IP 地址和引用网站信息。)</li><li>另一方面，消息扩展，看用户的 IP 地址和引用网站信息。</li><li>应用程序准则 （和 AppSource 审阅过程） 需要出于有效目的而 （通过 POST_MESSAGE_TEAM 权限中） 向用户发布个人聊天消息中的决定。 发生滥用，用户可以阻止 bot，租户管理员可以阻止该应用程序，以及 Microsoft 可以根据需要集中阻止自动程序。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">某些 bot 只能发送消息 (POST_MESSAGE_USER)。 其称作"仅限通知"自动程序，但术语不涉及哪些 bot 是允许或不允许执行，这意味着 bot 不想要公开交谈体验。 团队使用此字段禁用通常会启用; 在 UI 中的功能在什么它已允许执行不要公开交谈体验的 bot 相比，bot 不受限制。</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">正在开发人员预览。</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">正在开发人员预览。 为由<code>supportsFiles</code>上的应用程序 manifest.json 文件中的自动程序对象的布尔值属性。</td>
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
    <td valign="top"><ul><li>选项卡的风险配置文件是与浏览器选项卡中运行该相同网站几乎完全相同。 </li><li>选项卡还获取的上下文中运行，包括登录名和 UPN 当前用户 Azure AD 对象的当前用户的 ID 的 Office 365 组 （工作组） 其所在，租户 ID，并且用户的当前区域设置 ID。 但是，若要将这些 Id 映射到用户的信息，选项卡将必须使用户登录到 Azure AD。</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE。 某些连接器支持_可操作的消息_，使用户可以通过添加响应的 GitHub 问题或日期向 Trello 卡片例如张贴目标的答复连接器邮件。</td>
    <td valign="top"><ul><li>文章连接器邮件系统不知道其发布到或接收邮件的用户： 披露关于该收件人无信息。 （Microsoft 是实际的收件人，租户;Microsoft 执行的实际发布到该频道。）</li><li>没有数据离开企业网络时连接器邮件发布到通道。</li><li>支持可操作的消息 （REPLYTO_CONNECTOR_MESSAGE 权限） 的连接器也看不到 IP 地址和引用网站信息;此信息发送给 Microsoft，然后路由至已 Microsoft 连接器门户中的 HTTP 终结点。</li><li>连接器配置通道，每次创建该连接器实例的唯一的 URL。 如果删除该连接器实例，则可以不再使用的 URL。</li><li>连接器邮件不能包含附件的文件。</li><li>URL 应视为机密/机密的连接器实例： 任何人都 URL 可以发布，喜欢的电子邮件地址。 因此，是一些风险的垃圾邮件或网络钓鱼或恶意软件的网站的链接。 如果的发生，团队所有者可以删除的连接器实例。</li><li>如果发送连接器邮件已泄露和开始发送恶意软件垃圾邮件/网络钓鱼链接的服务，租户管理员可以阻止新连接器实例创建，可以通过 Microsoft 集中阻止。</li></ul></td>
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
    <td valign="top"><ul><li>传出 webhooks 类似于 bot 但具有更少的权限。 它们必须是明确提到，就像 bot。</li><li>传出 webhook 注册时，会生成_密码_，此程序允许传出 webhook 验证发件人，而不是恶意攻击者是 Microsoft 团队。 此密钥应保持机密;有权访问它的任何人都可以模拟的 Microsoft 团队。 如果密钥被泄露，传出 webhook 可以删除和重新创建，并将生成新密码。</li><li>虽然可以创建不验证密码传出 webhook，我们建议不要它。</li><li>接收和答复邮件，之外传出 webhooks 无法做： 无法主动发送的邮件，他们无法发送或接收文件，他们不能进行任何其他操作，可以执行除 bot，接收和答复邮件。</li></ul></td>
  </tr>
</table>