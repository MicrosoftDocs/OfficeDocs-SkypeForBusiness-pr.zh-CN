---
title: Microsoft Teams 中外部用户 (联合) 的本机聊天体验
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft Teams 中两个用户都 (Teams) 用户进行外部访问的本机 Teams 聊天体验。
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055654"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="aa4b5-103">Microsoft Teams 中外部用户 (联合) 的本机聊天体验</span><span class="sxs-lookup"><span data-stu-id="aa4b5-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="aa4b5-104">当 Microsoft Teams 用户与联合 (外部用户) 时，聊天体验仅限于文本。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="aa4b5-105">但是，如果你的 Teams 用户和另一个组织中人员都采用 TeamsOnly 升级模式，则你可以拥有"本机 Teams 聊天体验"，其中包括丰富的格式、@mentions和其他聊天功能。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="aa4b5-106">换言之，可以与其他组织中符合条件的人员具有相同的 1：1 Teams 聊天体验，就像与组织中用户一样。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="aa4b5-107">与其他组织中的人员进行本机 Teams 聊天仅限于 1：1 聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="aa4b5-108">为其他组织中的人员启用针对所有 Teams 租户的本机聊天体验，但并非所有人员都符合条件。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="aa4b5-109">若要提供本机聊天体验，需为发送方和接收者配置 TeamsOnly 升级模式。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="aa4b5-110">若要了解有关升级策略的信息，请阅读["设置共存和升级设置"。](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aa4b5-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="aa4b5-111">若要在 Teams 中查看外部访问用户的功能列表，请参阅["比较外部访问和来宾访问"。](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="aa4b5-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="aa4b5-112">如何知道我是否参与本机聊天？</span><span class="sxs-lookup"><span data-stu-id="aa4b5-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="aa4b5-113">如果只能在与其他组织人员聊天中交换文本，则使用标准外部访问 (联合) 聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="aa4b5-114">如果你已获得了所有其他聊天功能（包括格式、@mentions、表情符号等），则你正在本机 Teams 聊天中。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="aa4b5-115">Teams 会定期检查其他组织中的人员升级模式，当发现他们在 TeamsOnly 升级模式下运行 Teams 时，它会提示你切换到本机 Teams 聊天并锁定原始聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="aa4b5-116">切换到本机 Teams 聊天时，Teams 不会合并这两个对话。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="aa4b5-117">相反，你将在聊天源中看到这两个聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="aa4b5-118">新的本机 Teams 聊天处于活动状态，但旧式纯文本聊天已锁定。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="aa4b5-119">如果用户不再使用"仅 Teams"模式，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="aa4b5-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="aa4b5-120">如果你与其他组织中的人员进行了本机 Teams 聊天，然后其中一人退出 TeamsOnly 升级模式，则 Teams 会锁定本机 Teams 聊天，并为你提供仅限文本的有限聊天的链接。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="aa4b5-121">你将无法继续本机 Teams 聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="aa4b5-122">你仍然可以阅读本机 Teams 聊天，但无法继续在那里的对话。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="aa4b5-123">如果 Teams 找到了与此人的旧纯文本聊天，它将恢复该聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="aa4b5-124">否则，Teams 会创建新的纯文本聊天。</span><span class="sxs-lookup"><span data-stu-id="aa4b5-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa4b5-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="aa4b5-125">Related topics</span></span>

[<span data-ttu-id="aa4b5-126">在 Teams 中管理外部访问</span><span class="sxs-lookup"><span data-stu-id="aa4b5-126">Manage external access in Teams</span></span>](manage-external-access.md)
