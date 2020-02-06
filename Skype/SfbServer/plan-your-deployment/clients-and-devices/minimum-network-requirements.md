---
title: Skype 会议应用的最低网络要求
ms.author: v-lanac
author: lanachin
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
description: 摘要：有关不使用 Office 365 且需要访问由组织托管的会议的组织的信息。
ms.openlocfilehash: e158d93b68df761b59535f4e9239d14194c10443
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816021"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="3bea4-103">Skype 会议应用的最低网络要求</span><span class="sxs-lookup"><span data-stu-id="3bea4-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="3bea4-104">**摘要：** 适用于不使用 Office 365 的组织的信息，并且需要访问由组织托管的会议。</span><span class="sxs-lookup"><span data-stu-id="3bea4-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="3bea4-105">本文不适合这些应用的用户。</span><span class="sxs-lookup"><span data-stu-id="3bea4-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="3bea4-106">若要允许用户使用 Skype 会议应用来参与 Skype for Business Online 中托管的会议，没有使用 Office 365 的组织的网络管理员应使用白名单，或以其他方式使用以下所述的 Fqdn、IPs 和端口。</span><span class="sxs-lookup"><span data-stu-id="3bea4-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="3bea4-107">Skype 会议应用的连接要求</span><span class="sxs-lookup"><span data-stu-id="3bea4-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="3bea4-108">此处列出的信息是[Office 365 url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，它提供更多的深度，并且将始终保持最新。</span><span class="sxs-lookup"><span data-stu-id="3bea4-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="3bea4-109">应用</span><span class="sxs-lookup"><span data-stu-id="3bea4-109">App</span></span> |<span data-ttu-id="3bea4-110">目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="3bea4-110">Destination FQDNs</span></span>  |<span data-ttu-id="3bea4-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="3bea4-111">IP Addresses</span></span>  |<span data-ttu-id="3bea4-112">端口</span><span class="sxs-lookup"><span data-stu-id="3bea4-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="3bea4-113">**Skype 会议应用**</span><span class="sxs-lookup"><span data-stu-id="3bea4-113">**Skype Meetings App**</span></span> | <span data-ttu-id="3bea4-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-114">\*.lync.com</span></span> <br/><span data-ttu-id="3bea4-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="3bea4-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="3bea4-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="3bea4-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="3bea4-118">\*.msecnd.net</span></span><br/><span data-ttu-id="3bea4-119">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="3bea4-120">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="3bea4-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-121">\*.office.live.com</span></span><br/><span data-ttu-id="3bea4-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="3bea4-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="3bea4-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="3bea4-124">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="3bea4-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="3bea4-125">请参阅[Skype For BUSINESS ip 范围](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)和[Office IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="3bea4-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="3bea4-126">TCP： 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="3bea4-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="3bea4-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="3bea4-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="3bea4-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="3bea4-128">**Teams**</span></span>    | <span data-ttu-id="3bea4-129">\*<span></span>。 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="3bea4-130">\*<span></span>。 skype.com</span><span class="sxs-lookup"><span data-stu-id="3bea4-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="3bea4-131">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="3bea4-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="3bea4-132">请参阅[Skype For BUSINESS ip 范围](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)和[Office IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="3bea4-132">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="3bea4-133">TCP：443</span><span class="sxs-lookup"><span data-stu-id="3bea4-133">TCP:  443</span></span> <br/> <span data-ttu-id="3bea4-134">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="3bea4-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="3bea4-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bea4-135">See also</span></span>
<span data-ttu-id="3bea4-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="3bea4-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="3bea4-137">规划会议客户端（Web 应用和会议应用）</span><span class="sxs-lookup"><span data-stu-id="3bea4-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="3bea4-138">在 Skype for Business 服务器中部署 Web 可下载的客户端</span><span class="sxs-lookup"><span data-stu-id="3bea4-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="3bea4-139">Skype 会议应用支持的平台</span><span class="sxs-lookup"><span data-stu-id="3bea4-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
