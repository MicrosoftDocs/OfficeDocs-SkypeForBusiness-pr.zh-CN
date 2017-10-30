---
title: "Skype for Business 与 Microsoft Teams 如何交互 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "了解 Skype for Business 与 Microsoft Teams 如何交互，包括从聊天到通话。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="536f4-103">Skype for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="536f4-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="536f4-104">如果贵组织现在使用 Skype for Business，务必要了解 Skype for Business 与 Microsoft Teams 如何交互。</span><span class="sxs-lookup"><span data-stu-id="536f4-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="536f4-105">正式发布 Microsoft Teams 时，Microsoft Teams 与 Skype for Business Online 或 Hybrid 之间的基本互操作性仅适用于点对点 (P2P) 即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="536f4-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="536f4-106">默认行为是 Microsoft Teams 客户端同时登录 Microsoft Teams 后端服务和 Skype for Business 服务（双堆栈方法）。</span><span class="sxs-lookup"><span data-stu-id="536f4-106">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach).</span></span> <span data-ttu-id="536f4-107">Microsoft Teams 客户端面向 Skype for Business 仅呈现即时消息功能，因此，从 Skype for Business 查找某个 Microsoft Teams 用户时会仅将用户指示为“仅限即时消息”- 如以下示例中所示，Alix Wilber 仅登录到 Microsoft Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="536f4-107">The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="536f4-108">用户可以从 Microsoft Teams 搜索其组织中当前只能使用 Skype for Business 的其他用户，并可以进行即时消息聊天会话。</span><span class="sxs-lookup"><span data-stu-id="536f4-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="536f4-109">使用 Skype for Business 的用户可以回复即时消息，这些消息将显示在 Microsoft Teams 的聊天窗口中。</span><span class="sxs-lookup"><span data-stu-id="536f4-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="536f4-110">如果使用 Microsoft Teams 的用户也能够使用 Skype for Business，他们可以使用相应的客户端同时登录到 Microsoft Teams 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="536f4-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="536f4-111">系统优先使用最新的活动终结点，因此，如果用户当前正在使用 Microsoft Teams，则从 Skype for Business 用户发来的任何任何即时消息将显示在 Microsoft Teams 聊天窗口中。</span><span class="sxs-lookup"><span data-stu-id="536f4-111">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window.</span></span> <span data-ttu-id="536f4-112">如果用户当前正在使用 Skype for Business 接听/拨打电话或刚刚使用 Skype for Business 完成通话，且尚未回到 Microsoft Teams 客户端，则从 Skype for Business 用户发来的传入即时消息将显示在 Skype for Business 客户端中，因为这是最新的活动终结点。</span><span class="sxs-lookup"><span data-stu-id="536f4-112">If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="536f4-113">由于 Microsoft Teams 当前仅支持与 Skype for Business 之间的点对点 (P2P) 即时消息传递互操作性，因此，来自其他 Skype for Business 用户的任何形式的任何音频/视频通话或加入 Skype for Business 会议的邀请都将仅到达 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="536f4-113">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only.</span></span> <span data-ttu-id="536f4-114">而另一方面，来自 Microsoft Teams 客户端的任何形式的任何音频/视频呼叫或加入群组通话的邀请都将仅到达 Microsoft Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="536f4-114">In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="536f4-115">基于上述行为，最终用户可以轻松地同时使用 Microsoft Teams 和 Skype for Business，使用合适的工具满足特定的通信需求。</span><span class="sxs-lookup"><span data-stu-id="536f4-115">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool.</span></span> <span data-ttu-id="536f4-116">但是，最终用户需要正确了解互操作性的工作方式以及它对最终用户体验可能产生的影响。</span><span class="sxs-lookup"><span data-stu-id="536f4-116">However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="536f4-117">注意</span><span class="sxs-lookup"><span data-stu-id="536f4-117">Note:</span></span></br>      |<span data-ttu-id="536f4-118">使用 Skype for Business 互操作性功能时，到达 Teams 的即时消息不会记录在 Skype for Business 对话历史记录中。</span><span class="sxs-lookup"><span data-stu-id="536f4-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="536f4-119">Microsoft Teams 允许用户在“通知”设置中禁用 Skype for Business 互操作性。</span><span class="sxs-lookup"><span data-stu-id="536f4-119">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings.</span></span> <span data-ttu-id="536f4-120">此设置是用户控制的，从而允许每个用户根据其喜欢的行为进行设置。</span><span class="sxs-lookup"><span data-stu-id="536f4-120">This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
