---
title: 使用 Microsoft Teams 导出 API 导出内容
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 本文将了解如何使用 Microsoft Teams 导出 API 导出 Teams 内容。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c99bed1ef9a1862b469dd5214b8d829bde8479b
ms.sourcegitcommit: 15c45befbee35e69f9ec82493151cb82e61da4fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50096925"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft Teams 导出 API 导出内容

Teams 导出 API 允许你从 Microsoft Teams 导出 1：1、群组聊天和频道消息。 如果你的组织需要导出 Microsoft Teams 消息，可以使用 Teams 导出 API 提取它们。 *聊天消息* 表示频道或 [聊天中的单个](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 聊天 [消息](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。 聊天消息可以是根聊天消息或聊天消息中 **replyToId** 属性定义的回复线程的一部分。

下面是一些有关如何使用这些导出 API 的示例：

- **示例 1：** 如果已在你的组织中启用 Microsoft Teams，并且想要通过传递给定用户或团队的日期范围以编程方式导出所有 Microsoft Teams 消息。
- **示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。 导出 API 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 导出 API 支持哪些功能？

- **批量导出 Teams 消息：** Teams 导出 API 支持每个租户每个应用最多 200 个 RPS，应用程序最多支持 600 个 RPS，这些限制应能批量导出 Teams 消息。
- **应用程序上下文**：若要调用 Microsoft Graph，应用必须从 Microsoft 标识平台获取访问令牌。 访问令牌包含有关应用及其对通过 Microsoft Graph 提供的资源和 API 的权限的信息。 若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台，并且必须由用户或管理员授权才能访问所需的 Microsoft Graph 资源。

    如果你已熟悉将应用与 Microsoft 标识平台集成以获取令牌，请参阅"下一步[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)"部分，了解特定于 Microsoft Graph 的信息和示例。
- **混合环境：** 导出 API 支持在本地 Exchange 和 Teams (混合环境中预配的用户发送) 。 为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。
- **用户删除的消息：** 用户从 Teams 客户端中删除的消息可以使用导出 API 访问，自删除起最多 30 天。
- **邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。 使用导出 API 可以检索邮件中附加的文件。
- **聊天消息属性：** 请参阅此处 Teams 导出 API 支持的属性 [的完整列表](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>如何访问 Teams 导出 API

- **示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **示例 2** 是一个示例查询，它通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>如果有多个结果，API 会返回包含下一页链接的响应。 要获取下一组结果，只需从 @odata.nextlink 对 URL 调用 GET。 如果@odata.nextlink 不存在或为 null，则检索所有消息。

## <a name="prerequisites-to-access-teams-export-apis"></a>访问 Teams 导出 API 的先决条件 

- Teams 导出 API 目前以预览版提供。 它仅可供拥有 API 所需许可证 [的用户和租户](https://aka.ms/teams-changenotification-licenses) 使用。 将来，Microsoft 可能会要求你或你的客户根据通过 API 访问的数据量支付额外的费用。
- Microsoft Graph 中访问敏感数据的 Microsoft Teams API 被视为受保护的 API。 导出 API 要求在权限和许可之外拥有其他验证，然后才能使用它们。 若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。
- 应用程序权限由在不存在登录用户的情况下运行的应用使用;应用程序权限只能由管理员许可。 需要以下权限：

    - *Chat.Read.All：* 允许访问所有 1：1 和群组聊天消息 
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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型文章](https://docs.microsoft.com/graph/api/resources/chatmessage) 。
