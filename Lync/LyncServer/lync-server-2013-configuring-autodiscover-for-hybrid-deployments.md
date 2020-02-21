---
title: Lync Server 2013：配置混合部署的自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>在 Lync Server 2013 中配置自动发现以实现混合部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-12_

混合部署是使用 Microsoft Lync Online 云服务和本地部署的配置。 在此类型的配置中，自动发现服务必须能够找到用户实际所处的位置。 也就是说，自动发现功能会帮助查找用户帐户以及承载用户帐户的服务器所在的位置，而不管它是在本地部署中还是在 Lync Online 部署中。

例如，如果用户的帐户托管在 Lync Online 中的服务器上，则在称为 "*发现*" 的过程中，查找用户的尝试将按如下方式发生：

  - 用户启动对内部部署的连接尝试 **contoso.com**。

  - 会将尝试发送到 lyncdiscover.contoso.com，DNS 名称与自动发现服务相关联。

  - 自动发现是指在 contoso.com 本地部署中假定的注册器池，并提供有关 Lync Online 中托管的用户实际主服务器的信息。 然后自动发现会向用户对 **lync.com** 联机自动发现服务发送一个引用。

  - 用户对 lync.com 联机自动发现服务启动一个连接尝试，并能够找到用户的帐户和用户的主服务器。

若要使客户端能够发现用户主服务器所在的部署，必须使用新的统一资源定位器（URL）配置自动发现服务。 执行下列操作可配置自动发现服务。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>为混合部署配置自动发现

1.  在本主题中，[针对 Lync Server 2013 的自动发现服务要求](lync-server-2013-autodiscover-service-requirements.md)，您可以使用 CsHostingProvider 检索 ProxyFQDN 属性的值。

2.  在 Lync Server 命令行管理程序中，键入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    其中\[标识\]替换为共享 SIP 地址空间的域名。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

