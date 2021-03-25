---
title: 更新 Microsoft Edge 证书
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附录包括更新边缘证书的详细步骤，作为 Teams 和 Skype for Business 云整合的一部分。
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120341"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="59f6b-103">更新 Microsoft Edge 证书</span><span class="sxs-lookup"><span data-stu-id="59f6b-103">Update the edge certificate</span></span>

<span data-ttu-id="59f6b-104">更新边缘证书是确保具有 SipDomain1 的一个内部部署环境可以使用 SipDomain2 加入云环境并确保在跨两个 SIP 域的共享地址空间环境中正确路由的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="59f6b-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="59f6b-105">有关可能执行此步骤的上下文，请参阅 Teams 和 [Skype for Business](cloud-consolidation.md) 云合并中的步骤 14。</span><span class="sxs-lookup"><span data-stu-id="59f6b-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="59f6b-106">在我们的示例中，SipDomain1 是 AcquiredCompany。 <span>com 和 SipDomain2 为 OriginalCompany。 <span>com.</span><span class="sxs-lookup"><span data-stu-id="59f6b-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="59f6b-107">必须更新 (环境中) 边缘服务器上证书的主题备用名称 SAN) ，以包括纯联机租户环境中存在的所有 SIP 域 (不包括任何 onmicrosoft。 <span>com domains) ，格式为"sip. \<domain> "。</span><span class="sxs-lookup"><span data-stu-id="59f6b-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="59f6b-108">在我们的示例中，这是 sip。OriginalCompany。 <span>com.</span><span class="sxs-lookup"><span data-stu-id="59f6b-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="59f6b-109">在将任何用户迁移到云之前，此步骤至关重要。</span><span class="sxs-lookup"><span data-stu-id="59f6b-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="59f6b-110">**步骤：**</span><span class="sxs-lookup"><span data-stu-id="59f6b-110">**Steps:**</span></span>

1.  <span data-ttu-id="59f6b-111">获取边缘的新外部边缘证书，该边缘具有云环境中所有 SIP 域的所有现有条目以及 SAN 中的其他条目 (但 \*.onmicrosoft.com 域) 格式为 <DomainName> "sip."。</span><span class="sxs-lookup"><span data-stu-id="59f6b-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="59f6b-112">在每个边缘服务器上本地安装证书，并将其分配给每个边缘服务上的 Skype 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="59f6b-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="59f6b-113">有关详细步骤，请参阅 Deploy Edge Service in [Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)中的"外部边缘接口证书"部分。</span><span class="sxs-lookup"><span data-stu-id="59f6b-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="59f6b-114">在每个边缘服务器上重新启动边缘服务。</span><span class="sxs-lookup"><span data-stu-id="59f6b-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="59f6b-115">可以使用以下 PowerShell 命令为单个框进行此操作：</span><span class="sxs-lookup"><span data-stu-id="59f6b-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="59f6b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59f6b-116">See also</span></span>

[<span data-ttu-id="59f6b-117">Teams 和 Skype for Business 云合并</span><span class="sxs-lookup"><span data-stu-id="59f6b-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)