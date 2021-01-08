---
title: 使用 Microsoft Teams 范围目录搜索
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft Teams 范围目录搜索提供目录的自定义视图。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779926"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="edeb1-103">使用 Microsoft Teams 范围目录搜索</span><span class="sxs-lookup"><span data-stu-id="edeb1-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="edeb1-104">Microsoft Teams 目录搜索允许组织创建虚拟边界，控制用户如何查找组织中其他用户并与他人通信。</span><span class="sxs-lookup"><span data-stu-id="edeb1-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="edeb1-105">Microsoft Teams 允许组织向用户提供目录的自定义视图。</span><span class="sxs-lookup"><span data-stu-id="edeb1-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="edeb1-106">Microsoft Teams 使用 [信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 来支持这些自定义视图。</span><span class="sxs-lookup"><span data-stu-id="edeb1-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="edeb1-107">启用策略后，搜索其他用户返回的结果 (例如，启动聊天或将成员添加到团队) 将按配置的策略进行范围。</span><span class="sxs-lookup"><span data-stu-id="edeb1-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="edeb1-108">当范围搜索生效时，用户将无法搜索或发现团队。</span><span class="sxs-lookup"><span data-stu-id="edeb1-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="edeb1-109">在 Exchange 混合环境中，此功能仅适用于 Exchange Online 邮箱，而与本地邮箱不同。</span><span class="sxs-lookup"><span data-stu-id="edeb1-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="edeb1-110">何时应该使用范围目录搜索？</span><span class="sxs-lookup"><span data-stu-id="edeb1-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="edeb1-111">受益于范围目录搜索的方案类似于通讯簿策略方案。</span><span class="sxs-lookup"><span data-stu-id="edeb1-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="edeb1-112">例如，在下列情况下，可能需要使用范围目录搜索：</span><span class="sxs-lookup"><span data-stu-id="edeb1-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="edeb1-113">贵组织的租户中有多家你要保持独立的公司。</span><span class="sxs-lookup"><span data-stu-id="edeb1-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="edeb1-114">贵学校要限制教职员工与学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="edeb1-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="edeb1-115">若要了解如何使用通讯簿策略，请阅读 Exchange [Online 中的信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="edeb1-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edeb1-116">通讯簿策略仅从目录角度提供用户虚拟分离。</span><span class="sxs-lookup"><span data-stu-id="edeb1-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="edeb1-117">另请注意，在强制执行新的或更新的通讯簿策略之前，已缓存的任何用户数据将保留给用户最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="edeb1-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="edeb1-118">启用作用域目录搜索</span><span class="sxs-lookup"><span data-stu-id="edeb1-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="edeb1-119">使用信息屏障策略将组织配置为虚拟子组。</span><span class="sxs-lookup"><span data-stu-id="edeb1-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="edeb1-120">有关详细信息，请参阅"定义[信息屏障策略"。](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="edeb1-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="edeb1-121">在 Microsoft Teams 管理中心中，选择 **"组织范围的设置**  >  **Teams 设置"。**</span><span class="sxs-lookup"><span data-stu-id="edeb1-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="edeb1-122">在 **"搜索**"下，在 Teams 中使用 Exchange 通讯簿策略搜索范围目录 (**ABP) ，** 打开 **开关**。</span><span class="sxs-lookup"><span data-stu-id="edeb1-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 管理中心内的范围目录搜索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="edeb1-124">此更改可能需要几个小时才能复制。</span><span class="sxs-lookup"><span data-stu-id="edeb1-124">This change can take a few hours to replicate.</span></span>
