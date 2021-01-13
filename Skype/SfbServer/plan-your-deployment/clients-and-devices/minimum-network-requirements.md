---
title: Skype 会议应用最低网络要求
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要：不使用 Microsoft 365 或 Office 365 且需要访问由组织托管的会议的组织的信息。
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816302"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="65b07-103">Skype 会议应用最低网络要求</span><span class="sxs-lookup"><span data-stu-id="65b07-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="65b07-104">**摘要：**  有关不使用 Microsoft 365 或 Office 365 且需要访问由组织托管的会议的组织的信息。</span><span class="sxs-lookup"><span data-stu-id="65b07-104">**Summary:**  Information for organizations who don't use Microsoft 365 or Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="65b07-105">本文不面向这些应用的用户。</span><span class="sxs-lookup"><span data-stu-id="65b07-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="65b07-106">若要允许用户使用 Skype 会议应用参加 Skype for Business Online 中托管的会议，不使用 Microsoft 365 或 Office 365 的组织的网络管理员应允许或以其他方式提供下面提到的 FQDN、IP 和端口。</span><span class="sxs-lookup"><span data-stu-id="65b07-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Microsoft 365 or Office 365 should allow or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="65b07-107">Skype 会议应用连接要求</span><span class="sxs-lookup"><span data-stu-id="65b07-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="65b07-108">此处列出的信息是 [Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)和 IP 地址范围的子集，可提供更深入的信息，并且将始终保持最新。</span><span class="sxs-lookup"><span data-stu-id="65b07-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="65b07-109">应用</span><span class="sxs-lookup"><span data-stu-id="65b07-109">App</span></span> |<span data-ttu-id="65b07-110">目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="65b07-110">Destination FQDNs</span></span>  |<span data-ttu-id="65b07-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="65b07-111">IP Addresses</span></span>  |<span data-ttu-id="65b07-112">端口</span><span class="sxs-lookup"><span data-stu-id="65b07-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="65b07-113">**Skype 会议应用**</span><span class="sxs-lookup"><span data-stu-id="65b07-113">**Skype Meetings App**</span></span> | <span data-ttu-id="65b07-114">\*.lync.com</span><span class="sxs-lookup"><span data-stu-id="65b07-114">\*.lync.com</span></span> <br/><span data-ttu-id="65b07-115">\*.infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="65b07-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="65b07-116">\*.pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65b07-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="65b07-117">\*.sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="65b07-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="65b07-118">\*.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="65b07-118">\*.msecnd.net</span></span><br/><span data-ttu-id="65b07-119">\*broadcast <span></span> .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="65b07-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="65b07-120">\*powerpoint <span></span> .officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="65b07-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="65b07-121">\*.office.live.com</span><span class="sxs-lookup"><span data-stu-id="65b07-121">\*.office.live.com</span></span><br/><span data-ttu-id="65b07-122">\*.cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="65b07-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="65b07-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65b07-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="65b07-124">这些 IP 地址会经常更新。</span><span class="sxs-lookup"><span data-stu-id="65b07-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="65b07-125">请参阅 [Skype for Business IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 范围以及 Office IP [范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="65b07-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="65b07-126">TCP：80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="65b07-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="65b07-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="65b07-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="65b07-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="65b07-128">**Teams**</span></span>    | <span data-ttu-id="65b07-129">\*<span></span>.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65b07-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="65b07-130">\*<span></span>.skype.com</span><span class="sxs-lookup"><span data-stu-id="65b07-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="65b07-131">这些 IP 地址会经常更新。</span><span class="sxs-lookup"><span data-stu-id="65b07-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="65b07-132">请参阅 [Skype for Business IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 范围以及 Office IP [范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="65b07-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="65b07-133">TCP：443</span><span class="sxs-lookup"><span data-stu-id="65b07-133">TCP:  443</span></span> <br/> <span data-ttu-id="65b07-134">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="65b07-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="65b07-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65b07-135">See also</span></span>
<span data-ttu-id="65b07-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="65b07-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="65b07-137">规划 Web 应用和 (会议应用程序的会议) </span><span class="sxs-lookup"><span data-stu-id="65b07-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="65b07-138">在 Skype for Business Server 中部署 Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="65b07-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="65b07-139">Skype 会议应用支持的平台</span><span class="sxs-lookup"><span data-stu-id="65b07-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
