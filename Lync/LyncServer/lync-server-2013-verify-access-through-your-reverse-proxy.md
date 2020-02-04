---
title: Lync Server 2013：验证能否通过反向代理进行访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e13f7e23f3404191f7251c1f49bda6f8935a2929
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中验证能否通过反向代理进行访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-29_

使用以下过程验证用户是否可以访问反向代理上的信息。 你可能需要完成防火墙配置和域名系统（DNS）配置，access 才能正常工作。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>验证是否可以通过 Internet 访问网站

  - 打开 web 浏览器，在**地址**栏中键入客户端用于访问通讯簿文件和网站的地址栏中的 url，如下所示：
    
      - 对于 "通讯簿" 服务器，请键入类似于以下内容**https://externalwebfarmFQDN/abs**的 URL：其中 externalwebfarmFQDN 是托管通讯簿服务的外部 web 服务的外部 FQDN。 用户应收到 HTTP 质询，因为通讯簿服务器文件夹上的目录安全性默认配置为 Windows 身份验证。
    
      - 对于会议，请键入类似于以下内容的 URL **https://externalwebfarmFQDN/meet** ：其中 externalwebfarmFQDN 是托管会议内容的 web 场的外部 FQDN。 此 URL 应显示会议的疑难解答页面。 或者，确认会议的简单 URL 是否正常工作。 有关会议联接的简单 URL 的示例可能是https://meet.contoso.com
    
      - 对于通讯组扩展，请键入类似于以下内容的 URL **https://externalwebfarmFQDN/GroupExpansion/service.svc**：。 用户应收到 HTTP 质询，因为通讯组扩展服务上的目录安全性默认配置为 Windows 身份验证。
    
      - 对于 "拨入"，键入类似于以下**https://externalwebfarmFQDN/dialin**内容的简单 URL，其中 externalwebfarmFQDN 是托管电话拨入式会议的拨入页面的 web 场的外部 FQDN。 应将用户定向到拨入页面。 或者，确认你的简单 URL 拨入功能正常工作。 拨入的简单 URL 示例可能是https://dialin.contoso.com
    
      - 若要确认自动发现 URL 是否正常工作， https://lyncdiscover请键入。 externaldomainFQDN. 浏览器应提示您打开文件。 选择 "记事本" 将其打开。 典型的响应类似于：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

