---
title: Lync Server 2013：为音频会议提供商配置联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a85a8ef64d43561a68dca7c850f79cc6a1632fc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>在 Lync Server 2013 中为音频会议提供商配置联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-07-24_

如果要在混合部署中使用音频会议提供商（ACP）（使用 Lync Online 的 Lync Server），您需要在本地 Lync 部署和 ACP 合作伙伴之间配置联盟，作为允许的合作伙伴服务器。 您可以通过将 ACP 合作伙伴域和边缘服务器（也称为 "访问代理服务器"）添加到本地部署的 "联盟域" 列表中来配置联盟。 然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。 请与您的 ACP 提供商联系，以获取其他 detailsYour ACP 合作伙伴，然后需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。

  - **将 ACP 域和边缘服务器添加为允许的联盟域**
    
    若要将 ACP 域添加为允许的合作伙伴服务器（允许的联盟域），请按照在[Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步骤操作。 对于边缘服务器，添加 ACP 合作伙伴的边缘服务器的 FQDN。 您可能需要与您的 ACP 合作伙伴联系，以获取其边缘服务器的 FQDN，而您的 ACP 也可能将其称为访问代理。

  - **向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**
    
    ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加为允许的联盟域，从而配置联合以将您的本地域作为允许的合作伙伴服务器添加。

</div>

<span> </span>

</div>

</div>

</div>

