---
title: Lync Server 2013：外部用户访问的证书要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0561c2d6b36090a9499abf360373cf0468cdbda8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问的证书要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-03-29_

Microsoft Lync Server 2013 通信软件支持对访问和 web 会议边缘外部接口以及 A/V 身份验证服务使用一个公共证书。 边缘内部接口通常使用内部证书颁发机构 (CA) 颁发的专用证书，但同时也可以使用公共证书，前提是该证书是由受信任的公共 CA 颁发的。 部署中的反向代理使用公共证书，并会使用 HTTP 对反向代理与客户端以及反向代理与内部服务器之间的通信进行加密（即 HTTP 上的传输层安全性）。

以下是用于访问、Web 会议边缘外部接口以及 A/V 身份验证服务的公共证书的要求：

  - 证书必须由经过批准的公共 CA 颁发，且该 CA 支持使用者替代名称。 有关详细信息，请参阅 Microsoft 知识库文章 929395 "Exchange Server 和通信服务器的统一通信证书合作伙伴"，网址[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)为。

  - 如果证书要在边缘池上使用，必须将其创建为可导出的证书，并在边缘池中的每台边缘服务器上使用相同的证书。可导出的私钥要求针对的是 A/V 身份验证服务，该服务必须在池中所有边缘服务器上使用同一私钥。

  - 如果要最大限度地提高音频/视频服务的正常运行时间，请查看实现分离的 A/V 边缘服务证书（即，与其他外部边缘证书目的的单独 A/V 边缘服务证书）的证书要求。 有关详细信息，请参阅 lync server 2013 中的[更改，它会影响边缘服务器规划](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)，以及在[set-cscertificate 中使用-回滚在 LYNC server 2013 中暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。

  - 证书的使用者名称是访问边缘服务外部接口完全限定的域名（FQDN）或硬件负载平衡器 VIP （例如，access.contoso.com）。 ). 使用者名称不能包含通配符，它必须是显式名称。
    
    <div>
    

    > [!NOTE]  
    > 对于 Lync Server 2013，这不再是必需的，但仍建议与 Office 通信服务器兼容。

    
    </div>

  - 使用者替代名称列表包含以下各项的 FQDN：
    
      - 访问边缘服务外部接口或硬件负载平衡器 VIP （例如，sip.contoso.com）。
        
        <div>
        

        > [!NOTE]  
        > 即使证书使用者名称是访问边缘 FQDN，使用者替代名称还必须包含访问边缘 FQDN，因为传输层安全性 (TLS) 将忽略使用者名称，而使用使用者替代名称条目进行验证。

        
        </div>
    
      - Web 会议边缘外部接口或硬件负载平衡器 VIP（例如，webcon.contoso.com）。
    
      - 如果要使用客户端自动配置或联盟，还需要包含公司内部使用的任何 SIP 域 FQDN（例如，sip.contoso.com、sip.fabrikam.com）。
    
      - A/V 边缘服务不使用主题名称或主题备用名称条目。
    
    <div>
    

    > [!NOTE]  
    > 使用者替代名称列表中的 FQDN 顺序无关紧要。

    
    </div>

如果要在站点上部署多台负载平衡边缘服务器，则安装在每台边缘服务器上的 A/V 身份验证服务证书必须由同一 CA 颁发且必须使用同一私钥。请注意，证书的私钥必须是可导出的，不管是在一台边缘服务器上使用还是在多台边缘服务器上使用。如果要从任何计算机（边缘服务器除外）请求证书，则私钥也必须可导出。由于 A/V 身份验证服务不使用使用者名称或使用者替代名称，因此，一旦满足访问边缘和 Web 会议边缘的使用者名称和使用者替代名称要求，且证书的私钥是可导出的，您就能重用访问边缘证书。

用于边缘内部接口的专用（或公共）证书的要求如下所示：

  - 证书可由内部 CA 或经过批准的公共证书 CA 颁发。

  - 证书的使用者名称通常是边缘内部接口 FQDN 或硬件负载平衡器 VIP（例如，lsedge.contoso.com）。但是，可以在边缘内部上使用通配证书。

  - 不需要使用者替代名称列表。

部署服务中的反向代理请求：

  - 对会议的会议内容的外部用户访问权

  - 用于扩展和显示通讯组成员的外部用户访问权

  - 对可从通讯簿服务下载的文件的外部用户访问权

  - 外部用户对 Lync Web App 客户端的访问权限

  - 对“电话拨入式会议设置”网页的外部用户访问权

  - 对位置信息服务的外部用户访问权

  - 对设备更新服务的外部设备访问权并获取更新

反向代理会发布内部服务器 Web 组件 URL。 Web 组件 Url 在控制器、前端服务器或前端池上定义为拓扑生成器中的**外部 Web 服务**。

可以在分配给反向代理的证书的使用者替代名称字段中使用通配符条目。 有关如何为反向代理配置证书申请的详细信息，请参阅[在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

