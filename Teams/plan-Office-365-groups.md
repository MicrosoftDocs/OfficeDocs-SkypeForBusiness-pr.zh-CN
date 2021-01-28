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
description: 了解在 Teams 中规划 Microsoft 365 组，包括 Teams 对话中组&之间的差异，以及 Teams 如何遵守组命名策略。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: a6d52b656726d793649f4c6fadc117ec9e052816
ms.sourcegitcommit: 654199b413d1c0ab3feffbb9b7d7ddfa021ec273
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032361"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="40f07-103">在 Microsoft Teams 中创建团队时规划 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="40f07-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="40f07-104">在考虑使用 Microsoft 365 组或创建团队时，请考虑团队将用于什么目的、谁应具有访问权限，以及团队期望实现什么结果。</span><span class="sxs-lookup"><span data-stu-id="40f07-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="40f07-105">尤其要注意你创建的频道数，因为用户会由于内容传播太散（使用的频道太多）而很快变得难以忍受。</span><span class="sxs-lookup"><span data-stu-id="40f07-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="40f07-106">有两种方案需要讨论 Microsoft 365 组的规划及其对 (或 Microsoft Teams) 的影响：</span><span class="sxs-lookup"><span data-stu-id="40f07-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="40f07-107">首先，由于客户可以在组方面拥有现有投资，我们目前同时支持公共组和专用组，有关当前支持的成员数，请参阅 [Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)的限制和规范。</span><span class="sxs-lookup"><span data-stu-id="40f07-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span> <span data-ttu-id="40f07-108">如前所述，您希望使用 Teams 客户端（而不是 Microsoft 365 管理中心）管理团队中的人员成员身份。</span><span class="sxs-lookup"><span data-stu-id="40f07-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="40f07-109">在此方案中，如果用户习惯于 Microsoft 365 组中的话题对话，则值得注意的是，组对话本质上是电子邮件，与 Teams 频道中的聊天消息不同。</span><span class="sxs-lookup"><span data-stu-id="40f07-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="40f07-110">向你的用户解释此差异，并建议他们采用 Teams 中更加灵活的聊天消息，而不是使用 Outlook 或 OWA 向组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="40f07-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="40f07-111">其次，对于没有在 Microsoft 365 中定义现有组的客户，可以使用 Microsoft 365 管理中心、Teams Web 或桌面客户端创建组。</span><span class="sxs-lookup"><span data-stu-id="40f07-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="40f07-112">如前所述，使用 Teams 客户端管理 Microsoft 365 组的所有未来成员身份。</span><span class="sxs-lookup"><span data-stu-id="40f07-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="40f07-113">由于团队成员身份也在定义 Microsoft 365 组的成员身份，因此应让人员为此更改做好准备。</span><span class="sxs-lookup"><span data-stu-id="40f07-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="40f07-114">Teams 在个人预览版中 (Microsoft 365 组命名策略) </span><span class="sxs-lookup"><span data-stu-id="40f07-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="40f07-115">当用户创建或编辑团队名称时，管理员设置的任何 Microsoft 365 组命名策略都将在 Teams 中应用。</span><span class="sxs-lookup"><span data-stu-id="40f07-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="40f07-116">其中包括强制前缀或后缀等内容，以及排除禁用词语。</span><span class="sxs-lookup"><span data-stu-id="40f07-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="40f07-117">此功能为个人预览版，这意味着如果你不是此预览版的成员，Teams 尚不遵循此 Microsoft 365 组命名策略。</span><span class="sxs-lookup"><span data-stu-id="40f07-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="40f07-118">若要了解有关详细信息，请阅读 Teams 中的 [Microsoft 365 组命名策略](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="40f07-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="40f07-119">以下文章是查找 Microsoft 365 组的就绪状态和采用内容的好去处：</span><span class="sxs-lookup"><span data-stu-id="40f07-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="40f07-120">在 Outlook 中通过组获得更多</span><span class="sxs-lookup"><span data-stu-id="40f07-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="40f07-121">使用 Microsoft 365 管理中心在 Microsoft 365 组中添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="40f07-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="40f07-122">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="40f07-122">Restore a deleted group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)
