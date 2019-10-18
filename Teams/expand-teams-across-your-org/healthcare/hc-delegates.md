---
title: 消息委派
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 用户可以在其状态消息中将另一用户显式设置为代理人。
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570354"
---
# <a name="message-delegation"></a><span data-ttu-id="409f1-103">消息委派</span><span class="sxs-lookup"><span data-stu-id="409f1-103">Message delegation</span></span>

<span data-ttu-id="409f1-104">用户可以已将其状态显式设置为 "离开" 或 "请勿打扰"，并提供自定义文本。</span><span class="sxs-lookup"><span data-stu-id="409f1-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="409f1-105">邮件委派功能的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="409f1-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="409f1-106">用户 @username 在文本状态消息中提及另一个用户，这表示当他们是不可用的用户而想要与他们联系时，请联系 @username 提及的用户。</span><span class="sxs-lookup"><span data-stu-id="409f1-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="409f1-107">被分配为代理人的人员将收到通知，告知他们已被命名为代理人。</span><span class="sxs-lookup"><span data-stu-id="409f1-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="409f1-108">尝试与第一位用户联系的用户可以将其悬停在命名委派上，并且可以轻松地向代理发送消息。</span><span class="sxs-lookup"><span data-stu-id="409f1-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="409f1-109">这是客户端中的用户启动的进程，并且不需要管理员参与来启用该功能。</span><span class="sxs-lookup"><span data-stu-id="409f1-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="409f1-110">医疗保健中的委派使用方案</span><span class="sxs-lookup"><span data-stu-id="409f1-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="409f1-111">*没有设置代理人的用法示例：* Franco Piccio 在放射科的部门通话。</span><span class="sxs-lookup"><span data-stu-id="409f1-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="409f1-112">他收到了一次紧急个人通话，并且在接下来的几个小时内必须退出。</span><span class="sxs-lookup"><span data-stu-id="409f1-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="409f1-113">他在放射科的 Lena Ehrle 中询问了他的某位同事，以便在他离开时覆盖他。</span><span class="sxs-lookup"><span data-stu-id="409f1-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="409f1-114">他在 Ehrle 上，他一直在上监听紧急消息和 ping 并在 Piccio 上代表，并在她的当前责任的同时作出响应。</span><span class="sxs-lookup"><span data-stu-id="409f1-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="409f1-115">团队中的其他人可能无法实现非正式委派，并且 ensues 患者的护理造成混淆。</span><span class="sxs-lookup"><span data-stu-id="409f1-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="409f1-116">*设置代理人的用法示例：* Franco Piccio 在放射科的部门通话。</span><span class="sxs-lookup"><span data-stu-id="409f1-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="409f1-117">他收到了一次紧急个人通话，并且在接下来的几个小时内必须退出。</span><span class="sxs-lookup"><span data-stu-id="409f1-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="409f1-118">他在放射 Lena Ehrle 时，他将向他提出他的一位同事。</span><span class="sxs-lookup"><span data-stu-id="409f1-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="409f1-119">他将更改其自定义状态消息，以表达类似于 "我在今后几小时内不可用的内容。</span><span class="sxs-lookup"><span data-stu-id="409f1-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="409f1-120">请联系 @DrEhrle，获取任何紧急情况。 "</span><span class="sxs-lookup"><span data-stu-id="409f1-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="409f1-121">团队中的其他人在尝试联系 Piccio 时遇到委派问题，因此他们现在知道立即联系 Dr. Ehrle。</span><span class="sxs-lookup"><span data-stu-id="409f1-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="409f1-122">Ensues 患者的护理很少，不会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="409f1-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="409f1-123">团队客户端中的用户状态的共存模式的影响</span><span class="sxs-lookup"><span data-stu-id="409f1-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="409f1-124">管理员应注意，状态说明和委派提及的行为将部分地依赖于用户的共存模式。</span><span class="sxs-lookup"><span data-stu-id="409f1-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="409f1-125">此矩阵显示了可能性：</span><span class="sxs-lookup"><span data-stu-id="409f1-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="409f1-126">共存模式</span><span class="sxs-lookup"><span data-stu-id="409f1-126">Co-Existence Mode</span></span> | <span data-ttu-id="409f1-127">预期行为</span><span class="sxs-lookup"><span data-stu-id="409f1-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="409f1-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="409f1-128">TeamsOnly</span></span> |<span data-ttu-id="409f1-129">用户只能从团队设置笔记。</span><span class="sxs-lookup"><span data-stu-id="409f1-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="409f1-130">用户的团队备注在团队 & SfB 中可见。</span><span class="sxs-lookup"><span data-stu-id="409f1-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="409f1-131">群岛</span><span class="sxs-lookup"><span data-stu-id="409f1-131">Islands</span></span> | <span data-ttu-id="409f1-132">仅在团队中可见的团队中的用户备注集。</span><span class="sxs-lookup"><span data-stu-id="409f1-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="409f1-133">SfB 中的用户备注集仅在 SfB 中可见</span><span class="sxs-lookup"><span data-stu-id="409f1-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="409f1-134">SfB \* 模式</span><span class="sxs-lookup"><span data-stu-id="409f1-134">SfB\* modes</span></span> | <span data-ttu-id="409f1-135">用户只能从 SfB 设置笔记。</span><span class="sxs-lookup"><span data-stu-id="409f1-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="409f1-136">用户的 SfB 备注在 SfB & 团队中可见。</span><span class="sxs-lookup"><span data-stu-id="409f1-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="409f1-137">如果用户的模式为 TeamsOnly 或孤岛，则用户仅可在团队中设置注释。</span><span class="sxs-lookup"><span data-stu-id="409f1-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="409f1-138">在 Skype for Business 中显示备注集</span><span class="sxs-lookup"><span data-stu-id="409f1-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="409f1-139">不显示从 Skype for Business 设置笔记的视觉指示。</span><span class="sxs-lookup"><span data-stu-id="409f1-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="409f1-140">Skype for Business 不会对状态注释强制执行字符限制。</span><span class="sxs-lookup"><span data-stu-id="409f1-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="409f1-141">Microsoft 团队将仅显示 Skype for Business 中的笔记集的前280个字符。</span><span class="sxs-lookup"><span data-stu-id="409f1-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="409f1-142">注释末尾的省略号（...）表示截断。</span><span class="sxs-lookup"><span data-stu-id="409f1-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="409f1-143">Skype for Business 不支持对笔记的到期时间。</span><span class="sxs-lookup"><span data-stu-id="409f1-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="409f1-144">当用户升级到 TeamsOnly 模式时，不支持从 Skype for Business 迁移到团队的笔记。</span><span class="sxs-lookup"><span data-stu-id="409f1-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="409f1-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="409f1-145">Related topics</span></span>

[<span data-ttu-id="409f1-146">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="409f1-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
