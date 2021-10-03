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
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082862"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用导出 API Microsoft Teams内容

Teams使用导出 API，你可以从游戏导出 1：1、群组聊天、会议聊天和Microsoft Teams。 如果组织需要导出Microsoft Teams，可以使用导出 API Teams它们。 *聊天消息* 表示频道 [或聊天中的](/graph/api/resources/channel?view=graph-rest-beta) 单个聊天 [消息](/graph/api/resources/chat?view=graph-rest-beta)。 聊天消息可以是聊天消息中的根聊天消息或由聊天消息中的 **replyToId** 属性定义的回复线程的一部分。

下面是一些有关如何使用这些导出 API 的示例：

- **示例 1：** 如果已启用Microsoft Teams，并且想要通过传递给定用户或团队的日期范围，以编程方式导出所有 Microsoft Teams 消息。
- **示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。 导出 API 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>导出 API 支持Teams哪些功能？

- 批量导出 Teams 消息 **：Teams** 导出 API 支持每个租户最多 200 个 RPS，应用程序最多支持 600 个 RPS，这些限制应该可以批量导出 Teams 消息。
- **应用程序上下文**：若要调用 Microsoft Graph，你的应用必须从应用程序获取访问Microsoft 标识平台。 访问令牌包含有关应用的信息，以及该应用对通过 Microsoft Graph 提供的资源和 API 的权限。 若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台并且由用户或管理员授权才能访问所需的 Microsoft Graph资源。

    如果已熟悉将应用与应用集成Microsoft 标识平台获取令牌，请参阅"下一步"部分，了解特定于[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)Microsoft Graph。
- **混合环境：** 导出 API 支持在本地和本地混合环境中预配 (用户Exchange Teams) 。 为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。
- **用户已删除的消息：** 用户从客户端中删除的消息Teams自删除起最多 21 天内使用导出 API 访问。
- **邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。 使用导出 API 可以检索邮件中附加的文件。
- **聊天消息属性：** 请参阅此处导出 API 支持Teams的完整 [属性列表](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

>[!NOTE]
>导出 API 不支持 *回应*。

## <a name="how-to-access-teams-export-apis"></a>如何访问Teams API

- **示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **示例 2** 是一个示例查询，用于通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>如果有多个结果，API 会返回包含下一页链接的响应。 要获取下一组结果，只需从 @odata.nextlink 对 url 调用 GET。 如果@odata.nextlink 不存在或为 null，则检索所有消息。

## <a name="prerequisites-to-access-teams-export-apis"></a>访问导出 API Teams的先决条件 

- Microsoft TeamsMicrosoft 中用于Graph敏感数据的 API 被视为受保护的 API。 导出 API 需要具有除权限和许可之外的附加验证才能使用它们。 若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。
- 应用程序权限由在没有登录用户的情况下运行的应用使用;应用程序权限只能由管理员许可。 需要以下权限：

    - *Chat.Read.All：* 允许访问所有 1：1、群组聊天和会议聊天消息 
    - *ChannelMessage.Read.All：* 允许访问所有通道消息  
    - *User.Read.All：* 允许访问租户的用户列表

## <a name="license-requirements-for-teams-export-apis"></a>导出 API Teams许可证要求

导出 API 通过模型查询 (S+C) 和常规使用方案支持安全性和符合性。 模型 A (的 S+C 方案) 包括种子容量，并且需要 E5 订阅和常规使用方案 (模型 B) 可用于所有订阅，并且仅消耗。 有关种子容量和消耗费用详细信息，请参阅 Microsoft Graph Teams API 的许可[和付款要求](/graph/teams-licenses)。

### <a name="scmodel-a-scenarios"></a>S+C/模型 A 方案

限制为执行安全性和/或符合性功能的应用程序，用户必须具有特定的 E5 许可证，以便使用此功能并接收种子容量。 种子容量按用户计算，按月计算，在租户级别聚合。 对于超出种子容量的使用，应用所有者将按 API 使用计费。 模型 A 只能访问来自具有已分配 E5 许可证的用户的消息。

### <a name="general-usagemodel-b-scenarios"></a>常规用法/模型 B 方案

适用于所有非 S+C 相关方案，没有许可证要求或种子容量。 当消耗指标可用时，将针对所有每月 API 调用向应用所有者收费。 

### <a name="evaluation-mode-default"></a>评估模式 (默认) 

没有任何模型声明允许访问每个请求应用程序的使用量有限的 API，以便进行评估。 

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