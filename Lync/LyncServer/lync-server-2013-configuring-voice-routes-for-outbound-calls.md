---
title: Lync Server 2013：配置出站呼叫的语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>在 Lync Server 2013 中配置出站呼叫的语音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

Lync Server 2013 语音路由将目标电话号码与一个或多个公共交换电话网络（PSTN）网关或 SIP 中继以及一个或多个 PSTN 使用记录相关联。

**使用 Lync Server "控制面板" 查看语音路由**

1.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  单击 "**语音路由**"。

3.  单击“路由”****。

4.  双击语音路线以从语音路由列表中查看其他属性，或选择路线，然后单击 "**编辑**"。 然后单击 "**显示详细信息**"。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一个路线的详细信息。

    
    </div>

**使用 Windows PowerShell 查看语音路由**

  - 启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。 可以使用 Windows PowerShell 和**CsVoiceRoute** cmdlet 查看语音路线。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关所有语音路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsVoiceRoute
    
    这将返回与以下类似的信息：
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> 有关详细信息，请参阅规划文档中<A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的语音路由</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)

  - [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理语音路由](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

