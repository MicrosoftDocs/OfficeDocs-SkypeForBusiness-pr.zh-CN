---
title: 将内容与 Microsoft 团队导出 Api 一起导出
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 在本文中，你将了解如何使用 Microsoft 团队导出 Api 导出团队内容。
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
ms.openlocfilehash: 7849892870f54f43f0fda16564ad472426d46cd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171431"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>将内容与 Microsoft 团队导出 Api 一起导出

团队导出 Api 允许你从 Microsoft 团队导出1:1 和群组聊天消息。 如果你的组织需要导出 Microsoft 团队邮件，你可以使用团队导出 Api 提取它们。 *聊天消息* 表示 [频道](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 或 [聊天](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)中的单个聊天消息。 聊天消息可以是根聊天消息，也可以是由聊天消息中的 **replyToId** 属性定义的答复线程的一部分。

下面是有关如何使用这些导出 Api 的一些示例：

- **示例 1**：如果你已在组织中启用 microsoft 团队，并且希望通过为给定用户传递数据区域以编程方式导出所有 microsoft 团队邮件到日期。
- **示例 2**：如果希望通过提供数据区域以编程方式每天导出所有用户消息。 导出 Api 可以检索在给定日期范围内创建或更新的所有消息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>团队导出 Api 支持哪些内容？

- **批量导出团队邮件：** 团队导出 Api 支持每个租户的 200 RPS 和应用程序的 600 RPS，但这些限制应能够批量导出团队邮件。
- **应用程序上下文**：若要调用 microsoft Graph，你的应用必须从 Microsoft identity platform 获取访问令牌。 访问令牌包含有关应用的信息以及它对通过 Microsoft Graph 可用的资源和 Api 所拥有的权限。 若要获取访问令牌，你的应用必须向 Microsoft identity 平台注册，并由用户或管理员授权，以便访问它所需的 Microsoft Graph 资源。

    如果你已熟悉将应用与 Microsoft identity 平台集成以获取令牌，请参阅 " [后续步骤](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) " 部分，了解特定于 microsoft Graph 的信息和示例。
- **混合环境：** 导出 Api 支持在混合环境上预配的用户发送的消息 (本地 Exchange 和团队) 。 为混合环境配置的用户发送的任何消息都可通过导出 Api 进行访问。
- **用户已删除邮件：** 从团队客户端删除的邮件可以使用从删除时起30天内的 "导出 Api" 访问。
- **邮件附件：** 导出 Api 包括作为邮件的一部分发送的附件的链接。 使用导出 Api，可以检索邮件中附加的文件。
- **聊天消息属性：** 请参阅 [此处](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)的团队导出 api 支持的属性的完整列表。

## <a name="how-to-access-teams-export-apis"></a>如何访问团队导出 Api

- **示例 1** 是一种简单查询，用于检索不带任何筛选器的用户的所有消息：

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- **示例 2** 是一个示例查询，它通过指定日期时间筛选器和 top 50 消息来检索用户的所有消息：

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>当出现多个结果时，API 返回与下一页链接的响应。 若要获取下一组结果，只需调用来自 @odata 的 url 即可。 @Odata 如果 nextlink 不存在或为 null，则检索所有消息。

## <a name="prerequisites-to-access-teams-export-apis"></a>访问团队导出 Api 的先决条件 

- 团队导出 Api 当前处于预览版中，受 Microsoft Api 使用条款的制约。  只有具有所需许可证的用户和租户才能使用它。 尝试访问没有适当许可证的 Api 将导致403错误。
- Microsoft Graph 中的 microsoft 团队 Api 访问敏感数据被视为受保护的 Api。 导出 Api 要求你拥有其他验证（除权限和同意），然后才能使用它们。 若要请求对这些受保护的 Api 的访问权限，请填写 " [请求" 表单](https://aka.ms/teamsgraph/requestaccess)。
- 应用程序权限由在没有登录用户的情况下运行的应用使用;只有管理员才能同意应用程序权限。 需要以下权限：

    - 已*阅读 "聊天*"。所有：支持对所有1:1 和群组聊天消息的访问 
    - *User Read。 All*：启用对租户的用户列表的访问权限 

## <a name="json-representation"></a>JSON 表示形式

以下示例是资源的 JSON 表示形式：

命名空间： microsoft graph

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
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型](https://docs.microsoft.com/graph/api/resources/chatmessage) 文章。
