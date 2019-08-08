---
title: 在 Microsoft Teams 中创建团队时规划 Office 365 组
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在规划 Office 365 组时应做出的决策, 例如选择 "公共" 和 "专用组", 使用 "团队客户端" 或 "Office 365 管理" web 控制台, 以及如何指导团队使用对话。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b23525181de02cfe8498aa68db5c6c34e9feaded
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237430"
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="c2109-103">在 Microsoft Teams 中创建团队时规划 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c2109-103">Plan for Office 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="c2109-104">在考虑使用 Office 365 组时或创建团队时，请考虑团队的用途、哪些人应该有访问权限，以及团队要求实现的成果。</span><span class="sxs-lookup"><span data-stu-id="c2109-104">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="c2109-105">尤其要注意你创建的频道数，因为用户会由于内容传播太散（使用的频道太多）而很快变得难以忍受。</span><span class="sxs-lookup"><span data-stu-id="c2109-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="c2109-106">有两种应用场景可以用来围绕 Office 365 组的规划及其对（或受）Microsoft Teams 的影响展开某些讨论：</span><span class="sxs-lookup"><span data-stu-id="c2109-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="c2109-107">首先, 由于客户可以在组中拥有现有投资, 因此我们目前同时支持少于5000个成员的公共和专用组。</span><span class="sxs-lookup"><span data-stu-id="c2109-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="c2109-108">如前面所述, 你希望使用团队客户端 (而不是 Office 365 管理 web 控制台) 管理人员对团队的成员身份。</span><span class="sxs-lookup"><span data-stu-id="c2109-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="c2109-109">在此方案中, 如果用户用于 Office 365 组中的串接对话, 则值得注意, 组对话实质上是电子邮件, 而不是与团队频道中的聊天消息相同。</span><span class="sxs-lookup"><span data-stu-id="c2109-109">Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="c2109-110">向你的用户解释此差异，并建议他们采用 Teams 中更加灵活的聊天消息，而不是使用 Outlook 或 OWA 向组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c2109-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="c2109-111">其次，对于在 Office 365 中没有定义现有组的客户，你可以使用 Office 365 管理门户、Teams Web 控制台或桌面控制台来创建组。</span><span class="sxs-lookup"><span data-stu-id="c2109-111">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients.</span></span> <span data-ttu-id="c2109-112">如前所述，使用 Teams 客户端管理与 Office 365 的所有未来成员身份。</span><span class="sxs-lookup"><span data-stu-id="c2109-112">As mentioned previously, manage all future membership to the Office 365 Group using the Teams client.</span></span> <span data-ttu-id="c2109-113">由于对团队的成员身份也定义了 Office 365 组的成员身份, 因此应为用户准备此更改。</span><span class="sxs-lookup"><span data-stu-id="c2109-113">Since membership to a team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="c2109-114">Teams 遵循 Office 365 组命名策略（在私人预览版中）</span><span class="sxs-lookup"><span data-stu-id="c2109-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="c2109-115">在 Teams 中，当用户创建或编辑团队名称时，将应用你的管理员制定的任何 Office 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="c2109-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="c2109-116">其中包括强制前缀或后缀等内容，以及排除禁用词语。</span><span class="sxs-lookup"><span data-stu-id="c2109-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="c2109-117">此功能为私人预览版，即如果你不是此预览版的一部分，则 Teams 尚不遵循此 Office 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="c2109-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="c2109-118">要了解详细信息，请参阅 [Teams 中的 Office 365 组命名策略](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="c2109-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="c2109-119">以下文章是查找 Office 365 组的准备情况和采纳内容的好地方:</span><span class="sxs-lookup"><span data-stu-id="c2109-119">The following articles are a good place to find readiness and adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="c2109-120">在 Outlook 中通过组获得更多</span><span class="sxs-lookup"><span data-stu-id="c2109-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="c2109-121">使用 Microsoft 365 管理中心添加或删除 Office 365 组中的成员</span><span class="sxs-lookup"><span data-stu-id="c2109-121">Add or remove members from Office 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="c2109-122">还原已删除的 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c2109-122">Restore a deleted Office 365 Group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
