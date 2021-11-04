---
title: Skype 会议应用最低网络要求
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要：不使用会议或会议Microsoft 365 Office 365且需要访问由组织主持的会议的组织的信息。
ms.openlocfilehash: 2d27e578e448c44cd13190d4aedf1e15f611d997
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751571"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会议应用最低网络要求
 
**摘要：** 有关不使用会议或会议Microsoft 365 Office 365且需要访问由组织主持的会议的信息。 本文不适合这些应用的用户。
  
若要允许用户使用 Skype 会议应用参加 Skype for Business Online 中托管的会议，不使用 Microsoft 365 或 Office 365 的组织的网络管理员应允许或以其他方式提供下面提到的 FQN、IP 和端口。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>会议Skype连接性的要求

此处列出的信息是一部分Office 365 [URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)和 IP 地址范围，可提供更深入的信息，并且将始终保持最新状态。
                    
 
|应用 |目标 FQDN  |IP 地址  |端口  |
|---|---------|---------|---------|
|**Skype 会议应用** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   这些 IP 地址会经常更新。  请参阅[Skype for Business IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)范围以及Office [IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP：80 &amp; 443<br/>UDP：3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | 这些 IP 地址会经常更新。  请参阅[Skype for Business IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)范围以及Office [IP 范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP：443 <br/> UDP：3478-3481

## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[Plan for Meetings clients (Web App and Meetings App) ](meetings-clients.md)

[在客户端部署 Web 可下载Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype会议应用支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
