---
title: 'Lync Server 2013: 服务器角色和服务 cmdlet 疑难解答'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c4e8a69a87df5454a9e23cb75d2da85a8ae920
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的服务器角色和服务 cmdlet 疑难解答

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-27_

疑难解答 cmdlet 提供不同的方法来验证 Microsoft Lync Server 2013 是否按预期工作。 例如, CsHealthMonitoringConfiguration cmdlet 使你能够为注册机构和控制器池设置测试帐户。 然后, 你可以使用这些测试帐户验证用户是否能够成功完成常见任务, 如登录到系统、交换即时消息或呼叫位于公共交换电话网络 (PSTN) 的电话。

<div>


> [!NOTE]
> 有关 cmdlet 的其他信息, 请参阅 Lync Server&nbsp;Windows PowerShell 博客<A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>。 每个博客的内容及其 URL 如有更改，恕不另行通知。



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a>服务器角色和服务 Cmdlet

以下是与服务器角色和服务疑难解答直接相关的 cmdlet 的列表:

**服务器角色和服务疑难解答**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))

  - <span></span>  
    [新-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))

  - <span></span>  
    [新-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

