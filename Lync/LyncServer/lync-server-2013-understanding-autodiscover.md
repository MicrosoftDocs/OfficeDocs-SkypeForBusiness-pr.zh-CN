---
title: Lync Server 2013：了解自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaa9a938fe893ebca6f4e8abee4a3f41d1527dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>了解 Lync Server 2013 中的自动发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-06-03_

Lync Server 2013 自动发现服务是最初在 Microsoft Lync Server 2010 中引入的一项功能，作为 Lync Server 2010 累积更新的一部分：11月2011。 除修补外，此累积更新提供了对 Lync Mobile 和 Lync 2013 客户端的支持。

在 Lync Server 2013 中，自动发现服务是外部和内部移动客户端的操作不可或缺的一部分，自动发现也扩展到新客户端，如最近引入的适用于 Windows 8 的 Lync Windows 应用商店应用程序。 Lync 2013 桌面客户端也使用自动发现。 在 Lync Server 中通过所需的域名系统（DNS）记录 lyncdiscover. 识别自动发现 **。\<域\> **和**lyncdiscoverinternal.。\<域\>**。 此外，Lync 2010 和 Lync 2013 桌面客户端的较新版本更喜欢通过域名系统（DNS） SRV 记录的自动发现，只有在 lyncdiscover. 时才使用 DNS SRV 记录。\<domain\>或 lyncdiscoverinternal.。\<域\>不响应或无法解决。 适用于 Windows 8 和 Lync Mobile 的 Lync Windows 应用商店应用程序以独占方式使用自动发现，不会引用传统的 DNS SRV 记录。

在 Lync Server 2013 中，自动发现功能已展开，以与客户端通信，以便客户端可以使用哪些元素、功能和通信方法。 该信息通过从客户端发送的请求进行传递，并且 Lync Server web 服务使用明确定义的响应来响应客户端可以使用的信息，以及如何通过自动发现的格式来联系这些功能。响应文档。

了解自动发现响应文档（包括 web 服务如何通过此文档向客户端传达功能）的最佳方式是 dissect，并在来自 Lync web 服务自动发现响应文档的典型响应中定义每行。

<div class="">


> [!NOTE]  
> 在下面的详细信息中，用户已通过响应身份验证请求向主服务器进行身份验证。



</div>

<div class="">


> [!NOTE]  
> Lync 自动发现 Web 服务在 microsoft<STRONG>开发人员网络</STRONG>（MSDN）库的 "<STRONG>打开规范</STRONG>" 部分中的 " <STRONG>microsoft Office 协议</STRONG>" 中定义。 有关详细信息，请参阅： <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>中的完整规范文档 "Lync 自动发现 Web 服务协议"。 有关身份验证的详细信息，请参阅处<A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>的 "OC 身份验证 Web 服务协议"。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web 服务自动发现响应

向内部或外部客户端发送自动发现请求时返回的响应是相同的。 某些可感知位置的参数可能会发生变化。 如果收到客户端请求，但实际池不是已联系的池，则将为该用户设置用户的主池。 如果同事的用户帐户位于不同的池，但从同一个办公室登录，则响应会略有不同。 响应指示该用户的正确的前端服务器或前端池。

自动发现响应文档的示例：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>自动发现响应文档详细信息

自动发现响应文档可采用两种格式之一。 默认格式为 JavaScript 对象表示法（JSON）。 另一种格式是可扩展标记语言（XML）文档。 此示例使用 XML。 请求和响应是可预测的，因为文档具有确定格式的定义架构。 文档中描述所使用的架构的行是请求或响应中的第一行：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**AccessLocation = "External"** 的定义表明请求是从外部用户发出的。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

当前未使用 SipServerInternalAccess 和 SipServerExternalAccess。 保留这些项以供将来使用。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 和 SipClientExternalAccess 描述内部或外部客户端将用于访问定义的 SIP 服务器的完全限定的域名和端口。 Lync 桌面客户端和 Lync Windows 应用商店应用程序使用这些条目，具体取决于其位置（内部或外部），以查找控制器或前端服务器。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

这些`Autodiscover`引用包含自动发现服务的服务入口点。 令牌属性包含服务的名称，href 是为可在其中找到服务的客户端定义的 URL。 外部网络上的客户端使用`External/Autodiscover`。 自动发现服务作为部署过程的一部分进行安装。 `Internal/Autodiscover`当前未使用，并保留以供将来使用。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

这些`AuthBroker`引用包含内部和外部身份验证代理服务的服务入口点（在此示例中为 "sip."）。 令牌属性包含服务的名称，href 是为可在其中找到服务的客户端定义的 URL。 内部网络上使用`Internal/AuthBroker`的客户端。 外部网络上的客户端使用`External/AuthBroker`。 AuthBroker 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler`令牌引用用于客户端访问的 url，以供客户端访问 Lync Server 会议的基于 web 的计划。 目前，仅`External/WebScheduler`使用。 WebScheduler 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`以及`External/Mcx`在 Lync Server 2010 的累积更新中引入的移动服务的位置：11月2011。 在所有受支持的设备上，Lync 2010 Mobile 将继续使用这些引用。 Mcx 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**、 **External/Ucwa**和**Ucwa**为客户端提供了一种访问统一通信 WEB 应用程序编程接口（Ucwa API 或简单 Ucwa）的方法。 `Internal/Ucwa`和`External/Ucwa`虚拟目录是保留用于未来功能增强的访问点，不使用。 `Ucwa`虚拟目录用于 Microsoft Lync Mobile （在所有受支持的设备上引入了 Lync Server 2013）。 UCWA 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、 **External/XFrame**和**XFrame**提供对基于 UCWA 的服务器应用程序的访问权限。 XFrame 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self`令牌是指特定于发出请求的客户端（用户响应类型）的信息。 发出此请求的客户端是外部客户端，而此自动发现参考是对自动发现服务的用户部分。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 的外部用户访问组件的系统要求](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[在 Lync Server 2013 中规划自动发现](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

