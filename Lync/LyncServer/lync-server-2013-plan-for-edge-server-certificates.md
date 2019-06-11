---
title: Lync Server 2013：规划边缘服务器证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737e0845b4b9966accd8c450b8a300b4f1bb128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>在 Lync Server 2013 中规划边缘服务器证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-05_

在 Lync Server 2013 中简化了为 Edge 创建证书。

**边缘服务器的流程图**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

创建单个公共证书, 确保你具有为证书定义的可导出私钥, 并使用证书向导将其分配给以下 Edge 服务器外部接口:

<div>


> [!IMPORTANT]  
> Lync Server 不支持通配符证书, 除非使用反向代理汇总简单的 Url。 你必须为你的部署提供的每个 SIP 域名、Web 会议边缘服务、A/V 边缘服务和 XMPP 域定义不同的主题备用名称 (San)。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 中引入, 在当前证书过期时间之前暂存音频/视频身份验证证书需要额外的计划。 对于外部边缘接口, 而不是一个具有多个用途的证书, 你将需要两个证书, 一个证书分配给 "访问边缘服务" 和 "Web 会议边缘" 服务, 另一个证书用于 A/V 边缘服务。 有关其他详细信息, 请参阅<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">在 CsCertificate 中使用-滚在 Lync Server 2013 中暂存 AV 和 OAuth 证书</A>



</div>

<div>


> [!IMPORTANT]  
> 在边缘服务器池的事件中, 将带有私钥的证书导出到每个边缘服务器, 并将证书分配给每个 Edge 服务器服务。 对内部边缘服务器证书执行相同操作, 导出具有私钥的证书并分配给每个内部边缘接口。



</div>

  - 确保为证书分配了可导出的私钥

  - Access Edge 服务 (在证书向导中称为**SIP 访问边缘**)

  - 网络会议边缘服务 (在证书向导中称为 " **Web 会议边缘**")

  - A/V 身份验证服务 (在证书向导中称为**a/v Edge 外部**)

创建具有可导出私钥的单个内部证书, 将其复制并分配给每个边缘服务器内部接口:

  - 边缘服务器 (在证书向导中称为 "**边缘内部**")

<div>


> [!IMPORTANT]  
> 可以为每个 Edge 服务器服务使用单独和不同的证书。 选择单独的证书的一个好理由是您想要对 A/V 边缘服务证书使用新的滚动证书功能。 在此功能的情况下, 建议将 A/V 边缘服务证书与 "访问边缘" 服务分离, 并建议使用网络会议边缘服务。 如果你选择请求, 为每项服务获取并分配单独的证书, 则必须请求为 A/V 边缘服务导出私钥, 这同样是, 这是一个/v 身份验证服务, 并将相同的证书分配给 A/V每台边缘服务器上的边缘外部接口。



</div>

<div>

## <a name="see-also"></a>另请参阅


[在 CsCertificate 中使用-滚在 Lync Server 2013 中暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Lync Server 2013 中影响边缘服务器规划的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

