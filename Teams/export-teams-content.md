---
title: 使用导出 API Microsoft Teams内容
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 本文将了解如何使用导出 API Teams导出Microsoft Teams内容。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9d298ad18c6ed63c269c5f31b923a89e63a9f96
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620638"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用导出 API Microsoft Teams内容

Teams使用导出 API，你可以从游戏导出 1：1、群组聊天、会议聊天和Microsoft Teams。 如果组织需要导出Microsoft Teams，可以使用导出 API Teams它们。 *聊天消息* 表示频道 [或聊天中的](/graph/api/resources/channel?view=graph-rest-beta) 单个聊天 [消息](/graph/api/resources/chat?view=graph-rest-beta)。 聊天消息可以是聊天消息中的根聊天消息或由聊天消息中的 **replyToId** 属性定义的回复线程的一部分。

下面是一些有关如何使用这些导出 API 的示例：

- **示例 1：** 如果已启用Microsoft Teams，并且想要通过传递给定用户或团队的日期范围，以编程方式导出所有 Microsoft Teams 消息。
- **示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。 导出 API 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>导出 API 支持Teams哪些功能？

- 批量导出 **Teams** 消息：Teams 导出 API 支持每个租户每个应用最多 200 个 RPS，应用程序最多支持 600 个 RPS，这些限制应该可以批量导出 Teams 消息。
- **应用程序上下文**：若要调用 Microsoft Graph，你的应用必须从应用程序获取访问Microsoft 标识平台。 访问令牌包含有关你的应用的信息，以及该应用对通过 Microsoft Graph 提供的资源和 API 的权限。 若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台并且由用户或管理员授权才能访问所需的 Microsoft Graph资源。

    如果已熟悉将应用与应用集成Microsoft 标识平台获取令牌，请参阅"下一步"部分，了解特定于[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)Microsoft Graph。
- **混合环境：** 导出 API 支持在本地和本地混合环境中预配 (用户Exchange Teams) 。 为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。
- **用户已删除的消息：** 用户从客户端中删除Teams消息可以使用导出 API 访问，自删除起最多 21 天。
- **邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。 使用导出 API 可以检索邮件中附加的文件。
- **聊天消息属性：** 请参阅此处导出 API 支持Teams的完整 [属性列表](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>如何访问Teams API

- **示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **示例 2** 是一个示例查询，用于通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>如果有多个结果，API 会返回包含下一页链接的响应。 要获取下一组结果，只需从 @odata.nextlink 对 url 调用 GET。 如果@odata.nextlink 不存在或为 null，则检索所有消息。

## <a name="prerequisites-to-access-teams-export-apis"></a>访问导出 API Teams的先决条件 

- Teams导出 API 目前以预览版提供。 它仅对具有 API 所需许可证 [的用户和租户](/graph/teams-licenses) 可用。 将来，Microsoft 可能会要求你或你的客户根据通过 API 访问的数据量支付额外费用。
- Microsoft TeamsMicrosoft 中的 API Graph敏感数据被视为受保护的 API。 导出 API 需要具有除权限和许可之外的附加验证才能使用它们。 若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。
- 应用程序权限由在没有登录用户的情况下运行的应用使用;应用程序权限只能由管理员许可。 需要以下权限：

    - *Chat.Read.All：* 允许访问所有 1：1、群组聊天和会议聊天消息 
    - *ChannelMessage.Read.All：* 允许访问所有通道消息  
    - *User.Read.All：* 允许访问租户的用户列表

## <a name="json-representation"></a>JSON 表示形式

以下示例是资源的 JSON 表示形式：

命名空间：microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型一](/graph/api/resources/chatmessage) 文。