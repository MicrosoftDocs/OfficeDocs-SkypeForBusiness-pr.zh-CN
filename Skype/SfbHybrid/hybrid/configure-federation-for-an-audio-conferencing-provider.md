---
title: 在混合部署中为音频会议提供商配置联盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
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
description: 摘要：了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118971"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="240c5-103">在混合部署中为音频会议提供商配置联盟</span><span class="sxs-lookup"><span data-stu-id="240c5-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="240c5-104">**摘要：** 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。</span><span class="sxs-lookup"><span data-stu-id="240c5-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="240c5-105">如果要在具有联机) 的混合部署 (本地使用音频会议提供商 (ACP) ，需要将本地部署与 ACP 合作伙伴之间的联盟配置为允许的合作伙伴服务器。</span><span class="sxs-lookup"><span data-stu-id="240c5-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="240c5-106">您可以通过添加 ACP 合作伙伴域和边缘服务器 (这也称为内部部署的联合域列表中的访问代理) 。</span><span class="sxs-lookup"><span data-stu-id="240c5-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="240c5-107">然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联合域列表中。</span><span class="sxs-lookup"><span data-stu-id="240c5-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="240c5-108">有关其他详细信息，请与 ACP 提供商联系。</span><span class="sxs-lookup"><span data-stu-id="240c5-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="240c5-109">然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联合域列表中。</span><span class="sxs-lookup"><span data-stu-id="240c5-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="240c5-110">**将 ACP 域和边缘服务器添加为允许的联合域**</span><span class="sxs-lookup"><span data-stu-id="240c5-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="240c5-111">若要将 ACP 域添加为允许的合作伙伴服务器 (联盟域) ，请按照配置对允许的外部域的支持 [中的步骤操作](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)。</span><span class="sxs-lookup"><span data-stu-id="240c5-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="240c5-112">对于边缘服务器，添加 ACP 合作伙伴的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="240c5-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="240c5-113">您可能需要与 ACP 合作伙伴联系，以获取其边缘服务器的 FQDN，ACP 也可能将 FQDN 称为其访问代理。</span><span class="sxs-lookup"><span data-stu-id="240c5-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="240c5-114">**向 ACP 合作伙伴提供边缘服务器池的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="240c5-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="240c5-115">ACP 合作伙伴需要配置联盟，通过将边缘服务器池的 FQDN 添加为允许的联合域，将本地域添加为允许的合作伙伴服务器。</span><span class="sxs-lookup"><span data-stu-id="240c5-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>