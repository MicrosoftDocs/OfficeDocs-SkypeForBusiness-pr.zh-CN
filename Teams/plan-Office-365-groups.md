---
title: 在创建团队时规划 Microsoft 365 组
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解如何规划团队中的 Microsoft 365 组，包括组之间的差异 & 团队对话，以及团队对组命名策略的看法。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 06b79bc049d25493e2fc6e221dca5f298f55e18d
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656263"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="01ddf-103">在 Microsoft 团队中创建团队时规划 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="01ddf-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="01ddf-104">在考虑使用 Microsoft 365 组或创建团队时，请考虑团队将用于哪些人员，以及团队预期将获得哪些结果。</span><span class="sxs-lookup"><span data-stu-id="01ddf-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="01ddf-105">尤其要注意你创建的频道数，因为用户会由于内容传播太散（使用的频道太多）而很快变得难以忍受。</span><span class="sxs-lookup"><span data-stu-id="01ddf-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="01ddf-106">有两种方案可在规划 Microsoft 365 组以及它们对 (或) Microsoft 团队的影响方面提供一些讨论：</span><span class="sxs-lookup"><span data-stu-id="01ddf-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="01ddf-107">首先，由于客户可以在组中拥有现有投资，因此我们目前同时支持少于5000个成员的公共和专用组。</span><span class="sxs-lookup"><span data-stu-id="01ddf-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="01ddf-108">如前面所述，你希望使用团队客户端（而不是 Microsoft 365 管理中心）管理人员对团队的成员身份。</span><span class="sxs-lookup"><span data-stu-id="01ddf-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="01ddf-109">在此情况下，如果人员用于 Microsoft 365 组中的线程对话，则值得注意，组对话实质上是电子邮件，而不是与团队频道中的聊天消息相同。</span><span class="sxs-lookup"><span data-stu-id="01ddf-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="01ddf-110">向你的用户解释此差异，并建议他们采用 Teams 中更加灵活的聊天消息，而不是使用 Outlook 或 OWA 向组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="01ddf-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="01ddf-111">其次，对于没有在 Microsoft 365 中定义的现有组的客户，您可以使用 Microsoft 365 管理中心、团队 web 站点或桌面客户端创建它们。</span><span class="sxs-lookup"><span data-stu-id="01ddf-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="01ddf-112">如前面所述，使用团队客户端管理 Microsoft 365 组的所有未来成员身份。</span><span class="sxs-lookup"><span data-stu-id="01ddf-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="01ddf-113">由于对团队的成员身份也定义了 Microsoft 365 组的成员身份，因此你应该为用户准备此更改。</span><span class="sxs-lookup"><span data-stu-id="01ddf-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="01ddf-114">团队尊重 Microsoft 365 组命名策略 (私人预览版) </span><span class="sxs-lookup"><span data-stu-id="01ddf-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="01ddf-115">用户创建或编辑团队名称时，将在团队中应用任何已由管理员设置的 Microsoft 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="01ddf-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="01ddf-116">其中包括强制前缀或后缀等内容，以及排除禁用词语。</span><span class="sxs-lookup"><span data-stu-id="01ddf-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="01ddf-117">此功能在私人预览版中，这意味着如果你不是此预览的一部分，则团队还不会遵守此 Microsoft 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="01ddf-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="01ddf-118">若要了解详细信息，请阅读[团队中的 Microsoft 365 组命名策略](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="01ddf-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="01ddf-119">以下文章是查找 Microsoft 365 组的准备情况和采纳内容的好地方：</span><span class="sxs-lookup"><span data-stu-id="01ddf-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="01ddf-120">在 Outlook 中通过组获得更多</span><span class="sxs-lookup"><span data-stu-id="01ddf-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="01ddf-121">使用 Microsoft 365 管理中心添加或删除 Microsoft 365 组中的成员</span><span class="sxs-lookup"><span data-stu-id="01ddf-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="01ddf-122">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="01ddf-122">Restore a deleted group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)