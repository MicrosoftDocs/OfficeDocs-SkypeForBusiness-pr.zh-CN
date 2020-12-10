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
ms.openlocfilehash: 896e60e8de6e01208a07c40e757a79a12192383a
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611816"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="61edc-103">将内容与 Microsoft 团队导出 Api 一起导出</span><span class="sxs-lookup"><span data-stu-id="61edc-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="61edc-104">团队导出 Api 允许你从 Microsoft 团队导出1:1 和群组聊天消息。</span><span class="sxs-lookup"><span data-stu-id="61edc-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="61edc-105">如果你的组织需要导出 Microsoft 团队邮件，你可以使用团队导出 Api 提取它们。</span><span class="sxs-lookup"><span data-stu-id="61edc-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="61edc-106">*聊天消息* 表示 [频道](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 或 [聊天](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)中的单个聊天消息。</span><span class="sxs-lookup"><span data-stu-id="61edc-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="61edc-107">聊天消息可以是根聊天消息，也可以是由聊天消息中的 **replyToId** 属性定义的答复线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="61edc-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="61edc-108">下面是有关如何使用这些导出 Api 的一些示例：</span><span class="sxs-lookup"><span data-stu-id="61edc-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="61edc-109">**示例 1**：如果你已在组织中启用 microsoft 团队，并且希望通过传递给定用户的日期范围以编程方式导出所有 microsoft 团队邮件到日期。</span><span class="sxs-lookup"><span data-stu-id="61edc-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="61edc-110">**示例 2**：如果希望通过提供日期范围以编程方式每天导出所有用户消息。</span><span class="sxs-lookup"><span data-stu-id="61edc-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="61edc-111">导出 Api 可以检索在给定日期范围内创建或更新的所有消息。</span><span class="sxs-lookup"><span data-stu-id="61edc-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="61edc-112">团队导出 Api 支持哪些内容？</span><span class="sxs-lookup"><span data-stu-id="61edc-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="61edc-113">**批量导出团队邮件：** 团队导出 Api 支持每个租户的 200 RPS 和应用程序的 600 RPS，但这些限制应能够批量导出团队邮件。</span><span class="sxs-lookup"><span data-stu-id="61edc-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="61edc-114">**应用程序上下文**：若要调用 microsoft Graph，你的应用必须从 Microsoft identity platform 获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="61edc-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="61edc-115">访问令牌包含有关应用的信息以及它对通过 Microsoft Graph 可用的资源和 Api 所拥有的权限。</span><span class="sxs-lookup"><span data-stu-id="61edc-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="61edc-116">若要获取访问令牌，你的应用必须向 Microsoft identity 平台注册，并由用户或管理员授权，以便访问它所需的 Microsoft Graph 资源。</span><span class="sxs-lookup"><span data-stu-id="61edc-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="61edc-117">如果你已熟悉将应用与 Microsoft identity 平台集成以获取令牌，请参阅 " [后续步骤](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) " 部分，了解特定于 microsoft Graph 的信息和示例。</span><span class="sxs-lookup"><span data-stu-id="61edc-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="61edc-118">**混合环境：** 导出 Api 支持在混合环境上预配的用户发送的消息 (本地 Exchange 和团队) 。</span><span class="sxs-lookup"><span data-stu-id="61edc-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="61edc-119">为混合环境配置的用户发送的任何消息都可通过导出 Api 进行访问。</span><span class="sxs-lookup"><span data-stu-id="61edc-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="61edc-120">**用户已删除邮件：** 从团队客户端删除的邮件可以使用从删除时起30天内的 "导出 Api" 访问。</span><span class="sxs-lookup"><span data-stu-id="61edc-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="61edc-121">**邮件附件：** 导出 Api 包括作为邮件的一部分发送的附件的链接。</span><span class="sxs-lookup"><span data-stu-id="61edc-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="61edc-122">使用导出 Api，可以检索邮件中附加的文件。</span><span class="sxs-lookup"><span data-stu-id="61edc-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="61edc-123">**聊天消息属性：** 请参阅 [此处](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)的团队导出 api 支持的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="61edc-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="61edc-124">如何访问团队导出 Api</span><span class="sxs-lookup"><span data-stu-id="61edc-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="61edc-125">**示例 1** 是一种简单查询，用于检索不带任何筛选器的用户的所有消息：</span><span class="sxs-lookup"><span data-stu-id="61edc-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="61edc-126">**示例 2** 是一个示例查询，它通过指定日期时间筛选器和 top 50 消息来检索用户的所有消息：</span><span class="sxs-lookup"><span data-stu-id="61edc-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="61edc-127">当出现多个结果时，API 返回与下一页链接的响应。</span><span class="sxs-lookup"><span data-stu-id="61edc-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="61edc-128">若要获取下一组结果，只需调用来自 @odata 的 url 即可。</span><span class="sxs-lookup"><span data-stu-id="61edc-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="61edc-129">@Odata 如果 nextlink 不存在或为 null，则检索所有消息。</span><span class="sxs-lookup"><span data-stu-id="61edc-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="61edc-130">访问团队导出 Api 的先决条件</span><span class="sxs-lookup"><span data-stu-id="61edc-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="61edc-131">团队导出 Api 当前处于预览版中。</span><span class="sxs-lookup"><span data-stu-id="61edc-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="61edc-132">它仅适用于具有 Api [所需的许可证](https://aka.ms/teams-changenotification-licenses) 的用户和租户。</span><span class="sxs-lookup"><span data-stu-id="61edc-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="61edc-133">将来，Microsoft 可能会要求您或您的客户根据通过该 API 访问的数据量支付额外费用。</span><span class="sxs-lookup"><span data-stu-id="61edc-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="61edc-134">Microsoft Graph 中的 microsoft 团队 Api 访问敏感数据被视为受保护的 Api。</span><span class="sxs-lookup"><span data-stu-id="61edc-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="61edc-135">导出 Api 要求你拥有其他验证（除权限和同意），然后才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="61edc-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="61edc-136">若要请求对这些受保护的 Api 的访问权限，请填写 " [请求" 表单](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="61edc-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="61edc-137">应用程序权限由在没有登录用户的情况下运行的应用使用;只有管理员才能同意应用程序权限。</span><span class="sxs-lookup"><span data-stu-id="61edc-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="61edc-138">需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="61edc-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="61edc-139">已 *阅读 "聊天*"。所有：支持对所有1:1 和群组聊天消息的访问</span><span class="sxs-lookup"><span data-stu-id="61edc-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="61edc-140">*User Read。 All*：启用对租户的用户列表的访问权限</span><span class="sxs-lookup"><span data-stu-id="61edc-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="61edc-141">JSON 表示形式</span><span class="sxs-lookup"><span data-stu-id="61edc-141">JSON representation</span></span>

<span data-ttu-id="61edc-142">以下示例是资源的 JSON 表示形式：</span><span class="sxs-lookup"><span data-stu-id="61edc-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="61edc-143">命名空间： microsoft graph</span><span class="sxs-lookup"><span data-stu-id="61edc-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="61edc-144">有关 chatMessage 资源的更多详细信息，请参阅 [chatMessage 资源类型](https://docs.microsoft.com/graph/api/resources/chatmessage) 文章。</span><span class="sxs-lookup"><span data-stu-id="61edc-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
