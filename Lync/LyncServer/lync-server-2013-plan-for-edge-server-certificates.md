---
title: Lync Server 2013：规划边缘服务器证书
description: Lync Server 2013：规划边缘服务器证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578188"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>在 Lync Server 2013 中规划边缘服务器证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-05_

在 Lync Server 2013 中简化了为边缘创建证书。

**边缘服务器的证书流程图**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

使用证书向导创建单个公共证书，确保有一个证书定义的可导出私钥并将其分配到以下边缘服务器外部接口：

<div>


> [!IMPORTANT]  
> Lync Server 不支持通配符证书，除非使用反向代理汇总简单 Url。 您必须为您的部署提供的每个 SIP 域名、Web 会议边缘服务、A/V 边缘服务和 XMPP 域 (SANs) 定义不同的主题替代名称。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 中引入，在当前证书的过期时间之前暂存音频/视频身份验证证书需要进行一些额外的规划。 对于外部边缘接口，而不是一个具有多个用途的证书，您将需要两个证书，一个证书分配给访问边缘服务和 Web 会议边缘服务，另一个证书用于 A/V 边缘服务。 有关更多详细信息，请参阅<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">set-cscertificate 中的使用中的暂存 AV 和 OAuth 证书在 Lync Server 2013</A>中



</div>

<div>


> [!IMPORTANT]  
> 在边缘服务器池的事件中，可以将具有私钥的证书导出到每台边缘服务器，并将证书分配给每个边缘服务器服务。 对内部边缘服务器证书执行相同操作，使用私钥导出证书，并将其分配给每个内部边缘接口。



</div>

  - 确保有一个分配到该证书的可导出私钥

  - 访问边缘服务在证书向导中称为 " **外部 SIP 访问边缘** " () 

  - Web 会议边缘服务在证书向导中称为 " **Web 会议边缘（外部** ）" 的服务 () 

  - A/V 身份验证服务（在证书向导中称为“A/V 边缘外部”****）

使用可导出的私钥创建单个内部证书，并将其复制和分配到每个边缘服务器内部接口：

  - 边缘服务器（在证书向导中称为“边缘内部”****）

<div>


> [!IMPORTANT]  
> 可以对每个边缘服务器服务使用单独和不同的证书。 选择单独的证书的最佳原因是要对 A/V 边缘服务证书使用新的滚动证书功能。 在此功能的情况下，建议将 A/V 边缘服务证书与访问边缘服务和 Web 会议边缘服务相分离。 如果您选择请求、获取并为每个服务分配单独的证书，则必须请求再次为 A/V 边缘服务导出私钥 (，这实际上是 A/V 身份验证服务) 并将同一证书分配给每台边缘服务器上的 A/V 边缘外部接口。



</div>

<div>

## <a name="see-also"></a>另请参阅


[使用-Set-cscertificate 中的 Lync Server 2013 暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Lync Server 2013 中影响边缘服务器规划的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

