---
title: "针对 Who 配置权限"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "在 Microsoft Teams 中部署云语音功能实践指导"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="a53dd-103">针对 Who 配置权限</span><span class="sxs-lookup"><span data-stu-id="a53dd-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="a53dd-104">用户可以结合使用 Who 应用与 Microsoft Teams 来帮助他们根据其处理的内容及其共事的人员提出问题并在组织中查找任何人。</span><span class="sxs-lookup"><span data-stu-id="a53dd-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="a53dd-105">为了确保用户可以充分利用 Who，你必须在 Microsoft Graph 中启用以下成员权限。</span><span class="sxs-lookup"><span data-stu-id="a53dd-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="a53dd-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="a53dd-106">Calendars.Read</span></span>

- <span data-ttu-id="a53dd-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="a53dd-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="a53dd-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="a53dd-108">Mail.Read</span></span>

- <span data-ttu-id="a53dd-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a53dd-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="a53dd-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="a53dd-110">People.Read</span></span>

- <span data-ttu-id="a53dd-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="a53dd-111">People.Read.All</span></span>

- <span data-ttu-id="a53dd-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="a53dd-112">Sites.Read.All</span></span>

- <span data-ttu-id="a53dd-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="a53dd-113">User.Read.All</span></span>

<span data-ttu-id="a53dd-114">有关如何管理 Microsoft Graph 权限范围的详细信息，请参阅[权限范围](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)。</span><span class="sxs-lookup"><span data-stu-id="a53dd-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="a53dd-115">有关 Microsoft Graph 权限的详细信息，请参阅 [Microsoft Graph 权限参考](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)。</span><span class="sxs-lookup"><span data-stu-id="a53dd-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>