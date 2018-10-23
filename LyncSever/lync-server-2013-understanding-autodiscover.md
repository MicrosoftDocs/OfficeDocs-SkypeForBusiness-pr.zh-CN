---
title: 了解自动发现
TOCTitle: 了解自动发现
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945654(v=OCS.15)
ms:contentKeyID: 52061141
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 了解自动发现

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 自动发现服务是最初在 Microsoft Lync Server 2010 中作为 2011 年 11 月版的 Lync Server 2010 累积更新的一部分引入的一项功能。除了修复之外，此累积更新还提供了对 Lync Mobile 和 Lync 2013 客户端的支持。

在 Lync Server 2013 中，自动发现服务是外部和内部移动客户端操作必不可少的一部分，且自动发现还会扩展到新的客户端，例如最近为 Windows 8 引入的 Lync Windows 应用商店应用。Lync 2013 桌面客户端也会使用自动发现。自动发现在 Lync Server 中由所需的域名系统 (DNS) 记录 **lyncdiscover.\<域\>** 和 **lyncdiscoverinternal.\<域\>** 识别。此外，Lync 2010 和 Lync 2013 桌面客户端的较新版本更偏爱使用自动发现而不是域名系统 (DNS) SRV 记录，仅当 lyncdiscover.\<域\> 或 lyncdiscoverinternal.\<域\> 不响应或不解析时才使用 DNS SRV 记录。Windows 8 和 Lync Mobile 的 Lync Windows 应用商店应用仅仅使用自动发现且不会引用传统的 DNS SRV 记录。

在 Lync Server 2013 中，自动发现得到扩展可向客户端传达哪些元素、功能和通信方法可供客户端使用。该信息通过发送自客户端的一个请求进行传达，且 Lync Server Web 服务以一个明确定义的响应（指定哪些项可供客户端使用以及如何以自动发现响应文档的格式联系这些功能）进行响应。

理解自动发现响应文档（包括 Web 服务如何通过此文档将功能传达到客户端）的最佳方法是从 Lync Web 服务自动发现响应文档中仔细分析和定义典型响应中的每一行。

> [!NOTE]  
> 在随后的详细信息中，用户已经通过响应身份验证请求向主服务器进行了身份验证。


> [!NOTE]  
> Lync 自动发现 Web 服务是在 <strong>Microsoft Developer Network</strong> (MSDN) 库的<strong>开放性规范</strong>一节的 <strong>Microsoft Office 协议</strong>中定义的。有关详细信息，请参阅完整的规范文档“Lync 自动发现 Web 服务协议”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=273839" class="uri">http://go.microsoft.com/fwlink/?linkid=273839</a>。有关身份验证的详细信息，请参阅“OC 身份验证 Web 服务协议”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=279015" class="uri">http://go.microsoft.com/fwlink/?linkid=279015</a>。


## Lync Server Web 服务自动发现响应

发送自动发现请求时返回的响应与内部或外部客户端的相同。某些位置感知参数可能会变化。如果收到客户端请求，但实际池是已联系的池之外的一个池，则将为该用户设置用户的主池。用户帐户位于其他池上但从同一办公室登录的同事将得到略有不同的响应。该响应指示该用户的正确前端服务器或前端池。

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

## 自动发现响应文档的详细信息

自动发现响应文档可以采用两种格式之一。默认格式为 JavaScript Object Notation (JSON)。另一种格式为可扩展标记语言 (XML) 文档。此示例中使用了 XML。请求和响应是可预测的，因为文档具有一个确定格式的定义的架构。描述所用架构的文档中的行是请求或响应中的第一行：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**AccessLocation=”External”** 的定义指示请求是从外部用户发出的。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

   &nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess 和 SipServerExternalAccess 当前未使用。将保留这些条目以供将来使用。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

   &nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 和 SipClientExternalAccess 描述内部或外部客户端将用于访问定义的 SIP 服务器的完全限定域名和端口。Lync 桌面客户端和 Lync Windows 应用商店应用使用这些条目，基于其位置（内部或外部）来查找控制器或前端服务器。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

   &nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover` 引用包含自动发现服务的服务入口点。标记属性包含服务名称，href 是一个为可在其中找到该服务的客户端而定义的 URL。外部网络中的客户端使用 `External/Autodiscover`。自动发现服务作为部署过程的一部分进行安装。`Internal/Autodiscover` 当前未使用，且将保留以供将来使用。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

   &nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker` 引用包含内部和外部身份验证 Broker 服务的服务入口点，在此示例中，为 sip.svc。标记属性包含服务名称，href 是一个为可在其中找到该服务的客户端而定义的 URL。内部网络中的客户端使用 `Internal/AuthBroker`。外部网络中的客户端使用 `External/AuthBroker`。AuthBroker 服务作为您的内部 Lync Server 2013 部署 Web 服务的部署过程的一部分进行安装。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

   &nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler` 标记引用这些 URL 以便客户端访问基于 Web 的 Lync Server 会议计划。当前，仅使用了 `External/WebScheduler`。WebScheduler 作为您的内部 Lync Server 2013 部署 Web 服务的部署过程的一部分进行安装。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

   &nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` 和 `External/Mcx` 是 2011 年 11 月版的 Lync Server 2010 累积更新中引入的移动服务的位置。这些引用将继续由所有支持的设备上的 Lync 2010 Mobile 使用。Mcx 服务作为您的内部 Lync Server 2013 部署 Web 服务的部署过程的一部分进行安装。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

   &nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

   &nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**、**External/Ucwa** 和 **Ucwa** 为客户端提供了一种访问统一通信 Web 应用程序编程接口（UCWA API，或简写为 UCWA）的方法。`Internal/Ucwa` 和 `External/Ucwa` 虚拟目录是为将来的功能增强保留的访问点，且没有使用。`Ucwa` 虚拟目录用于所有支持的设备上的 Microsoft Lync Mobile（随 Lync Server 2013 引入）。UCWA 服务作为您的内部 Lync Server 2013 部署 Web 服务的部署过程的一部分进行安装。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、**External/XFrame** 和 **XFrame** 提供对基于 UCWA 的服务器应用程序的访问。XFrame 作为您的内部 Lync Server 2013 部署 Web 服务的部署过程的一部分进行安装。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self` 标记引用特定于正在发出请求的客户端（用户响应类型）的信息。发出此请求的客户端是外部的，此自动发现引用针对自动发现服务的用户部分。

## 另请参阅

#### 其他资源

[Lync Server 2013 的外部用户访问组件的系统要求](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[规划自动发现](lync-server-2013-planning-for-autodiscover.md)

