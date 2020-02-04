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
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部用户访问的证书要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-03-29_

Microsoft Lync Server 2013 通信软件支持使用单个公共证书访问和网络会议边缘外部接口，以及 A/V 身份验证服务。 Edge 内部接口通常使用由内部证书颁发机构（CA）颁发的专用证书，但也可以使用公共证书（前提是该证书来自受信任的公共 CA）。 部署中的反向代理使用公共证书，并使用 HTTP （即通过 HTTP 传输层安全性）将反向代理和反向代理的通信加密到内部服务器。

下面是用于访问和网络会议边缘外部接口以及 A/V 身份验证服务的公共证书的要求：

  - 证书必须由支持使用者备用名称的已批准公共 CA 颁发。 有关详细信息，请参阅 Microsoft 知识库文章929395： "Exchange Server 的统一通信证书合作伙伴和通信服务器" [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)。

  - 如果要在 Edge 池中使用证书，则该证书必须创建为可导出，并且在 Edge 池中的每个边缘服务器上使用相同的证书。 可导出私钥要求用于 A/V 身份验证服务，该服务必须在池中的所有边缘服务器上使用相同的私钥。

  - 如果你想要最大化音频/视频服务的正常运行时间，请查看用于实现已解除的 A/V 边缘服务证书的证书要求（即来自其他外部边缘证书用途的单独的 A/V 边缘服务证书）。 有关详细信息，请参阅[影响边缘服务器规划的 Lync server 2013 中的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中规划 edge 服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)和在[LYNC server 2013 中暂存 AV 和 OAuth 证书 CsCertificate 中的 "使用-滚](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)"。

  - 证书的使用者名称是访问边缘服务外部接口完全限定的域名（FQDN）或硬件负载平衡器 VIP （例如，access.contoso.com）。 ). 主题名称不能包含通配符，它必须是显式名称。
    
    <div>
    

    > [!NOTE]  
    > 对于 Lync Server 2013，不再需要这种情况，但仍建议使用它来与 Office 通信服务器兼容。

    
    </div>

  - "主题备用名称" 列表包含以下各项的 Fqdn：
    
      - 访问边缘服务外部接口或硬件负载平衡器 VIP （例如，sip.contoso.com）。
        
        <div>
        

        > [!NOTE]  
        > 即使证书使用者名称等于访问边缘 FQDN，"主题" 备用名称也必须包含访问边缘 FQDN，因为传输层安全性（TLS）会忽略使用者名称并使用 "主题备用名称" 条目进行验证.

        
        </div>
    
      - Web 会议边缘外部接口或硬件负载平衡器 VIP （例如，webcon.contoso.com）。
    
      - 如果你使用的是客户端自动配置或联盟，还包括你的公司内使用的任何 SIP 域 Fqdn （例如，sip.contoso.com、sip.fabrikam.com）。
    
      - A/V 边缘服务不使用 "主题名称" 或 "主题备用名称" 条目。
    
    <div>
    

    > [!NOTE]  
    > "主题备用名称" 列表中的 Fqdn 顺序无关紧要。

    
    </div>

如果要在网站上部署多个负载平衡的边缘服务器，则每台边缘服务器上安装的 A/V 身份验证服务证书必须来自同一 CA，并且必须使用相同的私钥。 请注意，证书的私钥必须是可导出的，无论它是在一台边缘服务器还是在多台边缘服务器上使用。 如果从除 Edge 服务器之外的任何计算机请求证书，也必须是可导出的。 由于 A/V 身份验证服务不使用使用者名称或使用者备用名称，因此你可以重复使用访问边缘证书，前提是访问边缘的主题名称和主题备用名称要求已达到访问边缘，并且证书的私钥可导出。

用于 Edge 内部接口的专用（或公用）证书要求如下所示：

  - 证书可以由内部 CA 或已批准的公共证书 CA 颁发。

  - 证书的使用者名称通常是边缘内部接口 FQDN 或硬件负载平衡器 VIP （例如，lsedge.contoso.com）。 但是，你可以在内部边缘使用通配符证书。

  - 不需要 "主题备用名称" 列表。

部署服务中的反向代理请求：

  - 对会议内容的外部用户访问

  - 用于展开和显示通讯组成员的外部用户访问权限

  - 外部用户从通讯簿服务访问可下载的文件

  - 对 Lync Web App 客户端的外部用户访问

  - 外部用户访问电话拨入式会议设置网页

  - 外部用户对位置信息服务的访问权限

  - 外部设备访问设备更新服务并获取更新

反向代理发布内部服务器 Web 组件 Url。 Web 组件 Url 在 "Director"、"前端服务器" 或 "前端池" 上定义为拓扑生成器中的**外部 Web 服务**。

在分配给反向代理的证书的 "主题备用名称" 字段中支持通配符条目。 有关如何配置反向代理的证书申请的详细信息，请参阅[在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

