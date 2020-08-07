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
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588286"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="302eb-103">在 Microsoft 团队中使用 NDI</span><span class="sxs-lookup"><span data-stu-id="302eb-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="302eb-104">网络设备接口 (NDI) 是一种用于连接媒体设备的现代解决方案， (如 studio 相机和混音器) 。</span><span class="sxs-lookup"><span data-stu-id="302eb-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="302eb-105">NDI 通过本地 intranet （包括在本地计算机上）启用连接，而不是使用物理连接。</span><span class="sxs-lookup"><span data-stu-id="302eb-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="302eb-106">NewTek NDI®已成为为流制作实时内容的标准行业解决方案，并且在专业直播领域获得重要意识和采纳。</span><span class="sxs-lookup"><span data-stu-id="302eb-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="302eb-107">Skype 以前在2018中向 Skype 添加了 NDI 功能。</span><span class="sxs-lookup"><span data-stu-id="302eb-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="302eb-108">Microsoft 团队利用此功能改善会议体验。</span><span class="sxs-lookup"><span data-stu-id="302eb-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="302eb-109">NDI 限制为本地网络，只能被视为生产工作流的一部分，而不是广播解决方案。</span><span class="sxs-lookup"><span data-stu-id="302eb-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="302eb-110">打开 NDI</span><span class="sxs-lookup"><span data-stu-id="302eb-110">Turn on NDI</span></span>

<span data-ttu-id="302eb-111">NDI 需要为用户打开两个步骤。</span><span class="sxs-lookup"><span data-stu-id="302eb-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="302eb-112">租户管理员必须在 CsTeamsMeetingPolicy 中启用 "AllowNDIStreaming" 属性。</span><span class="sxs-lookup"><span data-stu-id="302eb-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="302eb-113">填充此更改后，最终用户必须从 "**设置**" 权限为其特定客户端打开 NDI  >  **Permissions**。</span><span class="sxs-lookup"><span data-stu-id="302eb-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="302eb-114">当用户加入会议时，他们将看到一条消息，通知他们正在广播会议。</span><span class="sxs-lookup"><span data-stu-id="302eb-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="302eb-115">如果用户不希望包含在广播中，则需要将其从会议中删除。</span><span class="sxs-lookup"><span data-stu-id="302eb-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="302eb-116">下图显示了用户在团队会议中看到的标题消息。</span><span class="sxs-lookup"><span data-stu-id="302eb-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![团队会议中显示的 NDI 横幅的图像。](media/NDI-disclosure.png)

<span data-ttu-id="302eb-118">横幅有一个指向[Microsoft 隐私声明策略](https://aka.ms/teamsprivacy)的链接。</span><span class="sxs-lookup"><span data-stu-id="302eb-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="302eb-119">支持的区域设置和用户类型</span><span class="sxs-lookup"><span data-stu-id="302eb-119">Supported locales and user types</span></span>

<span data-ttu-id="302eb-120">所有区域设置均支持 NDI。</span><span class="sxs-lookup"><span data-stu-id="302eb-120">NDI is supported in all locales.</span></span> <span data-ttu-id="302eb-121">在 NDI 会议中支持以下用户：</span><span class="sxs-lookup"><span data-stu-id="302eb-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="302eb-122">租户内-完全支持，根据 "震铃/tenantId/userId" (提供，由会议策略控制) </span><span class="sxs-lookup"><span data-stu-id="302eb-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="302eb-123">联盟–即使在) <sup>1</sup>上有 NDI，也没有 (</span><span class="sxs-lookup"><span data-stu-id="302eb-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="302eb-124">Freemium- (默认值) </span><span class="sxs-lookup"><span data-stu-id="302eb-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="302eb-125">匿名–没有 (默认值) </span><span class="sxs-lookup"><span data-stu-id="302eb-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="302eb-126">来宾-没有 (默认值) </span><span class="sxs-lookup"><span data-stu-id="302eb-126">Guest – no  (default value)</span></span>

<span data-ttu-id="302eb-127"><sup>1</sup>台设备的 NDI 设置在默认情况下处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="302eb-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="302eb-128">如果会议参与者使用 NDI 关闭的设备，则他们需要启用 NDI。</span><span class="sxs-lookup"><span data-stu-id="302eb-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
