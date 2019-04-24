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
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会议应用的最低网络要求
 
**摘要：** 不使用 Office 365，并需要访问托管执行操作的组织的会议的组织的信息。 这篇文章不适合于这些应用程序的用户。
  
要允许用户使用 Skype 会议应用程序参加业务 online Skype 中托管的会议，请不要使用 Office 365 的网络管理员的组织应白名单或其他方式使可用 Ip，Fqdn 和端口下述。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 会议应用的连接要求

此处列出的信息是[Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)，它将提供更深入地且始终将最新的子集。
                    
 
|应用程序 |目标 FQDN  |IP 地址  |端口  |
|---|---------|---------|---------|
|**Skype 会议应用** | \*。 lync.com <br/>\*。 infra.lync.com<br/>\*。 pipe.aria.microsoft.com<br/>\*。 sfbassets.com<br/>\*。 msecnd.net<br/>\*广播<span></span>。 officeapps.live.com <br/>\*powerpoint<span></span>。 officeapps.live.com <br/>\*。 office.live.com<br/>\*。 cdn.office.net<br/>*.s-microsoft.com<br/>        |   这些 IP 地址经常更新。  请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)         |TCP: 80 &amp; 443<br/>UDP：3478-3481<br/>
|**Teams**    | \*<span></span>。 microsoft.com <br/>\*<span></span>。 skype.com | 这些 IP 地址经常更新。  请参阅为[Office Online IP 范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)或[为业务 IP 范围的 Skype](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)      |TCP：443 <br/> UDP：3478-3481

## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[规划会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)

[为业务服务器部署中 Skype Web 可下载的客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会议应用程序所支持的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)