---
title: 在 Microsoft Teams 中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598461"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="d98e7-103">在 ® 中使用 NDI Microsoft Teams 技术</span><span class="sxs-lookup"><span data-stu-id="d98e7-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="d98e7-104">NewTek NDI® (网络设备接口) 技术是一种现代解决方案，用于将媒体设备与 (例如工作室摄像头和混音器) 。</span><span class="sxs-lookup"><span data-stu-id="d98e7-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="d98e7-105">NDI-®技术无需使用物理连接，而是通过本地 Intranet（包括在本地计算机上）建立连接。</span><span class="sxs-lookup"><span data-stu-id="d98e7-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="d98e7-106">NDI® 技术已成为一种标准行业解决方案，用于为流生成实时内容，并获得了专业广播世界的重要认知和采用。</span><span class="sxs-lookup"><span data-stu-id="d98e7-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="d98e7-107">Skype 2018 年底® NDI Skype功能。</span><span class="sxs-lookup"><span data-stu-id="d98e7-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="d98e7-108">Microsoft Teams此功能来改善会议体验。</span><span class="sxs-lookup"><span data-stu-id="d98e7-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="d98e7-109">NDI®仅限本地网络，只应视为生产工作流的一部分，而不是广播解决方案。</span><span class="sxs-lookup"><span data-stu-id="d98e7-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="d98e7-110">启用 NDI®技术</span><span class="sxs-lookup"><span data-stu-id="d98e7-110">Turn on NDI® technology</span></span>

<span data-ttu-id="d98e7-111">NDI®技术要求为用户启用两个步骤。</span><span class="sxs-lookup"><span data-stu-id="d98e7-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="d98e7-112">租户管理员必须在 CsTeamsMeetingPolicy 中启用"AllowNDIStreaming"属性。</span><span class="sxs-lookup"><span data-stu-id="d98e7-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="d98e7-113">填充此更改后，最终用户必须从"权限"®**客户端启用** NDI设置  >  **技术**。</span><span class="sxs-lookup"><span data-stu-id="d98e7-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="d98e7-114">当用户加入会议时，他们将看到一条消息，通知他们正在直播会议。</span><span class="sxs-lookup"><span data-stu-id="d98e7-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="d98e7-115">如果用户不希望包含在直播中，则需要从会议删除。</span><span class="sxs-lookup"><span data-stu-id="d98e7-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="d98e7-116">下图显示了用户在会议或会议Teams消息。</span><span class="sxs-lookup"><span data-stu-id="d98e7-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![he NDI®技术横幅，显示在 Teams 会议。](media/NDI-disclosure.png)

<span data-ttu-id="d98e7-118">横幅包含指向 [Microsoft 隐私策略 的链接](https://aka.ms/teamsprivacy)。</span><span class="sxs-lookup"><span data-stu-id="d98e7-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="d98e7-119">NDI®每个会话激活。</span><span class="sxs-lookup"><span data-stu-id="d98e7-119">NDI® is activated per session only.</span></span> <span data-ttu-id="d98e7-120">下次登录时，用户必须先激活它，然后才能使用 NDI®。</span><span class="sxs-lookup"><span data-stu-id="d98e7-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="d98e7-121">支持区域设置和用户类型</span><span class="sxs-lookup"><span data-stu-id="d98e7-121">Supported locales and user types</span></span>

<span data-ttu-id="d98e7-122">所有®都支持 NDI-®技术。</span><span class="sxs-lookup"><span data-stu-id="d98e7-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="d98e7-123">NDI 技术流中包含®用户，但并非所有用户都可以访问 NDI®流：</span><span class="sxs-lookup"><span data-stu-id="d98e7-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="d98e7-124">租户内 - 完全支持，基于由会议策略组控制的 ring/tenantId/userId (提供) </span><span class="sxs-lookup"><span data-stu-id="d98e7-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="d98e7-125">联合 - 即使 (1 上具有 NDI®技术，也) <sup>流访问</sup></span><span class="sxs-lookup"><span data-stu-id="d98e7-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="d98e7-126">高级版 - 无流访问</span><span class="sxs-lookup"><span data-stu-id="d98e7-126">Premium - no stream access</span></span>
- <span data-ttu-id="d98e7-127">匿名 – 无流访问</span><span class="sxs-lookup"><span data-stu-id="d98e7-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="d98e7-128">来宾 – 无流访问</span><span class="sxs-lookup"><span data-stu-id="d98e7-128">Guest – no stream access</span></span>  

<span data-ttu-id="d98e7-129"><sup>1</sup> 设备具有默认® NDI 技术设置。</span><span class="sxs-lookup"><span data-stu-id="d98e7-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="d98e7-130">如果会议参与者使用的设备具有 NDI®技术，则需要启用 NDI®技术。</span><span class="sxs-lookup"><span data-stu-id="d98e7-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
