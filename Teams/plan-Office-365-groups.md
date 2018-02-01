---
title: "在 Microsoft Teams 中创建团队时规划 Office 365 组"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解在使用 Teams 客户端或 Office 365 管理 Web 控制台的情况下，规划 Office 365 时应制定的决策（例如，选择公用组和专用组），以及如何指导你的团队使用对话。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 330cb6e8eb572fc2fb4141a2cea8a0ad6055d309
ms.sourcegitcommit: 9861cc3eca070ef1c6b7375896ae1978a438c772
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="3b034-103">在 Microsoft Teams 中创建团队时规划 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="3b034-103">Plan for Office 365 groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="3b034-104">在考虑使用 Office 365 组时或创建团队时，请考虑团队的用途、哪些人应该有访问权限，以及团队要求实现的成果。</span><span class="sxs-lookup"><span data-stu-id="3b034-104">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="3b034-105">尤其要注意你创建的频道数，因为用户会由于内容传播太散（使用的频道太多）而很快变得难以忍受。</span><span class="sxs-lookup"><span data-stu-id="3b034-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="3b034-106">有两种应用场景可以用来围绕 Office 365 组的规划及其对（或受）Microsoft Teams 的影响展开某些讨论：</span><span class="sxs-lookup"><span data-stu-id="3b034-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="3b034-107">首先，由于客户可能在组中已有投入，我们当前支持少于 2500 个成员的公用组和专用组。</span><span class="sxs-lookup"><span data-stu-id="3b034-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 2500 members.</span></span> <span data-ttu-id="3b034-108">如前所述，你希望使用 Teams 客户端而不是 Office 365 管理 Web 控制台来管理用户与团队的成员身份。</span><span class="sxs-lookup"><span data-stu-id="3b034-108">As mentioned previously, you want to manage the membership of people to a Team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="3b034-109">在这种应用场景中，如果用户参与 Office 365 中的线索对话，值得注意的是，组对话基本上是电子邮件，而不是团队频道中的聊天消息。</span><span class="sxs-lookup"><span data-stu-id="3b034-109">Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Team channel.</span></span> <span data-ttu-id="3b034-110">向你的用户解释此差异，并建议他们采用 Teams 中更加灵活的聊天消息，而不是使用 Outlook 或 OWA 向组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3b034-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="3b034-111">其次，对于在 Office 365 中没有定义现有组的客户，你可以使用 Office 365 管理门户、Teams Web 控制台或桌面控制台来创建组。</span><span class="sxs-lookup"><span data-stu-id="3b034-111">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients.</span></span> <span data-ttu-id="3b034-112">如前所述，使用 Teams 客户端管理与 Office 365 的所有未来成员身份。</span><span class="sxs-lookup"><span data-stu-id="3b034-112">As mentioned previously, manage all future membership to the Office 365 Group using the Teams client.</span></span> <span data-ttu-id="3b034-113">由于与团队的成员身份也定义与 Office 365 的所有成员身份，你应该让用户准备好接受此变更。</span><span class="sxs-lookup"><span data-stu-id="3b034-113">Since membership to a Team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="3b034-114">Teams 遵循 Office 365 组命名策略（在私人预览版中）</span><span class="sxs-lookup"><span data-stu-id="3b034-114">Teams respects Office 365 Groups naming policy</span></span>
<span data-ttu-id="3b034-115">在 Teams 中，当用户创建或编辑团队名称时，将应用你的管理员制定的任何 Office 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="3b034-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="3b034-116">其中包括强制前缀或后缀等内容，以及排除禁用词语。</span><span class="sxs-lookup"><span data-stu-id="3b034-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="3b034-117">此功能为私人预览版，即如果你不是此预览版的一部分，则 Teams 尚不遵循此 Office 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="3b034-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="3b034-118">要了解详细信息，请参阅 [Teams 中的 Office 365 组命名策略](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="3b034-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="3b034-119">要了解 Office 365 组的就绪和采用内容，建议参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="3b034-119">The following articles are a good place to find readiness & adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="3b034-120">在 Outlook 中通过组获得更多</span><span class="sxs-lookup"><span data-stu-id="3b034-120">Get more with groups in Outlook</span></span>](https://support.office.com/en-us/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

<!-- -->

-   [<span data-ttu-id="3b034-121">在 Office 365 管理中心中管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="3b034-121">Manage Group membership in the Office 365 admin center</span></span>](https://support.office.com/en-us/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)
