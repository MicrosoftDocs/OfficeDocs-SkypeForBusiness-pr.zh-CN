---
title: 使用 Microsoft 团队范围目录搜索
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Microsoft 团队作用域的目录搜索来提供目录的自定义的视图。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e9cddc12a5ef4de6dfb42a714b83e29b6fb4f5f
ms.sourcegitcommit: dba62f1cb6058e73a1a4c75f3473119a04a1b9e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2018
ms.locfileid: "25456888"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="69ce5-103">使用 Microsoft 团队范围目录搜索</span><span class="sxs-lookup"><span data-stu-id="69ce5-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="69ce5-104">Microsoft 团队作用域的目录搜索允许组织创建虚拟控制如何查找用户并与其他组织中的用户进行通信的边界。</span><span class="sxs-lookup"><span data-stu-id="69ce5-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="69ce5-105">Microsoft 团队允许组织为用户提供的目录的自定义视图。</span><span class="sxs-lookup"><span data-stu-id="69ce5-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="69ce5-106">Microsoft 团队使用[Exchange 通讯簿策略](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019)以支持这些自定义视图。</span><span class="sxs-lookup"><span data-stu-id="69ce5-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="69ce5-107">一旦启用了策略，将根据配置的策略作用域 （例如，若要启动聊天，或添加到团队的成员） 的其他用户搜索返回的结果。</span><span class="sxs-lookup"><span data-stu-id="69ce5-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="69ce5-108">用户不能进行搜索或发现并加入新团队之外这些策略。</span><span class="sxs-lookup"><span data-stu-id="69ce5-108">Users will not be able to search or discover and join new teams outside of these policies.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="69ce5-109">您应该何时使用作用域的目录搜索？</span><span class="sxs-lookup"><span data-stu-id="69ce5-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="69ce5-110">受益于作用域的目录搜索的方案在类似于通讯簿策略方案。</span><span class="sxs-lookup"><span data-stu-id="69ce5-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="69ce5-111">例如，您可能想要在下列情况下使用作用域的目录搜索：</span><span class="sxs-lookup"><span data-stu-id="69ce5-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="69ce5-112">您的组织具有多个公司内您希望用于保存单独其租户。</span><span class="sxs-lookup"><span data-stu-id="69ce5-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="69ce5-113">您的学校希望限制教职员工学生之间的聊天。</span><span class="sxs-lookup"><span data-stu-id="69ce5-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="69ce5-114">您可以了解有关如何使用通讯簿策略的详细信息[此处](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019)。</span><span class="sxs-lookup"><span data-stu-id="69ce5-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69ce5-115">通讯簿策略提供分隔的用户从目录角度仅虚拟。</span><span class="sxs-lookup"><span data-stu-id="69ce5-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="69ce5-116">通过提供完整的电子邮件地址，用户仍然可以发起与其他人进行通信。</span><span class="sxs-lookup"><span data-stu-id="69ce5-116">Users can still initiate communications with others by providing complete email addresses.</span></span> 

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="69ce5-117">启用作用域的目录搜索</span><span class="sxs-lookup"><span data-stu-id="69ce5-117">Enable scoped directory search</span></span>

1.  <span data-ttu-id="69ce5-118">使用通讯簿策略来配置您的组织到虚拟组子组。</span><span class="sxs-lookup"><span data-stu-id="69ce5-118">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="69ce5-119">有关详细信息，请参阅[通讯簿策略的过程](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019)。</span><span class="sxs-lookup"><span data-stu-id="69ce5-119">For more information, see [Procedures for address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="69ce5-120">登录到 Microsoft 365 管理中心，选择**管理中心**、，然后选择**工作组和 Skype**。</span><span class="sxs-lookup"><span data-stu-id="69ce5-120">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="69ce5-121">选择**组织范围设置**中的 Microsoft 团队业务管理中心的 Skype， > **团队设置**。</span><span class="sxs-lookup"><span data-stu-id="69ce5-121">In the Microsoft Teams & Skype for Business admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="69ce5-122">在**搜索\*\*\*\*作用域目录搜索团队使用 Exchange 通讯簿策略 (APB) 中的**，旁边的下启用**上**的切换。</span><span class="sxs-lookup"><span data-stu-id="69ce5-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![范围内的目录搜索团队和 Skype 业务管理中心](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="69ce5-124">混合配置 （与 Exchange 内部部署团队） 不支持限定的搜索模式。</span><span class="sxs-lookup"><span data-stu-id="69ce5-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

