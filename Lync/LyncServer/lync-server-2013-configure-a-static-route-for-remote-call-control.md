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
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中为远程呼叫控制配置静态路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-22_

远程呼叫控制要求每个 Lync 服务器池都配置了一个从该池中的路径到连接到专用分支交换（PBX）的 SIP/CSTA 网关。 此路径要求每个池对每个网关都有一个静态路由，池将向该网关发送与 PBX 调用相关联的 SIP 呼叫控制消息。 如果为远程呼叫控制配置全局静态路由，则未使用池级别的静态路由配置的每个池都将使用全局静态路由。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>为远程呼叫控制配置静态路由

1.  登录到安装了 Lync Server Management Shell 的计算机作为 RTCUniversalServerAdmins 组的成员或为其分配了**CsStaticRoute** cmdlet 的基于角色的访问控制（RBAC）角色。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  若要创建静态路由并将其放在 $TLSRoute 或 $TCPRoute 的变量中，请执行下列操作之一：
    
    <div class="">
    

    > [!TIP]  
    > 若要匹配域的子域，可以在 MatchUri 参数中指定一个通配符值。 例如， <STRONG>*. contoso.net</STRONG>。 该值匹配以后缀<STRONG>contoso.net</STRONG>结尾的任何域。

    
    </div>
    
      - 对于传输层安全（TLS）连接，请在命令提示符处键入以下内容：
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        如果 UseDefaultCertificate 设置为 False，则必须指定 TLSCertIssuer 和 TLSCertSerialNumber 参数。 这些参数指示颁发证书的证书颁发机构（CA）的名称，该证书颁发机构（CA）分别用于在静态路由中使用的证书以及该 TLS 证书的序列号。 有关这些参数的详细信息，请参阅 Lync Server Management Shell 帮助，方法是在命令提示符处键入以下命令：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 对于传输控制协议（TCP）连接，请在命令提示符处键入以下内容：
        
        <div class="">
        

        > [!NOTE]  
        > 如果你指定完全限定的域名（FQDN），则必须首先配置域名系统（DNS） A 记录。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        以下是静态路由的可选参数的默认值：
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        我们强烈建议您不要更改这些默认值。 但是，如果必须更改这些参数中的任何一个，请参阅 Lync Server Management Shell 帮助，方法是在命令提示符处键入以下命令：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  若要在中央管理存储中保留新创建的静态路由，请根据需要运行下列操作之一：
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

