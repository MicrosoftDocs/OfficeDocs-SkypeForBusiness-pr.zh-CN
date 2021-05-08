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
ms.openlocfilehash: 013cd992619264f875841b1b6bb13aca3943d14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092441"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="e1586-103">使用导出 API Microsoft Teams内容</span><span class="sxs-lookup"><span data-stu-id="e1586-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="e1586-104">Teams使用导出 API，你可以从游戏导出 1：1、群组聊天、会议聊天和Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e1586-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="e1586-105">如果组织需要导出Microsoft Teams，可以使用导出 API Teams它们。</span><span class="sxs-lookup"><span data-stu-id="e1586-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="e1586-106">*聊天消息* 表示频道 [或聊天中的](/graph/api/resources/channel?view=graph-rest-beta) 单个聊天 [消息](/graph/api/resources/chat?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="e1586-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="e1586-107">聊天消息可以是聊天消息中的根聊天消息或由 **聊天消息中的 replyToId** 属性定义的回复线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="e1586-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="e1586-108">下面是一些有关如何使用这些导出 API 的示例：</span><span class="sxs-lookup"><span data-stu-id="e1586-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="e1586-109">**示例 1：** 如果已启用Microsoft Teams，并且想要通过传递给定用户或团队的日期范围，以编程方式导出所有 Microsoft Teams 消息。</span><span class="sxs-lookup"><span data-stu-id="e1586-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="e1586-110">**示例 2：** 如果要通过提供日期范围以编程方式每天导出所有用户或团队消息。</span><span class="sxs-lookup"><span data-stu-id="e1586-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="e1586-111">导出 API 可以检索在给定日期范围内创建或更新的所有消息。</span><span class="sxs-lookup"><span data-stu-id="e1586-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="e1586-112">导出 API 支持Teams哪些功能？</span><span class="sxs-lookup"><span data-stu-id="e1586-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="e1586-113">批量导出 **Teams** 消息：Teams 导出 API 支持每个租户每个应用最多 200 个 RPS，应用程序最多支持 600 个 RPS，这些限制应该可以批量导出 Teams 消息。</span><span class="sxs-lookup"><span data-stu-id="e1586-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="e1586-114">**应用程序上下文**：若要调用 Microsoft Graph，你的应用必须从应用程序获取访问Microsoft 标识平台。</span><span class="sxs-lookup"><span data-stu-id="e1586-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="e1586-115">访问令牌包含有关应用的信息，以及该应用对通过 Microsoft Graph 提供的资源和 API 的权限。</span><span class="sxs-lookup"><span data-stu-id="e1586-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="e1586-116">若要获取访问令牌，你的应用必须注册到 Microsoft 标识平台并且由用户或管理员授权才能访问所需的 Microsoft Graph资源。</span><span class="sxs-lookup"><span data-stu-id="e1586-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="e1586-117">如果已熟悉将应用与应用集成Microsoft 标识平台获取令牌，请参阅"下一步"部分，了解特定于[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)Microsoft Graph。</span><span class="sxs-lookup"><span data-stu-id="e1586-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="e1586-118">**混合环境：** 导出 API 支持在本地和本地混合环境中预配 (用户Exchange Teams) 。</span><span class="sxs-lookup"><span data-stu-id="e1586-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="e1586-119">为混合环境配置的用户发送的任何消息都可以使用导出 API 访问。</span><span class="sxs-lookup"><span data-stu-id="e1586-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="e1586-120">**用户已删除的消息：** 用户从客户端中删除的消息Teams自删除起最多 21 天内使用导出 API 访问。</span><span class="sxs-lookup"><span data-stu-id="e1586-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="e1586-121">**邮件附件：** 导出 API 包括作为邮件的一部分发送的附件的链接。</span><span class="sxs-lookup"><span data-stu-id="e1586-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="e1586-122">使用导出 API 可以检索邮件中附加的文件。</span><span class="sxs-lookup"><span data-stu-id="e1586-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="e1586-123">**聊天消息属性：** 请参阅此处导出 API 支持Teams的完整 [属性列表](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。</span><span class="sxs-lookup"><span data-stu-id="e1586-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="e1586-124">如何访问Teams API</span><span class="sxs-lookup"><span data-stu-id="e1586-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="e1586-125">**示例 1** 是一个简单的查询，用于检索用户或团队的所有消息，而无需任何筛选器：</span><span class="sxs-lookup"><span data-stu-id="e1586-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="e1586-126">**示例 2** 是一个示例查询，用于通过指定日期时间筛选器和前 50 条消息来检索用户或团队的所有消息：</span><span class="sxs-lookup"><span data-stu-id="e1586-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="e1586-127">如果有多个结果，API 会返回包含下一页链接的响应。</span><span class="sxs-lookup"><span data-stu-id="e1586-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="e1586-128">要获取下一组结果，只需从 @odata.nextlink 对 URL 调用 GET。</span><span class="sxs-lookup"><span data-stu-id="e1586-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="e1586-129">如果@odata.nextlink 不存在或为 null，则检索所有消息。</span><span class="sxs-lookup"><span data-stu-id="e1586-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="e1586-130">访问导出 API Teams的先决条件</span><span class="sxs-lookup"><span data-stu-id="e1586-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="e1586-131">Teams导出 API 目前以预览版提供。</span><span class="sxs-lookup"><span data-stu-id="e1586-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="e1586-132">它仅对具有 API 所需许可证 [的用户和租户](/graph/teams-licenses) 可用。</span><span class="sxs-lookup"><span data-stu-id="e1586-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="e1586-133">将来，Microsoft 可能会要求你或你的客户根据通过 API 访问的数据量支付额外费用。</span><span class="sxs-lookup"><span data-stu-id="e1586-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="e1586-134">Microsoft TeamsMicrosoft 中用于Graph敏感数据的 API 被视为受保护的 API。</span><span class="sxs-lookup"><span data-stu-id="e1586-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="e1586-135">导出 API 需要具有除权限和许可之外的附加验证才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="e1586-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="e1586-136">若要请求访问这些受保护的 API，请完成 [请求表单](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="e1586-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="e1586-137">应用程序权限由在没有登录用户的情况下运行的应用使用;应用程序权限只能由管理员许可。</span><span class="sxs-lookup"><span data-stu-id="e1586-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="e1586-138">需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="e1586-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="e1586-139">*Chat.Read.All：* 允许访问所有 1：1 和群组聊天消息</span><span class="sxs-lookup"><span data-stu-id="e1586-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="e1586-140">*User.Read.All：* 允许访问租户的用户列表</span><span class="sxs-lookup"><span data-stu-id="e1586-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="e1586-141">JSON 表示形式</span><span class="sxs-lookup"><span data-stu-id="e1586-141">JSON representation</span></span>

<span data-ttu-id="e1586-142">以下示例是资源的 JSON 表示形式：</span><span class="sxs-lookup"><span data-stu-id="e1586-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="e1586-143">命名空间：microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="e1586-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="e1586-144">有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型一](/graph/api/resources/chatmessage) 文。</span><span class="sxs-lookup"><span data-stu-id="e1586-144">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>