---
title: 不支持的浏览器上的 Microsoft Teams 会议
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解 Teams 如何在不支持的浏览器中支持音频和视频。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804522"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="dfef9-103">不支持的浏览器上的 Microsoft Teams 会议</span><span class="sxs-lookup"><span data-stu-id="dfef9-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="dfef9-104">某些浏览器（如 Internet Explorer 11、Safari 和 Firefox）支持 Microsoft Teams Web 应用，但不支持某些 Teams 呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="dfef9-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="dfef9-105">为了解决此限制，Teams Web 应用允许用户通过 PSTN 连接接收音频，并允许用户以降低的显示速率 (屏幕共享) 呈现的内容。</span><span class="sxs-lookup"><span data-stu-id="dfef9-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="dfef9-106">自 2021 年 8 月 17 日起，Microsoft 365 应用和服务将不支持 Internet Explorer 11 (从 2020 年 11 月 30 日至 2020 年 11 月 30 日Internet Explorer 11) 。</span><span class="sxs-lookup"><span data-stu-id="dfef9-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="dfef9-107">[了解详细信息](https://aka.ms/AA97tsw)。</span><span class="sxs-lookup"><span data-stu-id="dfef9-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="dfef9-108">请注意，Internet Explorer 11 将保留为受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="dfef9-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="dfef9-109">Internet Explorer 11 是 Windows 操作系统的一个组件，[](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge)它遵循安装它的产品的生命周期策略。</span><span class="sxs-lookup"><span data-stu-id="dfef9-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="dfef9-110">当 Teams 检测到不受支持的浏览器时，它会自动显示一条消息，说明问题以及会话限制。</span><span class="sxs-lookup"><span data-stu-id="dfef9-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="dfef9-111">该消息提供有关访问会议音频的更多说明，例如建议用户留下回叫号码以便 Teams 可以呼叫用户，或指示用户呼叫会议邀请中包含的会议号码。</span><span class="sxs-lookup"><span data-stu-id="dfef9-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="dfef9-112">该消息还鼓励用户下载并使用 [Teams 桌面客户端](https://teams.microsoft.com/downloads) 获得完整的 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="dfef9-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="dfef9-113">如果 PSTN 不可用，用户将看不到有关访问会议的说明，并且无法加入会议。</span><span class="sxs-lookup"><span data-stu-id="dfef9-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="dfef9-114">浏览器限制</span><span class="sxs-lookup"><span data-stu-id="dfef9-114">Browser limitations</span></span>

<span data-ttu-id="dfef9-115">在不支持的浏览器上使用 Teams Web 应用的人将遇到以下限制：</span><span class="sxs-lookup"><span data-stu-id="dfef9-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="dfef9-116">音频仅通过 PSTN 连接提供。</span><span class="sxs-lookup"><span data-stu-id="dfef9-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="dfef9-117">用户不能使用其麦克风。</span><span class="sxs-lookup"><span data-stu-id="dfef9-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="dfef9-118">用户无法共享其摄像头或查看其他参与者的视频，但可以通过基于图像的屏幕共享来查看展示的内容。</span><span class="sxs-lookup"><span data-stu-id="dfef9-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="dfef9-119">用户无法共享其屏幕，尽管他们可以看到另一个会议参与者共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="dfef9-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="dfef9-120">用户在屏幕共享会话期间无法控制。</span><span class="sxs-lookup"><span data-stu-id="dfef9-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="dfef9-121">用户不会收到传入呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="dfef9-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="dfef9-122">如果呼叫中断，会议不会自动重新连接。</span><span class="sxs-lookup"><span data-stu-id="dfef9-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="dfef9-123">用户无法启动会议。</span><span class="sxs-lookup"><span data-stu-id="dfef9-123">Users can't start meetings.</span></span>

<span data-ttu-id="dfef9-124">有关 Teams 中的浏览器支持详细信息，请参阅 Teams [的限制和规范](/microsoftteams/limits-specifications-teams#browsers)。</span><span class="sxs-lookup"><span data-stu-id="dfef9-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dfef9-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="dfef9-125">Related topics</span></span>

- [<span data-ttu-id="dfef9-126">在不支持的浏览器上加入 Teams 会议</span><span class="sxs-lookup"><span data-stu-id="dfef9-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
