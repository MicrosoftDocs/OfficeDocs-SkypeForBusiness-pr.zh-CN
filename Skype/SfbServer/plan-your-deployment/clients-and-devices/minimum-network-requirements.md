---
title: Skype 会议应用的最低网络要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要： 为不使用 Office 365，并需要访问托管执行操作的组织的会议的组织的的信息。
ms.openlocfilehash: e186b08a09f52e8de2d3f28867a4a0a30cdb1732
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19577029"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="cd535-103">Skype 会议应用的最低网络要求</span><span class="sxs-lookup"><span data-stu-id="cd535-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="cd535-104">**摘要：** 不使用 Office 365，并需要访问托管执行操作的组织的会议的组织的信息。</span><span class="sxs-lookup"><span data-stu-id="cd535-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="cd535-105">这篇文章不适合于这些应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="cd535-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="cd535-106">若要允许用户使用 Skype 会议 App 参加会议的 Skype 中承载业务联机状态，不使用<token>nm-office-365-short</token>的网络管理员的组织应白名单或使其获得 Fqdn，提到 Ip 和端口下方。</span><span class="sxs-lookup"><span data-stu-id="cd535-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use <token>nm-office-365-short</token> should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="cd535-107">Skype 会议应用的连接要求</span><span class="sxs-lookup"><span data-stu-id="cd535-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="cd535-108">此处列出的信息是[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)，它将提供更深入地且始终将最新的子集。</span><span class="sxs-lookup"><span data-stu-id="cd535-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="cd535-109">应用程序</span><span class="sxs-lookup"><span data-stu-id="cd535-109">App</span></span> |<span data-ttu-id="cd535-110">目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="cd535-110">Destination FQDNs</span></span>  |<span data-ttu-id="cd535-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="cd535-111">IP Addresses</span></span>  |<span data-ttu-id="cd535-112">端口</span><span class="sxs-lookup"><span data-stu-id="cd535-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="cd535-113">**Skype 会议应用程序**</span><span class="sxs-lookup"><span data-stu-id="cd535-113">**Skype Meetings App**</span></span> | <span data-ttu-id="cd535-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="cd535-114">\*.lync.com</span></span> <br/><span data-ttu-id="cd535-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd535-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="cd535-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cd535-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="cd535-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="cd535-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="cd535-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="cd535-118">\*.msecnd.net</span></span><br/><span data-ttu-id="cd535-119">\*广播<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="cd535-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="cd535-120">\*powerpoint<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="cd535-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="cd535-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="cd535-121">\*.office.live.com</span></span><br/><span data-ttu-id="cd535-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="cd535-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="cd535-123">\*.s microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cd535-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="cd535-124">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="cd535-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="cd535-125">请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)</span><span class="sxs-lookup"><span data-stu-id="cd535-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="cd535-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="cd535-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="cd535-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="cd535-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="cd535-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="cd535-128">**Teams**</span></span>    | <span data-ttu-id="cd535-129">*。 microsoft.com <br/> *。 skype.com</span><span class="sxs-lookup"><span data-stu-id="cd535-129">*.microsoft.com <br/>*.skype.com</span></span> | <span data-ttu-id="cd535-130">这些 IP 地址经常更新。</span><span class="sxs-lookup"><span data-stu-id="cd535-130">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="cd535-131">请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)</span><span class="sxs-lookup"><span data-stu-id="cd535-131">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office Online IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="cd535-132">TCP：443</span><span class="sxs-lookup"><span data-stu-id="cd535-132">TCP:  443</span></span> <br/> <span data-ttu-id="cd535-133">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="cd535-133">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="cd535-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd535-134">See also</span></span>
<span data-ttu-id="cd535-135"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="cd535-135"></span></span>

[<span data-ttu-id="cd535-136">规划会议客户端 （Web 应用程序和会议应用程序）</span><span class="sxs-lookup"><span data-stu-id="cd535-136">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="cd535-137">部署业务服务器 2015 Skype Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="cd535-137">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="cd535-138">Skype 会议应用程序所支持的平台</span><span class="sxs-lookup"><span data-stu-id="cd535-138">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)