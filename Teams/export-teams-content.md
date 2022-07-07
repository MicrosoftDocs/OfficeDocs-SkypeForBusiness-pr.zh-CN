---
title: 使用 Microsoft Teams 导出 API 导出内容
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 本文介绍如何使用 Microsoft Teams 导出 API 导出 Teams 内容。
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
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647644"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft Teams 导出 API 导出内容

使用 Teams 导出 API，可以从 Microsoft Teams 导出 1：1、群聊、会议聊天和频道消息。 如果组织需要导出 Microsoft Teams 消息，则可以使用 Teams 导出 API 提取这些消息。 *聊天消息* 表示 [频道](/graph/api/resources/channel) 或聊天中的单个 [聊天](/graph/api/resources/chat)消息。 聊天消息可以是根聊天消息或由聊天消息中的 **replyToId** 属性定义的回复线程的一部分。

下面是有关如何使用这些导出 API 的一些示例：

- **示例 1**：如果已在组织中启用 Microsoft Teams，并且想要通过传递给定用户或团队的日期范围，以编程方式导出所有 Microsoft Teams 消息。
- **示例 2**：如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。 导出 API 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 导出 API 支持什么？

- **批量导出 Teams 消息：** Teams 导出 API 支持每个租户最多 200 个 RPS，应用程序支持 600 个 RPS，这些限制应能够批量导出 Teams 消息。
- **应用程序上下文**：若要调用 Microsoft Graph，应用必须从Microsoft 标识平台获取访问令牌。 访问令牌包含有关应用的信息，以及它对通过 Microsoft Graph 提供的资源和 API 拥有的权限。 若要获取访问令牌，应用必须注册到Microsoft 标识平台，并经用户或管理员授权才能访问所需的 Microsoft Graph 资源。

    如果已熟悉将应用与Microsoft 标识平台集成以获取令牌，请[参阅“后续步骤”](/graph/auth/auth-concepts#next-steps)部分，了解特定于 Microsoft Graph 的信息和示例。
- **混合环境：** 导出 API 支持在混合环境 (本地 Exchange 和 Teams) 上预配的用户发送的消息。 配置为混合环境的用户发送的任何消息都可以使用导出 API 访问。
- **用户已删除的消息：** 用户从 Teams 客户端中删除的消息可以使用导出 API 访问，从删除时间起最多 21 天。
- **消息附件：** 导出 API 包括指向作为消息一部分发送的附件的链接。 使用导出 API 可以检索消息中附加的文件。
- **反应：** 导出 API 支持用户对 Teams 消息发出的反应。 目前支持的反应是心，愤怒，喜欢，悲伤，惊讶，笑。
- **聊天消息属性：** 请参阅 [此](/graph/api/resources/chatmessage#properties)处 Teams 导出 API 支持的属性的完整列表。


## <a name="how-to-access-teams-export-apis"></a>如何访问 Teams 导出 API

- **示例 1** 是一个简单的查询，用于在没有任何筛选器的情况下检索用户或团队的所有消息：

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

> [!NOTE]
> 如果出现多个结果，API 将返回具有下一页链接的响应。 若要获取下一组结果，只需从 @odata.nextlink 调用 GET。 如果不存在 @odata.nextlink 或 null，则检索所有消息。

## <a name="prerequisites-to-access-teams-export-apis"></a>访问 Teams 导出 API 的先决条件

- Microsoft Graph 中访问敏感数据的 Microsoft Teams API 被视为受保护的 API。 导出 API 要求在使用 API 之前，必须具有超出权限和许可的其他验证。 若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。
- 应用程序权限由在没有登录用户存在的情况下运行的应用使用;应用程序权限只能由管理员同意。 需要以下权限：
  - *Chat.Read.All*：允许访问所有 1：1、组聊天和会议聊天消息
  - *ChannelMessage.Read.All*：允许访问所有通道消息
  - *User.Read.All*：允许访问租户的用户列表

## <a name="license-requirements-for-teams-export-apis"></a>Teams 导出 API 的许可证要求

导出 API 通过模型查询参数支持安全性和符合性 (S+C) 和常规使用方案。  (模型 A) 的 S+C 方案包括种子化容量，并且需要 E5 订阅和常规使用方案 (模型 B) 适用于所有订阅，并且仅供使用。 有关种子容量和消耗费的详细信息，请参阅 [Microsoft Graph Teams API 的许可和付款要求](/graph/teams-licenses)。

### <a name="scmodel-a-scenarios"></a>S+C/模型 A 方案

仅限于执行安全性和/或符合性功能的应用程序，用户必须具有特定的 E5 许可证才能使用此功能并接收种子容量。 种子容量是每个用户，按月计算，在租户级别进行聚合。 对于超出种子容量的使用情况，应用所有者需按 API 使用量计费。 模型 A 只能访问分配有 E5 许可证的用户的消息。

### <a name="general-usagemodel-b-scenarios"></a>常规使用情况/B 模型方案

适用于所有非 S+C 相关方案，没有许可证要求或种子化容量。 当使用计量变为可用时，应用所有者将针对所有每月 API 调用收费。

### <a name="evaluation-mode-default"></a>评估模式 (默认) 

任何模型声明都无法访问每个请求应用程序的 API，但出于评估目的，每个请求应用程序的使用率有限。

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

> [!NOTE]
> 有关 chatMessage 资源的详细信息，请参阅 [chatMessage 资源类型](/graph/api/resources/chatmessage) 文章。
