---
title: Lync Server 2013： Lync Windows 应用商店应用要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48804305d58be57e824b1ac93f22c2a998d070ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013 的 lync Windows 应用商店应用程序要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-03_

具有 Lync Server 的本地部署的组织必须满足以下要求才能支持 Lync Windows 应用商店应用。

<div>


> [!NOTE]  
> 对于 lync server 2010，请运行 lync server 2010 的累积更新：2月2012（可在<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2670352</A>）或更高版本在所有服务器上运行。 若要使用户能够加入会议，请在服务器上运行 Lync Server 2010：10月2012（可在<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2737915</A>）的累积更新。



</div>

  - 在服务器上启用自动发现、Lync Web 应用和 Web 票证服务。

  - 在前端服务器或前端池上启用证书身份验证。 （通常将前端服务器或前端池上的用户注册过程称为 "注册器"。）有关详细信息，请参阅[在 Lync Server 2013 中创建注册器配置设置](lync-server-2013-create-registrar-configuration-settings.md)。

  - 为自动发现服务发布 DNS 别名（CNAME）资源记录。

  - 不再要求确保颁发给 Lync server 的证书的证书吊销列表（CRL）分发点（CDP）指向 HTTP 资源，而不是 LDAP 资源。 但是，请确保客户端计算机安装了最新的 Windows 更新。

  - 配置企业中的 HTTP 代理以允许与 Lync server 相关的 HTTP 流量。如有必要，请添加自动发现、Lync Web App 和 Web 票证服务的例外。

  - 在客户端上，安装 Windows 8.1 和最新版本的 Lync Windows 应用商店应用程序，修复通常在使用多个域时出现的登录问题（例如，当 SIP URI 为**userA@domainZ.com** ，但边缘服务器为**sip.domainX.com**）。

如果你的组织订阅 Lync Online 或 Office 365，并且你使用的是你自己的域名，则必须执行一些额外的步骤来设置你的网络以自动发现 Lync 服务器。 在移动设备上，Lync Windows 应用商店应用和 Lync 的网络配置要求相同。 请参阅 Office 365 wiki 文章 "设置 Lync mobile 设备" 中的 "设置网络" 说明，网址[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)为。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署 Lync Windows 应用商店应用](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

