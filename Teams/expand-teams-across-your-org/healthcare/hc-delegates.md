---
title: 消息委派
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 了解状态为“离开”或“请勿打扰”的用户如何在其状态消息中明确将其他用户设置为代理人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790464"
---
# <a name="message-delegation"></a><span data-ttu-id="c4a34-103">消息委派</span><span class="sxs-lookup"><span data-stu-id="c4a34-103">Message delegation</span></span>

<span data-ttu-id="c4a34-104">用户可将其状态明确设置为“离开”或“请勿打扰”，并提供自定义文本。</span><span class="sxs-lookup"><span data-stu-id="c4a34-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="c4a34-105">消息委派功能的工作原理如下：</span><span class="sxs-lookup"><span data-stu-id="c4a34-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="c4a34-106">用户 @username 在文本状态消息中提及另一个用户，表明当自己没空时，想要联系他们的人可联系 @username 提及的用户。</span><span class="sxs-lookup"><span data-stu-id="c4a34-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="c4a34-107">被指派为代理人的用户将收到通知，知晓自己被指定为代理人。</span><span class="sxs-lookup"><span data-stu-id="c4a34-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="c4a34-108">随后，试图联系第一个用户的某人将鼠标悬停在指定的代理人上，即可轻松地向代理人发送消息。</span><span class="sxs-lookup"><span data-stu-id="c4a34-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="c4a34-109">这是用户在客户端中启动的过程，无需管理员参与即可启用该功能。</span><span class="sxs-lookup"><span data-stu-id="c4a34-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="c4a34-110">医疗保健方面的委派使用方案</span><span class="sxs-lookup"><span data-stu-id="c4a34-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="c4a34-111">*未设置代理人的使用示例：* Franco Piccio 医生正在放射科值班。</span><span class="sxs-lookup"><span data-stu-id="c4a34-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c4a34-112">他接到一个紧急私人电话，不得不在接下来的几个小时离开。</span><span class="sxs-lookup"><span data-stu-id="c4a34-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c4a34-113">他请放射科的一位同事 Lena Ehrle 医生在他离开后顶替他值班。</span><span class="sxs-lookup"><span data-stu-id="c4a34-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="c4a34-114">他非正式地将其寻呼机移交给 Ehrle 医生，Ehrle 医生除了本职工作之外，还要负责接听寻呼机上的紧急消息和传呼，并代表 Piccio 医生回复它们。</span><span class="sxs-lookup"><span data-stu-id="c4a34-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="c4a34-115">团队的其他成员可能并未意识到发生了非正式委派，并且患者医治混乱随之而来。</span><span class="sxs-lookup"><span data-stu-id="c4a34-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="c4a34-116">*设置代理人的使用示例：* Franco Piccio 医生正在放射科值班。</span><span class="sxs-lookup"><span data-stu-id="c4a34-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c4a34-117">他接到一个紧急私人电话，不得不在接下来的几个小时离开。</span><span class="sxs-lookup"><span data-stu-id="c4a34-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c4a34-118">他请放射科的一位同事 Lena Ehrle 医生在他离开后顶替他值班。</span><span class="sxs-lookup"><span data-stu-id="c4a34-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="c4a34-119">他更改了自己的自定义状态消息，文字类似于“我接下来的几个小时没空。</span><span class="sxs-lookup"><span data-stu-id="c4a34-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="c4a34-120">如有任何紧急情况，请联系 @DrEhrle。”</span><span class="sxs-lookup"><span data-stu-id="c4a34-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="c4a34-121">团队的其他成员在尝试联系 Piccio 医生时会意识到发生了委派，因此他们现在知道在此期间应联系 Ehrle 医生。</span><span class="sxs-lookup"><span data-stu-id="c4a34-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="c4a34-122">患者医治方面很少甚至不会发生混乱。</span><span class="sxs-lookup"><span data-stu-id="c4a34-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="c4a34-123">共存模式对 Teams 客户端中的用户状态的影响</span><span class="sxs-lookup"><span data-stu-id="c4a34-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="c4a34-124">管理员应注意，状态备注和委派提及行为取决于用户的共存模式。</span><span class="sxs-lookup"><span data-stu-id="c4a34-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="c4a34-125">此列表显示了可能性：</span><span class="sxs-lookup"><span data-stu-id="c4a34-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="c4a34-126">共存模式</span><span class="sxs-lookup"><span data-stu-id="c4a34-126">Co-Existence Mode</span></span> | <span data-ttu-id="c4a34-127">预期行为</span><span class="sxs-lookup"><span data-stu-id="c4a34-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="c4a34-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="c4a34-128">TeamsOnly</span></span> |<span data-ttu-id="c4a34-129">用户只能从 Teams 设置备注。</span><span class="sxs-lookup"><span data-stu-id="c4a34-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="c4a34-130">用户的 Teams 备注在Teams 和 SfB 中可见。</span><span class="sxs-lookup"><span data-stu-id="c4a34-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="c4a34-131">Islands</span><span class="sxs-lookup"><span data-stu-id="c4a34-131">Islands</span></span> | <span data-ttu-id="c4a34-132">在 Teams 中设置的用户备注仅在 Teams 中可见。</span><span class="sxs-lookup"><span data-stu-id="c4a34-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="c4a34-133">在 SfB 中设置的用户备注仅在 SfB 中可见</span><span class="sxs-lookup"><span data-stu-id="c4a34-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="c4a34-134">SfB\* 模式</span><span class="sxs-lookup"><span data-stu-id="c4a34-134">SfB\* modes</span></span> | <span data-ttu-id="c4a34-135">用户只能从 SfB 设置备注。</span><span class="sxs-lookup"><span data-stu-id="c4a34-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="c4a34-136">用户的 SfB 备注在 SfB 和 Teams 中可见。</span><span class="sxs-lookup"><span data-stu-id="c4a34-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="c4a34-137">只有当用户的模式是 TeamsOnly 或 Islands 时，才能在 Teams 中设置备注。</span><span class="sxs-lookup"><span data-stu-id="c4a34-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="c4a34-138">显示 Skype for Business 中设置的备注</span><span class="sxs-lookup"><span data-stu-id="c4a34-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="c4a34-139">没有直观的迹象表明备注是从 Skype for Business 设置的。</span><span class="sxs-lookup"><span data-stu-id="c4a34-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="c4a34-140">Skype for Business 对于状态备注不强制实施字符限制。</span><span class="sxs-lookup"><span data-stu-id="c4a34-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="c4a34-141">Microsoft Teams 将仅显示从 Skype for Business 设置的备注的前 280 个字符。</span><span class="sxs-lookup"><span data-stu-id="c4a34-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="c4a34-142">备注末尾的省略号 (…) 表示截断。</span><span class="sxs-lookup"><span data-stu-id="c4a34-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="c4a34-143">Skype for Business 不支持备注的过期时间。</span><span class="sxs-lookup"><span data-stu-id="c4a34-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="c4a34-144">当用户升级到 TeamsOnly 模式时，不支持将备注从 Skype for Business 迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="c4a34-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4a34-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="c4a34-145">Related topics</span></span>

[<span data-ttu-id="c4a34-146">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="c4a34-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
