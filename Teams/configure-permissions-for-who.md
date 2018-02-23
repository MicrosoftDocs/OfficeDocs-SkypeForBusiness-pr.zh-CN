---
title: "针对 Who 配置权限"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "在 Microsoft Teams 中部署云语音功能实践指导"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="6c82f-103">针对 Who 配置权限</span><span class="sxs-lookup"><span data-stu-id="6c82f-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="6c82f-104">用户可以结合使用 Who 应用与 Microsoft Teams 来帮助他们根据其处理的内容及其共事的人员提出问题并在组织中查找任何人。</span><span class="sxs-lookup"><span data-stu-id="6c82f-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="6c82f-105">为了确保用户可以充分利用 Who，你必须在 Microsoft Graph 中启用以下成员权限。</span><span class="sxs-lookup"><span data-stu-id="6c82f-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="6c82f-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="6c82f-106">Calendars.Read</span></span>

- <span data-ttu-id="6c82f-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="6c82f-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="6c82f-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="6c82f-108">Mail.Read</span></span>

- <span data-ttu-id="6c82f-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6c82f-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="6c82f-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="6c82f-110">People.Read</span></span>

- <span data-ttu-id="6c82f-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c82f-111">People.Read.All</span></span>

- <span data-ttu-id="6c82f-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c82f-112">Sites.Read.All</span></span>

- <span data-ttu-id="6c82f-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c82f-113">User.Read.All</span></span>

<span data-ttu-id="6c82f-114">有关如何管理 Microsoft Graph 权限范围的详细信息，请参阅[权限范围](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)。</span><span class="sxs-lookup"><span data-stu-id="6c82f-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="6c82f-115">有关 Microsoft Graph 权限的详细信息，请参阅 [Microsoft Graph 权限参考](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference)。</span><span class="sxs-lookup"><span data-stu-id="6c82f-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span></span>