---
title: 使用 Microsoft Teams 范围目录搜索
author: LolaJacobsen
ms.author: lolaj
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
description: 了解如何使用 Microsoft 团队范围的目录搜索以提供目录的自定义视图。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca20e7293f20d68ea98f61a98090f7892ba294e8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836942"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="3f90f-103">使用 Microsoft Teams 范围目录搜索</span><span class="sxs-lookup"><span data-stu-id="3f90f-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="3f90f-104">Microsoft 团队范围目录搜索允许组织创建虚拟边界，以控制用户如何与组织中的其他用户进行查找和通信。</span><span class="sxs-lookup"><span data-stu-id="3f90f-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="3f90f-105">Microsoft 团队允许组织向其用户提供目录的自定义视图。</span><span class="sxs-lookup"><span data-stu-id="3f90f-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="3f90f-106">Microsoft 团队使用[信息障碍策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)来支持这些自定义视图。</span><span class="sxs-lookup"><span data-stu-id="3f90f-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="3f90f-107">启用策略后，搜索其他用户（例如启动聊天或向团队添加成员）所返回的结果将按配置的策略确定范围。</span><span class="sxs-lookup"><span data-stu-id="3f90f-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="3f90f-108">当范围搜索生效时，用户将无法搜索或发现团队。</span><span class="sxs-lookup"><span data-stu-id="3f90f-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="3f90f-109">在 Exchange 混合环境中，此功能仅适用于 Exchange Online 邮箱，而不适用于本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="3f90f-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="3f90f-110">何时应使用目录搜索范围？</span><span class="sxs-lookup"><span data-stu-id="3f90f-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="3f90f-111">从作用域目录搜索中受益的方案类似于通讯簿策略方案。</span><span class="sxs-lookup"><span data-stu-id="3f90f-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="3f90f-112">例如，你可能希望在以下情况下使用限定的目录搜索：</span><span class="sxs-lookup"><span data-stu-id="3f90f-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="3f90f-113">贵组织的租户中有多家你要保持独立的公司。</span><span class="sxs-lookup"><span data-stu-id="3f90f-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="3f90f-114">贵学校要限制教职员工与学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="3f90f-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="3f90f-115">若要了解如何使用通讯簿策略，请参阅[Exchange Online 中的信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="3f90f-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f90f-116">通讯簿策略仅提供用户从目录角度进行虚拟分离。</span><span class="sxs-lookup"><span data-stu-id="3f90f-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="3f90f-117">通过提供完整的电子邮件地址，用户仍然可以发起与其他人的通信。</span><span class="sxs-lookup"><span data-stu-id="3f90f-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="3f90f-118">另外，请务必注意，在实施新的或更新的通讯簿策略之前，已缓存的任何用户数据在30天内仍可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="3f90f-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="3f90f-119">打开范围的目录搜索</span><span class="sxs-lookup"><span data-stu-id="3f90f-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="3f90f-120">使用信息屏障策略将组织配置为虚拟子组。</span><span class="sxs-lookup"><span data-stu-id="3f90f-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="3f90f-121">有关详细信息，请参阅[定义信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="3f90f-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="3f90f-122">在 "Microsoft 团队管理中心" 中，选择 "**组织范围设置** > "**团队设置**。</span><span class="sxs-lookup"><span data-stu-id="3f90f-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="3f90f-123">在 "**搜索**" 下，在**使用 Exchange 通讯簿策略（APB）的团队中的 "范围目录搜索**" 旁边，打开 "打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="3f90f-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft 团队管理中心中的范围目录搜索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="3f90f-125">此更改可能需要长达24小时才能进行复制。</span><span class="sxs-lookup"><span data-stu-id="3f90f-125">This change can take up to 24 hours to replicate.</span></span>
