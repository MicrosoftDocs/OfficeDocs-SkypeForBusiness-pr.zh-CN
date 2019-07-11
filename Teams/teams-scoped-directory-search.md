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
- Teams_ITAdmin_Help
description: 了解如何使用 Microsoft 团队范围的目录搜索以提供目录的自定义视图。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 068a37af62ea31c53caed8c9dc22feec6fd60ec6
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "35614257"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="2a100-103">使用 Microsoft Teams 范围目录搜索</span><span class="sxs-lookup"><span data-stu-id="2a100-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="2a100-104">Microsoft 团队范围目录搜索允许组织创建虚拟边界, 以控制用户如何与组织中的其他用户进行查找和通信。</span><span class="sxs-lookup"><span data-stu-id="2a100-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="2a100-105">Microsoft 团队允许组织向其用户提供目录的自定义视图。</span><span class="sxs-lookup"><span data-stu-id="2a100-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="2a100-106">Microsoft 团队使用[Exchange 通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)来支持这些自定义视图。</span><span class="sxs-lookup"><span data-stu-id="2a100-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="2a100-107">启用策略后, 搜索其他用户 (例如启动聊天或向团队添加成员) 所返回的结果将按配置的策略确定范围。</span><span class="sxs-lookup"><span data-stu-id="2a100-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="2a100-108">当范围搜索生效时, 用户将无法搜索或发现团队。</span><span class="sxs-lookup"><span data-stu-id="2a100-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="2a100-109">何时应使用目录搜索范围？</span><span class="sxs-lookup"><span data-stu-id="2a100-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="2a100-110">从作用域目录搜索中受益的方案类似于通讯簿策略方案。</span><span class="sxs-lookup"><span data-stu-id="2a100-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="2a100-111">例如, 你可能希望在以下情况下使用限定的目录搜索:</span><span class="sxs-lookup"><span data-stu-id="2a100-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="2a100-112">贵组织的租户中有多家你要保持独立的公司。</span><span class="sxs-lookup"><span data-stu-id="2a100-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="2a100-113">贵学校要限制教职员工与学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="2a100-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="2a100-114">若要了解如何使用通讯簿策略, 请[在 Exchange Online 中阅读 "通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)"。</span><span class="sxs-lookup"><span data-stu-id="2a100-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a100-115">通讯簿策略仅提供用户从目录角度进行虚拟分离。</span><span class="sxs-lookup"><span data-stu-id="2a100-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="2a100-116">通过提供完整的电子邮件地址, 用户仍然可以发起与其他人的通信。</span><span class="sxs-lookup"><span data-stu-id="2a100-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="2a100-117">另外, 请务必注意, 在实施新的或更新的通讯簿策略之前, 已缓存的任何用户数据在30天内仍可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="2a100-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="2a100-118">打开范围的目录搜索</span><span class="sxs-lookup"><span data-stu-id="2a100-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="2a100-119">使用通讯簿策略将您的组织配置为虚拟子组。</span><span class="sxs-lookup"><span data-stu-id="2a100-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="2a100-120">有关详细信息, 请参阅[通讯簿策略的过程](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="2a100-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="2a100-121">在 "Microsoft 团队管理中心" 中, 选择 "**组织范围设置** > "**团队设置**。</span><span class="sxs-lookup"><span data-stu-id="2a100-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="2a100-122">在 "**搜索**" 下, 在**使用 Exchange 通讯簿策略 (APB) 的团队中的 "范围目录搜索**" 旁边, 打开 "打开"。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2a100-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft 团队管理中心中的范围目录搜索](media/teams-scoped-directory-search-image1.png)



