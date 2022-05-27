---
title: Skype 会议应用最低网络要求
ms.author: serdars
author: SerdarSoysal
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
description: 摘要：不使用Microsoft 365或Office 365且需要访问组织托管的会议的组织的信息。
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674524"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 会议应用最低网络要求

**总结：** 不使用Microsoft 365或Office 365且需要访问由组织托管的会议的组织的信息。 本文不适用于Office 365或Microsoft 365最终用户。

在不使用Microsoft 365或Office 365的组织中，Skype会议应用的用户可能需要参加在 Skype for Business Online 中托管的会议。 若要参加这些会议，其网络管理员需要通过防火墙允许以下 FQDN、IP 地址和端口。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype会议应用连接的要求

此处列出的信息是[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的信息的子集。 该主题更深入，并且始终是最新的。

|应用|目标 FQDN|IP 地址|端口|
|---|---------|---------|---------|
|**Skype会议应用**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|这些 IP 地址经常更新。 请参阅[Skype for Business和Microsoft Teams IP 范围](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)以及[Office IP 范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP：80 & 443<br/>UDP：3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|这些 IP 地址经常更新。 请参阅[Skype for Business和Microsoft Teams IP 范围](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)以及[Office IP 范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP：443 <br/> UDP：3478-3481|

## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[规划会议客户端 (Web 应用和会议应用) ](meetings-clients.md)

[在Skype for Business Server中部署 Web 可下载客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype会议应用支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
