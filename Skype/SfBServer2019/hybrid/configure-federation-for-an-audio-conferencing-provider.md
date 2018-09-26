---
title: 在混合部署中配置为音频会议提供商联盟
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何在 Skype for Business Online 配置为音频会议提供商联盟。
ms.openlocfilehash: 2f89045e7d2ee3e51a6526344d2dcf2f07c0d98d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030754"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="a3fe7-103">在混合部署中配置为音频会议提供商联盟</span><span class="sxs-lookup"><span data-stu-id="a3fe7-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="a3fe7-104">**摘要：** 了解如何在 Skype for Business Online 配置为音频会议提供商联盟。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="a3fe7-105">如果希望在混合部署（包含本地版与联机版）中使用音频会议提供商 (ACP)，您需要在本地部署和 ACP 合作伙伴（作为允许的合作伙伴服务器）之间配置联盟。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="a3fe7-106">您可以通过向本地部署的联盟域列表添加 ACP 合作伙伴域和边缘服务器（可称为访问代理）来配置联盟。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="a3fe7-107">然后，ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="a3fe7-108">联系您的 ACP 提供商以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="a3fe7-109">您的 ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="a3fe7-110">**将 ACP 域和边缘服务器添加为允许的联盟域**</span><span class="sxs-lookup"><span data-stu-id="a3fe7-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="a3fe7-111">若要将 ACP 的域添加为允许的伙伴服务器 （允许联盟域），请按照[将支持配置对允许的外部域](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="a3fe7-112">边缘服务器，将添加 ACP 伙伴的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="a3fe7-113">您可能需要联系 ACP 合作伙伴，获得其边缘服务器的 FQDN，ACP 也可能称之为访问代理。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="a3fe7-114">**提供给 ACP 伙伴的边缘服务器池的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="a3fe7-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="a3fe7-115">ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加到允许的联盟域列表，以便配置联盟，将您的本地域添加为允许的合作伙伴服务器。</span><span class="sxs-lookup"><span data-stu-id="a3fe7-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


