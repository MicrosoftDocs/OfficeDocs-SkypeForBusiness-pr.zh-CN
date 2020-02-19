---
title: Lync Server 2013：为远程呼叫控制配置静态路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46fe499cdf622315ae0d0d789f0a3ed4283d78c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中为远程呼叫控制配置静态路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

远程呼叫控制要求将每个 Lync Server 池配置为将来自该池的路径配置为连接到专用交换机（PBX）的 SIP/CSTA 网关。 该路径要求每个池中的每个网关都具有一个静态路由，池会将与对 PBX 的呼叫相关联的 SIP 呼叫控制消息代理到该路由。 如果为远程呼叫控制配置全局静态路由，则每个未在池级别配置静态路由的池都会使用该全局静态路由。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>为远程呼叫控制配置静态路由

1.  登录到安装了 Lync Server 命令行管理程序的计算机，或将其作为 RTCUniversalServerAdmins 组的成员或基于角色的访问控制（RBAC）角色（您已为其分配了**CsStaticRoute** cmdlet）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  要创建静态路由，并将其置于变量 $TLSRoute 或 $TCPRoute 中，请执行以下操作之一：
    
    <div class="">
    

    > [!TIP]  
    > 要匹配某个域的子域，可在 MatchUri 参数中指定通配符值。例如，<STRONG>*.contoso.net</STRONG>。该值与以后缀 <STRONG>contoso.net</STRONG> 结尾的任何域匹配。

    
    </div>
    
      - 对于传输层安全性 (TLS) 连接，请在命令提示符处键入以下内容：
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        如果 UseDefaultCertificate 设置为 False，则必须指定 TLSCertIssuer 和 TLSCertSerialNumber 参数。 这些参数分别指示发布静态路由中使用的证书的证书颁发机构 (CA) 名称和 TLS 证书的序列号。 有关这些参数的详细信息，请在命令提示符处键入以下内容，以查看 Lync Server 命令行管理程序帮助：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 对于传输控制协议 (TCP) 连接，请在命令提示符处键入以下内容：
        
        <div class="">
        

        > [!NOTE]  
        > 如果指定完全限定域名 (FQDN)，则必须首先配置域名系统 (DNS) A 记录。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        以下是静态路由可选参数的默认值：
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        强烈建议不要更改这些默认值。 但是，如果您必须更改这些参数中的任何参数，请在命令提示符处键入以下内容，以查看 Lync Server Management Shell 帮助：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  若要在中央管理存储中保存新创建的静态路由，请根据需要运行以下任一命令：
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

