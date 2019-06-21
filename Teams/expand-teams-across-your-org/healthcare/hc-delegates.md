---
title: 邮件委派
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 用户可以在其状态消息中将另一用户显式设置为代理人。
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119481"
---
# <a name="set-a-delegate-in-a-status-message"></a><span data-ttu-id="a844e-103">在状态邮件中设置代理人</span><span class="sxs-lookup"><span data-stu-id="a844e-103">Set a delegate in a status message</span></span>

<span data-ttu-id="a844e-104">用户可以已将其状态显式设置为 "离开" 或 "请勿打扰", 并提供自定义文本。</span><span class="sxs-lookup"><span data-stu-id="a844e-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="a844e-105">委派功能允许他们在文本状态消息中 @username 提及另一个用户, 并建议在文本状态消息中提及另一用户, 而不是希望与他们联系的人与 @username 的用户联系。</span><span class="sxs-lookup"><span data-stu-id="a844e-105">The delegation feature allows them to @username mention another user in part of a text status message, and suggest that while they are unavailable people who want to contact them contact the @username mentioned user instead.</span></span> <span data-ttu-id="a844e-106">尝试联系它们的人可以将其悬停在命名委派上, 并轻松地将其发送给他们。</span><span class="sxs-lookup"><span data-stu-id="a844e-106">Someone trying to contact them can then hover over the nominated delegate and easily message them instead.</span></span>  <span data-ttu-id="a844e-107">被分配为代理人的人员将收到通知, 告知他们已被命名为代理人。</span><span class="sxs-lookup"><span data-stu-id="a844e-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>

<span data-ttu-id="a844e-108">这是客户端中的用户启动的进程, 不需要管理员参与。</span><span class="sxs-lookup"><span data-stu-id="a844e-108">This is a user-initiated process in the client, and no Admin involvement is required.</span></span>

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="a844e-109">医疗保健中的委派使用方案</span><span class="sxs-lookup"><span data-stu-id="a844e-109">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="a844e-110">*没有设置代理人的用法示例:* Franco Piccio 在放射科的部门通话。</span><span class="sxs-lookup"><span data-stu-id="a844e-110">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="a844e-111">他收到了一次紧急个人通话, 并且在接下来的几个小时内必须退出。</span><span class="sxs-lookup"><span data-stu-id="a844e-111">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="a844e-112">他在放射科的 Lena Ehrle 中询问了他的某位同事, 以便在他离开时覆盖他。</span><span class="sxs-lookup"><span data-stu-id="a844e-112">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="a844e-113">他在 Ehrle 上, 他一直在上监听紧急消息和 ping 并在 Piccio 上代表, 并在她的当前责任的同时作出响应。</span><span class="sxs-lookup"><span data-stu-id="a844e-113">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="a844e-114">团队中的其他人可能无法实现非正式委派, 并且 ensues 患者的护理造成混淆。</span><span class="sxs-lookup"><span data-stu-id="a844e-114">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="a844e-115">*设置代理人的用法示例:* Franco Piccio 在放射科的部门通话。</span><span class="sxs-lookup"><span data-stu-id="a844e-115">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="a844e-116">他收到了一次紧急个人通话, 并且在接下来的几个小时内必须退出。</span><span class="sxs-lookup"><span data-stu-id="a844e-116">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="a844e-117">他在放射 Lena Ehrle 时, 他将向他提出他的一位同事。</span><span class="sxs-lookup"><span data-stu-id="a844e-117">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="a844e-118">他将更改其自定义状态消息, 以表达类似于 "我在今后几小时内不可用的内容。</span><span class="sxs-lookup"><span data-stu-id="a844e-118">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="a844e-119">请联系 @DrEhrle, 获取任何紧急情况。 "</span><span class="sxs-lookup"><span data-stu-id="a844e-119">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="a844e-120">团队中的其他人在尝试联系 Piccio 时遇到委派问题, 因此他们现在知道立即联系 Dr. Ehrle。</span><span class="sxs-lookup"><span data-stu-id="a844e-120">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="a844e-121">Ensues 患者的护理很少, 不会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="a844e-121">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="a844e-122">团队客户端中的用户状态的共存模式的影响</span><span class="sxs-lookup"><span data-stu-id="a844e-122">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="a844e-123">管理员应注意, 状态说明和委托提及将部分地依赖于用户的共存模式。</span><span class="sxs-lookup"><span data-stu-id="a844e-123">Admins should be aware that status notes and delegation mentions will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="a844e-124">此矩阵显示了可能性:</span><span class="sxs-lookup"><span data-stu-id="a844e-124">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="a844e-125">共存模式</span><span class="sxs-lookup"><span data-stu-id="a844e-125">Co-Existence Mode</span></span> | <span data-ttu-id="a844e-126">预期行为</span><span class="sxs-lookup"><span data-stu-id="a844e-126">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="a844e-127">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="a844e-127">TeamsOnly</span></span> |<span data-ttu-id="a844e-128">用户只能从团队设置笔记。</span><span class="sxs-lookup"><span data-stu-id="a844e-128">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="a844e-129">用户的团队备注在团队 & SfB 中可见。</span><span class="sxs-lookup"><span data-stu-id="a844e-129">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="a844e-130">群岛</span><span class="sxs-lookup"><span data-stu-id="a844e-130">Islands</span></span> | <span data-ttu-id="a844e-131">仅在团队中可见的团队中的用户备注集。</span><span class="sxs-lookup"><span data-stu-id="a844e-131">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="a844e-132">SfB 中的用户备注集仅在 SfB 中可见</span><span class="sxs-lookup"><span data-stu-id="a844e-132">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="a844e-133">SfB \* 模式</span><span class="sxs-lookup"><span data-stu-id="a844e-133">SfB\* modes</span></span> | <span data-ttu-id="a844e-134">用户只能从 SfB 设置笔记。</span><span class="sxs-lookup"><span data-stu-id="a844e-134">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="a844e-135">用户的 SfB 备注在 SfB & 团队中可见。</span><span class="sxs-lookup"><span data-stu-id="a844e-135">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="a844e-136">如果用户的模式为 TeamsOnly 或孤岛, 则用户仅可在团队中设置注释。</span><span class="sxs-lookup"><span data-stu-id="a844e-136">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="a844e-137">在 Skype for Business 中显示备注集</span><span class="sxs-lookup"><span data-stu-id="a844e-137">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="a844e-138">不显示从 Skype for Business 设置笔记的视觉指示。</span><span class="sxs-lookup"><span data-stu-id="a844e-138">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="a844e-139">Skype for Business 不会对状态注释强制执行字符限制。</span><span class="sxs-lookup"><span data-stu-id="a844e-139">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="a844e-140">Microsoft 团队将仅显示 Skype for Business 中的笔记集的前280个字符。</span><span class="sxs-lookup"><span data-stu-id="a844e-140">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="a844e-141">末尾的省略号 (...) 指示截断。</span><span class="sxs-lookup"><span data-stu-id="a844e-141">An ellipse (…) at the end indicates truncation.</span></span>
  
<span data-ttu-id="a844e-142">Skype for Business 不支持对笔记的到期时间。</span><span class="sxs-lookup"><span data-stu-id="a844e-142">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="a844e-143">当用户升级到 TeamsOnly 模式时, 不支持从 Skype for Business 迁移到团队的笔记。</span><span class="sxs-lookup"><span data-stu-id="a844e-143">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="configure-allowing-clients-to-use-delegates"></a><span data-ttu-id="a844e-144">配置允许客户使用代理人</span><span class="sxs-lookup"><span data-stu-id="a844e-144">Configure allowing clients to use delegates</span></span>

<span data-ttu-id="a844e-145">此功能不需要 Microsoft 团队管理中心的配置或使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a844e-145">This feature does not require configuration in Microsoft Teams admin center, or using PowerShell.</span></span> <span data-ttu-id="a844e-146">在支持它的租户中, 默认情况下, 它在团队客户端中可用。</span><span class="sxs-lookup"><span data-stu-id="a844e-146">In tenants that support it, it is available by default in the Teams client.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a844e-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="a844e-147">Related topics</span></span>

[<span data-ttu-id="a844e-148">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="a844e-148">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
