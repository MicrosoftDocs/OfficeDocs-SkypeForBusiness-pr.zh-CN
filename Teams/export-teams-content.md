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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="c2120-103">使用 Microsoft Teams 导出 API 导出内容</span><span class="sxs-lookup"><span data-stu-id="c2120-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="c2120-104">Teams 导出 API 允许你从 Microsoft Teams 导出 1：1、群组聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="c2120-105">如果你的组织需要导出 Microsoft Teams 消息，可以使用 Teams 导出 API 提取它们。</span><span class="sxs-lookup"><span data-stu-id="c2120-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="c2120-106">*聊天消息* 表示频道或 [聊天中的单个](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 聊天 [消息](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="c2120-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="c2120-107">聊天消息可以是根聊天消息或聊天消息中 **replyToId** 属性定义的回复线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="c2120-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="c2120-108">下面是一些有关如何使用这些导出 API 的示例：</span><span class="sxs-lookup"><span data-stu-id="c2120-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="c2120-109">**示例 1：** 如果已在你的组织中启用 Microsoft Teams，并且想要通过传递给定用户或团队的日期范围以编程方式导出所有 Microsoft Teams 消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="c2120-110">**示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="c2120-111">导出 API 可以检索在给定日期范围内创建或更新的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="c2120-112">Teams 导出 API 支持哪些功能？</span><span class="sxs-lookup"><span data-stu-id="c2120-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="c2120-113">**批量导出 Teams 消息：** Teams 导出 API 支持每个租户每个应用最多 200 个 RPS，应用程序最多支持 600 个 RPS，这些限制应能批量导出 Teams 消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="c2120-114">**应用程序上下文**：若要调用 Microsoft Graph，应用必须从 Microsoft 标识平台获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="c2120-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="c2120-115">访问令牌包含有关应用及其对通过 Microsoft Graph 提供的资源和 API 的权限的信息。</span><span class="sxs-lookup"><span data-stu-id="c2120-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="c2120-116">若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台，并且必须由用户或管理员授权才能访问所需的 Microsoft Graph 资源。</span><span class="sxs-lookup"><span data-stu-id="c2120-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="c2120-117">如果你已熟悉将应用与 Microsoft 标识平台集成以获取令牌，请参阅"下一步[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)"部分，了解特定于 Microsoft Graph 的信息和示例。</span><span class="sxs-lookup"><span data-stu-id="c2120-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="c2120-118">**混合环境：** 导出 API 支持在本地 Exchange 和 Teams (混合环境中预配的用户发送) 。</span><span class="sxs-lookup"><span data-stu-id="c2120-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="c2120-119">为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。</span><span class="sxs-lookup"><span data-stu-id="c2120-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="c2120-120">**用户删除的消息：** 用户从 Teams 客户端中删除的消息可以使用导出 API 访问，自删除起最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="c2120-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="c2120-121">**邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。</span><span class="sxs-lookup"><span data-stu-id="c2120-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="c2120-122">使用导出 API 可以检索邮件中附加的文件。</span><span class="sxs-lookup"><span data-stu-id="c2120-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="c2120-123">**聊天消息属性：** 请参阅此处 Teams 导出 API 支持的属性 [的完整列表](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。</span><span class="sxs-lookup"><span data-stu-id="c2120-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="c2120-124">如何访问 Teams 导出 API</span><span class="sxs-lookup"><span data-stu-id="c2120-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="c2120-125">**示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：</span><span class="sxs-lookup"><span data-stu-id="c2120-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- <span data-ttu-id="c2120-126">**示例 2** 是一个示例查询，它通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：</span><span class="sxs-lookup"><span data-stu-id="c2120-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="c2120-127">如果有多个结果，API 会返回包含下一页链接的响应。</span><span class="sxs-lookup"><span data-stu-id="c2120-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="c2120-128">要获取下一组结果，只需从 @odata.nextlink 对 URL 调用 GET。</span><span class="sxs-lookup"><span data-stu-id="c2120-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="c2120-129">如果@odata.nextlink 不存在或为 null，则检索所有消息。</span><span class="sxs-lookup"><span data-stu-id="c2120-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="c2120-130">访问 Teams 导出 API 的先决条件</span><span class="sxs-lookup"><span data-stu-id="c2120-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="c2120-131">Teams 导出 API 目前以预览版提供。</span><span class="sxs-lookup"><span data-stu-id="c2120-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="c2120-132">它仅可供拥有 API 所需许可证 [的用户和租户](https://aka.ms/teams-changenotification-licenses) 使用。</span><span class="sxs-lookup"><span data-stu-id="c2120-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="c2120-133">将来，Microsoft 可能会要求你或你的客户根据通过 API 访问的数据量支付额外的费用。</span><span class="sxs-lookup"><span data-stu-id="c2120-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="c2120-134">Microsoft Graph 中访问敏感数据的 Microsoft Teams API 被视为受保护的 API。</span><span class="sxs-lookup"><span data-stu-id="c2120-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="c2120-135">导出 API 要求在权限和许可之外拥有其他验证，然后才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="c2120-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="c2120-136">若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="c2120-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="c2120-137">应用程序权限由在不存在登录用户的情况下运行的应用使用;应用程序权限只能由管理员许可。</span><span class="sxs-lookup"><span data-stu-id="c2120-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="c2120-138">需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="c2120-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="c2120-139">*Chat.Read.All：* 允许访问所有 1：1 和群组聊天消息</span><span class="sxs-lookup"><span data-stu-id="c2120-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="c2120-140">*User.Read.All：* 允许访问租户的用户列表</span><span class="sxs-lookup"><span data-stu-id="c2120-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="c2120-141">JSON 表示形式</span><span class="sxs-lookup"><span data-stu-id="c2120-141">JSON representation</span></span>

<span data-ttu-id="c2120-142">以下示例是资源的 JSON 表示形式：</span><span class="sxs-lookup"><span data-stu-id="c2120-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="c2120-143">命名空间：microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="c2120-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="c2120-144">有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型文章](https://docs.microsoft.com/graph/api/resources/chatmessage) 。</span><span class="sxs-lookup"><span data-stu-id="c2120-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
