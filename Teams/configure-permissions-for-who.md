---
title: 针对 Who 配置权限
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 在 Microsoft Teams 中部署云语音功能实践指导
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860212"
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="8c1c5-103">针对 Who 配置权限</span><span class="sxs-lookup"><span data-stu-id="8c1c5-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="8c1c5-104">用户可以结合使用 Who 应用与 Microsoft Teams 来帮助他们根据其处理的内容及其共事的人员提出问题并在组织中查找任何人。</span><span class="sxs-lookup"><span data-stu-id="8c1c5-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="8c1c5-105">为了确保用户可以充分利用 Who，你必须在 Microsoft Graph 中启用以下成员权限。</span><span class="sxs-lookup"><span data-stu-id="8c1c5-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="8c1c5-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="8c1c5-106">Calendars.Read</span></span>

- <span data-ttu-id="8c1c5-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="8c1c5-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="8c1c5-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="8c1c5-108">Mail.Read</span></span>

- <span data-ttu-id="8c1c5-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8c1c5-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="8c1c5-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="8c1c5-110">People.Read</span></span>

- <span data-ttu-id="8c1c5-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c1c5-111">People.Read.All</span></span>

- <span data-ttu-id="8c1c5-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c1c5-112">Sites.Read.All</span></span>

- <span data-ttu-id="8c1c5-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="8c1c5-113">User.Read.All</span></span>

<span data-ttu-id="8c1c5-114">有关如何管理 Microsoft Graph 权限范围的详细信息，请参阅[权限范围](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)。</span><span class="sxs-lookup"><span data-stu-id="8c1c5-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="8c1c5-115">有关 Microsoft Graph 权限的详细信息，请参阅 [Microsoft Graph 权限参考](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)。</span><span class="sxs-lookup"><span data-stu-id="8c1c5-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>