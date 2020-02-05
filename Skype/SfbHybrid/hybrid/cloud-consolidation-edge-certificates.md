---
title: 更新边缘证书
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
description: 本附录包括更新边缘证书的详细步骤，作为团队和 Skype for business 的云合并的一部分。
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762850"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="095f1-103">更新边缘证书</span><span class="sxs-lookup"><span data-stu-id="095f1-103">Update the edge certificate</span></span>

<span data-ttu-id="095f1-104">更新边缘证书是确保具有 SipDomain1 的本地环境可以加入具有 SipDomain2 的云环境并确保在两个 SIP 域之间的共享地址空间环境中正确路由的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="095f1-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="095f1-105">请参阅[针对团队和 Skype for business 的云合并](cloud-consolidation.md)中可执行此步骤的上下文的步骤14。</span><span class="sxs-lookup"><span data-stu-id="095f1-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="095f1-106">在我们的示例中，SipDomain1 是 AcquiredCompany。<span>Com 和 SipDomain2 是 OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="095f1-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="095f1-107">必须更新本地环境中所有边缘服务器上的证书的使用者备用名称（SAN），以包含纯 online 租户中存在的所有 SIP 域（不包括任何 .onmicrosoft。<span>com 域）的形式，格式为 "sip。\<域> "。</span><span class="sxs-lookup"><span data-stu-id="095f1-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="095f1-108">在我们的示例中，这是 sip。OriginalCompany.<span>com。</span><span class="sxs-lookup"><span data-stu-id="095f1-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="095f1-109">在将任何用户迁移到云中之前，执行此步骤至关重要。</span><span class="sxs-lookup"><span data-stu-id="095f1-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="095f1-110">**引导**</span><span class="sxs-lookup"><span data-stu-id="095f1-110">**Steps:**</span></span>

1.  <span data-ttu-id="095f1-111">获取一个新的外部边缘证书，该证书包含所有现有条目以及 SAN 中所有 SIP 域（不包括 \* onmicrosoft.com 域）中的所有 SIP 域（格式为 "sip"）的所有现有条目和其他条目。<DomainName>"。</span><span class="sxs-lookup"><span data-stu-id="095f1-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="095f1-112">在每台边缘服务器上本地安装证书，并在每个边缘服务上将其分配给 Skype 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="095f1-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="095f1-113">有关详细步骤，请参阅[Skype For Business Server 2015 中的部署边缘服务](https://technet.microsoft.com/library/dn951368.aspx)中的 "外部边缘接口证书" 部分。</span><span class="sxs-lookup"><span data-stu-id="095f1-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="095f1-114">在每台边缘服务器上重新启动边缘服务。</span><span class="sxs-lookup"><span data-stu-id="095f1-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="095f1-115">您可以使用以下 PowerShell 命令为单个框执行此操作：</span><span class="sxs-lookup"><span data-stu-id="095f1-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="095f1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="095f1-116">See also</span></span>

[<span data-ttu-id="095f1-117">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="095f1-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
