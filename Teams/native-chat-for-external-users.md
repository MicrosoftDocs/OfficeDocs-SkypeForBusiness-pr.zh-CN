---
title: Microsoft 团队外部（联合）用户的本机聊天体验
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解 Microsoft 团队中的外部访问（联合）用户的本机团队聊天体验，在两个用户均处于 TeamsOnly 升级模式的外部用户之间可用。
ms.openlocfilehash: 572087d86672294b566cd99365599dbead1aa3e7
ms.sourcegitcommit: 1448bb2e66074322b8f4bf234fce36ea9c8f9913
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39966755"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="44f9b-103">Microsoft 团队外部（联合）用户的本机聊天体验</span><span class="sxs-lookup"><span data-stu-id="44f9b-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="44f9b-104">当 Microsoft 团队用户与外部（联合）用户聊天时，聊天体验仅限于文本。</span><span class="sxs-lookup"><span data-stu-id="44f9b-104">When a Microsoft Teams users is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="44f9b-105">但是，如果你的团队租户和外部用户的 TeamsOnly 升级模式，你可以拥有 "本机团队聊天体验"，其中包括丰富的格式、@mentions 和其他聊天功能。</span><span class="sxs-lookup"><span data-stu-id="44f9b-105">However, if both your Teams tenant and that of the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="44f9b-106">换句话说，你可以与符合条件的外部用户进行相同的丰富的1:1 团队聊天体验，就像在你的组织中的用户一样。</span><span class="sxs-lookup"><span data-stu-id="44f9b-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="44f9b-107">与外部用户的本机团队聊天仅限于1:1 聊天（外部用户无法进行群组聊天）。</span><span class="sxs-lookup"><span data-stu-id="44f9b-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="44f9b-108">适用于外部用户的本机聊天体验已针对所有团队租户启用，但并非所有用户都符合资格。</span><span class="sxs-lookup"><span data-stu-id="44f9b-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="44f9b-109">若要提供本机聊天体验，发送方和接收方都必须位于运行 TeamsOnly 升级模式的团队租户上。</span><span class="sxs-lookup"><span data-stu-id="44f9b-109">To be offered a native chat experience, both the sender and receiver need to be on a Teams tenant that's running the TeamsOnly upgrade mode.</span></span> <span data-ttu-id="44f9b-110">若要了解有关升级策略的详细信息，请阅读[设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="44f9b-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="44f9b-111">若要查看团队外部 access 用户的功能列表，请参阅[比较外部和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="44f9b-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="44f9b-112">如何知道我是否正在进行本机聊天？</span><span class="sxs-lookup"><span data-stu-id="44f9b-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="44f9b-113">如果您只能与外部用户交换您的聊天中的文本，则您使用的是标准的外部访问（联合）聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="44f9b-114">如果您已获得所有其他聊天功能，包括格式、@mentions、表情符号等，则您正在使用您的外部用户进行本地团队聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="44f9b-115">团队会定期检查外部用户的升级模式，当它在 TeamsOnly 升级模式中找到运行团队的外部用户时，它将提示你切换到本机团队聊天并锁定原始聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="44f9b-116">切换到本机团队聊天时，团队不会合并这两个对话。</span><span class="sxs-lookup"><span data-stu-id="44f9b-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="44f9b-117">你可以在聊天源中看到这两个聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="44f9b-118">新的本机团队聊天处于活动状态，但旧的、纯文本的聊天已被锁定。</span><span class="sxs-lookup"><span data-stu-id="44f9b-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="44f9b-119">如果用户不再属于 "仅工作组" 模式，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="44f9b-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="44f9b-120">如果您有一个本机团队与外部用户聊天，然后您将其中一个 TeamsOnly 升级模式切换出，则团队会锁定本机团队聊天，并为您提供仅限文本的有限聊天的链接。</span><span class="sxs-lookup"><span data-stu-id="44f9b-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="44f9b-121">你将无法继续参与本机团队聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="44f9b-122">您仍然可以阅读本机团队聊天，但不能继续对话。</span><span class="sxs-lookup"><span data-stu-id="44f9b-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="44f9b-123">如果团队发现此外部用户的旧的纯文本聊天，它将恢复该聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="44f9b-124">否则，团队会创建新的纯文本聊天。</span><span class="sxs-lookup"><span data-stu-id="44f9b-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="44f9b-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="44f9b-125">Related topics</span></span>

[<span data-ttu-id="44f9b-126">管理团队中的外部访问</span><span class="sxs-lookup"><span data-stu-id="44f9b-126">Manage external access in Teams</span></span>](manage-external-access.md)
