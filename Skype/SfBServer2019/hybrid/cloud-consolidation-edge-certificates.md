---
title: 更新边缘证书
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附录中包括有关云整合个团队和 Skype for Business 的一部分更新边缘证书的详细的步骤。
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247616"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="69a11-103">更新边缘证书</span><span class="sxs-lookup"><span data-stu-id="69a11-103">Update the edge certificate</span></span>

<span data-ttu-id="69a11-104">更新边缘证书是确保具有 SipDomain1 上 prem 环境可以加入与 SipDomain2 云环境和确保正确路由共享的地址空间环境中的两个 SIP 域之间的主要步。</span><span class="sxs-lookup"><span data-stu-id="69a11-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="69a11-105">请参阅步骤 14 中[个团队和 Skype for Business 的云整合](cloud-consolidation.md)上下文可能在其中执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="69a11-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="69a11-106">在我们的示例中，SipDomain1 是 AcquiredCompany。<span>com 和 SipDomain2 是 OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="69a11-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="69a11-107">在内部部署环境中的所有边缘服务器上的证书的使用者备用名称 (SAN) 必须更新以包括纯 online 租户中存在的所有 SIP 域 (不包括任何 onmicrosoft。<span>com 域），在窗体"sip。\<域 >"。</span><span class="sxs-lookup"><span data-stu-id="69a11-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="69a11-108">在本例中，这是 sip。OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="69a11-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="69a11-109">关键迁移到云中的任何用户之前执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="69a11-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="69a11-110">**步骤：**</span><span class="sxs-lookup"><span data-stu-id="69a11-110">**Steps:**</span></span>

1.  <span data-ttu-id="69a11-111">获取新的外部边缘证书具有云环境中的所有 SIP 域 SAN 中的所有现有项以及其他项的边缘 (不包括 \*。 onmicrosoft.com 域) 中的窗体"sip。<DomainName>"。</span><span class="sxs-lookup"><span data-stu-id="69a11-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="69a11-112">在每台边缘服务器上本地安装证书，并将其分配给每个边缘服务上的 Skype 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="69a11-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="69a11-113">有关详细步骤，请参阅[部署中的业务服务器 2015 Skype 的边缘服务](https://technet.microsoft.com/en-us/library/dn951368.aspx)中的"外部边缘接口证书"一节。</span><span class="sxs-lookup"><span data-stu-id="69a11-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="69a11-114">重新启动每台边缘服务器上的边缘服务。</span><span class="sxs-lookup"><span data-stu-id="69a11-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="69a11-115">可以使用以下 PowerShell 命令单个框来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="69a11-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="69a11-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69a11-116">See also</span></span>

[<span data-ttu-id="69a11-117">云整合个团队和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="69a11-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)