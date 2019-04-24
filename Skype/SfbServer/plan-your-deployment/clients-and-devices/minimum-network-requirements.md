---
title: Skype 会议应用的最低网络要求
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要： 为不使用 Office 365，并需要访问托管执行操作的组织的会议的组织的的信息。
ms.openlocfilehash: 00862a4acecb8a5e6555f44d9416a2efa5834e61
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214510"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="2e7d3-103">Skype 会议应用的最低网络要求</span><span class="sxs-lookup"><span data-stu-id="2e7d3-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="2e7d3-104">**摘要：** 不使用 Office 365，并需要访问托管执行操作的组织的会议的组织的信息。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="2e7d3-105">这篇文章不适合于这些应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="2e7d3-106">要允许用户使用 Skype 会议应用程序参加业务 online Skype 中托管的会议，请不要使用 Office 365 的网络管理员的组织应白名单或其他方式使可用 Ip，Fqdn 和端口下述。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="2e7d3-107">Skype 会议应用的连接要求</span><span class="sxs-lookup"><span data-stu-id="2e7d3-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="2e7d3-108">此处列出的信息是[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)，它将提供更深入地且始终将最新的子集。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="2e7d3-109">应用程序</span><span class="sxs-lookup"><span data-stu-id="2e7d3-109">App</span></span> |<span data-ttu-id="2e7d3-110">目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="2e7d3-110">Destination FQDNs</span></span>  |<span data-ttu-id="2e7d3-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="2e7d3-111">IP Addresses</span></span>  |<span data-ttu-id="2e7d3-112">端口</span><span class="sxs-lookup"><span data-stu-id="2e7d3-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="2e7d3-113">**Skype 会议应用**</span><span class="sxs-lookup"><span data-stu-id="2e7d3-113">**Skype Meetings App**</span></span> | <span data-ttu-id="2e7d3-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-114">\*.lync.com</span></span> <br/><span data-ttu-id="2e7d3-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="2e7d3-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="2e7d3-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="2e7d3-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="2e7d3-118">\*.msecnd.net</span></span><br/><span data-ttu-id="2e7d3-119">\*广播<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="2e7d3-120">\*powerpoint<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="2e7d3-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-121">\*.office.live.com</span></span><br/><span data-ttu-id="2e7d3-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="2e7d3-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="2e7d3-123">\*.s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="2e7d3-124">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="2e7d3-125">请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)</span><span class="sxs-lookup"><span data-stu-id="2e7d3-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="2e7d3-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="2e7d3-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="2e7d3-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="2e7d3-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="2e7d3-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="2e7d3-128">**Teams**</span></span>    | <span data-ttu-id="2e7d3-129">\*<span></span>。 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="2e7d3-130">\*<span></span>。 skype.com</span><span class="sxs-lookup"><span data-stu-id="2e7d3-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="2e7d3-131">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="2e7d3-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="2e7d3-132">请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)</span><span class="sxs-lookup"><span data-stu-id="2e7d3-132">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="2e7d3-133">TCP：443</span><span class="sxs-lookup"><span data-stu-id="2e7d3-133">TCP:  443</span></span> <br/> <span data-ttu-id="2e7d3-134">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="2e7d3-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="2e7d3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e7d3-135">See also</span></span>
<span data-ttu-id="2e7d3-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="2e7d3-136"></span></span>

[<span data-ttu-id="2e7d3-137">规划会议客户端 （Web 应用程序和会议应用程序）</span><span class="sxs-lookup"><span data-stu-id="2e7d3-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="2e7d3-138">为业务服务器部署中 Skype Web 可下载的客户端</span><span class="sxs-lookup"><span data-stu-id="2e7d3-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="2e7d3-139">Skype 会议应用程序所支持的平台</span><span class="sxs-lookup"><span data-stu-id="2e7d3-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)