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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944597"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft Teams 导出 API 导出内容

Teams 导出 API 允许你从 Microsoft Teams 导出 1：1、群组聊天和频道消息。 如果你的组织需要导出 Microsoft Teams 消息，可以使用 Teams 导出 API 提取它们。 *聊天消息* 表示频道或 [聊天中的单个](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 聊天 [消息](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。 聊天消息可以是根聊天消息或聊天消息中 **replyToId** 属性定义的回复线程的一部分。

下面是一些有关如何使用这些导出 API 的示例：

- **示例 1：** 如果已在你的组织中启用 Microsoft Teams，并且想要通过传递给定用户或团队的日期范围以编程方式导出所有 Microsoft Teams 消息。
- **示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。 导出 API 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 导出 API 支持哪些功能？

- **批量导出 Teams 消息：** Teams 导出 API 支持每个租户每个应用最多 200 个 RPS，应用程序支持 600 个 RPS，这些限制应能批量导出 Teams 消息。
- **应用程序上下文**：若要调用 Microsoft Graph，应用必须从 Microsoft 标识平台获取访问令牌。 访问令牌包含有关应用及其对通过 Microsoft Graph 提供的资源和 API 的权限的信息。 若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台，并且必须由用户或管理员授权才能访问所需的 Microsoft Graph 资源。

    如果你已熟悉将应用与 Microsoft 标识平台集成以获取令牌，请参阅"下一步[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)"部分，了解特定于 Microsoft Graph 的信息和示例。
- **混合环境：** 导出 API 支持在本地 Exchange 和 Teams (混合环境中预配的用户发送) 。 为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。
- **用户删除的消息：** 用户从 Teams 客户端中删除的消息可以使用导出 API 访问，自删除起最多 30 天。
- **邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。 使用导出 API 可以检索邮件中附加的文件。
- **聊天消息属性：** 请参阅此处 Teams 导出 API 支持的属性 [的完整列表](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>如何访问 Teams 导出 API

- **示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **示例 2** 是一个示例查询，它通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

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
