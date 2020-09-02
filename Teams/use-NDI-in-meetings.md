---
title: 在 Microsoft 团队中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft 团队中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323986"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="b7812-103">在 Microsoft 团队中使用 NDI®技术</span><span class="sxs-lookup"><span data-stu-id="b7812-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="b7812-104">NDI® (网络设备接口) 技术是用于连接媒体设备 (（如 studio 相机和混音器) ）的新式解决方案。</span><span class="sxs-lookup"><span data-stu-id="b7812-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="b7812-105">除了使用物理连接之外，NDI®技术可以通过本地 intranet （包括在本地计算机上）实现连接。</span><span class="sxs-lookup"><span data-stu-id="b7812-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="b7812-106">NewTek NDI®技术已成为为流制作实时内容的标准行业解决方案，并且在专业的广播世界中获得重要的意识和采纳。</span><span class="sxs-lookup"><span data-stu-id="b7812-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="b7812-107">Skype 以前在2018中向 Skype 添加了 NDI®功能。</span><span class="sxs-lookup"><span data-stu-id="b7812-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="b7812-108">Microsoft 团队利用此功能改善会议体验。</span><span class="sxs-lookup"><span data-stu-id="b7812-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="b7812-109">NDI®技术限制为本地网络，只能被视为生产工作流的一部分，而不是广播解决方案。</span><span class="sxs-lookup"><span data-stu-id="b7812-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="b7812-110">打开 NDI®技术</span><span class="sxs-lookup"><span data-stu-id="b7812-110">Turn on NDI® technology</span></span>

<span data-ttu-id="b7812-111">NDI®技术要求为用户打开两个步骤。</span><span class="sxs-lookup"><span data-stu-id="b7812-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="b7812-112">租户管理员必须在 CsTeamsMeetingPolicy 中启用 "AllowNDIStreaming" 属性。</span><span class="sxs-lookup"><span data-stu-id="b7812-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="b7812-113">填充此更改后，最终用户必须从 "**设置**" 权限为其特定客户端打开 NDI®技术  >  **Permissions**。</span><span class="sxs-lookup"><span data-stu-id="b7812-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="b7812-114">当用户加入会议时，他们将看到一条消息，通知他们正在广播会议。</span><span class="sxs-lookup"><span data-stu-id="b7812-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="b7812-115">如果用户不希望包含在广播中，则需要将其从会议中删除。</span><span class="sxs-lookup"><span data-stu-id="b7812-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="b7812-116">下图显示了用户在团队会议中看到的标题消息。</span><span class="sxs-lookup"><span data-stu-id="b7812-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![在团队会议中显示的 NDI®技术横幅的图像。](media/NDI-disclosure.png)

<span data-ttu-id="b7812-118">横幅有一个指向 [Microsoft 隐私声明策略](https://aka.ms/teamsprivacy)的链接。</span><span class="sxs-lookup"><span data-stu-id="b7812-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="b7812-119">支持的区域设置和用户类型</span><span class="sxs-lookup"><span data-stu-id="b7812-119">Supported locales and user types</span></span>

<span data-ttu-id="b7812-120">NDI®技术在所有区域设置中均受支持。</span><span class="sxs-lookup"><span data-stu-id="b7812-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="b7812-121">以下用户包括在 NDI®技术流中，但并非所有用户都可以访问 NDI®技术流：</span><span class="sxs-lookup"><span data-stu-id="b7812-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="b7812-122">租户内-完全支持，根据 "震铃/tenantId/userId" (提供，由会议策略控制) </span><span class="sxs-lookup"><span data-stu-id="b7812-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="b7812-123">联合-即使他们在) <sup>1</sup>上有 NDI®技术，也不能 (流访问</span><span class="sxs-lookup"><span data-stu-id="b7812-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="b7812-124">Freemium-无流访问</span><span class="sxs-lookup"><span data-stu-id="b7812-124">Freemium - no stream access</span></span>
- <span data-ttu-id="b7812-125">匿名–无流访问</span><span class="sxs-lookup"><span data-stu-id="b7812-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="b7812-126">来宾-无流访问</span><span class="sxs-lookup"><span data-stu-id="b7812-126">Guest – no stream access</span></span>  

<span data-ttu-id="b7812-127"><sup>1</sup> 台设备的 NDI®技术设置，默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="b7812-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="b7812-128">如果会议参与者使用的设备的 NDI®技术关闭，他们需要打开 NDI®技术。</span><span class="sxs-lookup"><span data-stu-id="b7812-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
