---
title: 在混合部署中为音频会议提供商配置联盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '摘要: 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160440"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="221c1-103">在混合部署中为音频会议提供商配置联盟</span><span class="sxs-lookup"><span data-stu-id="221c1-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="221c1-104">**摘要:** 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。</span><span class="sxs-lookup"><span data-stu-id="221c1-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="221c1-105">如果要在混合部署中使用音频会议提供商 (ACP) (本地和联机), 您需要在本地部署和 ACP 合作伙伴之间配置联盟, 作为允许的合作伙伴服务器。</span><span class="sxs-lookup"><span data-stu-id="221c1-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="221c1-106">您可以通过将 ACP 合作伙伴域和边缘服务器 (也称为 "访问代理服务器") 添加到本地部署的 "联盟域" 列表中来配置联盟。</span><span class="sxs-lookup"><span data-stu-id="221c1-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="221c1-107">然后, 您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。</span><span class="sxs-lookup"><span data-stu-id="221c1-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="221c1-108">有关其他详细信息, 请与您的 ACP 提供商联系。</span><span class="sxs-lookup"><span data-stu-id="221c1-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="221c1-109">然后, 您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。</span><span class="sxs-lookup"><span data-stu-id="221c1-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="221c1-110">**将 ACP 域和边缘服务器添加为允许的联盟域**</span><span class="sxs-lookup"><span data-stu-id="221c1-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="221c1-111">若要将 ACP 域添加为允许的合作伙伴服务器 (允许的联盟域), 请按照[Configure Support for An External](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)domain 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="221c1-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="221c1-112">对于边缘服务器, 添加 ACP 合作伙伴的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="221c1-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="221c1-113">您可能需要与您的 ACP 合作伙伴联系, 以获取其边缘服务器的 FQDN, 而您的 ACP 也可能将其称为访问代理。</span><span class="sxs-lookup"><span data-stu-id="221c1-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="221c1-114">**向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="221c1-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="221c1-115">ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加为允许的联盟域, 从而配置联合以将您的本地域作为允许的合作伙伴服务器添加。</span><span class="sxs-lookup"><span data-stu-id="221c1-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


