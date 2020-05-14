---
title: Skype 会议应用最低网络要求
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
description: 摘要：有关不使用 Microsoft 365 或 Office 365 的组织的信息，并且需要访问由组织托管的会议。
ms.openlocfilehash: 656f8fa52f4a1080cca0b8464becf77c8c2a0ef0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219722"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会议应用最低网络要求
 
**摘要：** 有关未使用 Microsoft 365 或 Office 365 并需要访问由组织托管的会议的组织的信息。 本文不适合这些应用程序的用户。
  
若要允许用户使用 Skype 会议应用来参加托管在 Skype for Business Online 中的会议，不使用 Microsoft 365 或 Office 365 的组织的网络管理员应使用白名单或以其他方式提供以下所述的 Fqdn、Ip 和端口。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会议应用程序连接的要求

此处列出的信息是[Office 365 url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，提供更深入的，并且始终是最新的。
                    
 
|应用 |目标 Fqdn  |IP 地址  |端口  |
|---|---------|---------|---------|
|**Skype 会议应用** | \*。 lync.com <br/>\*。 infra.lync.com<br/>\*。 pipe.aria.microsoft.com<br/>\*。 sfbassets.com<br/>\*。 msecnd.net<br/>\*<span></span>officeapps.live.com <br/>\*<span></span>officeapps.live.com <br/>\*。 office.live.com<br/>\*。 cdn.office.net<br/>*. s-microsoft.com<br/>        |   这些 IP 地址经常更新。  请参阅[Skype For BUSINESS ip 范围](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP： 80 &amp; 443<br/>UDP：3478-3481<br/>
|**Teams**    | \*<span></span>。 microsoft.com <br/>\*<span></span>。 skype.com | 这些 IP 地址经常更新。  请参阅[Skype For BUSINESS ip 范围](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP：443 <br/> UDP：3478-3481

## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[规划会议客户端（Web 应用程序和会议应用程序）](meetings-clients.md)

[在 Skype for Business Server 中部署 Web 可下载客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会议应用程序支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
