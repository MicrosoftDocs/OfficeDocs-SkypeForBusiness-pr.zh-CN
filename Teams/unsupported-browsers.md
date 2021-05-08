---
title: Microsoft Teams浏览器上打开会议
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
description: 了解如何Teams浏览器支持音频和视频。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121310"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="4f968-103">Microsoft Teams浏览器上打开会议</span><span class="sxs-lookup"><span data-stu-id="4f968-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="4f968-104">某些浏览器（如 Internet Explorer 11、Safari 和 Firefox）支持 Microsoft Teams Web 应用，但不支持某些Teams和会议功能。</span><span class="sxs-lookup"><span data-stu-id="4f968-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="4f968-105">若要解决此限制，Teams Web 应用允许用户通过 PSTN 连接接收音频，并允许用户以 (屏幕共享) 查看呈现的内容。</span><span class="sxs-lookup"><span data-stu-id="4f968-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="4f968-106">Microsoft 365应用和服务不支持 2021 年 8 月 17 Internet Explorer 11 日 (Microsoft Teams将不支持从 2020 年 11 月 3) 0 日到 2020 年 11 月 30 日之前Internet Explorer 11 日。</span><span class="sxs-lookup"><span data-stu-id="4f968-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="4f968-107">[了解详细信息](https://aka.ms/AA97tsw)。</span><span class="sxs-lookup"><span data-stu-id="4f968-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="4f968-108">请注意，Internet Explorer 11 将保留为受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="4f968-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="4f968-109">Internet Explorer 11 是 Windows 操作系统的一个组件，它遵循[](/lifecycle/faq/internet-explorer-microsoft-edge)安装它的产品的生命周期策略。</span><span class="sxs-lookup"><span data-stu-id="4f968-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="4f968-110">当Teams浏览器时，它会自动显示一条消息，说明此问题和会话限制。</span><span class="sxs-lookup"><span data-stu-id="4f968-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="4f968-111">该消息提供有关访问会议音频的更多说明，例如建议用户留下回电号码Teams以便 Teams 可以呼叫用户，或指示用户呼叫会议邀请中包含的会议号码。</span><span class="sxs-lookup"><span data-stu-id="4f968-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="4f968-112">该消息还鼓励用户下载并使用 Teams[桌面客户端](https://teams.microsoft.com/downloads)进行完整的Teams体验。</span><span class="sxs-lookup"><span data-stu-id="4f968-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="4f968-113">如果 PSTN 不可用，用户将看不到有关访问会议的说明，并且无法加入会议。</span><span class="sxs-lookup"><span data-stu-id="4f968-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="4f968-114">浏览器限制</span><span class="sxs-lookup"><span data-stu-id="4f968-114">Browser limitations</span></span>

<span data-ttu-id="4f968-115">在不受支持Teams Web 应用的人将遇到以下限制：</span><span class="sxs-lookup"><span data-stu-id="4f968-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="4f968-116">音频仅通过 PSTN 连接提供。</span><span class="sxs-lookup"><span data-stu-id="4f968-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="4f968-117">用户不能使用其麦克风。</span><span class="sxs-lookup"><span data-stu-id="4f968-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="4f968-118">用户无法共享其相机或查看其他参与者的视频，但可以通过基于图像的屏幕共享来查看呈现的内容。</span><span class="sxs-lookup"><span data-stu-id="4f968-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="4f968-119">用户无法共享其屏幕，尽管他们可以看到另一个会议参与者共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="4f968-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="4f968-120">在屏幕共享会话期间，用户无法控制。</span><span class="sxs-lookup"><span data-stu-id="4f968-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="4f968-121">用户不会收到传入呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="4f968-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="4f968-122">如果呼叫中断，会议不会自动重新连接。</span><span class="sxs-lookup"><span data-stu-id="4f968-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="4f968-123">用户无法启动会议。</span><span class="sxs-lookup"><span data-stu-id="4f968-123">Users can't start meetings.</span></span>

<span data-ttu-id="4f968-124">有关浏览器中对浏览器的支持Teams，请参阅适用于 Teams 的限制[和Teams。](./limits-specifications-teams.md#browsers)</span><span class="sxs-lookup"><span data-stu-id="4f968-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f968-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="4f968-125">Related topics</span></span>

- [<span data-ttu-id="4f968-126">在Teams浏览器加入会议</span><span class="sxs-lookup"><span data-stu-id="4f968-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)